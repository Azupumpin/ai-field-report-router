# 🚀 AI-Powered Field Agent Issue Triage & Jira Router

## 📌 Executive Summary
In field-heavy operations, support and ops teams often struggle with high volumes of unstructured reports submitted by field agents. Manually reviewing, categorizing, and logging complaints creates operational bottlenecks, delays bug resolution, and clutters engineering backlogs.

This project is an **event-driven workflow engine** built with **n8n**, **OpenRouter (Gemma 2 27B)**, **Jira Cloud**, and **Google Sheets**. It automatically captures field agent submissions, performs LLM-driven classification and data extraction in real time, and routes technical bugs directly to engineering backlogs while storing operational queries separately.

---

## 🛠️ Tech Stack & Integrations
* **Workflow Automation & Orchestration:** n8n Cloud
* **Trigger Endpoint:** n8n Form Trigger / Production Webhook
* **LLM Engine:** OpenRouter API (`google/gemma-2-27b-it`)
* **Data Transformation:** Custom JavaScript (Node.js) & n8n Switch Node
* **Endpoints:** Jira Software Cloud API & Google Sheets API

---

## 🔄 Workflow Architecture & Logic
```text
[Field Agent Submit Form] 
          │
          ▼
 [AI Assistant Analyzes Text]
          │
    ┌─────┴─────┐
    ▼           ▼
 (It's a Bug)  (It's Operational)
    │           │
    ▼           ▼
 [Create Jira] [Log in Sheet]
