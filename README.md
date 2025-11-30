## Retail Sales Analytics EDA 

This repository contains a full Exploratory Data Analysis (EDA) of a retail transactions dataset as part of the PGDSBA (IITG) Program.
  
The goal is to uncover insights related to:

- Customer behavior  
- Promotion performance  
- Seasonal trends  
- Revenue distribution  
- Product-level patterns  

All analysis was completed in Google Colab using Python (Pandas, Matplotlib, Seaborn).

---

 ## Repository Structure
 retail-analysis-python/
│
├─ data/
│ └─ Retail_Transactions_Dataset.csv (NOT uploaded due to 161 MB size)
│
├─ notebooks/
│ └─ retail_analysis.ipynb
│
├─ scripts/
│ └─ RetailAnalysis.py
│
├─ visuals/
│ ├─ transactions_per_city.png
│ ├─ payment_method_distribution.png
│ ├─ monthly_revenue_trend.png
│ └─ season_customercategory_heatmap.png
│
└─ README.md


---

## OBJECTIVE

To explore and analyze retail transaction data and derive insights around:

Customer purchasing patterns <br>
Best-performing products <br>
Seasonal & regional trends <br>
Promotion & discount impact on revenue <br>
Payment behavior and store-type comparisons <br>

The goal is to translate raw data into business-ready recommendations.

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

## DATA CLEANING & FEATURE ENGINEERING

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
df = df.drop_duplicates()```python

---

## KEY INSIGHTS

| Category            | Insight                                               |
| ------------------- | ----------------------------------------------------- |
|  Sales Trend      | Seasonal patterns clearly influence spending          |
|  Store Preference | Certain seasons favor specific store types            |
|  Top Products     | Few product categories dominate purchases             |
|  Payment Behavior | Payment preference varies by customer tier            |
|  Promotions       | Some promotions generate significantly higher revenue |

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
sns.heatmap(revenue_by_season, annot=True, cmap="Blues")```python

---

## TOP FINDINGS

* **Season with highest revenue:**
  → (Insert result here once extracted)

* **Most profitable promotion type:**
  → (Insert best performing promo)

* **Top customer category by spend:**
  → (Insert Gold/Silver/Bronze comparison)

* **City with the highest number of transactions:**
  → (Insert top city name)

* **Preferred payment method overall:**
  → (Based on % values from output)

---

## BUSINESS RECOMMENDATIONS

| Recommendation                                           | Why it Matters                                   |
| -------------------------------------------------------- | ------------------------------------------------ |
| Increase inventory & marketing during peak season        | Maximizes revenue where demand is proven highest |
| Scale the highest-performing promotion                   | Faster revenue lift with existing customer base  |
| Target Gold category customers with loyalty rewards      | Highest average spending → improve retention     |
| Push online store campaigns during strong digital months | Seasonal preference supports conversion growth   |
| Optimize payment gateway for most preferred method       | Reduces checkout friction → increases sales      |

These insights could guide real strategic decisions in **pricing, promotions, inventory allocation, marketing & store planning**.

---

## TECH STACK

| Tool                     | Purpose                         |
| ------------------------ | ------------------------------- |
| **Python**               | Core analysis                   |
| **Pandas / NumPy**       | Data manipulation & aggregation |
| **Matplotlib / Seaborn** | Visual storytelling             |
| **Jupyter/Google Colab** | Notebook execution              |


---

The dataset (`Retail_Transactions_Dataset.csv`) is 161 MB, which is too large for GitHub.

You can download it here:

[Download Dataset from Dropbox](https://www.dropbox.com/scl/fi/9xyxc2t07fqjm47va8gt8/Retail_Transactions_Dataset.csv?rlkey=9uur3b5u5q90i80zb7i6t9kgq&st=mnwofjv7&dl=0)



