# tech-portfolio

A curated portfolio showcasing backend architecture, frontend integration, and remote-first engineering practices. Includes code samples, architecture diagrams, case studies, and technical documentation.

## Table of Contents - 

- ✅ Code samples in .NET Core and Vue:

```
[HttpPost("login")]
public async Task<IActionResult> Login([FromBody] LoginDto dto)
{
    var user = await _userService.Authenticate(dto.Email, dto.Password);
    if (user == null) return Unauthorized();

    var token = tokenService.GenerateToken(user);
    return Ok(new { token });
}
```

📦 Full repo: [CommerceCircle](https://github.com/GregHowe/CommerceCircle)

This sample shows how I implemented a multi-tenant loyalty API using .NET Core. It includes:
- JWT authentication
- Modular service layers
- Clean separation of concerns





- 🧠 Architecture diagrams for distributed systems
- 📚 Case studies from real-world projects
- 📖 Technical documentation for onboarding and deployment

I focus on scalable, secure, and maintainable solutions that align with product goals and user needs.






