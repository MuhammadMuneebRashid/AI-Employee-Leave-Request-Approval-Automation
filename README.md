# AI Employee Leave Request & Approval Automation

An AI-powered **Employee Leave Request & Approval Automation** built with **n8n, Google Gemini AI, Google Sheets, and Gmail**.

This workflow automates the employee leave management process from receiving a leave request to validating the request, detecting conflicts, storing approved leave records, and sending automated approval or rejection emails.

## 🚀 Features

* Employee leave request submission through a webhook
* Automatic extraction of employee leave information
* AI-powered leave request analysis
* Structured leave data processing
* Leave date validation
* Automatic leave-day calculation
* Employee-specific leave conflict detection
* Overlapping date detection
* Google Sheets integration for leave records
* Automated leave approval emails
* Automated leave rejection emails
* AI-generated email responses

## 🔄 Workflow

```text
Employee Leave Request
        ↓
      Webhook
        ↓
 Extract Leave Information
        ↓
    Gemini AI Analysis
        ↓
 Structured Leave Data
        ↓
 Retrieve Existing Leaves
        ↓
 Validate Leave Request
        ↓
 Detect Date Conflicts
        ↓
      IF Condition
       ↙       ↘
   Valid        Invalid
     ↓             ↓
Save to Sheet   Rejection Email
     ↓
Approval Email
```

## 🧩 How It Works

### 1. Receive Leave Request

The workflow starts with a POST webhook that receives employee leave request data.

### 2. Extract Employee Information

JavaScript extracts the employee's:

* Full Name
* Email
* Leave Type
* Start Date
* End Date
* Reason for Leave

The extracted information is converted into structured data for further processing.

### 3. AI-Powered Analysis

Google Gemini AI analyzes the submitted leave information and returns structured output containing the employee and leave details.

### 4. Check Existing Leave Records

Existing leave records are retrieved from Google Sheets before processing the new request.

### 5. Validate Leave Request

The workflow validates:

* Start and end dates
* Date order
* Number of leave days
* Employee email
* Existing leave periods
* Overlapping leave dates

If the same employee already has leave covering the requested dates, the request is marked as a conflict.

### 6. Approval or Rejection

An IF condition checks whether the request is valid.

**If valid:**

* The leave request is stored in Google Sheets.
* An approval email is automatically generated and sent to the employee.

**If invalid:**

* A rejection email is automatically generated.
* The employee receives the rejection notification.

## 🛠️ Technologies Used

* **n8n** — Workflow automation
* **Google Gemini AI** — AI analysis and email generation
* **JavaScript** — Data processing and validation
* **Google Sheets** — Leave record management
* **Gmail** — Automated email notifications
* **Webhook** — Leave request intake

## 📋 Leave Request Information

The automation processes:

```text
Name
Email
Leave Type
Start Date
End Date
Reason for Leave
```

## 📊 Leave Conflict Detection

The system checks whether the employee already has an existing leave that overlaps with the requested dates.

For example:

```text
Existing Leave:
25-08-2026 → 27-08-2026

New Request:
25-08-2026 → 25-08-2026

Result:
❌ Leave Conflict Detected
```

The same employee cannot submit an overlapping leave request.

## 📧 Automated Email Notifications

### Approval Email

For valid requests, the workflow generates an AI-powered approval email containing the relevant leave information and sends it automatically to the employee.

### Rejection Email

For conflicting or invalid requests, the workflow generates a rejection email explaining the reason for rejection and sends it to the employee.

## 🎯 Benefits

* Reduces manual HR work
* Automates repetitive leave-processing tasks
* Prevents overlapping leave requests
* Maintains centralized leave records
* Provides faster employee communication
* Uses AI for intelligent data analysis and email generation
* Creates a consistent leave approval process

## 🔮 Future Improvements

The automation can be extended with:

* Manager approval
* Leave balance tracking
* Public holiday detection
* Weekend handling
* Employee leave history
* Calendar integration
* Slack or Microsoft Teams notifications
* HR dashboard
* Department-based approval rules

## 📌 Project Overview

**AI Employee Leave Request & Approval Automation** demonstrates how AI and workflow automation can be combined to create a practical HR solution.

By connecting **n8n, Google Gemini AI, Google Sheets, and Gmail**, the system provides an automated workflow for processing, validating, approving, rejecting, and communicating employee leave requests.

---

**Built with n8n + Google Gemini AI + Google Sheets + Gmail**
