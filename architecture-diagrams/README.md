
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
🔐 Auth0 / IdentityServer → connected to Backend

🌐 Load Balancer (Nginx / ELB) → in front of Backend

🗂️ S3 (Backups / Logs / Assets) → connected to Backend & DB

🛡️ VPC → wrap all cloud components in a grey box labeled "Secure Cloud Network"

⚙️ CI/CD Pipeline (GitHub Actions) → arrow into Docker Compose box

<img width="1536" height="1024" alt="Copilot_20250915_135202" src="https://github.com/user-attachments/assets/1be9f64b-75ff-42b6-a5df-9f4324bcf0d4" />
