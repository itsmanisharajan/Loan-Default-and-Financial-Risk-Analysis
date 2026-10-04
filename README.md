# Loan Default and Financial Risk Analysis

![Loan Default & Financial Risk Dashboard](screenshots/overview.png)

**End-to-end loan default and financial risk analysis using SQL Server, Power BI Service, Standard Gateway, Dataflow Gen1, Power Query, and DAX.**

## Table of Contents

- [Project Overview](#project-overview)
- [Data Pipeline](#data-pipeline)
- [Technologies Used](#technologies-used)
- [Dataset](#dataset)
- [SQL Server & Power BI Service](#sql-server--power-bi-service)
- [Dataflow Gen1](#dataflow-gen1)
- [Power BI Desktop](#power-bi-desktop)
- [Data Transformation & Preparation](#data-transformation--preparation)
- [DAX Analysis](#dax-analysis)
- [Dashboard Pages](#dashboard-pages)
- [Refresh Strategy](#refresh-strategy)
- [Dashboard Preview](#dashboard-preview)
- [Repository Structure](#repository-structure)
- [Key Skills Demonstrated](#key-skills-demonstrated)
- [Author](#author)

## Project Overview

This project analyzes loan applications and financial risk factors to understand **loan defaults, applicant demographics, income, credit score, loan amount, employment characteristics, and other financial indicators**.

The project follows an end-to-end Power BI workflow, starting with a CSV dataset imported into SQL Server, connecting SQL Server to Power BI Service through a **Standard Gateway**, using **Dataflow Gen1** to bring the data into Power BI Desktop, and then performing data preparation, analysis, DAX calculations, validation, and dashboard development.

The completed report was published to a dedicated **Power BI Service workspace**, with **scheduled refresh and incremental refresh** configured to support ongoing data updates.

## Data Pipeline

```text
CSV Dataset
     ↓
SQL Server
     ↓
Standard Gateway
     ↓
Power BI Service
     ↓
Dataflow Gen1
     ↓
Power BI Desktop
     ↓
Power Query
     ↓
Data Cleaning & Transformation
     ↓
DAX Measures & Calculated Columns
     ↓
Data Validation & Analysis
     ↓
Interactive Power BI Report
     ↓
Power BI Service Workspace
     ↓
Scheduled Refresh + Incremental Refresh
```

## Technologies Used

- **SQL Server** — database storage for the loan dataset
- **Power BI Service** — cloud report/dataflow environment and workspace
- **On-premises Data Gateway (Standard Mode)** — connects SQL Server with Power BI Service
- **Power BI Dataflow Gen1** — data preparation and movement between Power BI Service and Power BI Desktop
- **Power BI Desktop** — data profiling, transformation, data modeling, DAX, analysis, and report development
- **Power Query** — data cleaning, profiling, type management, and transformations
- **DAX** — measures and calculated-column based analysis
- **Power BI Service Refresh** — scheduled and incremental refresh configuration

## Dataset

**Dataset:** `Loan_default.csv`

The dataset contains loan applicant, financial, demographic, employment, and credit-related attributes.

Key fields include:

- Age
- Age Group
- Credit Score
- Credit Score Bins
- DTI Ratio
- Education
- Employment Type
- Has CoSigner
- Has Dependents
- Has Mortgage
- Income
- Income Bracket
- Interest Rate
- Loan Date
- Loan Amount
- Loan ID
- Loan Purpose
- Loan Term
- Marital Status
- Months Employed
- Number of Credit Lines
- Year

A separate **Column Definitions** file is included to document the dataset fields and their meanings.

## SQL Server & Power BI Service

The CSV dataset was first imported into **Microsoft SQL Server**.

SQL Server was then connected to **Power BI Service** using the **On-premises Data Gateway in Standard Mode**. The SQL Server table was made available in Power BI Service and used as the source for the Dataflow.

This setup allows the Power BI environment to access the SQL Server data through the configured gateway.

## Dataflow Gen1

A **Power BI Dataflow Gen1** was created in Power BI Service using the SQL Server data source.

The dataflow was then used to make the prepared dataset available in **Power BI Desktop** for further analysis and report development.

## Power BI Desktop

The main analytical work was completed in Power BI Desktop.

### Data Preparation

Data profiling and transformation were performed in Power Query, including:

- Reviewing column quality and data types
- Assigning appropriate data types
- Cleaning and preparing fields for analysis
- Creating age groups and credit score categories where required
- Preparing the dataset for DAX-based analysis and visualization

### Analysis

The report includes calculated measures and analysis for:

- Loan amount by purpose
- Average income by employment type
- Default rate by employment type
- Average loan amount by age group
- Default rate by year
- Median loan amount by credit score category
- Loan analysis by credit categories
- Loan amount by mortgage and dependents
- Loan analysis by education
- Year-over-year loan amount
- Year-over-year change in defaulted loans
- Year-to-date loan amount by credit score bins and marital status
- Decomposition Tree analysis for financial risk exploration

### Data Validation

Data validation was performed for key calculations and visuals, including:

- Average loan amount by age group
- Default rate by year
- Median calculations
- Donut chart analysis
- Clustered column chart analysis
- Education-based loan analysis

Validation was used to confirm that calculated results matched the underlying data.

## DAX Analysis

The project uses DAX functions and concepts such as:

```text
SUMX
FILTER
NOT
ISBLANK
CALCULATE
AVERAGE
ALLEXCEPT
ALL
COUNTROWS
DIVIDE
AVERAGEX
VALUES
MEDIANX
SUM
SWITCH
```

Time-based analysis includes:

- YOY Loan Amount
- YOY Default Loans Change
- YTD Loan Amount

These calculations support analysis of loan performance and financial risk across different applicant and loan segments.

## Dashboard Pages

The report contains multiple analytical views, including:

### 1. Loan Default & Overview

Provides a high-level view of loan activity and default-related metrics.

### 2. Applicant Demographics & Financial Profile

Analyzes applicant characteristics and financial attributes such as age groups, income, employment type, education, marital status, and related loan characteristics.

### 3. Financial Risk Metrics

Focuses on credit-related and loan-related risk indicators, including default rates, loan amounts, credit score categories, and time-based financial trends.

Interactive visualizations and filters allow users to explore the data across different dimensions.

## Refresh Strategy

The project uses Power BI Service refresh capabilities to support data updates.

### Scheduled Refresh

Scheduled refresh was configured for the report/dataflow so that updated data can be reflected without manually rebuilding the report.

### Incremental Refresh

Incremental refresh was configured for the Dataflow to support more efficient processing of changing data by refreshing relevant portions of the dataset instead of treating the entire dataset as new each time.

## Dashboard Preview

### Loan Default & Overview

![Loan Default & Overview](screenshots/overview.png)

### Applicant Demographics & Financial Profile

![Applicant Demographics & Financial Profile](screenshots/applicant-demographics.png)

### Financial Risk Metrics

![Financial Risk Metrics](screenshots/financial-risk-metrics.png)

## Repository Structure

```text
Loan-Default-and-Financial-Risk-Analysis/
│
├── data/
│   ├── Loan_default.csv
│   └── Column Definitions.xlsx
│
├── powerbi/
│   └── Loan_Default_Financial_Risk_Analysis.pbix
│
├── screenshots/
│   ├── overview.png
│   ├── applicant-demographics.png
│   └── financial-risk-metrics.png
│
└── README.md
```

> **Note:** If the repository is public, make sure the dataset does not contain real personal or sensitive information. Use a sanitized/sample dataset when necessary.

## Key Skills Demonstrated

- SQL Server data ingestion
- Power BI Service
- Standard Mode Gateway configuration
- Power BI Dataflow Gen1
- Power Query data profiling and transformation
- DAX measure development
- Calculated columns
- Data validation
- Financial and risk analysis
- Interactive dashboard development
- Power BI Service publishing
- Scheduled refresh
- Incremental refresh

## Author

**Manisha Rajan**

Data Analyst | SQL • Excel • Power BI • Python
