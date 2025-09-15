
📦 Full repo: [Migration-Legacy-To-RestApi](https://github.com/GregHowe/Migration-Legacy-To-RestApi)

## 🐳 Full-Stack Architecture Diagram

This diagram illustrates the flow of a client request through a Docker Compose–orchestrated system:

- 🌐 **Browser**: Initiates request to frontend
- 🟢 **Frontend (Vue.js)**: Serves UI on port `8080`
- 🟣 **Backend (.NET Core)**: Handles logic on port `5000`, uses JWT and DB connection string
- 🔵 **Database (PostgreSQL)**: Stores data on port `5432`, with persistent volume `dbdata`

All services are containerized and orchestrated via Docker Compose for local development and integration testing.

> 📦 *Pattern: Tiered Architecture + Secure Config + Environment Parity*

