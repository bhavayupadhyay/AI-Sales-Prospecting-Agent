# AI Sales Prospecting Agent

An AI-powered agent that automatically discovers potential customers, researches them, and generates personalized outreach emails.

The goal of this project is to automate the most time-consuming part of outbound sales: finding leads and writing personalized emails.

---

# Overview

Sales prospecting typically involves:

* searching for companies
* researching what they do
* identifying decision makers
* writing personalized cold emails

This project automates that entire workflow using AI and web data.

The system discovers companies, enriches them with context, identifies potential contacts, and generates short personalized outreach emails automatically.

---

# Features

### Lead Discovery

Searches the web for companies based on an industry or keyword.

Example queries:

* AI startups in California
* SaaS companies in fintech
* marketing agencies in New York

Data collected:

* company name
* website
* description

---

### Lead Enrichment

The agent visits company websites and extracts useful context such as:

* company summary
* product or service offering
* potential business pain points

This information is used to personalize outreach messages.

---

### Decision Maker Identification

Attempts to identify relevant contacts such as:

* Founder
* CEO
* Head of Growth
* Marketing Lead

Email addresses can be retrieved using email discovery APIs.

---

### AI Personalized Outreach

Using a language model, the system generates short personalized cold emails that reference information about the company.

Email characteristics:

* under 120 words
* natural tone
* personalized company reference
* non-spammy structure

---

### Email Automation

Generated emails can be sent automatically through Gmail.

Basic tracking includes:

* email sent
* delivery status
* reply status (optional extension)

---

# Architecture

The system is designed as a modular AI agent pipeline.

Agents include:

Lead Discovery Agent
Finds companies using search APIs.

Enrichment Agent
Extracts useful information from company websites.

Contact Discovery Agent
Finds potential decision makers and emails.

Email Generation Agent
Generates personalized outreach using an LLM.

Email Sending Agent
Sends emails using Gmail API.

---

# Tech Stack

Backend

* Python
* FastAPI

AI

* Claude API (Anthropic)

Database

* Supabase (PostgreSQL)

Search

* SerpAPI

Email Discovery

* Hunter API

Email Sending

* Gmail API

Frontend

* Simple dashboard (React / Next.js optional)

---

# Project Structure

```
ai-sales-agent/
│
├── app/
│   ├── agents/
│   │   ├── lead_discovery.py
│   │   ├── enrichment.py
│   │   ├── email_generator.py
│   │   └── email_sender.py
│   │
│   ├── services/
│   │   ├── serpapi_service.py
│   │   ├── hunter_service.py
│   │   └── gmail_service.py
│   │
│   ├── database/
│   │   └── supabase_client.py
│   │
│   └── main.py
│
├── .env.example
├── requirements.txt
└── README.md
```

---

# Environment Variables

Create a `.env` file and configure the following variables:

```
SUPABASE_URL=https://xxxx.supabase.co
SUPABASE_SERVICE_ROLE_KEY=xxxx

ANTHROPIC_API_KEY=sk-ant-xxxx

SERPAPI_KEY=xxxx
HUNTER_API_KEY=xxxx

GMAIL_SENDER_EMAIL=you@domain.com
```

---

# Installation

Clone the repository

```
git clone https://github.com/yourusername/ai-sales-agent.git
cd ai-sales-agent
```

Create a virtual environment

```
python -m venv venv
source venv/bin/activate
```

Install dependencies

```
pip install -r requirements.txt
```

Add your `.env` file with API keys.

---

# Running the Application

Start the FastAPI server

```
uvicorn app.main:app --reload
```

The API will run at:

```
http://localhost:8000
```

---

# Example Workflow

1. User inputs an industry or keyword
2. System searches for relevant companies
3. Agent visits company websites for enrichment
4. AI generates personalized outreach emails
5. Emails can be reviewed or sent automatically

---

# Future Improvements

Planned enhancements include:

* CRM integrations (HubSpot / Salesforce)
* email open and reply tracking
* meeting scheduling
* lead scoring
* LinkedIn enrichment
* automated follow-up sequences

---

# Disclaimer

This project is intended for educational and experimental purposes. Users should ensure compliance with email marketing regulations and anti-spam laws when sending automated outreach.

---

# License

MIT License
