# Problem Statement: Implementing Location Search in leadsAI Collection

## Background
The current `leadsAI` MongoDB collection supports semantic search on **industry embeddings**.  
However, MongoDB’s vector search is limited, preventing effective **location-based similarity search**.  
While MongoDB may support this in the future, we need a **temporary but scalable solution**.

---

## Objective
Enable **hybrid search** across:
- **Industry** (semantic embeddings)
- **Location** (semantic embeddings or geospatial similarity)
- **Designation** (keyword or embeddings)
- **Number of employees** (structured filter)

---

## Requirements
- Support combined **vector search + structured filtering**.
- Easy integration with **Node.js/Express** and **LangChain pipelines**.
- Scalable with clear upgrade paths (free tier → production).

---

## Solution Options

### 1. Pinecone
- Fully managed vector DB.  
- Simple API and strong documentation.  
- Best option for **ease of implementation**.

### 2. Redis Vector Search
- Lightweight, flexible, and production-ready.  
- Good option if Redis is already part of infra.  
- Requires more setup than Pinecone.

### 3. Azure Cognitive Search
- Enterprise-grade solution with **hybrid search** capabilities.  
- Heavier learning curve and cloud lock-in.  

---

## Deliverables
1. **Functional backend implementation** supporting hybrid queries  
   - Industry + Location + Designation + Employees  
2. **Documentation** of integration, architecture, and usage.  
3. *(Optional)* Frontend support for a **location filter**.  
4. *(Optional)* Demo video explaining approach and system flow.  

---

## Considerations
- Feasibility of integrating **Pinecone/Redis with MongoDB** while minimizing latency.  
- **Performance benchmarks**:  
  - Search latency `<200ms` for 95% of queries.  
  - Acceptable recall/accuracy of matches.  
- **Cost analysis**:  
  - Pinecone/Redis free tier usage.  
  - Estimated upgrade costs for production workloads.  

---

## Tech Stack
- **OpenAI** → embeddings generation  
- **LangChain** → query orchestration  
- **Pinecone** → vector database (primary choice)  
- **Node.js + Express.js** → backend integration  

---

## Next Steps
- Prototype using **Pinecone + LangChain + OpenAI**.  
- Run performance tests (latency, accuracy).  
- Document integration steps.  
- Extend frontend with optional location filter.

