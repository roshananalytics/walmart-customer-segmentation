# walmart-customer-segmentation
Unsupervised ML project segmenting 50,000 Walmart customers into 4 behavioural groups using K-Means clustering — includes EDA, PCA visualisation, and actionable business insights.

##  Project Overview

Customer segmentation is one of the most impactful applications of unsupervised learning in retail. This project analyses Walmart's customer purchase data to answer:

- **Who are our customers?** (demographics, behaviour)
- **How do different customer groups spend?** (purchase patterns, discounts)
- **What strategies should we apply to each group?** (business recommendations)

---

##  Repository Structure

```
walmart-customer-segmentation/
│
├── Walmart_Customer_Segmentation.ipynb   ← Main analysis notebook
├── Walmart_customer_purchases.csv        ← Raw dataset (50,000 records)
├── Walmart_customers_segmented.csv       ← Output: dataset with cluster labels
└── README.md                             ← Project documentation
```

---

## Dataset

| Feature            | Description                                      |
|--------------------|--------------------------------------------------|
| `Customer_ID`      | Unique customer identifier (UUID)                |
| `Age`              | Customer age (18–60)                             |
| `Gender`           | Male / Female / Other                            |
| `City`             | Purchase location                                |
| `Category`         | Product category (Electronics, Clothing, etc.)   |
| `Product_Name`     | Specific product purchased                       |
| `Purchase_Date`    | Date of transaction                              |
| `Purchase_Amount`  | Transaction value in USD ($10–$500)              |
| `Payment_Method`   | Credit Card / Debit Card / UPI / Cash on Delivery|
| `Discount_Applied` | Whether a discount was used (Yes/No)             |
| `Rating`           | Customer satisfaction rating (1–5)               |
| `Repeat_Customer`  | Returning customer flag (Yes/No)                 |

**Size:** 50,000 rows | 12 columns | No missing values

---

##  Methodology

```
Raw Data  →  EDA  →  Feature Engineering  →  Scaling  →  Elbow + Silhouette  →  K-Means  →  Cluster Profiling  →  Business Insights
```

### Steps

1. **Exploratory Data Analysis (EDA)**
   - Distribution plots for age, purchase amount, and ratings
   - Category, gender, and payment method breakdowns
   - Monthly revenue trend analysis

2. **Feature Engineering & Preprocessing**
   - Selected 7 features: Age, Purchase Amount, Rating, Repeat Customer, Discount Applied, Gender, Category
   - Binary encoding for Yes/No columns
   - Ordinal encoding for categorical variables
   - StandardScaler normalisation (required for distance-based clustering)

3. **Optimal Cluster Selection**
   - Elbow Method (Inertia vs. k) for k = 2–10
   - Silhouette Score analysis
   - **Result: k = 4** chosen based on elbow inflection and score convergence

4. **K-Means Clustering**
   - `n_clusters=4`, `n_init=10`, `random_state=42`
   - PCA 2-D projection for cluster visualisation

5. **Cluster Profiling & Naming**
   - Aggregated statistics per cluster
   - Radar chart comparison across normalised metrics
   - Category and payment breakdown per segment

---

## Customer Segments Identified

| Cluster | Segment Name         | Avg Age | Avg Spend | Repeat % | Key Trait            |
|---------|----------------------|---------|-----------|----------|----------------------|
| 0       | Budget Shoppers      | ~39     | Lower     | Moderate | Price-sensitive       |
| 1       | High-Value Loyalists | ~39     | Highest   | High     | Premium, repeat buyers|
| 2       | Occasional Explorers | ~39     | Moderate  | Low      | Infrequent, varied    |
| 3       | Young Deal Seekers   | ~38     | Moderate  | Moderate | Discount-driven, UPI  |

---

## Business Recommendations

| Segment               | Strategy                                                                 |
|-----------------------|--------------------------------------------------------------------------|
| 🔵 Budget Shoppers    | Promotional campaigns, bulk-buy offers, loyalty points                   |
| 🟢 High-Value Loyalists | VIP rewards, early product access, exclusive member discounts           |
| 🔴 Occasional Explorers | Re-engagement emails, personalised recommendations, push notifications |
| 🟣 Young Deal Seekers | Flash sales, student discounts, UPI cashback partnerships                |

---

## 📈 Key Visualisations

The notebook produces **11 plots** including:
- Age & Purchase Amount distributions
- Category, Gender, Payment Method pie charts
- Monthly revenue trend
- Elbow & Silhouette score charts
- Cluster scatter plot (Age vs. Purchase Amount)
- PCA 2-D cluster projection
- Radar chart for cluster comparison
- Stacked bar charts for category & payment per cluster
- Segment count horizontal bar chart

---

## ⚙️ Installation & Setup

### Prerequisites
- Python 3.10+
- Jupyter Notebook / JupyterLab

### Install Dependencies

```bash
pip install pandas numpy matplotlib seaborn scikit-learn jupyter
```

### Run the Notebook

```bash
git clone https://github.com/your-username/walmart-customer-segmentation.git
cd walmart-customer-segmentation
jupyter notebook Walmart_Customer_Segmentation.ipynb
```

---

## 🛠️ Tech Stack

| Tool           | Purpose                        |
|----------------|-------------------------------|
| Python 3.10    | Core language                 |
| Pandas         | Data manipulation             |
| NumPy          | Numerical operations          |
| Matplotlib     | Base visualisation            |
| Seaborn        | Statistical visualisation     |
| scikit-learn   | Preprocessing, K-Means, PCA  |
| Jupyter Notebook | Interactive environment     |

---

## 📄 License

This project is open source under the [MIT License](LICENSE).

---

## 👤 Author

**Roshan Basnet**  
Master of Data Analytics — University of Niagara Falls Canada  
[LinkedIn]https://www.linkedin.com/in/roshanbasnetanalytics · [GitHub]https://github.com/roshananalytics

---

> ⭐ If you found this project useful, please consider giving it a star!
