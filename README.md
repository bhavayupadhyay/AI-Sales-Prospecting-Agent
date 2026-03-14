# CCR - AI Sales Prospecting Agent

An AI-powered sales prospecting agent that automatically discovers potential customers, researches them, and generates personalized outreach emails. Built to automate the early stages of the sales pipeline that usually require hours of manual work from sales teams.

## What It Does

The system performs five core tasks in an automated pipeline:

**1. Lead Discovery**
Searches the web for companies matching a specific industry or keyword (e.g., "AI startups in California"). Collects company names, websites, and descriptions.

**2. Lead Enrichment**
Visits discovered company websites and gathers context about the business -- what they do, their scale, and potential pain points.

**3. Decision Maker Identification**
Identifies relevant contacts (founders, CEOs, heads of growth) and finds their professional information and email addresses.

**4. AI Personalized Outreach**
Uses an LLM to generate short, personalized cold emails that reference specific details about each company and how the product could help them.

**5. Email Automation**
Sends generated emails through Gmail and tracks basic delivery status.

## Why This Exists

Sales prospecting is one of the most time-consuming parts of building a pipeline. This project combines web search, data enrichment, and AI-generated outreach into a single automated workflow. Instead of manually researching companies and writing emails one by one, users can generate qualified leads and outreach messages automatically.

## Who It's For

- Startup founders doing outbound sales
- Small sales teams without dedicated SDRs
- Marketing agencies running outreach campaigns
- B2B SaaS companies scaling their pipeline

## Tech Stack

| Layer | Technology |
|-------|-----------|
| Backend | Python + FastAPI |
| Database | Supabase |
| AI/LLM | Anthropic (Claude) |
| Web Search | SerpAPI |
| Email Discovery | Hunter API |
| Email Sending | Gmail API |
| Frontend | Next.js (React) |

## Project Structure

```
CCR/
├── frontend/                # Next.js frontend application
│   ├── src/
│   │   ├── app/
│   │   │   ├── dashboard/   # Main dashboard view
│   │   │   ├── export/      # Lead export functionality
│   │   │   ├── jobs/        # Prospecting job management
│   │   │   │   └── new/     # Create new prospecting job
│   │   │   └── leads/       # Lead detail views
│   │   │       └── [id]/    # Individual lead page
│   │   ├── components/      # Shared UI components
│   │   ├── lib/             # Utility functions and API clients
│   │   └── types/           # TypeScript type definitions
│   └── public/              # Static assets
├── tools/                   # AI agent tools (search, enrich, email)
├── workflows/               # Orchestration workflows
├── .env                     # Environment variables (not committed)
└── .gitignore
```

## Getting Started

### Prerequisites

- Python 3.10+
- Node.js 18+
- A Supabase project
- API keys for: Anthropic, SerpAPI, Hunter, Gmail

### Setup

1. **Clone the repo**
   ```bash
   git clone https://github.com/YOUR_USERNAME/CCR.git
   cd CCR
   ```

2. **Set up the Python backend**
   ```bash
   python -m venv .venv
   source .venv/bin/activate
   pip install -r requirements.txt
   ```

3. **Set up the frontend**
   ```bash
   cd frontend
   npm install
   ```

4. **Configure environment variables**
   ```bash
   cp .env.example .env
   ```
   Then fill in your API keys:
   ```
   ANTHROPIC_API_KEY=your_key_here
   SERPAPI_KEY=your_key_here
   HUNTER_API_KEY=your_key_here
   GOOGLE_SHEET_ID=your_sheet_id
   SUPABASE_URL=your_supabase_url
   SUPABASE_KEY=your_supabase_key
   ```

5. **Run the backend**
   ```bash
   uvicorn main:app --reload
   ```

6. **Run the frontend**
   ```bash
   cd frontend
   npm run dev
   ```

## Current Status

This project is in early development. The core architecture and project structure are in place. Active development is underway on the backend pipeline and frontend dashboard.

## License

MIT
