# ⚡ n8n AI Workflows & Automation Hub

A curated repository of production-ready, AI-powered n8n workflows.

---

## 🎥 Workflow Demo

![Workflow Demo](assets/Job_Scrapper-video.gif)

*Above: Live execution demonstration of an automated n8n workflow.

---

## 🚀 Workflows

- **[job-scrapper](job-scrapper/README.md)**: Parses candidate CVs using Google Gemini AI, searches job boards concurrently via Tavily & Firecrawl, and delivers matched positions to Telegram.

---

## 📁 Repository Structure

```
.
├── assets/
│   ├── Job_Scrapper.gif          # Animated demorecording
├── <workflow-folder>/
│   ├── <workflow-or-agent>.json  # n8n workflow export ready to import
│   └── README.md                 # Setup guide & instructions
└── README.md                     # Main repository documentation
```

---

## 🛠️ Quick Start: Importing Workflows

1. **Clone the repository**:
   ```bash
   git clone <repository-url>
   cd n8n
   ```

2. **Import into n8n**:
   - Open your n8n instance.
   - Go to **Workflows** → **Import from File**.
   - Select the desired workflow `.json` file from its folder.

3. **Configure Credentials & Activate**:
   - Check the `README.md` inside the specific workflow folder for credential setup and usage instructions.
   - Activate the workflow!
