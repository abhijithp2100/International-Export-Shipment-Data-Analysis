# International Export Shipment Data Analysis

## Project Overview

This project performs an in-depth Exploratory Data Analysis (EDA) on an international export shipment dataset to uncover patterns in trade volume, shipping costs, delivery performance, and logistics efficiency.

The dataset contains **3,000 shipment records** across multiple countries, commodities, transport modes, and carriers. The objective is to transform raw shipment data into actionable business insights using Python.

---

## Project Structure

```
international-export-shipment-analysis/
│
├── data/
│   └── export_shipment_dataset.csv
│
├── scripts/
│   └── International Export Shipment Data Analysis.ipynb
│
└── README.md
```

---

## Dataset Summary

- Total Records: **3,000 shipments**
- Total Columns: **13 features**
- Time Dimension: Shipment Date
- Geographic Dimension: Multiple destination countries
- Logistics Variables: Transport Mode, Carrier, Container Type
- Financial Metrics: Export Value (USD), Shipping Cost (USD)
- Operational Metric: Delivery Days

### Key Columns

- Date  
- Country  
- Port_of_Loading  
- Commodity  
- Quantity_Tons  
- Export_Value_USD  
- Shipping_Cost_USD  
- Transport_Mode  
- Delivery_Days  
- Trade_Term_INCOTERM  
- Container_Type  
- Carrier  

---

## Data Cleaning Process

### 1. Column Removal
- Dropped `Shipment_ID` (identifier, no analytical value)

### 2. Missing Values Handling
Null values detected in:
- Quantity_Tons
- Export_Value_USD
- Shipping_Cost_USD
- Delivery_Days

Since distributions were skewed, missing values were replaced using **median imputation**.

Result:
- 100% null values removed.

### 3. Outlier Detection & Removal

- Method Used: IQR (Interquartile Range)
- Columns Analyzed:
  - Quantity_Tons
  - Export_Value_USD
  - Shipping_Cost_USD
  - Delivery_Days

Outliers detected:
- 0 in Quantity_Tons
- 20 in Export_Value_USD
- 20 in Shipping_Cost_USD
- 20 in Delivery_Days

All detected outliers were removed.

---

## Feature Engineering

New Features Created:

- Year (extracted from Date)
- Encoded categorical variables (One-Hot Encoding)
- Scaled numerical features using MinMaxScaler
- Correlation matrix for numerical analysis

---

## Exploratory Data Analysis

### Shipment Trends

- Identified top exported commodities by total quantity.
- Determined Top 10 countries by total export value.
- Analyzed yearly export value trends.

Key Insight:
Export value shows a consistent upward trend year-over-year, indicating growth in shipment scale and trade activity.

---

### Cost & Quantity Patterns

- Positive relationship between Quantity_Tons and Export_Value_USD.
- Moderate relationship between Shipping_Cost_USD and Delivery_Days.
- Heavier shipments generally incur higher transport costs.

---

### Delivery Performance

- Average delivery time: Approximately 12–18 days.
- Sea transport shows longest delivery times.
- Air transport is fastest but significantly more expensive.
- Delivery time varies across carriers.

---

### Logistics Insights

Transport Mode Distribution:
- Sea: Most frequently used
- Air: Second most used
- Road: Used primarily for regional shipments

Carrier Analysis:
- Compared average export value by carrier.
- Compared average shipping cost by carrier.
- Identified variation in cost-efficiency between logistics providers.

---

## Correlation Analysis

Correlation heatmap revealed:

- Strong positive correlation between Quantity_Tons and Export_Value_USD.
- Weak to moderate correlation between Shipping_Cost_USD and Delivery_Days.
- No strong multicollinearity detected among major financial features.

---

## Tools & Technologies Used

- Python
- Pandas
- NumPy
- Seaborn
- Matplotlib
- Scikit-learn

---

## Project Outcomes

- Cleaned and standardized 3,000 shipment records.
- Removed all missing values.
- Detected and eliminated 60 total outlier entries.
- Identified shipment, cost, and delivery performance patterns.
- Generated actionable logistics insights from raw trade data.

---

## Conclusion

This project demonstrates the ability to:

- Perform structured data cleaning
- Apply statistical techniques (IQR, correlation analysis)
- Conduct business-focused EDA
- Translate numerical findings into operational insights
- Prepare data for future machine learning applications

The analysis provides a data-driven view of international export operations, highlighting cost structures, transport trade-offs, and logistics efficiency patterns.
