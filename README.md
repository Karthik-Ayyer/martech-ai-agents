# MarTech AI Agents

AI-powered Marketing Technology agents built with Python and the Anthropic Claude API — designed by a MarTech professional for real-world Revenue Operations use cases.

## Agents

### 1. Lead Scoring Agent
Automatically scores B2B SaaS leads from 0-100 using a custom framework built on MarTech domain expertise.

**Scoring Framework:**
- Job Title (25 points) — seniority determines budget authority
- Company Size (20 points) — larger companies have bigger budgets and more complex needs
- Intent Signal (25 points) — 6sense-style behavioral intent matching
- Engagement (30 points) — website visits, email opens, form submissions

**Features:**
- Scores individual leads with full breakdown
- Batch scores multiple leads in one run
- Returns Hot/Warm/Cold recommendation and specific next action
- Powered by Claude AI with domain-defined scoring rules

## Tech Stack
- Python 3.13
- Anthropic Claude API (claude-haiku)
- Jupyter Notebook
- python-dotenv

## Setup
1. Clone this repository
2. Create a `.env` file in the root folder
3. Add your Anthropic API key: `ANTHROPIC_API_KEY=your-key-here`
4. Install dependencies: `pip install anthropic python-dotenv`
5. Open the notebook and run all cells

## System Design

See the `/system-design` folder for a complete GTM Data Governance 
and Lifecycle Orchestration Framework covering:

- Data quality and normalization strategy
- Identity resolution and deduplication logic
- Lead routing and lifecycle orchestration
- API integration design with OAuth, pagination, and idempotency
- Observability and reliability patterns

Built from hands-on experience with Marketo, Salesforce, LeanData, 6sense, and ZoomInfo.

## About
Built by **Karthik Ayyer** — Marketing Automation Manager with expertise in MarTech & Revenue Operations (Marketo, Salesforce, LeanData, 6sense, Looker).

This project demonstrates how AI agents can automate and enhance core MarTech workflows without requiring access to live enterprise systems.
