# 🛒 Cartly: E-Commerce Conversion Funnel & User Behavior Analysis

> A complete end-to-end data analytics project on a fictional digital products e-commerce platform — built with Python, Pandas, and Seaborn.

---

## 📖 Project Overview

**Cartly** is a fictional e-commerce company that sells **digital products** — online courses, e-books, software templates, and productivity tools. The business has been growing but has questions about:

- Why are most visitors leaving without buying?
- Which products are driving revenue and which are underperforming?
- How are users behaving across different devices?
- Where exactly in the purchase journey are users dropping off?

This project answers all of these questions using real data analysis techniques, visualisations, and actionable business insights.

---

## 🎯 Business Problem

Despite having **100,000 sessions** and **500,000 user events**, Cartly's revenue conversion from site visitors is low. The goal of this project is to:

1. Understand **who** Cartly's users are and how they behave
2. Identify **which products** generate revenue and which ones don't convert despite high interest
3. Map the **conversion funnel** from first page view to purchase
4. Pinpoint the **biggest drop-off points** and recommend targeted fixes

---

## 📁 Project Structure

```
cartly-analytics/
│
├── data/                          
│   ├── users.csv
│   ├── sessions.csv
│   ├── events.csv
│   ├── products.csv
│   └── transactions.csv
│
├── notebooks/
│   ├── 01_data_overview.ipynb         
│   ├── 02_user_behavior_analysis.ipynb
│   ├── 03_product_revenue_analysis.ipynb
│   └── 04_funnel_analysis.ipynb       
│
├── reports/                       
│
└── README.md                      
```

---

## 📊 Dataset Description

| File | Rows | Description |
|------|------|-------------|
| `users.csv` | 10,000 | User profiles — demographics, device type, signup date, acquisition source |
| `sessions.csv` | 100,000 | Web sessions — start/end time, pages viewed, time spent, bounce flag |
| `events.csv` | 500,000 | Granular user actions — page_view, product_click, add_to_cart, purchase_click |
| `products.csv` | 200 | Product catalog — category, sub-category, price, rating, active status |
| `transactions.csv` | 30,000 | Completed & failed purchases — amount, discount, payment method, order status |

### Column Reference

**users.csv**
- `user_id` — Unique user identifier
- `signup_date` — When the user registered
- `country`, `city` — Location
- `age_group`, `gender` — Demographics
- `device_type` — Mobile / Desktop / Tablet
- `acquisition_source` — How they found Cartly (Organic, Paid Ads, Referral, Social)

**sessions.csv**
- `session_id`, `user_id` — Identifiers
- `session_start_time`, `session_end_time`, `session_date` — Time fields
- `pages_viewed` — Number of pages in this session
- `time_spent_seconds` — Session duration
- `bounce_flag` — 1 if user bounced, 0 otherwise
- `traffic_source` — Organic / Paid / Social / Direct

**events.csv**
- `event_id`, `user_id`, `session_id`, `product_id` — Identifiers
- `event_time` — Timestamp of the event
- `event_type` — page_view / product_click / add_to_cart / purchase_click
- `page_name` — Which page triggered the event

**products.csv**
- `product_id`, `product_name` — Identifiers
- `category`, `sub_category` — Product taxonomy
- `price` — Listed price (₹)
- `rating` — Average user rating (1–5)
- `created_date` — When the product was added
- `is_active` — 1 = active, 0 = inactive

**transactions.csv**
- `transaction_id`, `user_id`, `product_id` — Identifiers
- `purchase_date` — Date of purchase
- `quantity` — Units purchased
- `amount` — Net amount paid (after discount)
- `discount_amount` — Discount applied
- `payment_method` — Card / NetBanking / UPI / Wallet
- `order_status` — Success / Failed / Cancelled

---

## 🔑 Key Insights

### 👥 User Insights
- **65% of users access Cartly via Mobile** — this is the dominant device, yet mobile users show worse engagement metrics than desktop
- **Organic is the top acquisition source** — word-of-mouth and SEO are working well; paid ads may need ROI review
- **Bounce rate is highest on mobile** — users arrive and leave without engaging, signalling UX friction

### 📈 Session & Engagement Insights
- **Desktop users spend more time per session** than mobile users — confirming the need for mobile UX improvements
- **Organic and Direct traffic users have the longest sessions** — they arrive with intent and explore deeply
- **DAU trends** show clear patterns of high and low engagement periods

### 💰 Revenue Insights
- **The top 3 categories drive the majority of revenue** — these need continued product investment
- **High-view, low-conversion products** represent a significant untapped revenue opportunity
- **Top 10% of customers account for a disproportionate share of revenue** — a VIP retention strategy is warranted
- **Discounts are significant** — blanket promotions are hurting margins; targeted discounts would be more efficient

---

## 🔽 Funnel Findings

The Cartly funnel is:
```
Page View → Product Click → Add to Cart → Purchase Click
```

| Stage | Users | Step Conversion |
|-------|-------|-----------------|
| Page View | ~9,700 | — |
| Product Click | ~5,800 | ~60% |
| Add to Cart | ~3,500 | ~60% |
| Purchase Click | ~1,800 | ~51% |

**Overall conversion rate: ~1.3% of all page-viewing users complete a purchase**

### Critical Drop-off Points

1. **Page View → Product Click** — The biggest absolute drop. Most visitors never engage with a specific product. This is a **discoverability & relevance problem**.

2. **Add to Cart → Purchase Click** — The most costly drop-off. Users with clear intent abandon at the checkout. This is a **friction & trust problem**.

3. **Mobile vs Desktop** — Desktop users convert at a higher rate despite fewer sessions. Mobile UX is the single biggest conversion bottleneck.

4. **Cart Abandonment Rate** — A significant percentage of users who add items to cart never complete the purchase — industry average is ~70%, and Cartly is in this range.


---

## 🛠️ Tools & Libraries

| Tool | Purpose |
|------|---------|
| **Python 3.10+** | Core language |
| **pandas** | Data loading, cleaning, and manipulation |
| **numpy** | Numerical calculations |
| **matplotlib** | Low-level chart creation |
| **seaborn** | Statistical visualisations |
| **Jupyter Notebook** | Interactive, story-driven analysis |

---

## 📸 Output Charts

After running all notebooks, you will find these charts in `reports/`:

| Chart | Notebook | Description |
|-------|----------|-------------|
| `01_users_overview.png` | NB01 | Device type & acquisition source distribution |
| `01_sessions_traffic.png` | NB01 | Traffic source breakdown |
| `01_events_distribution.png` | NB01 | Event type volume chart |
| `01_products_price_dist.png` | NB01 | Price range by category |
| `01_transactions_overview.png` | NB01 | Payment method & order status |
| `02_dau.png` | NB02 | Daily Active Users with 7-day rolling avg |
| `02_mau.png` | NB02 | Monthly Active Users trend |
| `02_bounce_rate.png` | NB02 | Bounce rate by device & traffic source |
| `02_session_duration.png` | NB02 | Session duration by device & source |
| `02_pages_viewed.png` | NB02 | Pages per session distribution |
| `02_signups.png` | NB02 | Monthly new user registrations |
| `02_top_countries.png` | NB02 | Top 10 countries by user count |
| `03_monthly_revenue.png` | NB03 | Revenue trend over time |
| `03_category_revenue.png` | NB03 | Revenue by category (bar + pie) |
| `03_top_products_revenue.png` | NB03 | Top 10 products by revenue |
| `03_views_vs_purchases.png` | NB03 | Views vs purchases scatter (with conversion rate) |
| `03_top_customers.png` | NB03 | Top 10 customers by lifetime spend |
| `03_discounts.png` | NB03 | Average discount by category |
| `04_funnel.png` | NB04 | Funnel bar chart + step conversion rates |
| `04_dropoff.png` | NB04 | User drop-off volume at each stage |
| `04_funnel_by_day.png` | NB04 | Funnel activity & conversion by day of week |
| `04_funnel_by_device.png` | NB04 | Funnel stages and conversion by device |
| `04_cart_abandonment.png` | NB04 | Cart abandonment pie chart |
| `04_full_funnel.png` | NB04 | Full funnel waterfall visualisation |

---

*Built as a portfolio project for data analytics learning and interview preparation.*
