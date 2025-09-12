# Backend – Visitor Tracker (Azure Functions)

## 📌 Overview
The Visitor Tracker feature was restructured using **Azure Functions** to make the system more modular, scalable, and cost-efficient.  
It works in two steps:
1. **Query Service** → Identifies if a visitor profile already exists in the system.  
2. **Registration Service** → Registers a new visitor if no profile is found.  

---

## 🛠️ My Contributions
- Designed and restructured the **Visitor Tracker flow into two Azure Functions**:
  - **Query Service** → Validate and fetch existing visitor profiles.  
  - **Registration Service** → Create new records when no profile exists.  
- Optimized the architecture for **clean separation of concerns**.  
- Integrated CI/CD pipelines with Azure DevOps for deployments.  
- Ensured smooth integration with the frontend for analytics reporting.  

---

## 🔧 Tech Used
- **Backend:** Azure Functions (serverless), Node.js  
- **Database:** Azure Cosmos DB  
- **Cloud Services:** Azure DevOps (Pipelines), Azure Monitor (logging & metrics)  

---

## 🏗️ Architecture Flow

```mermaid
graph TD
  U[Visitor Request] --> A[Azure Function - Query Service]
  A -->|User Exists| R[Return Existing Profile]
  A -->|Not Found| B[Azure Function - Registration Service]
  B --> DB[(Azure Cosmos DB)]
  DB --> R2[New Profile Created]
