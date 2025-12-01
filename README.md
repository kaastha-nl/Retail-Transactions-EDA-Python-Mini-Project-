## Retail Sales Analytics EDA 

## Project Motivation

Retail businesses rely heavily on customer behaviour, seasonal purchasing cycles, promotional effectiveness, and city-wise demand. The objective of this project is to analyze a real retail transaction dataset to uncover meaningful patterns that could guide business decisions such as inventory planning, marketing focus areas, promotional strategy optimisation and customer segmentation.

This project demonstrates end-to-end exploratory analysis, data cleaning, feature enrichment, insight extraction and visualisation to better understand what drives revenue and purchase behaviour in retail environments as part of the PGDSBA (IITG) Program.

---

## Python Libraries Used

pandas, numpy

matplotlib, seaborn

---

## Repository Structure <br>
 
| File/Folder                         | Description                                                     |
|------------------------------------|-----------------------------------------------------------------|
| `Retail_Sales_Analytics_EDA.ipynb` | Jupyter notebook containing all analysis, cleaning & visuals   |
| `visuals/`                         | Folder containing exported plots for interpretation            |
| `scripts/`                         | Contains `retail_analysis.py` automation & helper scripts      |
| `README.md`                        | Documentation describing objectives, approach and results      |
| `Retail_Transactions_Dataset.csv`  | Dataset used for the analysis (not uploaded if size-restricted)|

The dataset (`Retail_Transactions_Dataset.csv`) is 161 MB, which is too large for GitHub.

You can download it here:

[Download Dataset from Dropbox](https://www.dropbox.com/scl/fi/9xyxc2t07fqjm47va8gt8/Retail_Transactions_Dataset.csv?rlkey=9uur3b5u5q90i80zb7i6t9kgq&st=mnwofjv7&dl=0)


---

## Understanding the Business Context

The dataset represents retail store transactions across multiple cities with details on products sold, customer categories, pricing, discounts, promotions, payment methods and seasons.

A business wouldn't only want to know "what happened" in the past, but also why sales behaved the way they did and where opportunities exist to maximise profitability.
This analysis aims to support such decision-making through structured exploratory work.

---

## DATASET OVERVIEW

| Feature             | Description                                        |
| ------------------- | -------------------------------------------------- |
| `Transaction_ID`    | Unique ID for each sale                            |
| `Date`              | Date of purchase                                   |
| `Customer_Name`     | Customer identifier                                |
| `Customer_Category` | Tier/segment of customer (e.g. Gold/Silver/Bronze) |
| `Total_Items`       | Quantity purchased                                 |
| `Total_Cost`        | Total amount spent                                 |
| `Product`           | Product purchased                                  |
| `Payment_Method`    | Credit card / Cash / Wallet / UPI etc              |
| `Store_Type`        | Online vs Physical store                           |
| `Discount_Applied`  | Whether discount was applied                       |
| `Promotion`         | Type of promotion                                  |
| `City`              | Location of purchase                               |
| `Season`            | Season during the transaction                      |

---

## DATA CLEANING 

| Step                 | Action                                 |
| -------------------- | -------------------------------------- |
| Handle dates         | Converted `Date` → datetime format     |
| Time-based breakdown | Extracted `Year`, `Month`, `DayOfWeek` |
| Quality checks       | Removed duplicates                     |
| Grouping logic       | Customer & season segmentation         |
| Missing values       | Reviewed & validated completeness      |

Example code included:
```python
df["Date"] = pd.to_datetime(df["Date"])
df["Year"] = df["Date"].dt.year
df["Month"] = df["Date"].dt.month
df["DayOfWeek"] = df["Date"].dt.day_name()
df = df.drop_duplicates()
```

---

## Analysis Performed

Total transaction volume and revenue estimation

Top customer segments by spend level

Most purchased product categories

City-wise sales distribution

Average spend with and without discount influence

Promotion effectiveness analysis

Store-type preference by season

Payment method usage trend

Revenue comparison across seasons

---

##  VISUAL INSIGHTS

| Visualization                        | What it Shows                                   |
| ------------------------------------ | ----------------------------------------------- |
| Seasonal Spend Bar Chart             | Which seasons generate highest revenue          |
| Transactions per City                | Location-based demand distribution              |
| Payment Method Pie Chart             | Customer preference in payment behaviour        |
| Yearly Revenue Trend Line            | Revenue growth or decline over time             |
| Heatmap (Season × Customer Category) | Which customer groups spend more in each season |

Example code included:

```python
sns.barplot(x=avg_spend_season.index, y=avg_spend_season)
sns.countplot(data=df, x="Season", hue="Store_Type")
sns.heatmap(revenue_by_season, annot=True, cmap="Blues")
```

---

## Summary

Seasonal demand significantly drives revenue, indicating that marketing efforts must be intensified during peak sales periods.

city-wise behaviour reflects strong revenue concentration, suggesting regional targeting and inventory differentiation.

Top promotions display measurable revenue impact and can be prioritised in future discount cycles.

Customer segmentation by spend level highlights where loyalty, retention and reward programs deliver maximum return.

Payment method preference reveals checkout optimisation opportunities to reduce friction and abandonment.

Discounts influence order value positively, implying promotional strategy alignment with purchasing psychology.

Store-type and season interaction supports operational capacity planning in both physical and digital channels.

---

## How to Run this Project

- Download the repository.

- Download Retail_Transactions_Dataset.csv

- Install dependencies:pandas numpy matplotlib seaborn

- Open and run the python notebook


## TECH STACK

| Tool                     | Purpose                         |
| ------------------------ | ------------------------------- |
| **Python**               | Core analysis                   |
| **Pandas / NumPy**       | Data manipulation & aggregation |
| **Matplotlib / Seaborn** | Visual storytelling             |
| **Jupyter/Google Colab** | Notebook execution              |



