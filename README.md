# Installation Guide

## Install n8n via npm

### Prerequisites

- Node.js (version 18 or higher recommended)
- npm (comes with Node.js)

### Installation Steps

1. **Install n8n globally** (recommended):

```bash
npm install -g n8n
```

2. **Start n8n**:

```bash
n8n start
```

3. **Access n8n**:

Open your browser and navigate to:

```
http://localhost:5678
```

### Local Installation (Alternative)

If you prefer to install n8n locally in your project:

```bash
npm install n8n
```

Then run it with:

```bash
npx n8n start
```

### Verify Installation

Check if n8n is installed correctly:

```bash
n8n --version
```

## Importing a Flow

All workflows and their usage documentation are organized in separate folders within this repository. Each workflow folder contains:

- **`workflow.json`** - The n8n workflow file
- **`README.md`** - Instructions and details on how to use the workflow

### Quick Start: Import a Workflow

1. **Clone this repository**:

```bash
git clone <repository-url>
cd <repository-name>
```

2. **Start n8n** (if not already running):

```bash
n8n start
```

3. **Open n8n** in your browser:

```
http://localhost:5678
```

4. **Import your desired workflow**:
   - Click the menu icon (☰) in the top-left
   - Select **Workflows**
   - Click the **Import** button
   - Navigate to the workflow folder in the cloned repository
   - Select the **`workflow.json`** file
   - Click **Import**

5. **Read the workflow's README**:
   - Check the workflow folder's **`README.md`** for setup instructions and usage details

### Workflow Folder Structure

```
/repository
├── workflow-1/
│   ├── workflow.json
│   └── README.md
├── workflow-2/
│   ├── workflow.json
│   └── README.md
└── workflow-3/
    ├── workflow.json
    └── README.md
```

Simply clone the repo and choose the workflow you need from the folder structure.

### Additional Resources

- [n8n Official Documentation](https://docs.n8n.io)
- [GitHub Repository](https://github.com/n8n-io/n8n)
- [Community Forum](https://community.n8n.io)

---

**Note**: n8n requires Node.js to run. If you don't have it installed, download it from [nodejs.org](https://nodejs.org).
