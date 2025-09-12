# Backend – Visitor Tracker (Azure Functions)

## 📌 Overview
The Visitor Tracker backend was redesigned using **Azure Functions** with a clear separation of responsibilities for handling **GET** and **POST** requests.  
This makes the system modular, scalable, and easier to maintain.  

It works in two flows:  
1. **GET /visitor** → Query existing visitor profile.  
2. **POST /visitor** → Register or update a visitor profile (including visit count).  

---

## 🛠️ My Contributions
- Designed the **API-driven flow** separating **GET (Query Service)** and **POST (Visitor Handler)**.  
- Implemented **Visitor Handler** Azure Function to register new users and update visit counts.  
- Ensured seamless **Cosmos DB integration** for both query and update flows.  
- Optimized backend for **clean separation of read and write operations**.  
- Integrated CI/CD pipelines with Azure DevOps for deployments.  
- Collaborated with frontend team to ensure smooth analytics reporting.  

---

## 🔧 Tech Used
- **Backend:** Azure Functions (serverless), Node.js  
- **Database:** Azure Cosmos DB  
- **Cloud Services:** Azure DevOps (Pipelines), Azure Monitor (logging & metrics)  

---

## 🏗️ Architecture Flow

```mermaid
graph TD
  U[Visitor Request] --> API[API Endpoint]

  API -->|GET /visitor| Q[Azure Function - Query Service]
  Q --> DB[(Azure Cosmos DB)]
  DB --> QR[Return Existing Profile]

  API -->|POST /visitor| H[Azure Function - Visitor Handler]
  H --> DB
  DB --> UH[Update Visit Count]
  UH --> PR[Return Updated Profile]
