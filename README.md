# 🤖 AI Customer Feedback Analysis & Response Automation

An AI-powered **n8n automation workflow** that collects customer feedback, analyzes it using Google Gemini, detects repeated complaints, stores feedback in Google Sheets, and automatically sends professional email responses to customers and internal teams.

## 🚀 Overview

This workflow automates the complete customer feedback handling process.

When a customer submits feedback through a form, the workflow:

1. Receives the feedback through an **n8n Webhook**.
2. Extracts customer information such as name, email, order ID, feedback, and rating.
3. Uses **Google Gemini AI** to analyze the feedback.
4. Classifies the feedback type and generates a professional summary.
5. Checks previous feedback stored in **Google Sheets**.
6. Detects whether the complaint is repeated.
7. Stores the processed feedback and status in Google Sheets.
8. Sends an internal alert for repeated complaints.
9. Generates a professional customer response using AI.
10. Automatically sends the response to the customer via Gmail.

## ✨ Key Features

* 🔗 Webhook-based feedback collection
* 🤖 AI-powered feedback analysis
* ⭐ Customer rating processing
* 🏷️ Automatic feedback type classification
* 📝 AI-generated professional summaries
* 🔍 Repeated complaint detection
* 📊 Google Sheets data storage
* 🚨 Internal alerts for repeated complaints
* 📧 Automated customer email responses
* ✉️ AI-generated email subjects and messages
* 📦 Structured AI output using JSON schema

## 🔄 Workflow

```text
Customer Feedback Form
        ↓
     Webhook
        ↓
Extract Customer Data
        ↓
   Google Gemini AI
        ↓
Feedback Analysis
        ↓
   Google Sheets
        ↓
Repeated Complaint Check
        ↓
      IF Node
     ↙       ↘
Repeated      New
Complaint    Complaint
   ↓             ↓
Team Alert    Customer Reply
   ↓             ↓
Google Sheets ← Google Sheets
        ↓
      Gmail
```

## 🧠 AI Processing

Google Gemini is used to analyze the submitted feedback and generate structured information:

```json
{
  "name": "",
  "email": "",
  "order_id": "",
  "feedback": "",
  "rating": "",
  "feedback_type": "",
  "summary": ""
}
```

The AI identifies the **feedback type** and creates a concise professional summary that can be used by the support team.

## 🔍 Repeated Complaint Detection

The workflow compares the new feedback with previously stored feedback in Google Sheets.

If matching feedback is found:

```text
Status: Repeated Complaint
isRepeated: true
```

Otherwise:

```text
Status: New Complaint
isRepeated: false
```

The workflow also records the number of previous matches using:

```text
previousMatches
```

## 📧 Automated Email Handling

### For Repeated Complaints

The workflow generates:

* Internal alert subject
* Internal alert message
* Customer email subject
* Customer response

The internal team receives an alert so repeated customer issues can receive additional attention.

### For New Complaints

The workflow generates a professional customer reply based on:

* Customer feedback
* Rating
* Feedback type
* AI-generated summary
* Order ID

The response is then automatically sent through Gmail.

## 🛠️ Technologies Used

* **n8n** — Workflow automation
* **Google Gemini** — AI-powered analysis and response generation
* **Google Sheets** — Feedback storage and historical comparison
* **Gmail** — Automated email communication
* **JavaScript** — Data extraction and complaint detection
* **Webhook** — Form-to-workflow data integration

## 📋 Data Fields

| Field             | Description                                  |
| ----------------- | -------------------------------------------- |
| `name`            | Customer name                                |
| `email`           | Customer email                               |
| `order_id`        | Customer order ID                            |
| `feedback`        | Submitted customer feedback                  |
| `rating`          | Customer rating                              |
| `feedback_type`   | AI-generated feedback category               |
| `summary`         | AI-generated professional summary            |
| `isRepeated`      | Indicates whether feedback is repeated       |
| `previousMatches` | Number of previous matching feedback entries |
| `status`          | New Complaint or Repeated Complaint          |

## ⚙️ Setup

### 1. Import the Workflow

Import the provided JSON workflow into your n8n instance.

### 2. Configure Webhook

Connect your customer feedback form to the n8n webhook using a `POST` request.

### 3. Configure Google Gemini

Add your Google Gemini API credentials to the Gemini Chat Model nodes.

### 4. Configure Google Sheets

Create a Google Sheet containing columns for:

```text
name
email
order_id
feedback
rating
feedback_type
summary
isRepeated
previousMatches
status
```

Connect your Google Sheets credentials in n8n.

### 5. Configure Gmail

Connect your Gmail account to the Gmail nodes and configure the internal team recipient.

### 6. Activate the Workflow

After testing the workflow successfully, activate it and start receiving customer feedback automatically.

## 🎯 Use Cases

This automation can be used for:

* E-commerce customer feedback
* Product reviews
* Customer support systems
* Complaint management
* Order-related feedback
* Customer satisfaction analysis
* Repeated issue detection
* Automated customer service

## 💡 Benefits

* Reduces manual feedback processing
* Saves customer support time
* Identifies recurring complaints
* Maintains organized feedback records
* Provides faster customer responses
* Uses AI to improve communication quality
* Creates a consistent customer support process

## 🔐 Credentials

Before running the workflow, configure your own:

* Google Gemini API credentials
* Google Sheets OAuth credentials
* Gmail OAuth credentials

**Do not expose API keys, OAuth credentials, webhook secrets, or other sensitive information in a public repository.**

## 📌 Project Goal

The goal of this project is to demonstrate how **AI + workflow automation** can transform customer feedback management from a manual process into an intelligent, automated support system.

---

⭐ If you find this project useful, consider giving the repository a star!


<img width="1920" height="899" alt="542890" src="https://github.com/user-attachments/assets/46bb9c33-a03b-4a99-95c7-992d25f27fb3" />
<img width="1920" height="906" alt="567890" src="https://github.com/user-attachments/assets/4ab3727e-24e3-496b-b7ed-adf1ea49572c" />


