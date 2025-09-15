
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


```
// IBrandService defines the contract for brand-related data operations.
// It promotes separation of concerns by abstracting persistence logic from controllers.
// Each method is asynchronous, supporting scalable, non-blocking I/O operations.

    public interface IBrandService
    {
        public Task<IEnumerable<GetBrandListDTO>> GetBrandList();
        public Task<GetBrandDTO> GetBrand(int brandId);
        public Task<GetBrandDTO> GetBrandByHost(string host);
        public Task UpdateBrand(int brandId, UpdateBrandDTO brand);
    }
```


📦 Full repo: [Commerce-Circle](https://github.com/GregHowe/CommerceCircle)

📁 GraphQL Folder Structure (CQRS Applied)
    This image illustrates the separation of Queries and Mutations in our GraphQL API, following the CQRS (Command Query Responsibility Segregation) pattern. Each folder encapsulates its respective read or write operations, promoting modularity, scalability, and clearer team collaboration.

  <img width="431" height="512" alt="image" src="https://github.com/user-attachments/assets/d3834ee7-ae6f-4093-a12a-bc0320c992c7" />

<br><br>


🧱 Testability: “By abstracting the DbContext, we can inject mock implementations for unit testing without hitting the actual database.”

Transaction Control: “The explicit transaction methods (BeginTransactionAsync, CommitTransactionAsync, RollbackTransaction) give us fine-grained control over multi-step operations — crucial for consistency in financial or critical workflows.”

CQRS Alignment: “The separation of read models (GetBrandListDTO, etc.) from write models (UpdateBrandDTO) supports CQRS principles, even within EF Core.”

Scalability & Maintainability: “This interface allows us to swap out the underlying persistence layer (e.g., switch from EF Core to Dapper or Cosmos DB) with minimal impact on the application logic.”


// IApplicationDbContext abstracts the EF Core DbContext to enable dependency injection and mocking.
// This design supports clean architecture principles by decoupling infrastructure from business logic.
// It allows services and domain layers to depend on abstractions, not concrete implementations.

<img width="438" height="263" alt="image" src="https://github.com/user-attachments/assets/64f2ac85-6e6e-40c8-a9c6-a98c034ff2ca" />


T
