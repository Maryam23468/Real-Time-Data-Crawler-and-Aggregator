# 🛰️ Real-Time Data Crawler & Aggregator

Automated n8n workflow to fetch and filter remote job postings every 6 hours, and append relevant results to a connected Google Sheet in real time.

<div align="center">

[![n8n](https://img.shields.io/badge/Built%20With-n8n-1e90ff?style=for-the-badge&logo=n8n&logoColor=white)](https://n8n.io/)
[![Python](https://img.shields.io/badge/Automation-Powered%20by%20AI-blue?style=for-the-badge)](https://github.com/maryamanayatali)

</div>

---

## 🧠 Project Overview

This workflow fetches job postings from [RemoteOK API](https://remoteok.com/api) every 6 hours. It filters the jobs based on custom keywords and automatically appends matching listings to a Google Sheet.

**✨ Demo Video:**
**https://www.loom.com/share/1b4fb1c835554075a4e66707c2121b50?sid=654e2526-c9db-4e17-bb5d-21b863bc76d2**

**✨ Features:**
- Scheduled API polling every 6 hours
- Keyword-based job filtering
- Data extraction with JavaScript code node
- Auto-population to a Google Sheet
- Scalable and customizable with n8n UI

---

## 🔧 Workflow Breakdown

| Step                     | Description |
|--------------------------|-------------|
| 🕑 **Schedule Trigger**  | Executes every 6 hours to initiate the workflow |
| 🌐 **HTTP Request**      | Fetches data from the RemoteOK API |
| 🧪 **Code Node**         | Filters job listings using custom JavaScript (based on keywords like `marketing`, `fintech`, `engineering`, etc.) |
| 📄 **Google Sheets**     | Appends filtered jobs to the linked spreadsheet |

---

## 📝 Sample Code Logic

```javascript
const keywords = ["marketing", "fintech", "growth", "engineering", "analytics"];

return items
  .filter(item => item.json.position && item.json.company)
  .filter(item => {
    const ta
