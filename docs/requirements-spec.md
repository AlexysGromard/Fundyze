# Requirements Specification – Fundyze project

---

## 1. Project Objective

Develop a modern web application capable of **automatically monitoring** new companies going public (IPO) or raising funds, as well as **emerging crypto projects** with high potential or upcoming airdrops.

The application will integrate an **AI-based analysis system** (via a Large Language Model) to **summarize and evaluate** each project in a concise and insightful way.

All data will be **presented clearly and structurally** to the user, helping **investment decision-making**.

---

## 2. Functional Scope

### Data to Monitor

- Company in pre-IPO phase or recently listed
- Emerging crypto projects (new tokens, fundraising rounds, upcoming airdrops)

### Key Features

| Module           | Function             | Description                                                                 |
|------------------|----------------------|-----------------------------------------------------------------------------|
| Scraping/API     | Data Collection      | Automatically fetch project data via public APIs (Crunchbase, CoinGecko, SEC...) |
| Database         | Storage              | Store key project info (name, sector, pitch, IPO date, funding amount...)   |
| LLM Analysis     | Summarization & Scoring | Use an LLM to generate summaries and assign relevance scores              |
| React Frontend   | Visualization        | Display data in list/table views with filters (sector, date, score...)     |
| Alerts           | Notifications        | [WIP] Email alerts for newly tracked projects                                     |

---

## 3. Proposed Tech Stack

| Component       | Technology                        |
|------------------|----------------------------------|
| Frontend         | React + TypeScript               |
| Backend API      | Python + FastAPI                 |
| Scraping / APIs  | Python                           |
| Database         | MongoDB                          |
| AI / LLM         | mistral:7b                       |

---

## 4. AI Agents

| Agent      | Name                        | Main Role                                                                  | Input Sources                        | Outputs                                |
|------------|-----------------------------|----------------------------------------------------------------------------|--------------------------------------|----------------------------------------|
| Agent 1    | Data Collector              | Automatically fetch projects via scraping or public APIs                   | Public APIs                          | Raw project entries                    |
| Agent 2    | Contextualizer / Enricher   | Clean and enrich raw data (sector, country, market context...)             | Raw data                             | Enriched project entries               |
| Agent 3    | LLM Summarizer              | Generate structured summaries (pitch, strengths, risks, etc.)              | Enriched data                        | Summaries + insights                   |
| Agent 4    | Scoring & Evaluation        | Assign investment scores based on tech, market, trend, and other criteria  | Summaries + context                  | Final score + justification            |
| Agent 5    | Airdrop & Opportunity Watcher (Crypto) | Detect potential investment or airdrop opportunities in crypto projects | Summaries + official websites        | Airdrop indicators / investment flags  |
| Agent 6    | Weekly Synthesizer          | Compile weekly highlights and best projects                                | Project data from the week           | Weekly report + top picks              |

---
