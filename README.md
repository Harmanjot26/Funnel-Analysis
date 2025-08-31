# 📊 Funnel Analysis using SQL

## 🔍 Project Overview

This project performs a detailed **funnel analysis** using event-level user interaction data to identify drop-off points in a typical e-commerce journey (from `page_view` to `purchase`). It leverages **advanced SQL techniques** to analyze how users from the top 3 countries — 🇺🇸 United States, 🇮🇳 India, and 🇨🇦 Canada — behave across various funnel stages.

---

## 🎯 Objectives

- Clean and deduplicate raw event data (one event per user per step)
- Focus only on key funnel events (e.g., `page_view`, `view_item`, `add_to_cart`, `purchase`)
- Analyze event frequency across top countries
- Identify key **drop-off stages** and **country-wise user behavior**
- Generate a ranked, comparative funnel report

---

## 🛠️ Tech Stack

- **Language:** SQL (Google BigQuery syntax)
- **Data Source:** `turing_data_analytics.raw_events`
- **Techniques Used:**
  - Common Table Expressions (CTEs)
  - Window Functions (`ROW_NUMBER()`, `RANK()`)
  - Country & event-level grouping
  - Deduplication and filtering
  - Ranking by engagement

---

## 🗂️ Funnel Events Considered

1. `page_view`
2. `view_item`
3. `add_to_cart`
4. `add_shipping_info`
5. `add_payment_info`
6. `purchase`

These represent a typical customer journey in an e-commerce platform.

---

## 🔄 Step-by-Step Process

| Step | Description |
|------|-------------|
| **1. Deduplicate Events** | Use `ROW_NUMBER()` to keep only the first instance of each event per user |
| **2. Filter Events & Countries** | Focus only on the top 3 active countries and relevant funnel events |
| **3. Group & Rank Events** | Count how often each event occurs, globally and per country |
| **4. Build Final Funnel Table** | Join country-wise breakdowns to get a comparative analysis of each funnel step |

---

## 📈 Sample Output

| Category | Event Name       | 🇺🇸 US Events | 🇮🇳 India Events | 🇨🇦 Canada Events |
|----------|------------------|--------------|------------------|-------------------|
| Shopping | page_view        | 45,312       | 39,142           | 12,430            |
| Shopping | view_item        | 30,102       | 22,510           | 7,120             |
| Shopping | add_to_cart      | 18,545       | 12,843           | 4,870             |
| Shopping | add_payment_info | 10,012       | 5,205            | 1,911             |
| Shopping | purchase         | 7,145        | 2,103            | 905               |

✅ *Shows clear drop-off trend and allows business to take region-specific action.*

---

## 🔍 Key Insights

- **United States** had the highest engagement at every stage of the funnel.
- **India** showed major drop-offs post `add_to_cart`, hinting at friction during checkout.
- **Canada** had the lowest absolute engagement, but a more consistent funnel progression.

---

## 🧠 What I Learned

- How to clean and structure real-world event data for analysis
- Practical use of window functions like `ROW_NUMBER()` and `RANK()` in SQL
- Funnel analysis logic from scratch
- How to derive **actionable insights** from data, not just numbers

---

## 💡 Future Work

- Visualize the funnel using Python (Matplotlib / Seaborn)
- Create a dashboard in Power BI / Tableau for stakeholder presentation
- Run A/B test comparisons between countries or time periods
- Predict conversion probabilities using ML models



