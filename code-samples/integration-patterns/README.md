
📦 Full repo: [commerce-platform-fullstack-Dacodes](https://github.com/GregHowe/commerce-platform-fullstack-Dacodes/blob/main/docker-compose.yml)
 
Docker Compose is a prime candidate when discussing integration patterns, especially in the context of multi-service orchestration, test environments, and local development pipelines.

## 🐳 Docker Compose Integration Pattern

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
