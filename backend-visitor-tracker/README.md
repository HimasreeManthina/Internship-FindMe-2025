# Backend – Visitor Tracker Restructure

## 📌 Overview
This backend feature involved restructuring **Visitor History Metrics** for a cleaner and more maintainable architecture.

---

## 🛠️ My Contributions
- Refactored visitor tracking module into a dedicated **POC folder**  
- Improved **code organization and scalability**  
- Successfully passed CI/CD pipeline builds (#1978469701)  
- Ensured the restructure aligned with the **develop branch**  

---

## 🔧 Tech Used
- Node.js (Express.js)  
- MongoDB  
- CI/CD (Jenkins, GitHub Actions)  

---

## 🏗️ Architecture Flow

```mermaid
graph LR
  U[User Visit] --> F[Frontend]
  F --> VT[Visitor Tracker Service]
  VT --> DB[(MongoDB Database)]
  VT --> CICD[CI/CD Pipeline]
  CICD --> DEPLOY[Deployment Success]
