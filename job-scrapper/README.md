# Job Scraper & Matcher Workflow

An automated n8n workflow that parses candidate CV data using Google Gemini, searches for active job postings across top ATS platforms via Tavily, and delivers matched positions directly to Telegram.

---

## 🔗 Credentials & External Services Needed

Create accounts and obtain credentials for the following services:

1. **Google Gemini API** (Google AI Studio)
   - Create key: https://aistudio.google.com/app/apikey

2. **Tavily Search API**
   - Create key: https://tavily.com/

3. **Telegram Bot & Chat ID**
   - Create bot: https://t.me/BotFather

---

## ⚡ How It Works

```
[Schedule Trigger (09:00 AM) / Manual Execution]
                        │
                        ▼
            [CV Profile (JSON Node)]
                        │
                        ▼
      [Google Gemini Agent (LLM Extractor)]
    Extracts seniority, stack & search query
                        │
                        ▼
      [Tavily Deep Search API Engine]
    Searches Lever, Greenhouse, Ashby, etc.
                        │
                        ▼
         [JavaScript Formatting Node]
                        │
                        ▼
           [Telegram Bot Notification]
```

1. **CV Processing:** Reads the structured CV profile in the `CV in JSON` node (or processes PDF uploads via the chat trigger flow).
2. **Query Generation:** Google Gemini analyzes the experience and stack to produce an optimized search string (e.g., `"senior fullstack engineer React Node.js TypeScript remote contract LATAM"`).
3. **Job Search:** Tavily executes a targeted search across specified job domains (`lever.co`, `greenhouse.io`, `ashbyhq.com`, `linkedin.com`, etc.) for postings published in the last 24 hours.
4. **Delivery:** The workflow formats the matching opportunities and sends a Telegram message with direct application links.
