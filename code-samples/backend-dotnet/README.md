
📦 Full repo: [Commerce-platform-fullstack-Dacodes](https://github.com/GregHowe/commerce-platform-fullstack-Dacodes)

This controller demonstrates clean separation of concerns, secure access control, and scalable endpoint design. It’s part of a multi-tenant architecture where some brand data must be publicly accessible, while updates require authentication.


```
// [Authorize] ensures that all endpoints require valid authentication tokens.
// Injecting IBrandService and ILogger promotes testability and separation of concerns.
// BrandController remains thin — orchestration only, no business logic.

[Route("api/brands")]
[ApiController]
[Authorize]
public sealed class BrandController : ControllerBase
{
    private readonly IBrandService _brandRepo;
    private readonly ILogger<Controller> _logger;

    public BrandController(
        IBrandService brandRepo,
        ILogger<Controller> logger)
    {
        _brandRepo = brandRepo;
        _logger = logger;
    }
}
```

```
// Use [AllowAnonymous] selectively to expose public endpoints like GetBrandByHost.
// GET api/brands/by/host supports dynamic brand resolution based on request context.
// Useful for multi-tenant setups or domain-based branding.
// Error handling rationale “Centralized exception packaging via PackageExceptionResponse ensures consistent logging and client feedback.”

    [AllowAnonymous]
    [HttpGet("by/host", Name = "BrandByHost")]
    public async Task<IActionResult> GetBrandByHost()
    {
        try
        {
            var header = Request.GetTypedHeaders().Referer;

            if (header != null && !string.IsNullOrWhiteSpace(header.Host))
                return Ok(
                    await 
                    _brandRepo.GetBrandByHost(header.Host.ToLower().ToString()));
            else
                return Ok(null);
        }
        catch (Exception ex)
        {
            return ex.PackageExceptionResponse(_logger);
        }
    }
```

```
// PUT api/brands/{brandId} uses UpdateBrandDTO to enforce input shape and validation.
// Using UpdateBrandDTO enforces input validation and decouples domain logic from transport concerns.”

[HttpPut("{brandId}")]
    public async Task<IActionResult> UpdateBrand(int brandId, [FromBody] UpdateBrandDTO brand)
    {
        try
        {
            await _brandRepo.UpdateBrand(brandId, brand);
            return NoContent();
        }
        catch (Exception ex)
        {
            return ex.PackageExceptionResponse(_logger);
        }
    }
```

T
