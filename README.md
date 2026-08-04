# ⚡ n8n AI Workflows & Automation Hub

A curated repository of production-ready, AI-powered n8n workflows.

---

## 🎥 Workflow Demo

<video src="assets/Job_Scrapper.mp4" controls="controls" width="100%" style="max-height: 500px;">
  Your browser does not support the video tag. <a href="assets/Job_Scrapper.mp4">Download or view demo video</a>.
</video>

*Above: Live execution demonstration of an automated n8n workflow.*

---

## 🚀 Workflows

- **[job-scrapper](job-scrapper/README.md)**: Parses candidate CVs using Google Gemini AI, searches job boards concurrently via Tavily & Firecrawl, and delivers matched positions to Telegram.

---

## 📁 Repository Structure

```
.
├── assets/
│   └── Job_Scrapper.mp4          # Demo media assets
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
