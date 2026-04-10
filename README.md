# 📞 ShopTalk AI – Call Summary & Lead Capture

Transforming AI voice conversations into actionable business data. This **n8n workflow** automatically processes calls from **Vapi.ai**, summarizes the conversation for the team, and extracts lead information for the CRM.


<img width="1089" height="485" alt="Screenshot (1404)" src="https://github.com/user-attachments/assets/b024bcff-0836-46ad-a0af-eb9edf082502" />


## 🚀 Overview
When an AI Voice Agent finishes a call, the data often stays trapped in the logs. This automation ensures:
- **Instant Summaries:** Every call is summarized and sent to Slack.
- **Lead Capture:** If a caller shows interest, their details are automatically saved as a lead in Google Sheets.
- **Smart Routing:** Uses logic to distinguish between a general call summary and a high-value sales lead.

## 🛠️ How It Works

### 1. Monitor Vapi Calls (Webhook)
The workflow starts with a Webhook node that listens for "Call Ended" events from **Vapi.ai**. It receives the full transcript and caller data.

### 2. Identify Summary or Leads (Logic)
The **Switch/IF node** analyzes the incoming data. 
- If the data contains a general conversation, it follows the **True** path.
- If the data contains specific contact info or intent, it follows the **False** path (categorized as a Lead).

### 3. Route to Slack
For every call, a formatted summary is sent to a dedicated **Slack channel**, allowing the team to stay updated without listening to hours of recordings.

### 4. Append to Google Sheets
High-value leads are automatically appended to a **Google Sheet**, serving as a lightweight CRM for the sales team to follow up.

## ✨ Key Features
- **Real-time Processing:** No delay between call end and data logging.
- **Automated CRM:** Eliminates manual data entry for sales leads.
- **Team Transparency:** Keeps everyone in the loop via Slack.

## 💻 Tech Stack
- **n8n:** Workflow orchestration.
- **Vapi.ai:** AI Voice Agent platform.
- **Slack API:** For instant team notifications.
- **Google Sheets API:** For structured lead storage.

---

## 🚀 Setup Instructions
1. **Import:** Copy the `.json` workflow file into your n8n instance.
2. **Webhook URL:** Copy the Webhook URL from the first node and paste it into your Vapi.ai dashboard under "Webhooks."
3. **Connect Apps:** 
   - Authenticate your **Slack** workspace.
   - Connect your **Google account** and select the target sheet.
4. **Deploy:** Hit 'Execute' and watch your leads populate automatically.

---
**Empowering sales teams with AI Automation.**
