## 🧩 Case Study 1 – Migration from Legacy ERP to RESTful Architecture  
🔗 [GitHub Repository](https://github.com/GregHowe/Migration-Legacy-To-RestApi)

### 🧠 Problem  
A legacy ERP system was struggling with performance bottlenecks and lacked scalability. Its monolithic structure made it difficult to maintain and extend, limiting the organization’s ability to evolve.

### 🛠 Solution  
Led the migration to a modular, service-oriented architecture using:

- **.NET 8 APIs** for backend logic  
- **Vue 3 SPA** for a modern frontend experience  
- **Docker Compose** for local orchestration  
- **Entity Framework Core** for data access  
- **xUnit** for automated testing

The system was restructured to support clean separation of concerns, environment parity, and scalable deployment pipelines.

### 🚀 Result  
- Significant improvement in performance and maintainability  
- Easier onboarding for developers due to clearer structure and documentation  
- Scalable foundation ready for future integrations and cloud deployment

### 🧰 Tech Stack  

| Layer         | Tools & Frameworks                                  |
|---------------|-----------------------------------------------------|
| **Backend**   | .NET 8 (C#), Entity Framework Core, PostgreSQL      |
| **Frontend**  | Vue 3, Vite, TypeScript                             |
| **DevOps**    | Docker, Docker Compose                              |
| **Testing**   | xUnit                                               |
| **Versioning**| Git & GitHub                                        |
| **Docs**      | Architecture diagrams, coding guidelines, case study|

<hr>
## 🧩 Case Study 2 – CommerceCircle: Loyalty Platform with Clean Architecture  
🔗 [GitHub Repository](https://github.com/GregHowe/CommerceCircle)

### 🧠 Problem  
The client needed a scalable platform to promote customer loyalty through gamification strategies such as loyalty points, tiered levels, and reward triggers. The legacy system lacked modularity and flexibility to support evolving business rules.

### 🛠 Solution  
Designed and implemented a **Clean Architecture–based solution** in .NET 8.0, with clearly separated layers and asynchronous event processing. Key modules include:

- **API Layer**: GraphQL-based entry point coordinating requests across layers  
- **Application Layer**: Encapsulates business logic and use cases (e.g., BillPayment, Referral, Transaction)  
- **Domain Layer**: Defines core entities, value objects, and enums  
- **Infrastructure Layer**: Handles data access, external services (LoyaltiEngine, Wallet), and migrations  
- **EventWorker**: Background service for event-driven tasks like notifications  
- **Test Layer**: Comprehensive unit and integration testing across all layers

The system integrates with Azure Functions, Kubernetes, and external APIs, and supports CI/CD pipelines for scalable deployment.

### 🚀 Result  
- Delivered a modular, testable, and scalable loyalty platform  
- Enabled dynamic rule evaluation and multi-tenant event processing  
- Improved maintainability and reduced coupling between services

### 🧰 Tech Stack  

| Layer         | Tools & Frameworks                                                                 |
|---------------|-------------------------------------------------------------------------------------|
| **Backend**   | .NET 8 (C#), ASP.NET Core, Entity Framework Core, SQL Server                       |
| **Architecture**| Clean Architecture, GraphQL, MediatR, MassTransit, RulesEngine                   |
| **DevOps**    | Docker, Kubernetes, Azure Functions                                                |
| **Testing**   | xUnit, FluentValidation, Microsoft.NET.Test.Sdk, coverlet.collector                |
| **Observability**| Serilog, Swashbuckle                                                             |
| **Versioning**| Git & GitHub                                                                       |

<hr>

## 🧩 Case Study 3 – Core 2.0: Dynamic Site Builder for Franchise Networks  
🔗 [GitHub Repository – Internal Project Reference]

### 🧠 Problem  
Franchisees needed a way to create branded, compliant marketing websites without technical expertise. The system had to support dynamic content, template-based customization, and seamless deployment — all while respecting brand guidelines and user roles.

### 🛠 Solution  
As part of the Builder team, I developed dynamic Vue components that rendered based on user selections at runtime. The frontend was tightly integrated with a .NET 6 backend via REST APIs and Azure Service Bus events. Key features included:

- **Dynamic site generation** from reusable templates  
- **Scoped access control** (brand-level, site-level, global)  
- **Live preview and hot reload** via Docker Compose  
- **CI/CD pipelines** for staging and production environments  
- **Multi-tenant ingestion** via Azure Functions and background workers

The Builder was designed to empower users to author and deploy static sites with minimal friction, while maintaining compliance and scalability.

### 🚀 Result  
- Enabled non-technical users to generate and publish branded sites dynamically  
- Reduced deployment errors through automated pipelines and containerized environments  
- Improved developer experience with hot reload, modular architecture, and clear separation of concerns

### 🧰 Tech Stack  

| Layer         | Tools & Frameworks                                                                 |
|---------------|-------------------------------------------------------------------------------------|
| **Frontend**  | Vue 3, Nuxt, Vite, dynamic component rendering                                      |
| **Backend**   | .NET 6, SQL Server, Azure Active Directory                                          |
| **Architecture**| Event-driven via Azure Service Bus, REST API, multi-app orchestration             |
| **DevOps**    | Docker Compose, Azure CLI, GitHub Actions                                           |
| **Testing**   | E2E smoke tests, CI validation via `.github/test.yml`                              |
| **Versioning**| Git & GitHub                                                                        |

