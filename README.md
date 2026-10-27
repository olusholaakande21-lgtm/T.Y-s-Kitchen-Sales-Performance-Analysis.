# T.Y's Kitchen Sales Performance Analysis.

## Project Overview

This project analyses restaurant sales transactions from 2022 to 2023 using Microsoft Power BI, Power Query, and DAX. The goal is to transform raw transactional data into meaningful business insights that support revenue growth, product strategy, customer retention, and management decision-making.

The project covers data preparation, KPI development, interactive dashboard design, business analysis, and recommendations.

## Business Problem

Restaurant managers need to understand which products and categories drive revenue, how sales change over time, which customers contribute the most, and how payment methods are distributed.

This project addresses the following question:

**How can restaurant sales data be transformed into actionable insights that improve sales performance and support better business decisions?**

## Project Objectives

- Evaluate overall sales performance.
- Identify the highest-revenue products and categories.
- Compare revenue between 2022 and 2023.
- Analyse monthly sales trends.
- Examine customer revenue contribution.
- Analyse payment-method distribution.
- Identify data-quality issues.
- Recommend actions to improve business performance.

## Dataset

The dataset contains 17,104 transaction records and 13 fields covering 2022–2023.

Key fields include:

- Order ID
- Customer ID
- Category
- Item
- Price
- Quantity
- Order Total
- Order Date
- Payment Method
- Year
- Month
- Month Name
- Quarter

## Tools and Technologies

- **Microsoft Power BI:** Dashboard development and data visualization.
- **Power Query:** Data cleaning, transformation, and preparation.
- **DAX:** KPI and business measure calculations.
- **Business Intelligence:** Insight generation and decision support.

## Data Preparation

The dataset was prepared in Power Query. The workflow included reviewing column types, checking transaction fields, validating dates, examining unknown values, and preparing date-related fields for analysis.

The relationship between price, quantity, and order total was also checked.

### Data Quality Observations

The dataset contains records with Unknown values:

- Unknown Item records represent approximately $13,568 in revenue.
- Unknown Payment Method records represent approximately $18,906.50 in revenue.

These categories overlap in some transactions, so their revenue amounts should not be added together. The records were retained as a data-quality consideration rather than silently excluded.

## Key DAX Measures

### Total Revenue

```dax
Total Revenue =
SUM('restaurant_sales_dataset'[Order Total])
```

### Total Orders

```dax
Total Orders =
DISTINCTCOUNT('restaurant_sales_dataset'[Order ID])
```

### Units Sold

```dax
Units Sold =
SUM('restaurant_sales_dataset'[Quantity])
```

### Average Order Value

```dax
Average Order Value =
DIVIDE(
    [Total Revenue],
    [Total Orders],
    0
)
```

## Dashboard KPIs

| KPI | Result |
|---|---:|
| Total Revenue | $340,617.50 |
| Total Orders | 17,104 |
| Units Sold | 51,554 |
| Average Order Value | $19.91 |
| Unique Customers | 100 |

## Dashboard Visualizations

<img width="734" height="413" alt="Restaurant Dashboard" src="https://github.com/user-attachments/assets/a13d9894-8d90-4193-bccf-3b751ae47ff3" />

The interactive dashboard includes:

- Total Revenue by Item
- Total Revenue by Month and Year
- Total Revenue by Year
- Total Revenue by Category
- Total Revenue by Customer ID
- Total Revenue by Payment Method

Interactive slicers allow users to filter the dashboard by Category, Item, Year, Payment Method, and Month.

## Key Findings

### 1. Product Performance

Grilled Chicken generated $39,525, Pasta Alfredo $39,480, and Steak $36,680. Together, these three products generated approximately $115,685, or 34% of total revenue.

### 2. Category Performance

Main Dishes generated $160,553, representing approximately 47.1% of total revenue. Drinks contributed $22,588.50, or approximately 6.6%.

### 3. Year-over-Year Performance

Revenue declined from $174,102 in 2022 to $166,515.50 in 2023, a decrease of approximately 4.36%.

### 4. Monthly Performance

March was the strongest month when both years were combined, generating approximately $30,681.50. February was the weakest, at approximately $25,431.

### 5. Customer Contribution

The dataset contains 100 unique customers. The top 10 customers account for approximately 11.8% of total revenue, indicating that revenue is not heavily concentrated among a small group.

### 6. Payment Methods

Cash contributed 32.43% of revenue, Credit Card 31.29%, Digital Wallet 30.73%, and Unknown 5.55%.

## Business Recommendations

1. Protect the availability and quality of high-performing products.
2. Introduce meal bundles and add-on offers to increase Average Order Value.
3. Investigate the decline in revenue between 2022 and 2023.
4. Use monthly sales patterns to plan promotions and inventory.
5. Develop loyalty initiatives for repeat and high-value customers.
6. Improve transaction data capture to reduce Unknown item and payment records.

## Conclusion

This project demonstrates how Power BI can transform restaurant transaction data into an interactive business intelligence solution. The analysis identifies key revenue drivers, highlights changes in sales performance, and translates findings into practical recommendations.

The project demonstrates skills in data preparation, DAX, dashboard development, data storytelling, and business analysis.

## Repository Structure

```text
Restaurant-Sales-Performance-Analysis/
├── README.md
├── dataset/
│   └── restaurant_sales_dataset.csv
├── powerbi/
│   └── Restaurant_Sales_Performance.pbix
├── screenshots/
│   └── dashboard.png
└── documentation/
    └── project_documentation.pdf
```

Only include files that you actually upload. Confirm that you have permission to share the dataset before publishing it publicly.
