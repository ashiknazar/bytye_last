### Project Plan: News Multi-Agent Big Data System
___
#### Team Roles
### Project Execution Phases
- 1.Planner / Architect (Person A)
  - Designs system architecture
  - Defines database schemas
  - Designs Kafka topics
  - Designs agent workflows (LangGraph)
  - Breaks work into tasks (Jira)
  - Reviews all implementations
  - Owns integration and system correctness
- 2.Developer / Implementer (Person B)
  - Implements all services and pipelines
  - Writes ingestion scripts
  - Builds Spark jobs
  - Implements backend APIs
  - Implements agents
  - Builds frontend (React)
  - Writes Docker configurations
  - Integrates components
___
___
___
#### Phase 0: Project Initialization
- **Goals**:
  - Set up collaboration and repo structure
- **Actions**:
  - Create GitHub repos (or mono-repo with folders)
  - Define branching strategy:
     - main (production)
     - dev (integration)
     - feature branches
  - Setup Jira board with epics:
     - Ingestion
     - Processing
     - Storage
     - Agents
     - Backend
     - Frontend
     - DevOps
___
#### Phase 1: Infrastructure & Environment Setup

- **Goals**:
  - Prepare base environment for all services
- **Actions**:
  - Setup Docker + Docker Compose
  - Define services:
     - Kafka + Zookeeper
     - PostgreSQL
     - Redis
     - Backend (FastAPI)
  - Create base project structure

- **Owner**:
  - Planner defines architecture
  - Developer implements Docker setup
___
#### Phase 2: Data Ingestion Pipeline

- **Goals**:
  - Collect news data daily

- **Actions**:
  - Build Python ingestion scripts
  - Fetch news from APIs
  - Normalize and clean raw JSON
  - Push data into Kafka topics (e.g., raw_news)

- **Owner**:
  - Developer implements
  - Planner defines schema + data format
___

#### Phase 3: Stream Processing (Big Data Layer)

- **Goals**:
   - Process data at scale
- **Actions**:
   - Setup Spark (PySpark)
   - Consume Kafka streams
   - Perform:
     - Cleaning
     - Deduplication
     - Emotion detection
   - Output processed data

- **Output goes to**:
   - PostgreSQL
   - HDFS
   - Vector DB
___

#### Phase 4: Storage Design

- **Goals**:
  - Persist all types of data properly
- **Actions**:
  - Design PostgreSQL schema:
     - news table
     - user table 
     - interactions table
  - Setup HDFS for raw/historical data 
  - Setup vector database for embeddings
___

#### Phase 5: Machine Learning / NLP Layer
- **Goals**:
   - Add intelligence to news
- **Actions**:
   - Implement:
      - Emotion classification model
      - Embedding generation (transformers)
   - Store:
      - emotion labels
      - vector embeddings
___

#### Phase 6: Multi-Agent System

- **Goals**:
  - Build intelligent decision system

- **Agents to implement**:
  - Query Understanding Agent
  - Recommendation Agent
  - Filtering Agent
  - Router Agent
  - Aggregator Agent

- **Flow**:
```bash
User Query → Router → Relevant Agents → Aggregator → Response
```

- **Framework**:
  - LangGraph / LangChain
____

#### Phase 7: Backend API Layer
- **Goals**:
  - Expose system to frontend

- **Actions**:
  - Build FastAPI endpoints:
     - /search
     - /recommendations
     - /news
  - Connect:
     - agents
     - databases
     - vector store
___
#### Phase 8: Frontend (React)
- **Goals**:
  - User interface
- **Features**:
  - News dashboard
  - Search bar (agent-driven queries)
  - Recommendation feed
  - Filters (emotion/category)
___

#### Phase 9: Dockerization & Integration

- **Goals:**
  - Run full system locally like production
- **Actions**:
  - Create Dockerfiles for:
    - backend
    - frontend
    - ingestion service
    - Spark jobs
  - Setup Docker Compose to run entire stack together
___
#### Phase 10: Monitoring & Logging

- **Goals**:
   - Observe system behavior

- **Actions**:

   - Prometheus → metrics
   - Grafana → dashboards
   - ELK → logs

- **Track**:
   - API latency
   - ingestion success/failure
   - agent decisions
   - system load
___

#### Phase 11: Testing & Validation

- **Goals**:
  - Ensure system stability
- **Actions**:
  - Unit tests (Pytest)
  - API tests (Postman)
  - End-to-end testing of pipeline
  - Debugging and optimization
____
#### Phase 12: Collaboration Workflow
- Jira used for task tracking
- Each feature becomes a ticket
- Developer works on assigned tasks
- Pull Requests required for merging
- Planner reviews all PRs
___
### How Work Flows Between Two People
- 1.Planner defines:
  - architecture
  - tasks
  - schemas
  - agent logic
- 2.Developer implements:
  - services
  - pipelines
  - UI
  - integrations
- 3.Planner reviews:
  - code
  - architecture alignment
  - integration correctness
