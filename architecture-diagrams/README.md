
📦 Full repo: [Migration-Legacy-To-RestApi](https://github.com/GregHowe/Migration-Legacy-To-RestApi)

## 🐳 Full-Stack Architecture Diagram

This diagram illustrates the flow of a client request through a Docker Compose–orchestrated system:

- 🌐 🖥️ **Browser**: Initiates request to frontend
- 🟢 **Frontend (Vue.js)**: Serves UI on port `8080`
- 🟧 . **Backend (.NET Core)**: Handles logic on port `5000`, uses JWT and DB connection string
- 🐘  **Database (PostgreSQL)**: Stores data on port `5432`, with persistent volume `dbdata`

All services are containerized and orchestrated via Docker Compose for local development and integration testing.

> 📦 *Pattern: Tiered Architecture + Secure Config + Environment Parity*

Local Architected Diagram

<img width="640" height="366" alt="image" src="https://github.com/user-attachments/assets/b309b07f-ea9c-430a-aaa3-58c5ae9a0f27" />

<br><br>
Production Architected Diagram
<br>
<br>
🔐 Auth0 / IdentityServer → connected to Backend

🌐 Load Balancer (Nginx / ELB) → in front of Backend

🗂️ S3 (Backups / Logs / Assets) → connected to Backend & DB

🛡️ VPC → wrap all cloud components in a grey box labeled "Secure Cloud Network"

⚙️ CI/CD Pipeline (GitHub Actions) → arrow into Docker Compose box
<br><br>
<img width="1063" height="730" alt="image" src="https://github.com/user-attachments/assets/a2ed449d-26e3-4d66-a200-0ae3dec73d2d" />

<hr>

📦 Full repo: [commerce-platform-fullstack-Dacodes](https://github.com/GregHowe/commerce-platform-fullstack-Dacodes)


## 🐳 Full-Stack Architecture Diagram

This diagram illustrates the architecture of Core 2.0, a multi-application platform designed for franchisees to author and deploy compliant static websites. It showcases the local orchestration via Docker Compose, the event-driven communication through Azure Service Bus, and the interaction between frontend, backend, and static site generation components. Each service is containerized and designed for modularity, scalability, and integration with Azure cloud infrastructure. This layout reflects my architectural thinking around separation of concerns, CI/CD readiness, and developer experience optimization.

Components: 
## 🧩 Component Descriptions

| **🔧 Component**           | **📘 English Description**                                                                 |
|---------------------------|--------------------------------------------------------------------------------------------|
| 🧑‍💻 **Client**              | End-user accessing the platform via browser.                                              |
| 🖥️ **Core.Builder**         | Nuxt-based frontend for authoring compliant static sites.                                 |
| 🛠️ **Core.Backend**         | .NET 6 API exposing REST endpoints and managing user files and permissions.               |
| ⚙️ **Core.DotnetFunctions** | Azure Functions app for ingesting resources and generating previews from file input.      |
| 🏗️ **Core.Generator**       | Nuxt-based static site generator triggered by publish events from Core.Builder.           |
| 📦 **Core.Library**         | Shared components and utilities used by Builder and Generator.                            |
| 🧪 **Core.E2E**             | End-to-end testing suite for validating system integrity between backend services.        |
| ☁️ **Azure Service Bus**    | Event-driven messaging layer coordinating communication between backend services.         |
| 🐳 **Docker Compose**       | Local orchestration tool for spinning up all services in isolated containers.             |


<img width="989" height="688" alt="image" src="https://github.com/user-attachments/assets/de87af0a-b654-4cb0-abe8-7a8f34320894" />

d
