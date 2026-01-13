# 👋 Hi, I'm Nabit Mikan Castano

**AI Automation Architect | Generative AI Engineer | E-Commerce Specialist** 📍 Berlin, Germany | 🌐 [genflowautomation.com](https://genflowautomation.com)

---

## 🚀 About Me

A few years ago, I grew frustrated with the traditional marketing industry. Everyone was selling the same formulas: "more clicks, more leads, more magic." But behind the noise, real, scalable results were missing. I decided to build what I couldn't find: **intelligent systems that actually work.**

Today, I am an **AI Automation Architect** specializing in **agentic AI systems**. I don't just "automate tasks"; I design self-improving engines that create, publish, and learn autonomously. I blend my background as a **Certified Online Marketing Manager** with AI engineering to transform business problems into robust, production-grade software solutions.

As **CEO of Genflow Automation**, my mission is to free professionals from repetitive work, giving them back the time to create, innovate, and grow.

---

## 🏗️ Featured Project: Botanery Content Agent

**Botanery** is an autonomous, closed-loop content system designed for e-commerce. Unlike simple linear workflows, this agent makes data-driven decisions to manage the entire content lifecycle for a brand.

### System Architecture
The system utilizes a **Job-Queue architecture** with strict separation of concerns, ensuring the creation process is fault-tolerant, scalable, and production-ready.

```mermaid
graph LR
    subgraph "Persistence & Queue"
        DB[(Supabase DB)] -- "Fetch Pending Jobs" --> Worker
        Worker -- "Update Status / Log Results" --> DB
    end

    subgraph "Execution Layer (Node.js)"
        Worker[Main Node.js Worker]
    end

    subgraph "Intelligence & Creative"
        Worker -- "Prompt & Context" --> LLM[OpenAI / Midjourney]
        LLM -- "Generated Assets" --> Worker
    end

    subgraph "Distribution"
        Worker -- "Publish Content" --> Meta[Meta Graph API]
        Meta -- "Media ID" --> Worker
    end

    subgraph "Learning Loop"
        Collector[Metrics Collector] -- "Get Engagement" --> Meta
        Collector -- "Store Signals" --> DB
        DB -- "Optimize Selection" --> Worker
    end

    style Worker fill:#f9f,stroke:#333,stroke-width:2px
    style DB fill:#00dfd8,stroke:#333
    style Collector fill:#ffcc00,stroke:#333
