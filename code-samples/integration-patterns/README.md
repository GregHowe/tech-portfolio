### 🐳 Docker Compose Integration Pattern

This section demonstrates how I orchestrate multi-service environments using **Docker Compose**, ensuring environment parity, modular deployment, and smooth onboarding for developers.  
The integration pattern shown here reflects a real-world setup used in Core 2.0, where services like the backend API, builder frontend, static site generator, and Azure-connected functions are containerized and coordinated locally.

Key highlights include:
- **Service composition** with isolated containers for backend, frontend, and background workers  
- **Live development support** via mounted volumes and hot reload  
- **Cloud integration** through secure injection of Azure credentials  
- **Resilience and modularity** with restartable containers and CI-ready configurations

This orchestration pattern supports both local development and integration testing, and reflects my architectural thinking around scalability, developer experience, and deployment consistency.

<hr>

📦 Full repo: [commerce-platform-fullstack-Dacodes](https://github.com/GregHowe/commerce-platform-fullstack-Dacodes/blob/main/docker-compose.yml)
 
This `docker-compose.yml` orchestrates multiple services for local development and integration testing:

- 🟢 `backend`: .NET Core API with exposed port `8080`
- 🟣 `dotnetfunctions`: Function container for isolated logic
- 🔵 `generator`: Azure-authenticated service for dynamic content generation
- 🟠 `sitebuilder`: Mounted volume for live development and auto-restart on failure

### 🔐 Cloud Integration
Environment variables for Azure credentials are injected securely for authenticated operations.

### 🔄 Resilience & Modularity
Each service is independently buildable and restartable, supporting CI workflows and team onboarding.

> 📦 *Pattern: Service Composition + Environment Parity + Sidecar Integration*


<img width="690" height="970" alt="image" src="https://github.com/user-attachments/assets/e13f9f61-48ef-4a30-9e74-54893abfc764" />

<br>
<hr>
📦 Full repo: [Migration-Legacy-To-RestApi](https://github.com/GregHowe/Migration-Legacy-To-RestApi/blob/main/fullstack-dockerized/docker-compose.yml)

## 🐳 Full-Stack Docker Compose Setup

This configuration orchestrates a PostgreSQL database, a .NET Core backend, and a Vue.js frontend:

### 🔧 Services
- 🟢 `db`: PostgreSQL 15 with persistent volume `dbdata`
- 🟣 `backend`: .NET Core API with injected connection string and JWT key
- 🔵 `frontend`: Vue.js app served on port `8080`

### 🔐 Environment Injection
Secure variables for database access and JWT authentication are passed via `environment`.

### 🔄 Integration Pattern
- **Service Composition**: All tiers defined and networked in one file
- **Environment Parity**: Local setup mirrors production structure
- **Resilience**: Named volumes and dependency chains ensure stability

> 📦 *Pattern: Local Integration + Secure Config + Tiered Architecture*

<img width="812" height="936" alt="image" src="https://github.com/user-attachments/assets/e12edcdb-878d-4bf3-84bc-6a84d00c27c6" />


 

