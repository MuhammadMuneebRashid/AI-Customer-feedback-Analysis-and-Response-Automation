# 🤖 AI Customer Feedback Analysis & Response Automation

An AI-powered **Customer Feedback Analysis and Response Automation** workflow built with **n8n**. The system collects customer feedback, analyzes it using **Google Gemini**, classifies the feedback, determines its priority, stores the results in **Google Sheets**, and automatically sends an appropriate email response.

## 🚀 Overview

This automation is designed to reduce manual customer-support work by automatically processing customer feedback from submission to response.

Customers provide:

* Customer Name
* Email
* Feedback
* Order ID
* Rating

The workflow extracts this information from a webhook submission and sends it to an AI agent for analysis.

## 🔄 Workflow

```text
Customer Feedback Form
        ↓
      Webhook
        ↓
 JavaScript Data Extraction
        ↓
    Google Gemini AI
        ↓
Feedback Classification
        ↓
Priority Detection
        ↓
    Google Sheets
        ↓
   Priority Check
      ↙       ↘
   High      Normal
    ↓          ↓
Alert Email  Normal Response
```

## ✨ Key Features

* 📩 Receives customer feedback through a webhook
* 🔍 Extracts customer and order information automatically
* ⭐ Processes customer ratings
* 🤖 Uses Google Gemini for AI-powered analysis
* 💬 Identifies the type of feedback
* 📊 Determines feedback priority
* 📝 Generates a professional summary
* 📋 Stores analyzed feedback in Google Sheets
* 🚨 Sends an alert for high-priority feedback
* 📧 Automatically responds to customers through Gmail

The AI output is structured into fields including **name, email, feedback, order ID, rating, priority, kind of feedback, and summary**.

## 🧠 AI Analysis

Google Gemini analyzes the submitted feedback and identifies:

* Customer information
* Feedback content
* Rating
* Type of feedback
* Priority
* Professional summary

The workflow then uses the detected priority to decide which response path should be executed.

## 📊 Data Storage

Analyzed feedback is stored in **Google Sheets** for centralized record keeping and future review.

The stored information includes:

* Name
* Email
* Feedback
* Order ID
* Rating
* Priority
* Kind of feedback
* Summary

## 📧 Automated Email Responses

The workflow has two response paths:

### 🚨 High-Priority Feedback

When feedback is classified as **High priority**, the workflow generates an alert response and sends it to the configured notification email.

### 💬 Normal Feedback

For feedback that does not have high priority, the workflow generates a normal professional response and sends it directly to the customer.

## 🛠️ Technologies Used

* **n8n** — Workflow automation
* **Google Gemini** — AI-powered feedback analysis
* **JavaScript** — Data extraction and processing
* **Google Sheets** — Feedback storage
* **Gmail** — Automated email communication
* **Tally Forms / Webhook** — Feedback collection

## 🎯 Benefits

This automation can help businesses:

* Reduce manual feedback processing
* Respond to customers faster
* Identify urgent complaints
* Organize customer feedback
* Maintain centralized feedback records
* Improve customer-support workflows
* Automate repetitive communication

## 📌 Use Cases

This workflow can be adapted for:

* E-commerce businesses
* Online stores
* SaaS products
* Customer support teams
* Service businesses
* Product review systems
* Order management systems

## 🔧 Workflow Structure

The main workflow consists of:

1. **Webhook** — Receives customer feedback.
2. **JavaScript Code** — Extracts submitted form fields.
3. **AI Agent** — Analyzes and classifies feedback.
4. **Structured Output Parser** — Produces consistent AI output.
5. **Edit Fields** — Organizes the analyzed data.
6. **Google Sheets** — Stores the feedback analysis.
7. **IF Node** — Checks the feedback priority.
8. **AI Response Agent** — Generates the appropriate response.
9. **Gmail** — Sends the automated email.

The workflow connections implement this processing sequence from webhook through AI analysis, spreadsheet storage, priority routing, and email response.

## 🔐 Credentials

Before running the workflow, configure your own credentials for:

* Google Gemini
* Google Sheets
* Gmail

**Do not commit personal credentials, API keys, or sensitive configuration to GitHub.**

## 📈 Future Improvements

Possible improvements include:

* Slack or Microsoft Teams alerts
* Dashboard for feedback analytics
* Sentiment scoring
* Automatic ticket creation
* CRM integration
* Feedback trend analysis
* Multi-language feedback analysis
* Automatic escalation based on priority

## 👨‍💻 Project

Built as a practical demonstration of combining **AI with workflow automation** to create an intelligent customer-support system.

**n8n + AI + Automation = Smarter Customer Feedback Management**
