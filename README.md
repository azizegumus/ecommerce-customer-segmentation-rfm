# ecommerce-customer-segmentation-rfm

An end-to-end data analytics project performing rule-based customer segmentation using the **RFM (Recency, Frequency, Monetary)** framework on UK-based online retail transaction data.

---

## 🎯 Project Overview
The objective of this project is to analyze customer purchasing behavior (how recently they purchased, how often, and how much they spent) to categorize them into actionable business segments and develop targeted marketing strategies.

## 🛠️ Tech Stack & Libraries
- **Language:** Python
- **Libraries:** Pandas, NumPy, Matplotlib, Seaborn
- **Environment:** Google Colab / Jupyter Notebook

---

## 📈 Methodology (The RFM Framework)

1. **Data Preprocessing & Cleaning:**
   - Handled missing values (removed records with missing `CustomerID`).
   - Filtered out canceled transactions (invoices starting with 'C').
   - Calculated total transaction spend (`TotalPrice = Quantity * UnitPrice`).

2. **RFM Metrics Calculation:**
   - **Recency:** Number of days since the customer's last purchase relative to the analysis date.
   - **Frequency:** Total count of unique completed orders per customer.
   - **Monetary:** Total monetary value spent by the customer.

3. **Scoring (1 to 5):**
   - Transformed raw metrics into standardized quantiles using `pd.qcut`.
   - **Recency Score:** Inverted scale (1 = inactive for a long time, 5 = purchased very recently).
   - **Frequency & Monetary Scores:** Standard scale (1 = low, 5 = high activity/value).
   - **RFM Score:** Formed by concatenating Recency and Frequency scores (e.g., `'55'`, `'12'`).

4. **Customer Segmentation Mapping:**
   - Mapped 2-digit RFM scores to strategic behavioral segments using regular expressions.

---

## 👥 Key Customer Segments & Business Strategies

| Segment | Behavior Profile | Recommended Action |
| :--- | :--- | :--- |
| 🏆 **Champions** | Bought recently, buy often, and spend the most. | Reward them with VIP loyalty programs, early product releases, and brand advocacy perks. |
| 💎 **Loyal Customers** | Responsive to promotions, consistent order frequency. | Upsell higher-value products and offer personalized loyalty incentives. |
| ⚠️ **At Risk** | Purchased frequently in the past, but haven't returned recently. | Send "We Miss You" win-back campaigns and personalized discount incentives. |
| 💤 **Hibernating** | Low spenders who made infrequent purchases a long time ago. | Re-engage with relevant low-cost email campaigns or avoid high ad-spend allocation. |
| 🌱 **New Customers** | High recency but low frequency (first-time buyers). | Build onboarding journeys and offer incentives for their second purchase. |

---

## 🚀 How to Run
1. Clone this repository:
   ```bash
   git clone [https://github.com/YOUR_USERNAME/ecommerce-customer-segmentation-rfm.git](https://github.com/YOUR_USERNAME/ecommerce-customer-segmentation-rfm.git)
