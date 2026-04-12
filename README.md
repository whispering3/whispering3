<div align="center">

<img src="https://readme-typing-svg.demolab.com?font=JetBrains+Mono&weight=600&size=20&pause=1000&color=00FFA3&center=true&vCenter=true&width=650&lines=Ola%2C+eu+sou+o+Danilo;Desenvolvedor+Backend+Junior;Apaixonado+por+Python+%7C+PostgreSQL+%7C+Docker;Construindo+projetos+reais+para+aprender+de+verdade" alt="Typing SVG" />

<br/>

[![Visualizações](https://komarev.com/ghpvc/?username=whispering3&color=00ffa3&style=flat-square&label=VISITAS+AO+PERFIL)](https://github.com/whispering3)
&nbsp;
![Status](https://img.shields.io/badge/STATUS-BUSCANDO_PRIMEIRA_OPORTUNIDADE-00ffa3?style=flat-square)
&nbsp;
![Foco](https://img.shields.io/badge/FOCO-Backend_Development-blue?style=flat-square)

</div>

---

## Sobre mim

```typescript
const dev = {
  nome:     "Danilo Souza",
  nivel:    "Júnior",
  foco:     "Desenvolvimento Backend",
  local:    "Brasil 🇧🇷",

  situacao: {
    momento:   "Sem experiência formal ainda, mas construindo projetos reais",
    buscando:  "Primeira oportunidade como desenvolvedor backend",
    estudando: ["NestJS", "Docker", "Arquitetura de APIs REST", "PostgreSQL avançado"],
  },

  o_que_me_move: [
    "Entender como as coisas funcionam por baixo dos panos",
    "Construir projetos que resolvam problemas reais",
    "Escrever código limpo e que faça sentido",
    "Aprender com cada erro de compilação 😅",
  ],
} as const;
```

---

## 🛠️ Tecnologias que estou aprendendo e usando

<div align="center">

### Linguagens
![TypeScript](https://img.shields.io/badge/TypeScript-007ACC?style=for-the-badge&logo=typescript&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black)
![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)

### Backend & Frameworks
![Node.js](https://img.shields.io/badge/Node.js-339933?style=for-the-badge&logo=nodedotjs&logoColor=white)
![NestJS](https://img.shields.io/badge/NestJS-E0234E?style=for-the-badge&logo=nestjs&logoColor=white)
![Express](https://img.shields.io/badge/Express-404D59?style=for-the-badge&logo=express&logoColor=white)
![FastAPI](https://img.shields.io/badge/FastAPI-009688?style=for-the-badge&logo=fastapi&logoColor=white)

### Banco de Dados
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-316192?style=for-the-badge&logo=postgresql&logoColor=white)
![Redis](https://img.shields.io/badge/Redis-DC382D?style=for-the-badge&logo=redis&logoColor=white)
![MongoDB](https://img.shields.io/badge/MongoDB-4EA94B?style=for-the-badge&logo=mongodb&logoColor=white)

### ORMs & Query Builders
![Prisma](https://img.shields.io/badge/Prisma-3982CE?style=for-the-badge&logo=Prisma&logoColor=white)
![TypeORM](https://img.shields.io/badge/TypeORM-FE0803?style=for-the-badge&logo=typeorm&logoColor=white)

### Infraestrutura
![Docker](https://img.shields.io/badge/Docker-2CA5E0?style=for-the-badge&logo=docker&logoColor=white)
![GitHub Actions](https://img.shields.io/badge/GitHub_Actions-2088FF?style=for-the-badge&logo=github-actions&logoColor=white)
![Linux](https://img.shields.io/badge/Linux-FCC624?style=for-the-badge&logo=linux&logoColor=black)

### Ferramentas
![Git](https://img.shields.io/badge/Git-F05032?style=for-the-badge&logo=git&logoColor=white)
![Insomnia](https://img.shields.io/badge/Insomnia-5849BE?style=for-the-badge&logo=insomnia&logoColor=white)
![VSCode](https://img.shields.io/badge/VSCode-007ACC?style=for-the-badge&logo=visual-studio-code&logoColor=white)

</div>

---

## 🚀 Meus Projetos de Estudo

> Sem experiência formal ainda — mas esses projetos são onde boto a mão na massa de verdade.

---

### 📦 PG-Queue — Fila de Jobs com PostgreSQL Puro

> **O que aprendi:** Que não precisa de Redis pra ter uma fila robusta. PostgreSQL resolve.

**O problema que quis resolver:**
Entender como sistemas de filas funcionam por dentro, sem depender de ferramentas prontas como BullMQ ou RabbitMQ.

**O que implementei:**
- Fila transacional usando `FOR UPDATE SKIP LOCKED` no PostgreSQL
- Workers concorrentes sem race condition
- Retry automático com backoff em caso de falha
- Painel simples para visualizar o status dos jobs

**O que aprendi na prática:**
- Como transações do banco garantem consistência em ambientes concorrentes
- A diferença entre concorrência otimista e pessimista
- Como o PostgreSQL se comporta sob carga com múltiplos workers

**Stack:** `TypeScript` · `NestJS` · `PostgreSQL` · `Docker`

[![Ver Projeto](https://img.shields.io/badge/Ver_no_GitHub-181717?style=for-the-badge&logo=github)](https://github.com/whispering3/worker-orchestrator)

---

### ⛓️ Solana Volume Engine — Estudo de Transações On-Chain

> **O que aprendi:** Como blockchains públicas funcionam de verdade, além do tutorial básico.

**O problema que quis resolver:**
Entender como transações em blockchain são construídas, assinadas e executadas programaticamente — sem usar abstrações que escondem a complexidade.

**O que implementei:**
- Integração com a RPC da Solana para envio de transações
- Estudo de como MEV (Maximal Extractable Value) funciona
- Orquestração de múltiplas carteiras de forma programática
- Uso do Jupiter v6 para roteamento de swaps

**O que aprendi na prática:**
- Como uma transação blockchain é estruturada em bytes
- O que são Address Lookup Tables e por que existem
- A diferença entre confirmação otimista e finalidade

**Stack:** `TypeScript` · `Solana Web3.js` · `Jupiter API` · `Node.js`

[![Ver Projeto](https://img.shields.io/badge/Ver_no_GitHub-181717?style=for-the-badge&logo=github)](https://github.com/whispering3/solana-pumpfun-volume-bot)

---

### 🛡️ Marketplace com Foco em Privacidade — Estudo de Segurança

> **O que aprendi:** Segurança de verdade é muito mais do que colocar JWT no header.

**O problema que quis resolver:**
Estudar como sistemas que exigem privacidade real são arquitetados — autenticação, criptografia e pagamentos sem custódia.

**O que implementei:**
- Autenticação via desafio PGP (sem senha tradicional)
- Criptografia de ponta a ponta nas mensagens entre usuários
- Integração com RPC do Monero para pagamentos sem rastreabilidade
- Mecanismo de invalidação de sessão por PIN de emergência

**O que aprendi na prática:**
- Como criptografia assimétrica funciona na prática (não só na teoria)
- Diferença entre autenticação e autorização em profundidade
- O que é e como evitar ataques de replay

**Stack:** `NestJS` · `PostgreSQL` · `PGP` · `Monero RPC` · `TypeScript`

> 🔒 Repositório privado.

---

## 📊 Minhas estatísticas no GitHub

<div align="center">

[![GitHub Streak](https://streak-stats.demolab.com?user=whispering3&theme=tokyonight&hide_border=true&background=0D1117&stroke=00ffa3&ring=00ffa3&fire=ff6b6b&currStreakLabel=00ffa3)](https://git.io/streak-stats)

</div>

---

## 📚 O que estou estudando agora

```
✅ Concluído        🔄 Em andamento      🗓️ Na fila
```

| Tópico | Status | Onde estou estudando |
|:---|:---:|:---|
| APIs REST com NestJS | ✅ | Projetos próprios |
| Docker & containerização | ✅ | Projetos próprios |
| PostgreSQL avançado (índices, transações) | 🔄 | Projetos próprios + documentação oficial |
| Arquitetura de microsserviços | 🔄 | Livro: Designing Data-Intensive Applications |
| Testes automatizados (Jest) | 🔄 | Projetos próprios |
| CI/CD com GitHub Actions | 🔄 | Projetos próprios |
| Kubernetes (básico) | 🗓️ | — |
| Redis avançado | 🗓️ | — |

---

## 🤝 Vamos conversar?

<div align="center">

Estou buscando minha **primeira oportunidade** como desenvolvedor backend.
Se você tem um time que acredita em júniores com disposição para aprender, me chama! 👇

<br/>

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white)](https://linkedin.com/in/danilosoz)
[![Email](https://img.shields.io/badge/Email-D14836?style=for-the-badge&logo=gmail&logoColor=white)](mailto:drsouza14@gmail.com)

</div>

---

<div align="center">

*"Todo sênior já foi júnior que não desistiu."*

</div>
