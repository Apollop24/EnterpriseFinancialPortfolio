# Enterprise Financial Intelligence Suite
### Institutional-Grade Power BI Portfolio | Financial Analytics | Business Intelligence

[![Power BI](https://img.shields.io/badge/Power%20BI-F2C811?style=for-the-badge&logo=powerbi&logoColor=black)](https://powerbi.microsoft.com)
[![SQL](https://img.shields.io/badge/SQL-4479A1?style=for-the-badge&logo=postgresql&logoColor=white)](https://www.postgresql.org)
[![DAX](https://img.shields.io/badge/DAX-185FA5?style=for-the-badge&logo=microsoft&logoColor=white)](https://docs.microsoft.com/dax)
[![Excel](https://img.shields.io/badge/Excel-217346?style=for-the-badge&logo=microsoft-excel&logoColor=white)](https://microsoft.com/excel)

---

> **A world-class financial analytics platform equivalent to dashboards used at Goldman Sachs,
> JPMorgan, BlackRock, McKinsey, and Fortune 500 finance departments.**
> Built to demonstrate senior-level competency in Power BI, DAX, SQL data warehousing,
> financial analysis, risk analytics, and executive reporting.

---

## Portfolio Overview

| Metric | Value |
|---|---|
| Dashboard Pages | 12 |
| Visual Elements | 179 |
| DAX Measures | 98 |
| SQL Tables | 14 |
| Star Schema Relationships | 15 |
| Data Rows | 45,581 |
| Data Sources | SEC EDGAR · NSE · LSE · NYSE · NASDAQ · FRED · World Bank · IMF |
| Technologies | Power BI · DAX · PostgreSQL · Excel |

---

## 12 Dashboard Pages

### Page 1 — CFO Executive Financial Performance Dashboard
**Audience:** CFO · CEO · Board of Directors

Displays the complete profit and loss summary for executive consumption.
Revenue KPI cards update dynamically using DAX CALCULATE with ALLSELECTED.
The rolling 12-month revenue uses DATESINPERIOD. YoY growth uses SAMEPERIODLASTYEAR.

**Key Metrics:** Total Revenue · Gross Profit · EBITDA · Net Income · Gross Margin % · EBITDA Margin % · Net Margin % · ROE · ROA · ROIC

**Visuals:** Revenue trend line · Revenue by sector column chart · Gross profit by company bar chart · EBITDA trend · Revenue by region donut
<img width="1286" height="726" alt="image" src="https://github.com/user-attachments/assets/e7ee7bff-c25c-4826-88ed-4a11e64650fa" />

---

### Page 2 — Enterprise Financial Statement Analysis
**Audience:** CFO · Financial Controllers · Auditors · Equity Analysts

Ten-year financial statement explorer. The DuPont decomposition — Net Margin × Asset Turnover × Equity Multiplier — is calculated through a multi-level CTE in SQL and exposed as a DAX chain.

**Key Metrics:** Revenue · Gross Profit · EBIT · Net Income · Total Debt · Total Equity · Cash · Debt-to-Equity · Current Ratio · Quick Ratio

**Visuals:** Revenue vs COGS by year · EBITDA by company · Net income trend · Debt by company · Assets by sector donut
<img width="1365" height="767" alt="image" src="https://github.com/user-attachments/assets/186fc52c-58bf-44fb-a450-542b9317cf39" />

---

### Page 3 — Equity Research Command Center
**Audience:** Equity Research Analysts · Portfolio Managers · Investment Committees

Bloomberg-style market data terminal. MA20, MA50, MA200 calculated with DATESINPERIOD.
30-day annualised volatility = STDEV.P × SQRT(252). 52-week range using 365-day window.

**Key Metrics:** Latest Price · Total Market Cap · Total Volume · 52W High · 52W Low · Avg Daily Return · 30D Volatility %

**Visuals:** Price trend with moving averages · Market cap by sector · Volume area chart · Return by sector · Market cap by exchange donut
<img width="1371" height="785" alt="image" src="https://github.com/user-attachments/assets/90424406-9672-45d0-a303-914da7e44516" />

---

### Page 4 — Portfolio Management Analytics Dashboard
**Audience:** Asset Managers · Portfolio Managers · Investment Committees

Full CFA-compliant risk analytics. Sharpe Ratio = (Return − Rf) / σ. Sortino uses downside deviation only. Information Ratio = Active Return / Tracking Error.

**Key Metrics:** Total Portfolio Value · Avg Daily Return · Avg Beta · Avg Std Dev · Benchmark Return · Sharpe Ratio · Sortino Ratio · Information Ratio · Alpha

**Visuals:** Portfolio return trend · Sector allocation donut · Portfolio value area · Beta by sector · Return by sector bar
<img width="1355" height="776" alt="image" src="https://github.com/user-attachments/assets/6d12a0a8-8691-4d2b-a4df-4d20f0e93e51" />

---

### Page 5 — Credit Risk Analytics Dashboard
**Audience:** Chief Risk Officers · Credit Committees · Basel III Compliance

Implements the Basel III / IFRS 9 Expected Credit Loss model: EL = PD × EAD × LGD.
Risk tier classification: Green (<1% PD) · Amber (<5%) · Red (<15%) · Critical (≥15%).

**Key Metrics:** Total EAD · Avg PD · Avg LGD · Collateral Value · Expected Loss · NPL Ratio · Coverage Ratio · Unexpected Loss

**Visuals:** EAD by rating bar · Avg PD by sector · Exposure by sector donut · Collateral by rating · EAD by tenor · Exposure by tenor donut
<img width="1337" height="768" alt="image" src="https://github.com/user-attachments/assets/2fd973cf-1bcd-474f-ad31-c57bb76b0ea4" />

---

### Page 6 — Forensic Accounting and Fraud Detection
**Audience:** Internal Audit · Compliance · Forensic Accountants · CFO

Benford's Law first-digit analysis. Composite fraud score combining 5 signals:
Benford deviation · 3-sigma amount threshold · Duplicate payment flag · Round number bias · Off-hours timing.

**Key Metrics:** Total Transactions · Total Amount · Avg Fraud Score · Flagged Transaction Count · Off-Hours % · Benford Deviation Index

**Visuals:** Amount by flag reason · Fraud score by reason · Transaction trend · Amount by hour of day · Amount mix donut
<img width="1334" height="750" alt="image" src="https://github.com/user-attachments/assets/09614889-8add-43cf-b7aa-5575d0de22d6" />

---

### Page 7 — FP&A Planning and Variance Analysis
**Audience:** CFO · FP&A Directors · Department Heads · Cost Centre Managers

Full budget-actual-forecast triangle. Variance Status uses SWITCH(TRUE()) for dynamic RAG classification. Full Year Forecast adds actuals to remaining-month forecasts using DimDate[Month] > MONTH(TODAY()).

**Key Metrics:** Budget · Actual · Forecast · Variance $ · Variance % · Forecast Accuracy % · Budget Attainment % · Full Year Forecast

**Visuals:** Budget vs actual by department · Actual by cost centre · Budget trend · Actual vs forecast trend · Spend by department donut
<img width="1348" height="778" alt="image" src="https://github.com/user-attachments/assets/2bcfe9f9-6710-4cc4-b8f5-d8dcdb30cd6e" />

---

### Page 8 — Treasury Command Center
**Audience:** Group Treasurer · Treasury Committee · CFO · ALCO

Basel III regulatory ratios daily monitoring. LCR = HQLA / Net Stressed Outflows ≥ 100%.
NSFR = ASF / RSF ≥ 100%. FX exposure net long/short by currency.

**Key Metrics:** Total Cash · FX Long · FX Short · HQLA · Net Cash Outflows 30D · LCR % · NSFR % · LCR Status

**Visuals:** Cash balance trend · FX exposure by currency · HQLA area trend · Cash by currency · FX mix donut
<img width="944" height="533" alt="image" src="https://github.com/user-attachments/assets/498cbbd6-87b6-4ca3-a607-4c9e05c20923" />

---

### Page 9 — ESG and Sustainability Analytics
**Audience:** Board ESG Committee · Investor Relations · Sustainability Officers

MSCI-methodology ESG composite: E × 40% + S × 35% + G × 25%.
Rating bands: AAA (≥80) · AA (≥70) · A (≥60) · BBB (≥50) · BB (≥40) · B (<40).
Carbon intensity YoY uses SAMEPERIODLASTYEAR.

**Key Metrics:** Avg E Score · Avg S Score · Avg G Score · ESG Composite Score · ESG Rating Band · Avg Carbon Intensity · Carbon YoY Change % · Board Diversity %

**Visuals:** E score by company · S score by company · Carbon intensity by company · G score by company · ESG by sector donut
<img width="1334" height="759" alt="image" src="https://github.com/user-attachments/assets/f838ce0f-6eef-4a31-9bf1-b404d9899d5c" />

---

### Page 10 — Macroeconomic Intelligence Dashboard
**Audience:** Strategy Teams · Investment Committees · Chief Economists

Country-level macro aggregation from FRED, World Bank, and IMF.
Real Policy Rate = Nominal Rate − Inflation (Fisher equation proxy).

**Key Metrics:** Avg GDP Growth · Avg Inflation · Avg Policy Rate · Real Policy Rate · Avg Unemployment · Avg USD Index · Avg VIX

**Visuals:** GDP growth trend · Inflation by country · Policy rate trend area · Unemployment by country · VIX by country
<img width="1339" height="766" alt="image" src="https://github.com/user-attachments/assets/0b26bcb8-0701-4f39-87c1-058a47498c89" />

---

### Page 11 — Balance Sheet and Capital Structure Analysis
**Audience:** CFO · Credit Analysts · Rating Agency Analysts

Full balance sheet decomposition. Cash Conversion Cycle = DIO + DSO − DPO.
Equity Multiplier feeds the DuPont ROE chain. Working Capital = Current Assets − Current Liabilities.

**Key Metrics:** Total Assets · Total Equity · Total Debt · Cash · Current Assets · Current Liabilities · Working Capital · Debt-to-Equity · Net Debt to EBITDA

**Visuals:** Total assets trend · Debt by company · Equity by company · Cash trend area · Assets by company donut
<img width="1352" height="765" alt="image" src="https://github.com/user-attachments/assets/b3649122-d20c-4329-aa4d-524bd4befe13" />

---

### Page 12 — Executive Boardroom Command Center
**Audience:** Board of Directors · CEO · CFO · Investment Committee

The flagship page. All 12 analytical domains unified on one screen.
Cross-filtering: clicking any visual instantly updates all others.
Three-row layout: Revenue & Portfolio | Credit & Treasury | P&L & FP&A & ESG.

**Key Metrics:** All 9 fact table KPIs on a single page

**Visuals:** 3 × 3 grid of the most important chart from each analytical domain with 7 KPI cards at the top
<img width="1333" height="766" alt="image" src="https://github.com/user-attachments/assets/e0d7a401-d791-4eae-9357-b22dd574929b" />

---

## Repository Structure

```
EnterpriseFinancialPortfolio/
│
├── README.md                              ← You are here
│
├── dashboards/
│   ├── EnterpriseFinancialPortfolio.pbix  ← Main portfolio (12 pages, 179 visuals)
│   ├── EnterpriseFinancialPortfolio_Template.pbit  ← Portable template version
│   └── Nairobi_Womens_Hospital_Dashboard.pbix      ← Bonus healthcare dashboard
│
├── data/
│   └── EnterpriseFinancialPortfolio_Data.xlsx ← 14 tables, 45,581 rows
│       ├── DimDate                (2,192 rows)
│       ├── DimCompany             (10 rows)
│       ├── DimTicker              (10 rows)
│       ├── DimDepartment          (8 rows)
│       ├── DimEconomicIndicators  (30 rows)
│       ├── FactFinancials         (720 rows)
│       ├── FactBalanceSheet       (720 rows)
│       ├── FactMarketPrices       (5,220 rows)
│       ├── FactPortfolio          (5,220 rows)
│       ├── FactCreditRisk         (600 rows)
│       ├── FactFPA                (288 rows)
│       ├── FactTreasury           (27,370 rows)
│       ├── FactFraud              (3,000 rows)
│       └── FactESG                (60 rows)
│
├── sql/
│   ├── 01_star_schema_DDL.sql    ← Full data warehouse DDL (PostgreSQL compatible)
│   └── 02_analytics_queries.sql  ← Advanced SQL: CTEs, window functions, procedures
│
├── dax/
│   └── DAX_Measures_Library.dax  ← All 98 DAX measures with documentation
│
├── docs/
│   ├── Data_Dictionary.md        ← Full data dictionary for all 14 tables
│   └── Interview_Talking_Points.md ← Dashboard-by-dashboard interview guide
│
└── screenshots/
    └── (add your dashboard screenshots here for LinkedIn and GitHub preview)
```

---

## Data Sources

All data originates from official public sources. No Kaggle datasets used.

| Domain | Source | URL |
|---|---|---|
| Financial Statements | SEC EDGAR | https://efts.sec.gov |
| Market Prices (US) | NYSE · NASDAQ | https://finance.yahoo.com |
| Market Prices (Africa) | NSE Kenya | https://www.nse.co.ke |
| Market Prices (Europe) | London Stock Exchange | https://www.londonstockexchange.com |
| Macro Indicators | FRED (St. Louis Fed) | https://fred.stlouisfed.org |
| GDP · Unemployment | World Bank | https://data.worldbank.org |
| Country Macro | IMF Data | https://www.imf.org/en/Data |
| Kenya Rates | Central Bank of Kenya | https://www.centralbank.go.ke |

---

## Technical Stack

| Technology | Version | Purpose |
|---|---|---|
| Power BI Desktop | June 2026 (v2.155) | Dashboard development |
| DAX | — | 98 measures across 9 domains |
| PostgreSQL | 15+ | Star schema DDL, analytics queries |
| Excel (xlsx) | — | Data source (14 sheets, 45K rows) |
| SQL Server | 2022 | Partitioned fact tables, materialized views |
| Snowflake | — | Cloud data warehouse compatible DDL |

---

## Advanced DAX Techniques Demonstrated

| Function Category | Functions Used |
|---|---|
| Filter context | CALCULATE · FILTER · ALL · ALLSELECTED · ALLEXCEPT |
| Aggregation | SUM · AVERAGE · SUMX · AVERAGEX · STDEV.P · RANKX |
| Time intelligence | DATESINPERIOD · SAMEPERIODLASTYEAR · DATEADD · TOTALYTD · TOTALQTD · TOTALMTD · PREVIOUSQUARTER · LASTDATE |
| Logical / flow | SWITCH · IF · SELECTEDVALUE · ISINSCOPE |
| Table functions | TREATAS · TOPN · GENERATESERIES · VALUES |
| Statistical | STDEV.P · SQRT · DIVIDE (zero-safe) |
| Dynamic | Dynamic titles · Context-aware tooltips · Conditional formatting |

---

## Advanced SQL Techniques Demonstrated

| Category | Techniques |
|---|---|
| Window functions | ROW_NUMBER · RANK · DENSE_RANK · NTILE · LAG · LEAD · SUM OVER · AVG OVER · STDEV OVER |
| CTEs | Multi-level CTEs · Recursive CTEs · DuPont decomposition |
| Stored procedures | sp_calc_expected_loss with risk tier classification |
| Views & materialized views | vw_fpa_variance · mv_monthly_kpi_summary |
| Partitioning | Range partitioning on fiscal_year for FactFinancials |
| Indexing | Clustered indexes on date+company keys · Covering indexes |
| Advanced | Benford's Law detection · Dynamic SQL · Triggers |

---

## Star Schema Design

```
                     ┌─────────────┐
                     │   DimDate   │
                     └──────┬──────┘
                            │
          ┌─────────────────┼─────────────────┐
          │                 │                 │
   ┌──────┴───────┐  ┌──────┴───────┐  ┌──────┴───────┐
   │FactFinancials│  │FactMarketPrx │  │ FactPortfolio│
   └──────┬───────┘  └──────┬───────┘  └──────┬───────┘
          │                 │                 │
   ┌──────┴───────┐  ┌──────┴───────┐  ┌──────┴───────┐
   │  DimCompany  │  │  DimTicker   │  │  DimTicker   │
   └──────────────┘  └──────────────┘  └──────────────┘

   ┌───────────────┐  ┌────────────┐  ┌──────────────┐
   │FactBalanceSheet│  │ FactFPA   │  │FactTreasury  │
   └───────┬───────┘  └─────┬──────┘  └──────┬───────┘
           │                │                 │
   ┌───────┴───────┐  ┌─────┴──────┐  ┌──────┴───────┐
   │  DimCompany   │  │DimDepartmnt│  │   DimDate    │
   └───────────────┘  └────────────┘  └──────────────┘

   ┌───────────────┐  ┌────────────┐  ┌──────────────┐
   │FactCreditRisk │  │ FactFraud  │  │   FactESG    │
   └───────┬───────┘  └─────┬──────┘  └──────┬───────┘
           │                │                 │
   ┌───────┴───────┐  ┌─────┴──────┐  ┌──────┴───────┐
   │   DimDate     │  │  DimDate   │  │ DimCompany   │
   └───────────────┘  └────────────┘  └──────────────┘
```

---

## Quick Start

### Option A — Open and Connect (Recommended)

1. Download `dashboards/EnterpriseFinancialPortfolio.pbix`
2. Download `data/EnterpriseFinancialPortfolio_Data.xlsx`
3. Open the `.pbix` in Power BI Desktop (June 2026 or later)
4. Go to `Home → Transform Data → Data Source Settings`
5. Select the Excel source → click `Change Source`
6. Browse to `EnterpriseFinancialPortfolio_Data.xlsx` → click `OK`
7. Click `Close & Apply`
8. All 179 visuals across 12 pages populate automatically

### Option B — Build the Data Model from Scratch

1. Open Power BI Desktop
2. `Home → Get Data → Excel Workbook`
3. Browse to `EnterpriseFinancialPortfolio_Data.xlsx`
4. Select all 14 sheets in the Navigator → click `Load`
5. In `Model View`, draw the 15 relationships per the table in `docs/Data_Dictionary.md`
6. In `Report View`, add measures from `dax/DAX_Measures_Library.dax`
7. Build your own visualisations or import the `.pbix` layout

### Option C — Deploy the SQL Data Warehouse

```bash
# PostgreSQL
psql -U postgres -d financial_dw -f sql/01_star_schema_DDL.sql
psql -U postgres -d financial_dw -f sql/02_analytics_queries.sql

# Load data from Excel into staging tables then run ETL
```

---

## Connecting Power BI to the SQL Warehouse

1. `Home → Get Data → PostgreSQL database`
2. Server: `localhost` · Database: `financial_dw`
3. Select all fact and dimension tables
4. Relationships auto-detect from matching key column names
5. Add DAX measures from `dax/DAX_Measures_Library.dax`

---

## Skills Demonstrated

### Financial Analytics
- Income statement, balance sheet, and cash flow analysis
- Profitability, liquidity, leverage, and efficiency ratios
- DuPont ROE decomposition
- DCF valuation concepts
- Investment portfolio risk metrics (CFA methodology)
- Basel III credit risk: PD, EAD, LGD, EL, LCR, NSFR
- ESG scoring (MSCI methodology)
- Forensic accounting and Benford's Law

### Business Intelligence & Data Engineering
- Star schema and snowflake schema design
- SCD Type 2 slowly changing dimensions
- Table partitioning by fiscal year
- Materialized views for performance
- Row-level security design
- ETL pipeline design
- Data quality framework

### Power BI / DAX
- 98 DAX measures across 9 analytical domains
- Time intelligence (YTD, QTD, MTD, YoY, rolling windows)
- Advanced CALCULATE with ALL, ALLSELECTED, ALLEXCEPT
- Dynamic titles and conditional formatting
- Cross-filtering and drill-through design
- Interactive slicers for Year, Sector, Region, Currency

### SQL
- Complex joins and self-joins
- Window functions and analytical queries
- Multi-level CTEs
- Stored procedures and triggers
- Views and materialized views
- Query optimisation and index strategy

---

## Author

**Philip Kibet**
Biostatistician & Data Manager | Financial Data Analyst
Nairobi, Kenya

- GitHub: [@Apollop24](https://github.com/Apollop24)
- Specialisations: Biostatistics · Financial Analytics · SQL · Power BI · Python · R · SPSS · SAS
- Available for: Freelance data analytics, biostatistics consulting, financial reporting projects

---

## Licence

This project is released under the MIT Licence. See `LICENSE` for details.

Data used in this portfolio originates exclusively from official public sources
(SEC EDGAR, NSE, LSE, FRED, World Bank, IMF) and is used for educational and
portfolio demonstration purposes only.

---

*Built with Power BI · DAX · SQL · Excel · Python*
*Data: SEC EDGAR · NSE Kenya · LSE · NYSE · NASDAQ · FRED · World Bank · IMF*
