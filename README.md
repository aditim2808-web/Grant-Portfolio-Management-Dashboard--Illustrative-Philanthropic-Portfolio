# Grant Portfolio Monitoring & Reporting Dashboard(Illustrative)

An Excel-based grant monitoring and reporting dashboard, built as a work sample to demonstrate the budget tracking, disbursement monitoring, and portfolio reporting skills relevant to grant/programme analyst roles. Applied here to a mock India air quality grant portfolio.

## Tools Used

- Microsoft Excel
- PivotTables & PivotCharts
- Conditional Formatting
- Data Validation
- Excel Formulas (SUMIFS, COUNTIFS, IF, XLOOKUP, INDEX/MATCH)
- Dashboard Design
---

## Overview

This project tracks a 5-grant illustrative portfolio across the given files in the repository: an auto-generated executive summary, a visual dashboard, a detailed grant tracker, and a finance/deliverables log. All figures update live off formulas — change a disbursement amount or a status, and the summary sentence, KPI cards, charts, and health scores all recalculate.

## Dashboard

<img width="1871" height="1323" alt="dashboard (1)" src="https://github.com/user-attachments/assets/2daad7a3-21a8-4efb-b80e-6b2a8a939857" />


KPI cards, five charts (budget vs. disbursed, grant status, risk distribution, utilisation by grant, and a composite health score), and a live reporting calendar with 🟢/🟡/🔴 status indicators.

## Executive Summary

<img width="1754" height="1241" alt="executive_summary" src="https://github.com/user-attachments/assets/8bbc79d1-6064-4f1d-9bc0-dd783c1d9fc3" />


A formula-driven narrative paragraph plus key portfolio figures — designed to be the first thing a reviewer reads, answering "how is this portfolio doing" in one glance.

## Grant Tracker

<img width="1754" height="1241" alt="grant_tracker" src="https://github.com/user-attachments/assets/e1b3c08d-09c6-4077-a681-a0bce4dc0b88" />


The core 21-field tracker: budget, disbursement, budget variance against a time-elapsed burn-rate benchmark, timeline, reporting status, and a composite **Health Score** (0–100, synthesising status, risk level, and reporting timeliness into a single management metric).

## Key Management Insights

The dashboard enables programme managers to quickly identify:

- Grants requiring immediate follow-up due to overdue reporting.
- Projects under- or over-spending relative to implementation timelines.
- High-risk grants requiring additional oversight.
- Upcoming reporting deadlines and payment milestones.
- Overall portfolio health through a single, interpretable management indicator. 

## Features

- **Executive Summary** — auto-generated portfolio narrative and key figures
- **Dashboard** — KPI cards, 5 embedded charts, reporting calendar
- **Grant Tracker** — budget/disbursement tracking, variance analysis, timeline progress, Health Score
- **Finance & Deliverables** — payment request/approval/invoice tracking, deliverable completion tracking
- Built entirely with live formulas (no hardcoded derived values), conditional formatting, and data validation dropdowns

## Skills Demonstrated

- Grant/budget tracking and disbursement monitoring across a multi-grant portfolio
- Variance analysis: comparing actual disbursement against a time-elapsed burn-rate benchmark, not just a flat % figure
- Composite performance metric design (Health Score)
- Dashboard and data visualisation for a non-technical, time-constrained reviewer audience
- Structured payment and deliverable tracking consistent with funder reporting requirements

## Grant Health Score Methodology

To provide a quick portfolio-level assessment, each grant is assigned a **Grant Health Score (0–100)**. The score is a transparent, rule-based indicator designed to summarise operational performance rather than predict future outcomes.

Each grant begins with a score of **100**, with deductions applied for implementation delays, elevated risk, and overdue reporting. Every deduction corresponds to an observable management issue, making the score easy to interpret during portfolio reviews.

### Scoring Rules

| Factor | Condition | Points Deducted |
|---------|-----------|----------------:|
| Status | Needs Attention | -10 |
| Status | Delayed | -20 |
| Risk | Medium | -15 |
| Risk | High | -30 |
| Reporting | Reporting overdue (grant not completed) | -20 |

Grants that are **On Track**, **Completed**, **Low Risk**, or have **current reporting** receive no deductions for those categories.

### Formula

```excel
=100
- IF(Status="Delayed",20,IF(Status="Needs Attention",10,0))
- IF(Risk="High",30,IF(Risk="Medium",15,0))
- IF(AND(Status<>"Completed",ReportingDue<TODAY()),20,0)
```

### Rating Scale

| Rating | Score | Interpretation |
|---------|------:|---------------|
| 🟢 Green | 80–100 | Performing well; no immediate management action required |
| 🟡 Amber | 50–79 | Emerging risks or delays; monitor closely |
| 🔴 Red | <50 | Significant implementation or reporting issues requiring intervention |

> **Design Note:** The Health Score is a rule-based management index rather than a statistical model. The deduction values are heuristic and were chosen to reflect the relative operational importance of common grant management issues while ensuring that every score can be traced back to specific project conditions.

## Data & Limitations

All grant names, partner types, budgets, dates, and statuses are **illustrative**, built for demonstration purposes — no confidential or actual Clean Air Fund data was used. Partner organisation types (Research Institute, State Pollution Control Board, Urban Local Body, Public Health Foundation, Civil Society Organisation) reflect realistic categories of implementing partners in the Indian clean air ecosystem, not real named entities with confirmed grants.

This project focuses on grant monitoring and reporting workflows and does not model the full grant-making process (e.g., due diligence, legal review, or procurement).

---

*Built by Aditi Mishra as a self-directed work sample.*
