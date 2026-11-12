# Consumer Complaint Intelligence & Management Reporting

**A Business Intelligence Case Study | Bank of America | 2017–2023**

## 1. Project Overview

This project analyses consumer complaints submitted to the Consumer Financial Protection Bureau (CFPB) concerning Bank of America between May 2017 and August 2023.

The objective is to turn complaint records into useful management information: identifying where complaints are concentrated, which issues occur most frequently, how complaints are recorded as being handled, and where operational performance requires further investigation.

Rather than presenting complaint counts in isolation, the project uses data cleaning, SQL analysis, KPI development and Power BI reporting to support management decisions.

**The central question is: Where should management focus its attention to better monitor complaint patterns, response performance and operational exceptions?**

## 2. Business Understanding

### The management challenge

Customer complaints provide an important source of information about product experiences and service processes. However, large volumes of complaint records are difficult to interpret without structured reporting.

Management needs to understand:

- Which products account for the largest complaint volumes?
- What customer issues occur most frequently?
- Are complaint volumes increasing or decreasing?
- What outcomes are recorded against complaints?
- How many complaints are marked as receiving a timely response?
- Which products or periods require closer performance monitoring?
- How quickly are complaints forwarded from the CFPB to the company?

Without consistent KPI definitions and an accessible reporting process, these questions can be difficult to answer consistently.

### Business objectives

This analysis was designed around five objectives:

| Business objective | Management question | Intended use |
|---|---|---|
| Complaint concentration | Which products generate the most complaints? | Prioritise product-level reviews. |
| Issue identification | Which problems are reported most frequently? | Direct root-cause investigations. |
| Trend monitoring | How do complaint volumes change over time? | Identify emerging patterns and periods requiring attention. |
| Response performance | What response outcomes and timeliness statuses are recorded? | Monitor response performance and exceptions. |
| Forwarding efficiency | How long does it take for complaints to reach the company? | Identify unusually long forwarding intervals. |

## 3. Dataset at a Glance

| Dataset attribute | Description |
|---|---|
| Source | CFPB Consumer Complaint Database |
| Company | Bank of America |
| Reporting period | May 2017 – August 2023 |
| Total records | 62,516 complaints |
| Unit of analysis | Individual complaint |
| Main analytical dimensions | Product, issue, sub-product, state, year and submission channel |
| Response information | Company response category and timely response status |
| Date information | Date submitted and date received |

Each row represents a complaint record. Complaint counts should not be interpreted as the percentage of customers experiencing a problem because customer or account population denominators are not available.

## 4. Key Findings

The initial analysis established several important patterns.

### 4.1 Complaint concentration by product

Two product categories account for the majority of recorded complaints.

| Product | Complaints | Share |
|---|---:|---:|
| Checking or savings account | 24,814 | 39.69% |
| Credit card or prepaid card | 16,197 | 25.91% |
| **Combined** | **41,011** | **65.60%** |

**Management interpretation:** Complaint monitoring should give particular attention to checking/savings and credit card/prepaid products. Investigating the issues within these categories may provide greater value than treating all product categories equally.

### 4.2 Leading complaint issues

| Complaint issue | Complaints | Share |
|---|---:|---:|
| Managing an account | 15,109 | 24.17% |
| Incorrect information on your report | 4,931 | 7.89% |
| Problem with a purchase shown on your statement | 4,415 | 7.06% |
| Closing an account | 2,953 | 4.72% |
| Trouble during payment process | 2,827 | 4.52% |

**Management interpretation:** Account management is the largest individual complaint category. Further analysis should examine its sub-issues and product distribution to identify where more detailed operational investigation is warranted.

### 4.3 Complaint volume trends

| Year | Complaints |
|---|---:|
| 2017 | 5,394 |
| 2018 | 7,872 |
| 2019 | 7,075 |
| 2020 | 8,942 |
| 2021 | 11,149 |
| 2022 | 12,953 |
| 2023 | 9,131 |

Complaint volumes increased from 8,942 in 2020 to 12,953 in 2022.

The 2022 figure represents the highest complete-year volume in the dataset. The 2017 and 2023 reporting periods are incomplete, so they should not be compared directly with full-year totals.

**Management interpretation:** The increase between 2020 and 2022 warrants investigation into the products and issues contributing to the growth.

### 4.4 Recorded company response outcomes

| Response category | Complaints | Share |
|---|---:|---:|
| Closed with explanation | 41,044 | 65.65% |
| Closed with monetary relief | 14,697 | 23.51% |
| Closed with non-monetary relief | 5,273 | 8.43% |
| In progress | 1,494 | 2.39% |
| Closed | 8 | 0.01% |

**Management interpretation:** Most complaints were recorded as closed with explanation. Response categories should be monitored separately because closure with explanation and closure with relief represent different recorded outcomes. These categories do not independently establish customer satisfaction or resolution quality.

### 4.5 Response timeliness

Timeliness calculations use only records with a valid Yes or No status.

| Measure | Complaints |
|---|---:|
| Marked timely — Yes | 58,619 |
| Marked untimely — No | 2,403 |
| Valid timeliness records | 61,022 |
| Missing timeliness status | 1,494 |

**Valid timely response rate: 96.06%**

**Management interpretation:** Although the recorded timely response rate is high, the 2,403 untimely records warrant further investigation. The 1,494 records without a timeliness status are reported separately and are not classified as untimely.

### 4.6 CFPB forwarding intervals

Forwarding time is calculated as:

**Date received by company − Date submitted to CFPB**

| Measure | Result |
|---|---:|
| Average forwarding time | 1.22 days |
| Median forwarding time | 0 days |
| Same-day forwarding | 49,634 (79.39%) |
| Forwarded within one day | 55,209 (88.31%) |
| Forwarded within three days | 58,065 (92.88%) |
| Forwarded within seven days | 60,073 (96.09%) |
| More than seven days | 2,443 (3.91%) |
| 90th percentile | 2 days |
| 95th percentile | 5 days |
| Maximum recorded interval | 275 days |

**Management interpretation:** Most complaints were forwarded quickly. However, the long-delay tail, including records exceeding seven days, requires separate examination. The maximum interval should be validated against the original record.

This measure describes CFPB forwarding time, not the company's internal investigation or complaint resolution time.

## 5. Management Recommendations

The findings suggest five areas for management attention.

| Priority | Recommended action | How to monitor |
|---|---|---|
| 1. Product concentration | Prioritise checking/savings and credit card/prepaid complaint reviews. | Monthly complaints and issue share by product. |
| 2. Recurring issues | Investigate account management and other high-volume issues at sub-issue level. | Monthly top issues and repeat issue patterns. |
| 3. Timeliness exceptions | Establish a review process for complaints marked untimely. | Untimely count and valid timely response rate. |
| 4. Pending complaints | Monitor complaints recorded as in progress and their ageing. | Pending case count and ageing distribution, where dates are available. |
| 5. Forwarding delays | Investigate complaints with forwarding intervals exceeding seven days. | Number of verified exceptions and forwarding-time percentiles. |

These recommendations are intended to guide investigation and performance monitoring. Numerical improvement targets should be agreed only after operational teams validate the underlying causes and establish appropriate baselines.

## 6. Power BI Management Dashboard

The report is organised into four pages, each designed around a specific management question.

| Dashboard page | Focus | Management value |
|---|---|---|
| 01. Executive Complaint Overview | Complaint volumes, growth, product concentration and leading issues | Provides an overall performance snapshot. |
| 02. Product & Issue Intelligence | Product and issue patterns | Identifies areas for deeper investigation. |
| 03. Company Response & Timeliness | Recorded response outcomes and timeliness | Supports response monitoring and exception review. |
| 04. Complaint Timeline & Forwarding Analysis | Monthly trends and CFPB forwarding intervals | Highlights forwarding patterns and longer intervals. |

The dashboard includes interactive filters for relevant dimensions such as year, product and state.

*Dashboard screenshots and the Power BI report will be added to this repository after final validation.*

## 7. Methodology and Tools

The project follows an end-to-end analytical workflow.

1. **Business understanding:** Define management questions and the decisions the analysis should support.
2. **Data inspection:** Review the dataset structure, data dictionary, fields and completeness.
3. **Data cleaning:** Standardise fields, validate dates and identifiers, and preserve meaningful missing values.
4. **Data transformation:** Create reporting fields, including year, month and CFPB forwarding intervals.
5. **SQL analysis:** Aggregate complaints, calculate shares and validate key business metrics.
6. **KPI development:** Establish consistent definitions and denominators.
7. **Power BI reporting:** Develop interactive management dashboards.
8. **Business interpretation:** Convert findings into investigation priorities and measurable recommendations.

### Technology stack

| Tool | Application |
|---|---|
| Excel | Initial dataset inspection and validation |
| Python (Pandas) | Data cleaning, transformation and quality checks |
| SQL (DuckDB) | Data aggregation, KPI validation and analytical queries |
| Power BI | Interactive dashboard and management reporting |
| DAX | Measures, calculations and reporting KPIs |
| GitHub | Version control and project documentation |

## 8. Data Quality and Limitations

Data quality is central to reliable management reporting.

The analysis identified the following missing values:

| Field | Missing records | Missing percentage |
|---|---:|---:|
| Sub-issue | 10,858 | 17.37% |
| Company public response | 2,175 | 3.48% |
| Timely response? | 1,494 | 2.39% |

Additional forwarding-date validation identified:

- Zero missing forwarding intervals.
- Zero negative forwarding intervals.

### Important limitations

- The dataset does not contain total customer or account populations. Complaint counts are not customer-level complaint rates.
- Missing public-response information does not establish that the company failed to respond to a consumer.
- Missing timeliness statuses are excluded from the valid Yes/No response-rate denominator.
- Response categories do not independently establish customer satisfaction or resolution quality.
- CFPB forwarding time is not company resolution time.
- The reporting periods for 2017 and 2023 are incomplete.
- The dataset does not establish the causes of complaint increases or operational delays.

These limitations are considered when interpreting results and making recommendations.

## 9. Repository Structure

```text
consumer-complaint-intelligence/
│
├── README.md
│
├── data/
│   ├── raw/
│   └── processed/
│
├── python/
│   └── data_cleaning.py
│
├── sql/
│   ├── complaint_trends.sql
│   ├── product_analysis.sql
│   ├── response_analysis.sql
│   └── forwarding_analysis.sql
│
├── powerbi/
│   └── Consumer_Complaint_Dashboard.pbix
│
├── documentation/
│   ├── data_dictionary.md
│   ├── data_quality_report.md
│   ├── kpi_definitions.md
│   └── business_recommendations.md
│
└── screenshots/
    ├── page_1_executive_overview.png
    ├── page_2_product_issue_intelligence.png
    ├── page_3_response_timeliness.png
    └── page_4_forwarding_analysis.png
```

Files will be added as the project artifacts are finalised. The structure represents the intended repository organisation, not a claim that every file is already available.

## 10. Project Deliverables

The completed project will include:

- A cleaned dataset or reproducible cleaning script.
- SQL queries for the major analytical questions.
- Documented KPI definitions and calculations.
- An interactive four-page Power BI dashboard.
- Evidence-based business insights.
- Actionable recommendations with measurable monitoring indicators.
- Data dictionary and data-quality documentation.
- Reproducible project documentation.

## 11. Conclusion

This project demonstrates how consumer complaint data can be transformed into structured management information.

The analysis identifies significant complaint concentration in checking/savings and credit card/prepaid products, highlights account management as the leading individual issue, evaluates recorded response outcomes and timeliness, and examines the CFPB forwarding process.

The resulting dashboard is intended to help management move beyond basic complaint counts towards more focused product reviews, exception monitoring and evidence-based operational decisions.

**The objective is not simply to report how many complaints were received. It is to identify where management should investigate, what should be monitored and how improvement can be measured.**

---

**Data source:** [CFPB Consumer Complaint Database](https://www.consumerfinance.gov/data-research/consumer-complaints/)

**Disclaimer:** This is an independent analytical portfolio project using publicly available complaint records. It does not represent an official Bank of America report or an assessment endorsed by the company or CFPB.
