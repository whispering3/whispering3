<div align="center">

<img src="https://capsule-render.vercel.app/api?type=waving&color=0:0D1117,60:0B3D2E,100:00FFA3&height=210&section=header&text=Danilo%20Souza&fontSize=50&fontColor=FFFFFF&fontAlignY=36&desc=AI%20Infrastructure%20%C2%B7%20Distributed%20Systems%20%C2%B7%20Backend%20Architecture&descSize=16&descAlignY=58&descColor=C9D1D9" alt="Danilo Souza" width="100%"/>

<img src="https://readme-typing-svg.demolab.com?font=JetBrains+Mono&weight=500&size=18&pause=1200&color=00FFA3&center=true&vCenter=true&width=720&lines=Creator+of+SCAO+%E2%80%94+a+2nd-order+optimizer+on+PyPI;Building+decentralized+LLM+training+on+consumer+GPUs;Postgres-native+queues%2C+AI+orchestration%2C+observability;Performance%2C+reliability+and+security+from+day+one" alt="Typing SVG" />

<br/><br/>

[**About**](#about) &nbsp;·&nbsp; [**Featured Work**](#featured-work) &nbsp;·&nbsp; [**Ecosystem**](#ecosystem) &nbsp;·&nbsp; [**Tech Stack**](#tech-stack) &nbsp;·&nbsp; [**Contact**](#contact)

<br/>

![Location](https://img.shields.io/badge/Brazil-Remote--first-0D1117?style=flat-square&labelColor=0D1117&color=00FFA3)
![Open to](https://img.shields.io/badge/Open_to-Full--time_·_Contract-0D1117?style=flat-square&labelColor=0D1117&color=00FFA3)
![PyPI](https://img.shields.io/pypi/v/scao?style=flat-square&label=scao%20on%20PyPI&labelColor=0D1117&color=00FFA3)
![Views](https://komarev.com/ghpvc/?username=whispering3&style=flat-square&label=PROFILE+VIEWS&labelColor=0D1117&color=00FFA3)

</div>

<br/>

## About

I'm a software engineer who works where **machine learning meets systems engineering**. I like problems where the abstraction leaks: a 2nd-order optimizer that doesn't fit in VRAM, a job queue that has to survive a worker crash mid-flight, an agent pipeline that must be observable and deterministic in production.

My approach is simple: understand the system from the ground up, measure everything, and ship code that other people can maintain.

<table>
<tr>
<td width="50%" valign="top">

**What I build**
- Optimization & training infrastructure for LLMs
- Decentralized / federated AI training protocols
- Fault-tolerant job queues and RAG pipelines
- Multi-agent orchestration platforms
- Observable, production-grade backends

</td>
<td width="50%" valign="top">

**How I work**
- Benchmarks and ablations before claims
- Explicit failure modes: retries, leases, DLQs
- Fewer moving parts (Postgres before a new broker)
- ADRs for every non-obvious trade-off
- Security and observability as defaults

</td>
</tr>
</table>

<br/>

## Featured Work

### SCAO — Sparse Curvature-Aware Adaptive Optimizer

> **A second-order PyTorch optimizer with near-AdamW memory and throughput cost.** Drop-in replacement for `AdamW`, published on PyPI and archived on Zenodo.

[![PyPI](https://img.shields.io/pypi/v/scao?style=flat-square&labelColor=0D1117&color=00FFA3)](https://pypi.org/project/scao/)
[![License](https://img.shields.io/badge/license-Apache_2.0-0D1117?style=flat-square&labelColor=0D1117&color=3178C6)](https://github.com/whispering3/scao/blob/main/LICENSE)
[![DOI](https://img.shields.io/badge/DOI-10.5281%2Fzenodo.19870556-0D1117?style=flat-square&labelColor=0D1117&color=3178C6)](https://doi.org/10.5281/zenodo.19870556)
[![Python](https://img.shields.io/badge/Python-3.10+-0D1117?style=flat-square&logo=python&logoColor=white&labelColor=0D1117&color=3776AB)](https://pypi.org/project/scao/)
[![Repo](https://img.shields.io/badge/View_Source-0D1117?style=flat-square&logo=github&labelColor=0D1117&color=181717)](https://github.com/whispering3/scao)

Full Shampoo-style preconditioning is out of reach on consumer hardware: at transformer widths around 4096, its curvature matrices exceed 128 GB per model copy. SCAO keeps the useful part of the curvature and drops the rest.

| Innovation | What it does |
|---|---|
| **Adaptive rank selection** | Keeps only the top-*k* eigenvectors holding ≥ 95% of spectral mass, cutting memory from `O(m²+n²)` to `O((m+n)·k)` |
| **Sparse block-diagonal FIM** | Bounds eigendecomposition cost on very wide layers without discarding inter-parameter correlation |
| **Phase-transition stability** | EMA bias correction, 50-step blend ramp and adaptive Tikhonov regularization for the Adam → SCAO handoff |
| **Int8 EMA quantization** | Curvature accumulators stored in int8 for a 4× memory saving, with eigendecomposition still in float32 |
| **Fused CUDA / Triton kernels** | Tiled GEMM and fused Kronecker preconditioner with automatic pure-PyTorch fallback |

**Results**

| Benchmark | Outcome |
|---|---|
| Qwen2.5-3B QLoRA on a single 16 GB T4 | **7.14 GB VRAM, stable run**, while full Shampoo failed at step 1 |
| WikiText-2 (500 steps) | **+54% throughput**, validation PPL within 1.5% of AdamW |
| Time-to-quality (PPL ≤ 14.10) | **1.82× faster** wall-clock than AdamW |
| Scaling trend (5M / 10M params) | **−9.6% / −4.8% PPL** vs AdamW |

**Ecosystem:** HuggingFace `Trainer` integration · Axolotl integration ([PR #3624](https://github.com/axolotl-ai-cloud/axolotl/pull/3624)) · scale presets from `scao_sub1b()` to `scao_125b()` · 66 automated tests · full ablation study.

```python
from scao import scao_3b

optimizer = scao_3b(model, lr=2e-4)   # one-line swap for AdamW
```

<br/>

### AZUOS — Decentralized Federated LLM Training

> **Fine-tune large language models collectively, on consumer GPUs, without a centralized cloud.**

Peers join a P2P network and contribute gradients. SCAO is the optimization core, which reduces how often nodes need to synchronize.

- **P2P layer:** Rust daemon on `libp2p` for peer discovery and GossipSub gradient propagation
- **Privacy & robustness:** Rényi differential privacy (DP-SGD) and Krum aggregation against Byzantine peers
- **Onboarding:** Tauri v2 desktop app for miners

`Python` · `PyTorch` · `Rust (libp2p)` · `Tauri` · `TypeScript` &nbsp;|&nbsp; *Private repository, available for review on request*

<br/>

### Worker Orchestrator — PostgreSQL as the Only Broker

> **A low-latency job queue that needs nothing but PostgreSQL 16.** No Redis, no RabbitMQ, no extra failure domain.

[![Repo](https://img.shields.io/badge/View_Source-0D1117?style=flat-square&logo=github&labelColor=0D1117&color=181717)](https://github.com/whispering3/worker-orchestrator)

<table>
<tr>
<td width="55%" valign="top">

- **Transactional enqueue:** a job exists only if the business data was committed
- **Zero-collision concurrency** with `FOR UPDATE SKIP LOCKED`
- **Sub-millisecond reactivity** through `LISTEN/NOTIFY`
- **Lease expiry:** a crashed worker's job is reclaimed automatically
- **Exponential backoff with ±20% jitter** to prevent retry storms
- **Dead letter queue** preserving `payload` and `last_error`
- React dashboard and ADRs documenting each trade-off

</td>
<td width="45%" valign="top">

| Metric | Result |
|---|---|
| Fetch latency | **< 3 ms** |
| Throughput | **> 1,200 jobs/s** on a single RDS instance |
| Concurrency | **50+ workers**, zero deadlocks |

</td>
</tr>
</table>

`Python` · `FastAPI` · `PostgreSQL 16` · `React` · `Docker`

<br/>

### CARQ — Context-Aware RAG Processing Queue

> **A resilient ingestion and semantic-search pipeline for RAG**, built around rate limits, partial failures and resource contention.

[![Repo](https://img.shields.io/badge/View_Source-0D1117?style=flat-square&logo=github&labelColor=0D1117&color=181717)](https://github.com/whispering3/CARQ)

- **10,000+ chunks/min** with graceful degradation
- **Surgical recovery:** only failed chunks are retried, never whole documents
- **Adaptive rate limiting**, circuit breaker and dead letter queue for provider limits
- **Idempotent ingestion** through content-hash deduplication
- **ACID durability** on PostgreSQL + `pgvector`, with multi-instance worker coordination
- **Observability:** structured JSON logs, Prometheus metrics, correlation IDs; Docker and Kubernetes manifests included

`Python` · `FastAPI` · `asyncio` · `PostgreSQL + pgvector` · `SQLAlchemy 2.0` · `Docker` · `Kubernetes`

<br/>

### ORQUESTRA PRO — AI Orchestration Platform

> **Multi-agent pipelines with deterministic execution, live streaming and production observability.**

[![Repo](https://img.shields.io/badge/View_Source-0D1117?style=flat-square&logo=github&labelColor=0D1117&color=181717)](https://github.com/whispering3/Orquestrador-AI)

- **XState state machines** for explicit transitions and controlled error handling instead of unpredictable agent loops
- **API fully decoupled from workers**, so load on one never destabilizes the other
- **Real-time mission streaming** over SSE (`task.*` and `step.*` events)
- **Telemetry** with Prometheus and Grafana: worker health, queue depth, cost and latency
- **BullMQ + Redis** for distributed execution, **Prisma + PostgreSQL** for state persistence

`TypeScript` · `Fastify` · `BullMQ` · `Redis` · `PostgreSQL` · `XState` · `Prometheus` · `Grafana` · `React`

<br/>

## Ecosystem

Two tracks that inform each other: **ML systems** (making advanced training practical on modest hardware) and **backend infrastructure** (making AI workloads reliable in production).

```mermaid
flowchart LR
    subgraph ML["ML Systems"]
        direction TB
        SCAO["SCAO<br/>2nd-order optimizer"]
        AZUOS["AZUOS<br/>federated LLM training"]
        HF["HuggingFace Trainer"]
        AX["Axolotl"]
        SCAO --> AZUOS
        SCAO --> HF
        SCAO --> AX
    end

    subgraph BE["Backend Infrastructure"]
        direction TB
        WO["Worker Orchestrator<br/>Postgres job queue"]
        CARQ["CARQ<br/>RAG ingestion pipeline"]
        ORQ["ORQUESTRA PRO<br/>agent orchestration"]
        WO -. "Postgres-as-broker pattern" .-> CARQ
    end

    ML ~~~ BE
```

<br/>

## Tech Stack

<div align="center">

<img src="https://skillicons.dev/icons?i=py,ts,rust,go,nodejs,fastapi,nestjs,fastify,pytorch,react&theme=dark&perline=10" alt="Languages and frameworks"/>
<br/>
<img src="https://skillicons.dev/icons?i=postgres,redis,mongodb,prisma,docker,kubernetes,prometheus,grafana,githubactions,linux&theme=dark&perline=10" alt="Data and infrastructure"/>

</div>

| Area | Tools |
|---|---|
| **Languages** | Python · TypeScript · Rust · Go · CUDA / Triton |
| **ML** | PyTorch · LLM fine-tuning (LoRA / QLoRA) · optimization · differential privacy |
| **Backend** | FastAPI · Fastify · NestJS · Node.js · asyncio |
| **Queues & orchestration** | PostgreSQL (`SKIP LOCKED`, `LISTEN/NOTIFY`) · BullMQ · XState |
| **Data** | PostgreSQL · pgvector · Redis · MongoDB · Prisma · SQLAlchemy |
| **Infra & observability** | Docker · Kubernetes · Prometheus · Grafana · GitHub Actions |

<br/>

## Open Source & Writing

- **[`scao`](https://pypi.org/project/scao/)** — published on PyPI with a citable DOI and an integration PR open in [Axolotl](https://github.com/axolotl-ai-cloud/axolotl/pull/3624)
- **[InstructLab proposal](https://github.com/instructlab/training/issues/703)** — adding SCAO as an optimizer option for constrained-hardware training
- **[TabNews write-up](https://www.tabnews.com.br/danilosoz/como-ganhei-convergencia-de-2-ordem-de-graca-no-fine-tuning-de-llms-apresentando-o-scao)** — how SCAO gets second-order convergence "for free" during QLoRA fine-tuning (in Portuguese)

<br/>

## GitHub Activity

<div align="center">

[![GitHub Streak](https://streak-stats.demolab.com?user=whispering3&theme=tokyonight&hide_border=true&background=0D1117&stroke=00ffa3&ring=00ffa3&fire=00ffa3&currStreakLabel=00ffa3)](https://git.io/streak-stats)

</div>

<br/>

## Contact

I'm open to **full-time roles, contract work and technical collaborations**, especially in AI infrastructure, distributed systems and backend architecture.

<div align="center">

[![LinkedIn](https://img.shields.io/badge/LinkedIn-Connect-0D1117?style=for-the-badge&logo=linkedin&logoColor=white&labelColor=0077B5&color=0D1117)](https://linkedin.com/in/danilosoz)
&nbsp;
[![Email](https://img.shields.io/badge/Email-Get_in_touch-0D1117?style=for-the-badge&logo=gmail&logoColor=white&labelColor=D14836&color=0D1117)](mailto:drsouza14@gmail.com)

<br/>

<img src="https://capsule-render.vercel.app/api?type=waving&color=0:00FFA3,60:0B3D2E,100:0D1117&height=110&section=footer" alt="" width="100%"/>

</div>
