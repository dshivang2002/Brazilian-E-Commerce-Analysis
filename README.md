# 🛒 Brazilian E-Commerce (Olist) — EDA Insights & Recommendations

> **Dataset:** Olist Brazilian E-Commerce Public Dataset  
> **Scope:** 99,441 customers | 99,441 orders | 32,951 products | 73 categories | 112,650 order items  
> **Period:** 2016 – 2018

---
In this project, I analyze a Brazilian e-commerce dataset to understand customer behavior, payment patterns, delivery performance, and product trends.

The goal of this analysis is to explore the dataset and extract meaningful insights that can help e-commerce businesses improve their operations , customer satisfaction and manage inventory.

Tools used in this analysis include Python, Pandas, and data visualization libraries

# 🗂️ Dataset Structure Overview
This dataset contains information about e-commerce orders made in Brazil between 2016 and 2018.

It includes multiple tables such as:

```
olist_customers_dataset.csv       → 99,441 rows | 5 cols
olist_orders_dataset.csv          → 99,441 rows | 8 cols
olist_order_items_dataset.csv     → 112,650 rows | 7 cols
olist_products_dataset.csv        → 32,951 rows | 9 cols
olist_sellers_dataset.csv         → seller info
olist_order_payments_dataset.csv  → 103,886 rows | 5 cols
olist_order_reviews_dataset.csv   → reviews with scores 1–5
olist_geolocation_dataset.csv     → lat/lng for zip codes
product_category_name_translation.csv → PT → EN category names
```

These tables provide insights into customer behavior, payment methods, delivery times, and product performance.

## Schema :

<img width="1786" height="1075" alt="HRhd2Y01" src="https://github.com/user-attachments/assets/ae2e75ef-26fb-4750-8ffe-b1c7b10e4962" />

## 9. Recommendations to Improve the Platform
 
### 🚚 Logistics & Delivery
1. **Regional fulfillment centers**: Build or partner with warehouses in the Northeast (Salvador, Fortaleza, Recife) and North regions to reduce delivery times for non-SP customers.
2. **Delivery time accuracy**: The 8% late delivery rate in top cities needs attention — invest in better delivery estimation algorithms using real-time carrier data.
3. **Prioritize bulky category logistics**: Office furniture and large appliances take 20 days on average. Dedicated large-item logistics partners (similar to dedicated freight) can help.
4. **Last-mile tracking**: Give customers real-time tracking notifications to improve perceived experience even when delays occur.
 
### 💳 Payments & Revenue
5. **Promote debit card & PIX**: Debit card usage is only 1.5%. With Brazil's PIX instant payment system (launched post-dataset), there's a major opportunity to reduce dependence on credit cards and boleto processing costs.
6. **Voucher upselling**: Since voucher users have the smallest basket (R$65.70), create targeted offers/bundles to increase their order value.
7. **Installment-driven promotions for high-ticket items**: Leverage the existing credit card installment culture to promote computers, appliances, and furniture with "0% interest, 12x" campaigns.
 
### 📦 Product & Category Strategy
8. **Invest in bottom categories strategically**: CDs/DVDs and arts & crafts have very low volume but high satisfaction scores — niche marketing or curated collections could unlock growth.
9. **Fix Security & Services (2.50 avg. rating)**: Investigate why this category has the lowest reviews. Likely causes: difficult installation, misleading product descriptions, or compatibility issues. Improve listings and offer installation support.
10. **Diapers & Hygiene** (3.38 avg. rating + 39 orders): A high-frequency essential product with poor satisfaction. Investigate delivery damage and packaging quality.
 
### 🌍 Geographic Expansion
11. **Seller recruitment in underserved regions**: Actively recruit sellers from Northeast and North Brazil to shorten supply chains and reduce freight costs for those customers.
12. **Targeted marketing in SP-adjacent states**: States like GO, ES, and BA have significant customer bases but proportionally fewer sellers. Marketing campaigns targeting those regions, backed by better seller coverage, could accelerate growth.
 
### ⭐ Customer Experience & Reviews
13. **Post-delivery review nudging**: With 87,656 orders missing a review comment title, implement smart prompts to collect more feedback — richer feedback drives better seller accountability.
14. **Category-specific quality control**: For low-scoring categories (office furniture, fashion male clothing, home comfort), implement seller scorecards and minimum quality thresholds.
15. **Leverage high-performing categories**: Fashion children's clothes and books have excellent scores (4.5+). Feature them prominently in recommendations and homepage banners to drive discovery.
 
---

*Analysis performed using Python (pandas, matplotlib, seaborn). All figures derived from Olist's public dataset on Kaggle.*
