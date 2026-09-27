# E-commerce Business Performance Analysis

## Project Overview

This project analyzes e-commerce session, customer, sales, and revenue data to identify key business patterns and evaluate relationships between major business metrics.

The project combines **SQL, Python, statistical analysis, and Tableau** in an end-to-end data analytics workflow.

---

## Business Questions

The analysis focuses on the following questions:

- How does traffic volume change over time and across different acquisition channels?
- How do registered users and guests differ in purchasing behavior?
- Which geographic markets and traffic channels generate the most revenue?
- Which products and categories contribute most to sales and revenue?
- Is there a relationship between session volume and revenue?
- Do sales across different channels, continents, and products move together?
- Are observed differences between selected groups statistically significant?

---

## Dataset

The dataset contains approximately **350,000 session-level observations** covering **87 days** of e-commerce activity.

The data includes:

- Session and account information
- Date and geographic attributes
- Device, browser, and system information
- Traffic acquisition channel
- Registration and subscription information
- Product category and product name
- Purchase price

Data was extracted from **Google BigQuery** and analyzed using Python.

---

## Tools & Technologies

- **SQL / Google BigQuery** — data extraction
- **Python** — data cleaning, EDA, and statistical analysis
- **Pandas / NumPy** — data manipulation
- **SciPy / Statsmodels** — statistical testing
- **Matplotlib / Seaborn** — visualization
- **Tableau** — interactive dashboards
- **Jupyter Notebook / VS Code** — development environment

---

## Analytical Approach

### Data Preparation

The dataset was cleaned and validated before analysis.

Key steps included:

- Handling missing values and duplicates
- Converting variables to appropriate data types
- Validating identifier fields
- Investigating inconsistent device model classifications
- Examining price distribution and potential outliers using IQR and Z-score methods

Extreme price observations were retained after investigation because there was no sufficient evidence that they represented data errors.

### Exploratory & Business Analysis

The analysis covers:

- Sessions and traffic acquisition
- Registered users
- Customer purchasing behaviour
- Revenue and sales
- Geographic performance
- Product and category performance
- Relationships between business metrics

### Statistical Analysis

Statistical methods were used to validate selected findings:

- Pearson correlation
- One-way ANOVA
- Two-proportion z-test
- Normality testing

---

## Key Business Findings

### Traffic & Revenue

Daily sessions and revenue show a strong positive linear relationship:

**Pearson r = 0.79, p < 0.001**

Higher-traffic days generally coincide with higher revenue, although correlation does not establish causation.

### Geographic Performance

The **Americas** generate the highest number of sessions, sales, and revenue, followed by **Asia** and **Europe**.

At the country level, the **United States** is the largest market, followed by **India** and **Canada**.

### Traffic Channels

**Organic Search** is the leading traffic and revenue channel, accounting for more than 35% of both sessions and revenue.

Daily sales across traffic channels also show strong positive correlations, with Pearson coefficients ranging from approximately **0.77 to 0.93**.

### Customer Behaviour

Registered users and guests have very similar purchase rates:

- Registered: **9.95%**
- Guest: **9.56%**

The difference is statistically significant (`p = 0.0347`), but the practical difference is small.

### Product Performance

Sales volume and revenue contribution differ substantially across products and categories.

**BESTÅ** is the most frequently purchased product, while products such as **GRÖNLID** and **LIDHULT** generate substantially more revenue per sale.

At the category level, **Bookcases & Shelving units** lead in sales volume, while **Sofas & Armchairs** generate the highest total revenue.

### Statistical Relationships

Daily sales across the top three continents show strong positive correlations:

- Americas ↔ Asia: **r = 0.93**
- Americas ↔ Europe: **r = 0.92**
- Asia ↔ Europe: **r = 0.89**

All relationships are statistically significant (`p < 0.001`).

---

## Tableau Dashboards

### Key Business Metrics

This dashboard covers:

- KPI overview
- Sessions and revenue over time
- Geographic performance
- Traffic channel performance
- Revenue and sales distribution

**[View Tableau Dashboard](https://public.tableau.com/app/profile/eduard.kovalskyy/viz/KeyBusinessMetrics/KeyBusinessMetrics?publish=yes)**

### Products & Customer Behaviour

This dashboard covers:

- Registered vs. guest users
- Purchase behaviour
- Subscription status
- Product performance
- Category performance
- Revenue and sales comparisons

**[View Tableau Dashboard](https://public.tableau.com/app/profile/eduard.kovalskyy/viz/ProductMetricsCustomerBehaviour/ProductsCustomerBehaviour?publish=yes)**

---

## Project Structure

```text
E-commerce Business Performance Analysis/
│
├── data_sources_tableau/
│   ├── ecommerce_cleaned.csv
│
├── notebooks/
│   └── ecommerce_analysis.ipynb
│
├── dashboards/
│   └── key_metrics_customer_behaviour.twbx
│
└── README.md