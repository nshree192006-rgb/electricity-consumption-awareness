# ⚡ EnergyAI — AI Agent for Electricity Consumption Awareness

> **IBM Hackathon — Problem Statement #20**
> Built with IBM Langflow · IBM Granite (watsonx.ai) · React · Tailwind CSS

---

## 🎯 Overview

EnergyAI is a conversational AI Agent that helps households understand their electricity consumption patterns, identify high-usage appliances, and adopt energy-efficient behaviours.

| Feature | Description |
|---|---|
| 📊 Dashboard | Real-time overview with charts and appliance breakdown |
| 🧮 Calculator | Interactive appliance kWh & bill calculator |
| 🤖 AI Agent | Chat with IBM Granite-powered energy advisor |
| 💡 Tips | 20+ categorised, expandable energy-saving tips |

---

## 🚀 Quick Start

### 1. Install dependencies
```bash
cd electricity-ai-agent
npm install
```

### 2. Configure environment
```bash
cp .env.example .env
# Edit .env with your Langflow URL and Flow ID
```

### 3. Start the app
```bash
npm run dev
# Opens at http://localhost:5173
```

> **No Langflow yet?** Enable **Demo Mode** in the chat page to explore with built-in smart responses.

---

## 🔧 IBM Langflow Setup

### Step 1 — Install & Run Langflow
```bash
pip install langflow
langflow run
# Opens at http://localhost:7860
```

### Step 2 — Import the flow
1. Open Langflow → click **Import**
2. Upload `langflow/electricity_agent_flow.json`
3. Configure the **IBM watsonx** component:
   - API Key: your `WATSONX_API_KEY`
   - Project ID: your `WATSONX_PROJECT_ID`
   - Model: `ibm/granite-3-8b-instruct`
4. Click **Deploy** and copy the **Flow ID**

### Step 3 — Update .env
```env
VITE_LANGFLOW_BASE_URL=http://localhost:7860
VITE_FLOW_ID=<paste your flow id here>
```

---

## 🏗️ Project Structure

```
electricity-ai-agent/
├── src/
│   ├── api/
│   │   └── langflowClient.js     # Langflow REST API client
│   ├── components/
│   │   ├── Navbar.jsx             # Responsive navigation
│   │   ├── Dashboard.jsx          # Stats, charts, appliance table
│   │   ├── ApplianceForm.jsx      # Interactive kWh calculator
│   │   ├── ChatInterface.jsx      # AI chat with typing animation
│   │   └── TipsPanel.jsx          # Energy tips with categories
│   ├── utils/
│   │   └── electricityCalculator.js  # Calculation utilities
│   ├── App.jsx                    # Router setup
│   ├── main.jsx
│   └── index.css                  # Global styles + dark theme
├── langflow/
│   └── electricity_agent_flow.json   # Langflow flow export
├── .env.example
└── README.md
```

---

## 🤖 AI Agent System Prompt

The Langflow flow uses the following system prompt for the IBM Granite model:

```
You are an intelligent Energy Advisor AI Agent. Your role is to:
1. Analyze household appliance usage data provided by the user.
2. Identify appliances or habits that cause high electricity consumption.
3. Educate users with simple, friendly explanations about how their activities impact electricity bills.
4. Provide 3-5 specific, practical energy-saving tips tailored to the user's situation.
5. Answer follow-up questions about electricity usage, tariffs, appliance efficiency, and green energy.

Always respond in a friendly, non-technical tone. Use units (kWh, watts) only when explaining clearly.
If the user provides appliance usage data, calculate estimated monthly consumption and highlight the top energy consumers.
Encourage small behavioral changes that lead to significant savings.
```

---

## 🌐 Environment Variables

| Variable | Required | Description |
|---|---|---|
| `VITE_LANGFLOW_BASE_URL` | ✅ | Langflow server URL (e.g., `http://localhost:7860`) |
| `VITE_FLOW_ID` | ✅ | Flow ID from Langflow dashboard |
| `VITE_LANGFLOW_API_KEY` | ⬜ | API key if Langflow auth is enabled |
| `WATSONX_API_KEY` | ✅ | Set in Langflow component settings |
| `WATSONX_PROJECT_ID` | ✅ | Set in Langflow component settings |

---

## 💬 Sample Questions for the Agent

- *"Which appliance in my house uses the most electricity?"*
- *"How much does running my AC for 8 hours a day cost monthly?"*
- *"Give me 5 tips to reduce my electricity bill by 30%"*
- *"What is the difference between a 1-star and 5-star AC?"*
- *"How does solar net metering work in India?"*
- *"My monthly bill is ₹3,500. Is that normal for a 2BHK?"*

---

## 🛠️ Tech Stack

| Layer | Technology |
|---|---|
| AI Orchestration | IBM Langflow |
| LLM | IBM Granite (`ibm/granite-3-8b-instruct`) via watsonx.ai |
| Frontend | React 19 + Vite 6 |
| Styling | Tailwind CSS v4 |
| Charts | Recharts |
| Icons | Lucide React |
| Routing | React Router v7 |

---

## 📄 License

MIT — IBM Hackathon Project
