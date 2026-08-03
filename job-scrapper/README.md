# Job Scraper & Matcher Workflow

An automated n8n workflow that parses candidate CV data using Google Gemini, searches for active job postings concurrently across top tech job boards and ATS platforms via **Tavily** and **Firecrawl**, merges the results, and delivers matched positions directly to Telegram.

---

## 🔗 Credentials & External Services Needed

Create accounts and obtain credentials for the following services:

1. **Google Gemini API** (Google AI Studio)
   - Create key: https://aistudio.google.com/app/apikey

2. **Tavily Search API**
   - Create key: https://tavily.com/

3. **Firecrawl API**
   - Create key: https://firecrawl.dev/

4. **Telegram Bot & Chat ID**
   - Create bot: https://t.me/BotFather
   - Note down your bot token and target Chat ID.

---

## ⚡ How It Works

```
                     [Schedule Trigger (09:00 AM) / Manual Execution / Chat Trigger]
                                                    │
                                                    ▼
                                        [CV Profile (JSON Node)]
                                                    │
                                                    ▼
                                  [Google Gemini Agent (LLM Extractor)]
                                Extracts seniority, role & top 2 stack techs
                                                    │
                         ┌──────────────────────────┴──────────────────────────┐
                         ▼                                                     ▼
         [Tavily Deep Search API Engine]                       [Firecrawl Search API Engine]
       (Lever, Greenhouse, Ashby, BuiltIn...)             (WeWorkRemotely, Arc.dev, JustRemote...)
                         │                                                     │
                         └──────────────────────────┬──────────────────────────┘
                                                    ▼
                                              [Merge Node]
                                                    │
                                                    ▼
                                       [JavaScript Formatting Node]
                                                    │
                                                    ▼
                                        [Telegram Bot Notification]
```

1. **CV Processing & Parsing:** Reads structured CV data from the `CV in JSON` node or extracts text from PDF uploads via the Chat Trigger (`Extract from File` + Gemini CV JSON generator).
2. **Query Generation:** Google Gemini analyzes experience and skills to construct an optimized query string following the template `"{seniority} {role} engineer {stack}"` (e.g., `"senior full stack engineer React Node.js"` with seniority mapped to `junior`, `ssr`, `senior`, or `staff`).
3. **Dual Parallel Job Search:**
   - **Tavily Search API:** Executes targeted web searches across ATS platforms (`lever.co`, `greenhouse.io`, `ashbyhq.com`, `builtin.com`, `workable.com`, `wellfound.com`, `linkedin.com`, etc.).
   - **Firecrawl API (`v2/search`):** Concurrently queries remote tech job boards (`weworkremotely.com`, `justremote.co`, `arc.dev`, `gun.io`, `unjobs.org`, etc.).
4. **Result Merging & Formatting:** The `Merge` node combines outputs from both search engines. The `Create Final Message` JavaScript node parses results from both Tavily (`results`) and Firecrawl (`data.web`) into a unified Markdown notification message.
5. **Delivery:** The `Send found jobs` node sends the formatted list directly to your specified Telegram Chat ID.
