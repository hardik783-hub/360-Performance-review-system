# 360-Degree Performance Review & OKR Tracking System

## Overview

The **360-Degree Performance Review & OKR Tracking System** is a cloud-native employee performance management platform built on **AWS Serverless Services**. The system enables organizations to conduct structured employee performance reviews, collect feedback from multiple stakeholders, track Objectives and Key Results (OKRs), and generate performance reports.

The platform replaces traditional manual review processes with an automated, scalable, and data-driven workflow.

---

## Key Features

### Performance Review Management

* Self Reviews
* Peer Reviews
* Manager Reviews
* Anonymous Peer Feedback
* Review Cycle Management

### OKR Tracking

* Create and track Objectives & Key Results
* Employee-level OKR monitoring
* Progress visualization

### HR Analytics Dashboard

* Workforce performance insights
* Review completion tracking
* Average rating analysis
* Top performer identification

### Automated Reporting

* Performance report generation
* HTML report publishing to Amazon S3
* HR access to employee reports

### Workflow Automation

* Automated review reminders
* Review status monitoring
* Performance report generation workflow
* Event-driven notifications

---

# System Architecture

Frontend (Next.js + TypeScript)

↓

Amazon API Gateway

↓

AWS Lambda Functions

↓

Amazon DynamoDB

↓

Amazon S3 (Reports)

↓

Amazon SES (Email Notifications)

↓

Amazon EventBridge

↓

AWS Step Functions

---

## Technology Stack

### Frontend

* Next.js 15
* React
* TypeScript
* Tailwind CSS
* Recharts

### Backend

* AWS Lambda
* Amazon API Gateway
* Amazon DynamoDB

### AWS Services

* Amazon Cognito (Authentication)
* Amazon SES (Email Notifications)
* Amazon S3 (Report Storage)
* Amazon EventBridge (Scheduled Jobs)
* AWS Step Functions (Workflow Orchestration)

---

# User Roles

## Employee

* Submit Self Reviews
* Submit Peer Reviews
* Track OKRs
* View Assigned Review Cycles

## Manager

* Submit Manager Reviews
* Evaluate Employee Performance
* Provide Feedback and Ratings

## HR

* Create Review Cycles
* Monitor Review Progress
* View Analytics Dashboard
* Access Employee Reports

---

# Project Workflow

## 1. HR Creates Review Cycle

HR creates a review cycle by specifying:

* Cycle Name
* Start Date
* End Date
* Employee List

The system stores the cycle in DynamoDB and sends review notifications.

---

## 2. Review Submission

Employees participate in the review process through:

### Self Review

Employees evaluate their own performance.

### Peer Review

Employees provide feedback to colleagues.

### Manager Review

Managers assess employee performance across multiple categories.

---

## 3. Workflow Automation

AWS Step Functions monitor review completion.

The workflow:

* Checks review status
* Determines completion state
* Sends reminder emails when reviews are pending
* Generates reports when reviews are completed

---

## 4. Report Generation

After completion:

* Performance scores are aggregated
* Reports are generated
* HTML reports are uploaded to Amazon S3
* HR can access reports through the dashboard

---

# AWS Resources Used

## DynamoDB Tables

### Reviews

Stores:

* Self Reviews
* Peer Reviews
* Manager Reviews

### ReviewCycles

Stores:

* Cycle Information
* Assigned Employees
* Status Tracking

### OKRs

Stores:

* Employee Objectives
* Key Results
* Progress Data

---

## Lambda Functions

### Review Management

* submitSelfReview
* submitPeerReview
* submitManagerReview

### Cycle Management

* createReviewCycle
* getCycles

### Reporting

* generatePerformanceReport
* generateAndUploadReport

### Workflow

* getReviewStatus
* sendReviewReminders

---

## API Endpoints

### Reviews

POST /reviews/self

POST /reviews/peer

POST /reviews/manager

---

### Review Cycles

POST /cycles

GET /cycles

---

### Reports

GET /reports/{employeeId}

GET /report-html/{employeeId}

---

### Workflow

GET /review/status/{employeeId}

---

# Authentication

The application uses **Amazon Cognito** for authentication and role-based access control.

Supported Roles:

* Employee
* Manager
* HR

Authentication Features:

* Secure Login
* Session Management
* Role-Based Dashboard Access
* Logout Support

---

# Setup Instructions

## Clone Repository

```bash
git clone <repository-url>
cd performance-review-system
```

## Install Dependencies

```bash
npm install
```

## Configure Environment Variables

Create a `.env.local` file:

```env
NEXT_PUBLIC_API_URL=<api-gateway-url>

COGNITO_DOMAIN=<cognito-domain>
COGNITO_USER_POOL_ID=<user-pool-id>
COGNITO_CLIENT_ID=<client-id>
COGNITO_CLIENT_SECRET=<client-secret>

AUTH_SESSION_SECRET=<generated-secret>
```

## Start Development Server

```bash
npm run dev
```

Application URL:

```text
http://localhost:3000
```

---

# Future Enhancements

* Multi-level approval workflows
* AI-generated performance insights
* Advanced analytics dashboards
* PDF report generation
* Real-time notifications
* Department-level reporting
* Automated cycle completion
* Fine-grained RBAC

---

# Learning Outcomes

This project demonstrates:

* Serverless Application Development
* AWS Cloud Architecture
* Workflow Automation
* Authentication & Authorization
* Event-Driven Systems
* Full Stack Development
* Cloud-Native Design Patterns

---

# Author

Internship Project

**360-Degree Performance Review & OKR Tracking System**

Built using AWS Serverless Technologies, Next.js, TypeScript, and DynamoDB.
