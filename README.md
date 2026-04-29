<div align="center">

<img src="https://readme-typing-svg.demolab.com?font=JetBrains+Mono&weight=600&size=20&pause=1000&color=00FFA3&center=true&vCenter=true&width=650&lines=Hi%2C+I'm+Danilo;Software+Engineer;Focused+on+AI%2C+Blockchain+%26+Distributed+Systems;Building+real-world+solutions+at+scale" alt="Typing SVG" />

<br/>

[![Profile Views](https://komarev.com/ghpvc/?username=whispering3&color=00ffa3&style=flat-square&label=PROFILE+VIEWS)](https://github.com/whispering3)
&nbsp;
![Focus](https://img.shields.io/badge/FOCUS-Backend_Architecture_%26_AI-blue?style=flat-square)
&nbsp;
![Stack](https://img.shields.io/badge/MAIN_STACK-TypeScript_%7C_Node.js_%7C_Python_%7C_LLMs-3178C6?style=flat-square)

</div>

---

## 👨‍💻 About Me

```typescript
const engineer = {
  name:     "Danilo Souza",
  focus:    "Backend Architecture & Distributed Systems",
  location: "Brazil 🇧🇷",

  current_status: {
    building: ["Decentralized AI Training Protocols", "Layer 1 Blockchains", "Autonomous AI Agents"],
    core_stack: ["TypeScript", "Node.js", "Python", "Rust", "PostgreSQL"],
  },

  engineering_philosophy: [
    "Understand systems from the ground up, not just the abstractions.",
    "Prioritize performance, scalability, and security from day one.",
    "Write pragmatic, maintainable code that solves real problems.",
    "Constant learning through building complex architectures."
  ],
} as const;
```

---

## 🛠️ Technology Stack

<div align="center">

### Languages
![TypeScript](https://img.shields.io/badge/TypeScript-007ACC?style=for-the-badge&logo=typescript&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black)
![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)
![Rust](https://img.shields.io/badge/Rust-000000?style=for-the-badge&logo=rust&logoColor=white)
![Go](https://img.shields.io/badge/Go-00ADD8?style=for-the-badge&logo=go&logoColor=white)

### Backend & Frameworks
![Node.js](https://img.shields.io/badge/Node.js-339933?style=for-the-badge&logo=nodedotjs&logoColor=white)
![NestJS](https://img.shields.io/badge/NestJS-E0234E?style=for-the-badge&logo=nestjs&logoColor=white)
![Express](https://img.shields.io/badge/Express-404D59?style=for-the-badge&logo=express&logoColor=white)
![FastAPI](https://img.shields.io/badge/FastAPI-009688?style=for-the-badge&logo=fastapi&logoColor=white)

### Databases
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-316192?style=for-the-badge&logo=postgresql&logoColor=white)
![Redis](https://img.shields.io/badge/Redis-DC382D?style=for-the-badge&logo=redis&logoColor=white)
![MongoDB](https://img.shields.io/badge/MongoDB-4EA94B?style=for-the-badge&logo=mongodb&logoColor=white)

### Infrastructure & Tools
![Docker](https://img.shields.io/badge/Docker-2CA5E0?style=for-the-badge&logo=docker&logoColor=white)
![GitHub Actions](https://img.shields.io/badge/GitHub_Actions-2088FF?style=for-the-badge&logo=github-actions&logoColor=white)
![Linux](https://img.shields.io/badge/Linux-FCC624?style=for-the-badge&logo=linux&logoColor=black)
![Git](https://img.shields.io/badge/Git-F05032?style=for-the-badge&logo=git&logoColor=white)

</div>

---

## 🚀 Featured Projects

I believe in learning by building complex, real-world systems. Here are some of the major projects I'm working on:

---

### 🧠 SwarmTrain — Decentralized Federated LLM Training

> **Focus:** Distributed Systems, AI Optimization, P2P Networks, Privacy.

**The Vision:**
Democratizing AI development by enabling ordinary users to collectively fine-tune large language models (LLMs) on consumer GPUs, bypassing the need for expensive centralized cloud infrastructure.

**Key Architecture:**
- **SCAO Integration:** Powered by the **Sparse Curvature-Aware Adaptive Optimizer (SCAO)**, a 2nd-order optimizer I developed that drastically reduces network synchronization frequency by converging up to 2.4x faster.
- **P2P Network:** Built a highly performant Rust daemon (libp2p) to handle decentralized peer discovery and GossipSub gradient propagation.
- **Privacy & Security:** Implemented Rényi Differential Privacy (DP-SGD) and Krum aggregation to protect raw data and defend against Byzantine faults.
- **UX:** Developed a Tauri v2 desktop application for seamless miner onboarding.

**Stack:** `Python` · `PyTorch` · `Rust (libp2p)` · `Tauri` · `TypeScript`

*(Private Repository)*

---

### 🧮 SCAO — Sparse Curvature-Aware Adaptive Optimizer

> **Focus:** Machine Learning Algorithms, CUDA Engineering, Performance Optimization.

**The Vision:**
Solving the memory bottlenecks of 2nd-order optimizers for LLM training on consumer hardware.

**Key Architecture:**
- **Adaptive Rank Selection:** Compresses curvature matrices by retaining ≥95% spectral mass, reducing memory footprint by 16-32x compared to full-rank methods like Shampoo.
- **Int8 EMA Quantization:** Developed a technique to store moving averages in int8, saving 4x memory without degrading perplexity.
- **CUDA Kernels:** Wrote custom fused CUDA kernels to resolve complexity bottlenecks in projection implementations.
- **Proven Results:** Successfully maintained 100% stability during a 3B parameter model fine-tuning on a single 16GB GPU, outperforming AdamW baselines.

**Stack:** `Python` · `PyTorch` · `CUDA`

[![View Source](https://img.shields.io/badge/View_Source-181717?style=for-the-badge&logo=github)](https://github.com/whispering3/scao)

---

### ⛓️ Azuos Chain (AZU) — Sovereign Layer 1 Blockchain

> **Focus:** Cryptography, Consensus Mechanisms, Distributed Ledgers.

**The Vision:**
Developing a fully sovereign Layer 1 blockchain built from the ground up, emphasizing decentralization and privacy.

**Key Architecture:**
- **Consensus:** Custom Proof-of-Work (SHA-256) implementation.
- **Privacy:** Integrated Ring Signatures for transaction anonymity.
- **Economics:** Engineered a strict 18 million supply limit and a 70/30 fee split model.
- **Status:** Currently operating on Mainnet v7.5 (April 2026).

**Stack:** `Go` · `Cryptography`

*(Private Repository)*

---

### 🤖 Agentizze — AI Agents SaaS Platform

> **Focus:** AI Orchestration, SaaS Architecture, Full-Stack Development.

**The Vision:**
Creating a platform for deploying and managing autonomous AI agents.

**Key Architecture:**
- **E-commerce Strategist:** Developed an automated agent utilizing Mistral Large 2411 to analyze the Etsy USA market, identifying high-demand, low-competition products.
- **Platform Development:** Building the SaaS infrastructure to support scalable agent deployment and management.

**Stack:** `TypeScript` · `Node.js` · `Mistral LLM`

*(Private Repository)*

---

## 📊 GitHub Stats

<div align="center">

[![GitHub Streak](https://streak-stats.demolab.com?user=whispering3&theme=tokyonight&hide_border=true&background=0D1117&stroke=00ffa3&ring=00ffa3&fire=ff6b6b&currStreakLabel=00ffa3)](https://git.io/streak-stats)

</div>

---

## 🤝 Let's Connect

I'm always open to discussing complex engineering challenges, AI optimization, and distributed systems.

<div align="center">

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white)](https://linkedin.com/in/danilosoz)
[![Email](https://img.shields.io/badge/Email-D14836?style=for-the-badge&logo=gmail&logoColor=white)](mailto:drsouza14@gmail.com)

</div>
```

How does this new structure feel? It's much more aligned with the impressive work you are actually doing!
