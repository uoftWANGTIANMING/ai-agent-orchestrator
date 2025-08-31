# AI Agent Orchestrator

## Overview
A **multi-agent orchestration** framework that coordinates LLM-powered agents to autonomously **decompose tasks, execute tools, and merge results**.  
*(Beta: minimal planner/worker/reviewer agents.)*

---

## Architecture
- **API (FastAPI):** Submit tasks and retrieve results
- **Planner Agent:** Breaks down the goal into sub-tasks
- **Worker Agent:** Executes sub-tasks via tools (e.g., code, search, math)
- **Reviewer Agent:** Validates intermediate results and merges outputs
- **State Management:** Redis-backed task queue + DAG tracking

---

## Features
- [x] Autonomous task decomposition (planner agent)
- [x] Tool-calling with LangChain integration
- [x] Redis-backed fault-tolerant queue
- [ ] Vector database for context-aware tasks *(planned)*
- [ ] Parallel sub-task execution *(planned)*

---

## Tech Stack
**Languages:** Python  
**Frameworks:** FastAPI, LangChain  
**Tools:** Redis, Docker, PyTest

---

## Quickstart

    # Clone repository
    git clone https://github.com/<your-username>/ai-agent-orchestrator.git
    cd ai-agent-orchestrator

    # Build and start services
    docker compose up -d

    # Submit a multi-step task
    curl -X POST localhost:9000/tasks \
        -H "Content-Type: application/json" \
        -d '{"goal":"Summarize 3 URLs and draft a short brief"}'

    # Check task result
    curl localhost:9000/tasks/<id>

---

## Status & Roadmap
- [x] Planner → Worker → Reviewer agents (MVP)
- [x] Redis queue + retries for fault tolerance
- [ ] Vector database integration *(planned)*
- [ ] Tool plugins (code execution, web scraping) *(planned)*
- [ ] Multi-agent collaboration at scale *(planned)*

---

## License
MIT
