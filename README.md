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

### 2. Data Hygiene Agent
Automatically analyzes B2B lead records and identifies data quality issues before they impact marketing operations.

**Issues Detected:**
- Duplicate records across the database
- Invalid or missing email addresses
- Test and disposable email accounts
- Missing required fields (company, title)
- Inconsistent data formats (country, name casing, company names)

**Output:** Detailed issue report with severity rating and specific recommendations — merge, quarantine, enrich, normalize, or delete.

### 3. Lead Routing Agent
Automatically routes incoming B2B leads to the correct sales rep based on territory, company size, lead score, and existing account ownership rules.

**Routing Logic:**
- Territory-based assignment (APAC, USA/Canada, Europe, Rest of World)
- Company size override — 1000+ employees always route to Enterprise team
- Lead score override — 80+ score triggers HOT priority flag
- Existing account ownership rule — always routes to current account owner

**Output:** Rep assignment with queue, priority level, full routing reason, and SLA deadline.

**Mirrors:** LeanData routing logic used in production MarTech stacks.

### 4. Campaign Performance Analyzer
Automatically analyzes B2B marketing campaign results, compares against industry benchmarks, flags anomalies, and generates CMO-ready recommendations.

**Analysis Framework:**
- Performance rating — Excellent / Good / Needs Improvement / Critical
- Key metrics — open rate, click rate, cost per MQL, pipeline ROI
- Benchmark comparison — actual vs target with variance percentage
- Anomaly detection — unusual patterns flagged with severity levels
- Recommendations — immediate, short-term, and strategic actions
- Executive summary — 3-sentence CMO-ready report

**Real-World Use:** Replaces hours of manual campaign reporting with instant AI-driven insights posted directly to Slack or email after every send.

### 5. Salesforce OAuth2 Integration with AI Lead Scoring

Live Salesforce integration that connects Python to a real Salesforce org, creates leads via API, scores them using the Lead Scoring Agent, and writes AI scores back to Salesforce as a custom field.

**What it does:**
- Authenticates to Salesforce using OAuth2 Client Credentials flow
- Creates B2B leads in Salesforce via Python API
- Fetches leads using SOQL queries
- Scores each lead using the Lead Scoring Agent
- Writes AI Lead Score back to Salesforce as a custom field (`AI_Lead_Score__c`)

**Key concepts demonstrated:**
- OAuth2 authentication (no username/password)
- SOQL queries
- Duplicate detection before lead creation
- Read/write operations on Salesforce objects
- Modular design — scoring criteria imported from `scoring_config.py`

**Tech:** Python, simple-salesforce, Anthropic Claude API, Salesforce Developer Edition

## Tech Stack
- Python 3.13
- Anthropic Claude API (claude-haiku)
- Jupyter Notebook
- python-dotenv
- simple-salesforce
- Salesforce (OAuth2 Client Credentials Flow)


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

This project demonstrates how AI agents can automate and enhance core MarTech workflows — including live Salesforce integrations.
