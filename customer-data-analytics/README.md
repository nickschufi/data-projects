# Customer Behavioral Insights in Banking Data

Group project completed for the **Customer Data Analytics** course.

## Objective

We analyze card transaction data from a digital banking partner to understand how customer spending behavior differs by usage intensity, guided by two research questions:

1. *How do heavy users (in terms of frequency) differ in their daily, weekly, and seasonal spending patterns compared to non-heavy users?*
2. *How can the bank use these differences to create timely offers and grow customer loyalty and share of wallet?*

## Data Source

Card transaction data from a digital banking partner, spanning **2021–2023**, combined into a single unified dataset covering transaction amounts, categories, timing, and location.

## Approach

1. **Data preparation**: loaded and combined three years of transaction data into one dataset. Identified the top spending categories (Transport, Shopping, Groceries, Restaurants) for focused analysis.
2. **Exploratory analysis**: Visualized overall spending distribution by category, spending trends over time (yearly, monthly, and by day of week), and seasonal patterns to detect recurring behavior.
3. **Customer segmentation (RFM + K-Means)**: Calculated Recency, Frequency, and Monetary (RFM) metrics per customer, then applied K-Means clustering to segment users by behavior. Initially tested a 2-cluster (heavy vs. normal) solution, then refined to a **3-cluster model** (heavy, normal, low users) after evaluating fit via the elbow method and inertia, the 3-cluster solution gave a clearly better fit (5'677.76 vs. the 2-cluster baseline).
4. **Segment profiling**: Merged cluster labels back into the transaction data to compare what, where, and when heavy, normal, and low users spend, using category breakdowns, geographic spending patterns, and monthly time series by segment.

## Tools & Technologies

`Python` · `pandas` · `numpy` · `matplotlib` · `seaborn` · `scikit-learn` (`KMeans`, `StandardScaler`)

## Key Findings

- Spending activity was concentrated in a handful of categories, with **Transport, Shopping, Groceries, and Restaurants** consistently emerging as the top spending segments across the dataset.
- Clear **seasonal and weekly patterns** emerged — spending fluctuated by month and varied by day of the week, with certain categories (e.g. restaurants, shopping) showing weekend spikes.
- RFM-based clustering revealed that a **3-segment model** (heavy, normal, low users) captured customer behavior better than a simple 2-segment split, giving a more precise separation for targeting.
- **Heavy users** stood out with more frequent transactions, higher total spend, and more recent activity, distinguishing them clearly from normal and low-activity users across category, geography, and timing dimensions.
- These segment-level differences point to concrete opportunities for the bank to design **timing- and category-specific offers** to increase loyalty and share of wallet among heavy users, while identifying levers to activate low-engagement customers.

## How to View

Open `Customer_data_analytics.ipynb` in Jupyter Notebook, JupyterLab, VS Code or else to explore the full analysis and code, or download and open `Customer_data_analytics.html` directly in a browser to view the pre-rendered report.

