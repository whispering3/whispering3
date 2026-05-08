<div align="center">

<img src="https://readme-typing-svg.demolab.com?font=JetBrains+Mono&weight=600&size=20&pause=1000&color=00FFA3&center=true&vCenter=true&width=650&lines=Hi%2C+I'm+Danilo;Software+Engineer;Focused+on+AI%2C+Blockchain+%26+Distributed+Systems;Building+real-world+solutions+at+scale" alt="Typing SVG" />

<br/>

[![Profile Views](https://komarev.com/ghpvc/?username=whispering3&color=00ffa3&style=flat-square&label=PROFILE+VIEWS)](https://github.com/whispering3)
&nbsp;
[![LinkedIn](https://img.shields.io/badge/LinkedIn-Connect-0077B5?style=flat-square&logo=linkedin)](https://linkedin.com/in/danilosoz)
&nbsp;
[![Email](https://img.shields.io/badge/Email-Hire%20Me-D14836?style=flat-square&logo=gmail&logoColor=white)](mailto:drsouza14@gmail.com)

![Focus](https://img.shields.io/badge/FOCUS-Backend_Architecture_%26_AI-blue?style=flat-square)
&nbsp;
![Stack](https://img.shields.io/badge/MAIN_STACK-TypeScript_%7C_Node.js_%7C_Python_%7C_Rust-3178C6?style=flat-square)
&nbsp;
![Open To](https://img.shields.io/badge/OPEN_TO-Full--time_%7C_Contract_%7C_Remote-00ffa3?style=flat-square)

</div>

---

## 👨‍💻 About Me

```typescript
const engineer = {
  name:     "Danilo Souza",
  role:     "Senior Software Engineer",
  focus:    "Backend Architecture, AI Systems & Distributed Computing",
  location: "Brazil 🇧🇷 · Remote-first",

  what_i_build: [
    "Decentralized AI Training Protocols",
    "High-Throughput AI Orchestration Platforms",
    "High-Performance Job Queue Systems",
    "Autonomous AI Agents & SaaS Infrastructure",
  ],

  core_stack: {
    languages:    ["TypeScript", "Python", "Rust", "Go"],
    backend:      ["Node.js", "Fastify", "NestJS", "FastAPI"],
    ai_ml:        ["PyTorch", "LLMs", "XState", "BullMQ"],
    databases:    ["PostgreSQL", "Redis", "MongoDB"],
    infra:        ["Docker", "Prometheus", "Grafana", "GitHub Actions"],
  },

  engineering_philosophy: [
    "Understand systems from the ground up, not just the abstractions.",
    "Prioritize performance, scalability, and security from day one.",
    "Write pragmatic, maintainable code that solves real problems.",
    "Constant learning through building complex architectures.",
  ],
} as const;
```

---

## 🚀 Featured Projects

---

### 🎭 ORQUESTRA PRO — Institutional AI Orchestration Platform

> **Focus:** AI Orchestration · Distributed Systems · Real-Time Streaming · Production Observability

**The Vision:**
A high-performance AI orchestration platform designed to manage complex multi-agent pipelines with full observability, real-time streaming, and fault recovery — built for production environments.

**Key Architecture:**
- **State Machine Orchestration (XState):** Deterministic execution flows with explicit state transitions and advanced error handling, eliminating unpredictable agent behavior.
- **Decoupled Architecture:** API layer fully separated from execution workers, ensuring system stability under heavy load.
- **Real-Time Mission Streaming:** Live mission tracking via Server-Sent Events (SSE), delivering immediate `task.*` and `step.*` event feedback to the UI.
- **Industrial Observability:** End-to-end telemetry pipeline with Prometheus and Grafana — monitoring worker health, queue status, and cost/latency metrics.
- **High-Concurrency Processing:** Distributed execution powered by BullMQ + Redis for massive scalability, with full state persistence via Prisma + PostgreSQL.
- **Smart Context Injection:** Automatic skill discovery and context enrichment injected directly into agent prompts.

**Stack:** `TypeScript` · `Fastify` · `Node.js` · `BullMQ` · `Redis` · `PostgreSQL` · `XState` · `Prometheus` · `Grafana` · `React`

[![View Source](https://img.shields.io/badge/View_Source-181717?style=for-the-badge&logo=github)](https://github.com/whispering3/Orquestrador-AI)

---

### 🧠 AZUOS — Decentralized Federated LLM Training

> **Focus:** Distributed Systems · AI Optimization · P2P Networks · Privacy Engineering

**The Vision:**
Democratizing AI development by enabling ordinary users to collectively fine-tune large language models on consumer GPUs — no expensive centralized cloud required.

**Key Architecture:**
- **SCAO Integration:** Powered by a custom 2nd-order optimizer (SCAO) that reduces network synchronization frequency by converging up to **2.4x faster** than standard methods.
- **P2P Network:** High-performance Rust daemon (libp2p) for decentralized peer discovery and GossipSub gradient propagation.
- **Privacy & Security:** Rényi Differential Privacy (DP-SGD) + Krum aggregation to protect raw data and defend against Byzantine faults.
- **Desktop UX:** Tauri v2 application for seamless miner onboarding.

**Stack:** `Python` · `PyTorch` · `Rust (libp2p)` · `Tauri` · `TypeScript`

*(Private Repository — available for review upon request)*

---

### 🧮 SCAO — Sparse Curvature-Aware Adaptive Optimizer

> **Focus:** ML Algorithms · CUDA Engineering · Performance Optimization

**The Vision:**
Solving the memory bottlenecks of 2nd-order optimizers for LLM training on consumer hardware — making advanced optimization accessible without requiring A100-class GPUs.

**Key Architecture:**
- **Adaptive Rank Selection:** Compresses curvature matrices retaining ≥95% spectral mass — **16–32x memory reduction** vs. full-rank methods like Shampoo.
- **Int8 EMA Quantization:** Custom technique storing moving averages in int8, saving 4x memory without perplexity degradation.
- **Custom CUDA Kernels:** Fused CUDA kernels resolving complexity bottlenecks in projection implementations.
- **Proven Results:** 100% stability on 3B parameter model fine-tuning on a single 16GB GPU, outperforming AdamW baselines.

**Stack:** `Python` · `PyTorch` · `CUDA`

[![View Source](https://img.shields.io/badge/View_Source-181717?style=for-the-badge&logo=github)](https://github.com/whispering3/scao)

---

### 🕷️ Worker Orchestrator — High-Performance PostgreSQL Job Queue

> **Focus:** Distributed Systems · Database Engineering · Fault Tolerance · Systems Design

**The Vision:**
A high-performance, low-latency job orchestration system using **PostgreSQL 16 as the sole broker** — eliminating the operational complexity of managing Redis or RabbitMQ as an extra dependency.

**Why PostgreSQL?** In many production scenarios, introducing Redis just for queues creates an extra point of failure and backup complexity. This project demonstrates how to leverage powerful database primitives to achieve enterprise-grade queuing without the overhead:

1. **Guaranteed Transactionality:** A job is only created if the business data is saved successfully — no dual-write inconsistencies.
2. **Atomic Concurrency:** Multiple workers with zero collisions via `FOR UPDATE SKIP LOCKED`.
3. **Near-Zero Latency:** Sub-millisecond reactivity via PostgreSQL `LISTEN/NOTIFY`.

**Key Architecture:**
- **Lease Expiry System:** If a worker crashes mid-processing, the `lease_expires_at` field expires automatically and another worker claims the job on the next fetch cycle — zero manual intervention.
- **Exponential Backoff with Jitter (±20%):** Temporary failures (e.g., network timeouts) don't create retry storms. Randomized delay prevents thousands of failed jobs retrying simultaneously.
- **Dead Letter Queue (DLQ):** Persistently failing jobs move to `dead` status, preserving the full `payload` and `last_error` for manual audit and reprocessing via the dashboard.
- **React Dashboard:** Modern UI for monitoring queue health, worker status, and DLQ management.
- **ADR Documentation:** Architectural Decision Records detailing every technical trade-off made during design.

**Benchmarks:**
| Metric | Result |
|---|---|
| Fetch Latency | < 3ms |
| Throughput | > 1,200 jobs/sec (Single RDS instance) |
| Concurrency | 50+ parallel workers — zero deadlocks |

**Stack:** `Python` · `FastAPI` · `PostgreSQL 16` · `React` · `Docker`

[![View Source](https://img.shields.io/badge/View_Source-181717?style=for-the-badge&logo=github)](https://github.com/whispering3/worker-orchestrator)

---

### 🤖 Agentizze — AI Agents SaaS Platform

> **Focus:** AI Orchestration · SaaS Architecture · Full-Stack Development

**The Vision:**
A platform for deploying and managing autonomous AI agents with real business impact — starting with an e-commerce market intelligence agent for the Etsy ecosystem.

**Key Architecture:**
- **Market Intelligence Agent:** Automated agent using Mistral Large 2411 to analyze the Etsy USA market, identifying high-demand, low-competition product opportunities.
- **Platform Infrastructure:** Scalable SaaS architecture supporting multi-tenant agent deployment and lifecycle management.

**Stack:** `TypeScript` · `Node.js` · `Mistral LLM`

[![Live Product](https://img.shields.io/badge/Live_Product-agentizze.com-00ffa3?style=for-the-badge&logo=rocket&logoColor=white)](https://agentizze.com)

---

## 🛠️ Technology Stack

<div align="center">

### Languages
![TypeScript](https://img.shields.io/badge/TypeScript-007ACC?style=for-the-badge&logo=typescript&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black)
![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)
![Rust](https://img.shields.io/badge/Rust-000000?style=for-the-badge&logo=rust&logoColor=white)

### Backend & Frameworks
![Node.js](https://img.shields.io/badge/Node.js-339933?style=for-the-badge&logo=nodedotjs&logoColor=white)
![Fastify](https://img.shields.io/badge/Fastify-000000?style=for-the-badge&logo=fastify&logoColor=white)
![NestJS](https://img.shields.io/badge/NestJS-E0234E?style=for-the-badge&logo=nestjs&logoColor=white)
![FastAPI](https://img.shields.io/badge/FastAPI-009688?style=for-the-badge&logo=fastapi&logoColor=white)

### AI & ML
![PyTorch](https://img.shields.io/badge/PyTorch-EE4C2C?style=for-the-badge&logo=pytorch&logoColor=white)
![CUDA](https://img.shields.io/badge/CUDA-76B900?style=for-the-badge&logo=nvidia&logoColor=white)
![XState](https://img.shields.io/badge/XState-2C3E50?style=for-the-badge)
![BullMQ](https://img.shields.io/badge/BullMQ-FF6A00?style=for-the-badge)

### Databases
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-316192?style=for-the-badge&logo=postgresql&logoColor=white)
![Redis](https://img.shields.io/badge/Redis-DC382D?style=for-the-badge&logo=redis&logoColor=white)
![MongoDB](https://img.shields.io/badge/MongoDB-4EA94B?style=for-the-badge&logo=mongodb&logoColor=white)

### Infrastructure & Observability
![Docker](https://img.shields.io/badge/Docker-2CA5E0?style=for-the-badge&logo=docker&logoColor=white)
![Prometheus](https://img.shields.io/badge/Prometheus-E6522C?style=for-the-badge&logo=prometheus&logoColor=white)
![Grafana](https://img.shields.io/badge/Grafana-F46800?style=for-the-badge&logo=grafana&logoColor=white)
![GitHub Actions](https://img.shields.io/badge/GitHub_Actions-2088FF?style=for-the-badge&logo=github-actions&logoColor=white)
![Linux](https://img.shields.io/badge/Linux-FCC624?style=for-the-badge&logo=linux&logoColor=black)

</div>

---

## 📊 GitHub Stats

<div align="center">

[![GitHub Streak](https://streak-stats.demolab.com?user=whispering3&theme=tokyonight&hide_border=true&background=0D1117&stroke=00ffa3&ring=00ffa3&fire=ff6b6b&currStreakLabel=00ffa3)](https://git.io/streak-stats)

</div>

---

## 🤝 Let's Connect

I'm available for **full-time roles, contract work, and technical collaborations** — especially in AI infrastructure, distributed systems, and backend architecture.

<div align="center">

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white)](https://linkedin.com/in/danilosoz)
[![Email](https://img.shields.io/badge/Email-D14836?style=for-the-badge&logo=gmail&logoColor=white)](mailto:drsouza14@gmail.com)

</div>
