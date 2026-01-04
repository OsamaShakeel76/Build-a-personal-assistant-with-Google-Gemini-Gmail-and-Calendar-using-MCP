# 🤖 Personal AI Assistant with Google Gemini, Gmail & Calendar (MCP + n8n)

This project builds a **personal AI assistant** powered by **Google Gemini** and orchestrated with **n8n**, using the **Model Context Protocol (MCP)** to securely interact with **Gmail**, **Google Calendar**, and **Google Sheets (CRM-style contacts)**.

The assistant understands natural language instructions and performs real actions such as drafting emails, managing calendar events, and updating contact data—while maintaining conversational memory.

---

## ✨ Key Capabilities

### 📧 Gmail
- Search inbox for specific emails
- Retrieve recent email threads
- Draft emails for review (no auto-send)
- Extract context from previous conversations

### 📅 Google Calendar
- Create new calendar events
- Find single or multiple events
- Update existing events
- Summarize upcoming meetings

### 📇 Contacts / CRM (Google Sheets)
- Add new contacts
- Find existing contact details
- Update contact information
- Use contact data for email and calendar actions

### 🧠 AI Intelligence
- **Google Gemini 2.5 Pro** for reasoning and planning
- **MCP (Model Context Protocol)** for tool-based execution
- **Conversation memory** for follow-up questions
- Multi-step task execution from a single instruction

---

## 🧠 Architecture Overview

**User Chat → Gemini Agent → MCP Server → Google Tools → Response**

### Core Components
- **Chat Trigger** – Entry point for user messages
- **Gemini Chat Model** – Plans actions and generates responses
- **Personal Assistant Agent** – Decides which tools to call
- **MCP Server Trigger** – Secure execution layer
- **MCP Client** – Connects agent to tool server
- **Google Tools**:
  - Gmail
  - Google Calendar
  - Google Sheets
- **Simple Memory** – Maintains conversation context

---

## 🛠 Technologies Used

- **n8n** – Workflow orchestration
- **Google Gemini 2.5 Pro** – LLM reasoning engine
- **Model Context Protocol (MCP)** – Secure AI tool execution
- **Gmail API** – Email operations
- **Google Calendar API** – Scheduling
- **Google Sheets API** – Lightweight CRM
- **LangChain (n8n-native nodes)** – Agent + memory

---

## 🚀 Setup Instructions

### 1️⃣ Prerequisites
- n8n (self-hosted or cloud)
- Google Cloud project with:
  - Gmail API enabled
  - Google Calendar API enabled
  - Google Sheets API enabled
- Google Gemini API key

---

### 2️⃣ Configure Credentials in n8n
Create and attach the following credentials:
- **Google Gemini (Google AI)** → API Key
- **Google OAuth2** → Gmail, Calendar, Sheets access

---

### 3️⃣ MCP Configuration
1. Copy the **MCP Server Trigger URL**
2. Paste it into the **MCP Client node** (`sseEndpoint`)
3. Ensure all tool nodes are connected to the MCP trigger

---

### 4️⃣ Activate the Workflow
- Enable the workflow
- Open the **Chat UI** from the Chat Trigger
- Start issuing natural language commands

---

## 💬 Example Commands

- “Find my last 5 emails from John and draft a reply apologizing for the delay.”
- “Schedule a meeting with Sarah next Wednesday at 9 AM and send her a reminder.”
- “Update Rick’s email address and company name.”
- “Summarize all my meetings today and draft reminder emails.”

---

## 🔐 Design Principles

- 🔒 Secure tool execution via MCP
- 🧠 LLM decides *what* to do, tools decide *how*
- 📎 Real actions, not mock responses
- 💬 Conversational and memory-aware
- ⚙️ Modular and extensible

---

## ⚠️ Notes & Limitations

- Drafts emails but does not auto-send (safe by design)
- Requires proper Google OAuth permissions
- CRM uses Google Sheets (not a full database)

---

## 🔧 Customization Ideas

- Add Slack, WhatsApp, or Telegram notifications
- Auto-send emails with approval logic
- Replace Sheets with a real CRM
- Add task management (e.g., Google Tasks, Notion)

