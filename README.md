**📌 Overview**

This project delivers an interactive Power BI solution for analyzing policies, premiums, coverage, claims, and customer feedback in the insurance domain.

Data is sourced from Microsoft SQL Server (insurance dataset) and enriched with Excel-based customer feedback for sentiment analysis. The report is published to Power BI Service, secured with Row-Level Security (RLS), and updated through scheduled refresh using an on-premises gateway.

**🎯 Business Objectives**

Track total premium, coverage, and claim amounts.

Monitor policy activity (Active vs. Inactive).

Visualize claim status distribution (Settled, Pending, Rejected).

Compare premium contributions by policy type (Auto, Health, Home, Life, Travel).

Analyze claim amounts by age group.

Explore coverage across policy type × claim status.

Perform sentiment analysis on customer feedback.

**🗃️ Data Sources**

**SQL Server:** insuranceDB (≈10k rows) containing policies, customers, premiums, coverage, claims, claim status.

**Excel:** Customer feedback (97 records) used for sentiment analysis.

🧰 **Tech Stack**

Power BI Desktop (modeling, visuals)

Power Query (data cleaning & transformations)

DAX (measures, RLS filters)

SQL Server & SSMS

Power BI Service

On-premises Data Gateway (scheduled refresh)

**🏗️ Data Preparation**

Imported data from SQL Server (insuranceDB).

Performed data profiling & type corrections in Power Query.

Added calculated/conditional columns:

Age Group (Young Adult, Adult, Elder)

Active/Inactive Status (based on policy end date)

Applied sentiment analysis on customer feedback via Power BI AI Insights, producing:

Sentiment Score (0–1)

Feedback Category (Excellent, Good, Needs Improvement)

**🔗 Data Model**

Star schema with insurance fact table linked to supporting dimensions.

Combined SQL + Excel sources in the same PBIX.

Relationships defined for drill-through and cross-filtering across visuals.

**📄 Report Pages & Features**

Page 1 – Overview

Slicers: Policy No., Claim No., Customer ID

KPI Cards: Premium, Coverage, Claim Amount

Multi-row Card: Gender counts

Ribbon Chart: Claim status distribution

Bar Chart: Premium by policy type

Line Chart: Claim amount by age group

Donut Chart: Active vs. Inactive policies

Matrix: Coverage by policy type × claim status

Page 2 – Drill-through Details

Full table view of insurance data (row-level detail)

Drill-through enabled on Policy Type for contextual insights

Page 3 – Customer Feedback (Sentiment)

Word Cloud: Most frequent feedback terms

Bar Chart: Customer distribution by sentiment category

Table: Customer Name, Sentiment Score, Feedback

**🔒 Row-Level Security (RLS)**

Roles created in Desktop:

Travel Role → filters Policy Type = Travel

Health Role → filters Policy Type = Health

Tested in Power BI Desktop (“View As”) and validated in Power BI Service.

Assigned users to roles for secure access.

**☁️ Deployment & Sharing**

Published report to Power BI Service


