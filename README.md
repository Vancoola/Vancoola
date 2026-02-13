# 👋 Hello, I'm Denis
### System Architect & Rust Enthusiast 🦀

<p align="left">
  <img src="https://img.shields.io/badge/Rust-2024-orange?style=for-the-badge&logo=rust" alt="Rust">
  <img src="https://img.shields.io/badge/WebAssembly-624DE8?style=for-the-badge&logo=webassembly&logoColor=white" alt="WASM">
  <img src="https://img.shields.io/badge/PostgreSQL-336791?style=for-the-badge&logo=postgresql&logoColor=white" alt="Postgres">
  <img src="https://img.shields.io/badge/Tokio-000000?style=for-the-badge&logo=tokio&logoColor=white" alt="Tokio">
</p>

---

## 🚀 About Me

I build high-performance, resilient, and type-safe systems. My passion lies in **Modular Monoliths**, **Event-Driven Architecture**, and pushing the boundaries of what's possible with **Rust**.

- 🛠️ Currently architecting **[Oxide LMS](https://github.com/Vancoola/oxide-lms)** — a next-gen learning platform powered by Rust and sandboxed WASM plugins.
- 🏗️ Deeply interested in **Clean Architecture**, **Transactional Outbox patterns**, and **Zero-cost abstractions**.
- ⚡ Focus: Low-latency backends, secure sandboxing, and scalable database design.

---

## 🛠️ Engineering Toolkit

| Layer | Technologies |
| :--- | :--- |
| **Backend** | `Rust (Axum, Tokio, SQLx)`, `C#` |
| **Frontend** | `Leptos (WASM)`, `Tailwind CSS` |
| **Infrastructure** | `PostgreSQL`, `Redis`, `Docker`, `NATS` |
| **Extensibility** | `Wasmtime`, `WIT (Component Model)` |

---

## 📊 Project Showcase: Oxide LMS 🦀
*The core of my current research in modular systems.*



```mermaid
graph LR
    subgraph Clients [Frontend Applications]
        direction TB
        admin[oxide-admin]
        dean[oxide-dean]
        web[oxide-web]
    end

    subgraph ClientShared [Client Shared]
        common[oxide-web-common]
        ui[oxide-ui]
        i18n[oxide-i18n]
    end

    admin --> common
    dean --> common
    web --> common
    
    common --> ui
    common --> i18n

    shared_types[oxide-shared-types]
    web -.-> shared_types
    api -.-> shared_types

    subgraph External [External storage]
        redis[(Redis)]
        db[(PostgreSQL)]
        ES[(Elasticsearch)]
    end

    subgraph Server [Backend Engine]
        api[oxide-api]
        subgraph IL [Infrastructure Layer]
            inf[oxide-infrastructure]
            data[oxide-data]
        end
        biz[oxide-business]
        wasm[oxide-wasm-provider]
        
        
        api --> biz
        biz --> inf
        biz --> data
        biz --> wasm
        wasm --x plugins{{WASM Plugins}}

        dom[oxide-domain]
        macros[oxide-macros]
        
        dom ==> macros
        
        data --> dom
        inf --> dom
        biz --> dom
        wasm --> dom
        
    end
    
    
    
    data --> External
```


**Key architectural achievements:**
* **Sandboxed Plugins:** Executing untrusted code via Wasmtime with sub-millisecond overhead.
* **Guaranteed Event Delivery:** Custom Transactional Outbox implementation using Postgres `LISTEN/NOTIFY`.
* **Type-Safe Sync:** Shared DTOs between Leptos frontend and Axum backend for zero-overhead API contracts.

---

## 📫 Let's Connect

- 💼 LinkedIn: [linkedin.com/in/denis-suzdaltsev](https://linkedin.com/in/denis-suzdaltsev)
- 📧 Email: suzdaltsevdenis@icloud.com
- 🦀 Rustaceans are always welcome to open a PR or a Discussion in my repos!
