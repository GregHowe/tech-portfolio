# tech-portfolio

A curated portfolio showcasing backend architecture, frontend integration, and remote-first engineering practices. Includes code samples, architecture diagrams, case studies, and technical documentation.

## Table of Contents - 

- ✅ Code samples in .NET Core and Vue:

```
// [Authorize] ensures that all endpoints require valid authentication tokens.

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

📦 Full repo: [CommerceCircle](https://github.com/GregHowe/CommerceCircle)

T




- 🧠 Architecture diagrams for distributed systems
- 📚 Case studies from real-world projects
- 📖 Technical documentation for onboarding and deployment

I focus on scalable, secure, and maintainable solutions that align with product goals and user needs.








