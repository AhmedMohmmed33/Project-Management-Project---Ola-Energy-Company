# OLA Energy Project Management Platform

> End-to-End Project Portfolio Management Solution built using Microsoft Power Platform.

---

## Overview

This project was developed for OLA Energy to centralize project management, streamline data collection, automate document handling, and provide executive-level visibility into project financial and timeline performance.

The solution combines multiple Microsoft technologies into a single ecosystem:

- Power Apps
- Power Automate
- SharePoint Online
- Power BI
- Power Query (M)
- DAX

The objective was to transform scattered project information into a centralized platform that supports project execution, financial control, delivery monitoring, and executive decision-making.

---

## Platform Flow

Power Apps → SharePoint → Power Automate → Power BI

The architecture enables:

- Controlled project data entry
- Role-based access management
- Automated document processing
- Financial monitoring
- Timeline monitoring
- Executive reporting

---

## Technology Stack

| Technology        | Purpose                 |
| ----------------- | ----------------------- |
| Power Apps        | Project Data Management |
| SharePoint Online | Data Storage            |
| Power Automate    | Workflow Automation     |
| Power BI          | Analytics & Reporting   |
| Power Query       | Data Transformation     |
| DAX               | Business Logic & KPIs   |

---

## Stage 1 — Power Apps Application

![Power Apps Application](assets/app.png)

The first stage focused on building a centralized project management application.

The application allows project stakeholders to create, manage, and update project information through a controlled interface.

### User Roles

#### Admin
- Create new projects
- Edit all projects
- Maintain master data
- Control sensitive fields
- Manage all countries

#### Manager
- View projects assigned to their country
- Update project information
- Monitor project progress

### Key Features
- Project Search
- Project Update Form
- Controlled Permissions
- Role-Based Security
- SharePoint Integration

### Business Value

The application ensures data consistency, improves governance, and reduces manual project tracking activities.

---

## Stage 2 — Power Automate Workflow

![Power Automate Flow](assets/flow.png)

A major challenge appeared during report deployment related to project images.

Initially, project images were uploaded from Power Apps and stored as SharePoint List Attachments.

This approach created limitations when publishing reports to Power BI Service and affected image accessibility.

### Challenge
- Images stored as SharePoint Attachments
- Dynamic image references
- Reporting limitations in Power BI Service
- Refresh and accessibility issues

### Solution

A Power Automate workflow was developed to:

1. Receive image from Power Apps
2. Save image inside SharePoint Document Library
3. Generate permanent image URL
4. Update project record automatically
5. Provide Power BI with a stable image source

### Business Value

The solution created a reliable image management process while ensuring stable reporting and refresh operations inside Power BI Service.

---

## Stage 3 — Power BI Dashboard

The dashboard was designed as one integrated reporting stage, and it contains five pages:

- Cover
- Executive Summary
- Financial
- Timeline
- Details

---

### 3.1 Cover

![Cover](assets/cover.png)

---

### 3.2 Executive Summary

![Executive Summary Dashboard](assets/summary.png)

The Executive Summary page provides leadership with a high-level overview of the project portfolio.

#### Key KPIs
- Total Projects
- Total Budget
- Total Spend
- Total Committed
- Completion %
- On-Time Delivery %
- Delayed Projects
- Total Forecasted

#### Key Insights
- Overall portfolio health
- Financial performance
- Delivery performance
- Project execution status

#### Business Value

Allows executives to quickly assess portfolio performance and identify areas requiring attention.

---

### 3.3 Financial Dashboard

![Financial Dashboard](assets/financial.png)

The Financial Dashboard focuses on budget control and financial performance monitoring.

#### Key KPIs
- Total Budget
- Total Spend
- Total Committed
- Total Forecasted
- Burn Rate
- Commitment Ratio
- Spend-to-Forecast Index
- Forecast Overrun

#### Business Questions Answered
- Are projects staying within budget?
- Which areas consume the highest spending?
- How much budget is already committed?
- Are forecasts exceeding approved budgets?

#### Business Value

Provides complete financial transparency across the project portfolio and supports better budget planning.

---

### 3.4 Timeline Dashboard

![Timeline Dashboard](assets/timeline.png)

The Timeline Dashboard tracks project execution and delivery performance.

#### Key KPIs
- Total Projects
- Delayed Projects
- Average Delay Days
- Average Start Delay Days
- On-Time Delivery %
- Completion %
- DCF %
- Not Started (Overdue Start)

#### Business Questions Answered
- Which projects are delayed?
- How severe are the delays?
- Are projects starting on time?
- Which business areas face delivery risks?

#### Business Value

Provides visibility into project execution and enables early identification of schedule risks.

---

### 3.5 Project Details Page

![Project Details Dashboard](assets/details.png)

The Details page provides a complete project-level view.

#### Available Information

##### General Information
- Project Name
- Project Reference
- Country
- Business Group
- Business Area
- Status

##### Timeline Information
- Planned Start Date
- Actual Start Date
- Planned End Date
- Actual End Date
- Delay Metrics

##### Financial Information
- Budget
- Additional Budget
- Total Budget
- Spend
- Forecast
- Commitments
- Overrun %

##### Supporting Information
- Project Comments
- Project Reasons
- Project Images

#### Business Value

Allows stakeholders to investigate any project without leaving the reporting environment.

---

## Live Dashboard

🔗 [Live Dashboard Demo](https://app.powerbi.com/view?r=eyJrIjoiYjk0NmRkOGQtMmNlMC00NWE2LWI5NjktNjE4OGNmZmU2ZmQ0IiwidCI6IjJiYjZlNWJjLWMxMDktNDdmYi05NDMzLWMxYzZmNGZhMzNmZiIsImMiOjl9)  
> Demo version contains sample data only.

---

## LinkedIn Post

🔗 [LinkedIn Post / Project Story](https://www.linkedin.com/posts/ahmed-mohammed-112637344_powerbi-powerapps-powerautomate-activity-7474162056628256768-F1Ph?utm_source=share&utm_medium=member_desktop&rcm=ACoAAFY8Kt4B8mfQYZGbZXdUEFZW3-u1Vlm_8sk)

---

## Technical Challenges & Solutions

### Challenge 1 — Image Handling

#### Problem
Images stored as SharePoint Attachments created deployment and refresh challenges in Power BI Service.

#### Solution
Power Automate was implemented to move images into SharePoint Document Library and generate stable URLs.

#### Result
Reliable image rendering and successful Power BI Service refresh.

---

### Challenge 2 — Project Delay Calculation

Custom DAX measures were developed to accurately calculate:
- Delivery Delays
- Start Delays
- On-Time Delivery %
- Delayed Projects
- Completion KPIs

Additional business rules were implemented to support:
- Ongoing Projects
- Not Started Projects
- Overdue Starts
- On-Hold Period Exclusions

---

## Business Impact

The final platform provides:
- Centralized Project Management
- Financial Visibility
- Timeline Monitoring
- Executive Reporting
- Workflow Automation
- Role-Based Access Control
- Improved Governance
- Better Decision-Making

The solution enables OLA Energy to monitor projects from data entry through executive reporting within a single integrated ecosystem.