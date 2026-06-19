# 🚀 PerformAI – 360° Performance Review & OKR Tracking System

<div align="center">

![Next.js](https://img.shields.io/badge/Next.js-15-black?style=for-the-badge&logo=next.js)
![TypeScript](https://img.shields.io/badge/TypeScript-3178C6?style=for-the-badge&logo=typescript)
![AWS](https://img.shields.io/badge/AWS-Serverless-FF9900?style=for-the-badge&logo=amazonaws)
![DynamoDB](https://img.shields.io/badge/DynamoDB-4053D6?style=for-the-badge&logo=amazondynamodb)
![S3](https://img.shields.io/badge/Amazon_S3-569A31?style=for-the-badge&logo=amazons3)
![SES](https://img.shields.io/badge/Amazon_SES-232F3E?style=for-the-badge&logo=amazonaws)
![Cognito](https://img.shields.io/badge/Amazon_Cognito-FF9900?style=for-the-badge&logo=amazonaws)

### Cloud-Native Employee Performance Management Platform

</div>

---

## 📌 Overview

PerformAI is a cloud-native **360-Degree Performance Review & OKR Tracking System** built using AWS Serverless technologies and Next.js.

The platform enables organizations to conduct structured employee performance reviews through Self Reviews, Peer Reviews, and Manager Reviews while tracking Objectives & Key Results (OKRs), generating performance reports, and providing HR teams with actionable workforce insights.

---

## ✨ Features

### 👨‍💼 Employee Portal

- Submit Self Reviews
- Submit Peer Reviews
- Track OKRs
- View Assigned Review Cycles

### 👨‍💻 Manager Portal

- Submit Manager Reviews
- Evaluate Employee Performance
- Leadership Assessment
- Communication Assessment
- Technical Skill Assessment

### 🏢 HR Dashboard

- Create Review Cycles
- Monitor Review Progress
- Workforce Analytics
- View Employee Reports
- Track Performance Metrics

### 📊 Analytics & Reporting

- Performance Reports
- Employee Ratings Analysis
- Top Performer Identification
- Review Completion Tracking

### 📧 Workflow Automation

- Automated Review Notifications
- Reminder Emails using Amazon SES
- Event-Based Scheduling
- Step Functions Workflow Orchestration

---

## 🏗️ Architecture

```text
Frontend (Next.js)
        │
        ▼
Amazon API Gateway
        │
        ▼
AWS Lambda Functions
        │
 ┌──────┼─────────┬─────────┬────────┐
 ▼      ▼         ▼         ▼        ▼

DynamoDB  S3    SES   EventBridge Step Functions
   │       │      │        │          │
   ▼       ▼      ▼        ▼          ▼

Reviews  Reports Email  Scheduling Workflow
Cycles   Storage Notifications Automation
OKRs
```

---

## 🛠️ Tech Stack

### Frontend

- Next.js 15
- React
- TypeScript
- Tailwind CSS

### Backend

- AWS Lambda
- Amazon API Gateway

### Database

- Amazon DynamoDB

### Authentication

- Amazon Cognito

### Storage

- Amazon S3

### Notifications

- Amazon SES

### Workflow Automation

- Amazon EventBridge
- AWS Step Functions

---

## 📂 Project Structure

```bash
PerformAI/
│
├── src/
│   ├── app/
│   │   ├── employee/
│   │   ├── hr/
│   │   ├── reviews/
│   │   ├── api/
│   │
│   ├── components/
│   │   ├── dashboard/
│   │   ├── forms/
│   │   ├── layouts/
│   │
│   ├── services/
│   ├── context/
│   ├── lib/
│   └── types/
│
├── backend/
│   ├── lambdas/
│   ├── step-functions/
│
├── public/
│
└── README.md
```

---

## 🔄 Workflow

### 1️⃣ Create Review Cycle

```text
HR Creates Review Cycle
        ↓
Assign Employees
        ↓
Store in DynamoDB
        ↓
Send Email Notifications
```

### 2️⃣ Submit Reviews

```text
Self Review
      ↓
Peer Review
      ↓
Manager Review
      ↓
Store in DynamoDB
```

### 3️⃣ Workflow Automation

```text
Review Status Check
         ↓
Step Functions
         ↓
Cycle Monitoring
         ↓
Generate Reports
```

### 4️⃣ Report Generation

```text
Collect Reviews
       ↓
Calculate Ratings
       ↓
Generate Report
       ↓
Upload to Amazon S3
       ↓
HR Access Dashboard
```

---

## 📊 AWS Services Used

| Service | Purpose |
|----------|----------|
| AWS Lambda | Backend Business Logic |
| API Gateway | REST APIs |
| DynamoDB | Data Storage |
| Cognito | Authentication |
| SES | Email Notifications |
| EventBridge | Scheduling & Reminders |
| Step Functions | Workflow Automation |
| S3 | Report Storage |

---

## 📦 DynamoDB Tables

### Reviews

Stores:

- Self Reviews
- Peer Reviews
- Manager Reviews

### ReviewCycles

Stores:

- Cycle Information
- Employee Assignments
- Review Status

### OKRs

Stores:

- Objectives
- Key Results
- Progress Tracking

---

## 🚀 Getting Started

### Clone Repository

```bash
git clone https://github.com/yourusername/performai.git
cd performai
```

### Install Dependencies

```bash
npm install
```

### Configure Environment Variables

Create a `.env.local` file:

```env
NEXT_PUBLIC_API_URL=

COGNITO_DOMAIN=
COGNITO_USER_POOL_ID=
COGNITO_CLIENT_ID=
COGNITO_CLIENT_SECRET=

AUTH_SESSION_SECRET=
```

### Run Development Server

```bash
npm run dev
```

Open:

```text
http://localhost:3000
```

---

## 🌟 Future Enhancements

- AI Performance Insights
- Sentiment Analysis
- PDF Report Generation
- Department-Level Analytics
- Slack Integration
- Mobile Application
- Automated Cycle Completion

---

## 📈 Learning Outcomes

- AWS Lambda
- API Gateway
- DynamoDB
- Cognito
- SES
- EventBridge
- Step Functions
- S3
- Next.js
- TypeScript
- Serverless Architecture

---

## 👨‍💻 Team PerformAI

360° Performance Review & OKR Tracking System

Built using AWS Serverless Technologies, Next.js, TypeScript, DynamoDB, Cognito, SES, S3, EventBridge, and Step Functions.

---

## ⭐ Support

If you found this project useful, consider giving it a star ⭐ on GitHub.
