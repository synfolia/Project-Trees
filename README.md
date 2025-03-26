# Project-Trees - an applied MoDEM initiative 
The intelligent Forest

# MoDEM – Modular Distributed Expert Models  
*A Project Trees Initiative*  
“Not one brain. A hive of them.”

![Project Trees Logo](./assets/project-trees-logo.png)

---

## Overview

MoDEM is a distributed AI framework designed to route prompts intelligently to domain-specific expert language models.  
Instead of using one centralized generalist model, MoDEM lets you build a **modular swarm of local experts** — optimized for **speed**, **privacy**, and **domain alignment**.

---

## Key Features

- **Router model (Teacher):** Determines which expert SLM handles each query.
- **Expert models (Students):** Lightweight, domain-specific LLMs (LLaMA, DeepSeek, etc).
- **Feedback loop:** Automatically improves models daily based on usage.
- **Hybrid RAG:** Fetches documents from local/global vector stores (torrent-style).
- **Optional GPT fallback:** For out-of-distribution prompts.

---

## Architecture

![MoDEM Architecture](./assets/modem-architecture.png)

> Each component is containerized and easily orchestrated using Docker Compose or Kubernetes.

---

## Stack

| Layer         | Tech Used                      |
|---------------|--------------------------------|
| Router        | DeepSeek, Gorilla, OpenRouter  |
| Expert Models | LLaMA 3.1, DeepSeek-v2         |
| Feedback      | Custom JSON logging + daily retraining |
| RAG           | Local vector DB (e.g. Chroma) + torrent fetch |
| UI            | OpenWebUI / Custom React app   |
| Fallback      | OpenAI GPT (optional)          |

---

## Quickstart (PoC)

```bash
git clone https://github.com/project-trees/modem
cd modem

# Spin up the router + 2 expert models
docker-compose up
