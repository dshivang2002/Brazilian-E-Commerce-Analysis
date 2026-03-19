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

---

## 1. Customer Geography Analysis
 
### Findings
- The dataset contains **99,441 unique customers** spread across **27 states** and **4,119 cities**.
- **São Paulo (SP)** dominates with **41,746 customers (~42%)** — more than 3× the second-largest state.
- **Top 5 States by Customer Count:**
 
| Rank | State | Customers |
|------|-------|-----------|
| 1 | SP (São Paulo) | 41,746 |
| 2 | RJ (Rio de Janeiro) | 12,852 |
| 3 | MG (Minas Gerais) | 11,635 |
| 4 | RS (Rio Grande do Sul) | 5,466 |
| 5 | PR (Paraná) | 5,045 |
 
- **Top cities within states:**
  - SP → São Paulo city alone accounts for **15,540** customers
  - RJ → Rio de Janeiro city: **6,882**
  - MG → Belo Horizonte: **2,773**
  - DF → Brasília dominates its state with **2,131** out of 2,140 customers (99.6%)
 
### Insight
> The customer base is **heavily concentrated in the Southeast region (SP, RJ, MG)**. Over 66% of customers come from just 3 states, revealing a major geographic imbalance and untapped potential in Brazil's North, Northeast, and Center-West regions.
 
---
 
## 2. Payment Behavior Analysis
 
### Findings
- **Total payment records:** 103,886 (no missing values, no duplicates)
- **Payment Method Distribution:**
 
| Payment Type | Count | Share |
|---|---|---|
| Credit Card | 76,795 | ~74% |
| Boleto | 19,784 | ~19% |
| Voucher | 5,775 | ~5.6% |
| Debit Card | 1,529 | ~1.5% |
| Not Defined | 3 | ~0% |
 
- **Average Transaction Value by Method:**
  - Credit Card: **R$ 163.32** (avg. 3.5 installments, up to 24)
  - Boleto: **R$ 145.03** (always 1 installment)
  - Debit Card: **R$ 142.57** (always 1 installment)
  - Voucher: **R$ 65.70** (smallest ticket size)

 <img width="613" height="466" alt="image" src="https://github.com/user-attachments/assets/0694ab1a-e48a-4a2e-a103-f11d4b1159c8" />

 
- Credit card users split payments into **up to 24 installments**, with a median of 3.
 
### Insight
> Credit cards are the overwhelmingly preferred payment method, and the installment feature (parcelamento) is a key driver of higher average order values. Boleto remains significant (~19%) as a banking staple for unbanked/underbanked populations in Brazil.
 
---
 
## 3. Order & Delivery Analysis

<img width="756" height="271" alt="image" src="https://github.com/user-attachments/assets/f5d95431-9df3-4811-8350-a316b055f75a" />

 
### Findings
- **Total Orders:** 99,441
- **Delivery Rate:** **97.02%** — excellent operational efficiency
- **Cancellation Rate:** only **0.63%**
- **Average delivery time:** **12.09 days** from purchase to delivery
 
- **Late Deliveries:** **8,212 orders (~8%)** were delivered later than the estimated date
  - These span **1,359 different cities**
  - Cities most affected by late deliveries:
 
| City | Late Orders |
|---|---|
| São Paulo | 1,021 |
| Rio de Janeiro | 796 |
| Salvador | 213 |
| Belo Horizonte | 170 |
| Porto Alegre | 165 |

<img width="827" height="487" alt="image" src="https://github.com/user-attachments/assets/23671aa1-5c9a-4d15-81a1-64d42126e488" />

 
- **Slowest product categories to deliver (avg. days):**
 
| Category | Avg. Delivery Days |
|---|---|
| Office Furniture | 20 days |
| Christmas Supplies | 15 days |
| Security & Services | 15 days |
| Fashion Shoes | 15 days |
| Home Comfort 2 | 14 days |
<img width="743" height="451" alt="image" src="https://github.com/user-attachments/assets/655986ca-1ce9-49fe-96ad-3dc9e402b9f5" />

 
- **Fastest product categories to deliver:**
 
| Category | Avg. Delivery Days |
|---|---|
| Arts & Craftmanship | 5 days |
| La Cuisine | 7 days |
| Books Imported | 8 days |
| Fashion Children's Clothes | 8 days |
| Food | 9 days |

 <img width="736" height="448" alt="image" src="https://github.com/user-attachments/assets/d59ee90a-f5bd-4804-9216-1648e61f62bb" />

### Insight
> While overall delivery performance is strong (97% success rate), the 8% late delivery rate in major urban centers like São Paulo and Rio is a concern — especially since these cities have the highest order volumes. Bulky categories like furniture and office supplies naturally take longer, but the gap between estimated and actual delivery in these categories needs attention.
 
---
 
## 4. Product Category Analysis

 <img width="518" height="468" alt="image" src="https://github.com/user-attachments/assets/87aa72ba-312f-4bee-acb5-5c2e559798a3" />


### Findings
- **Total unique products:** 32,951 across **73 categories**
- **All 32,951 products were ordered at least once** — 100% catalogue utilization
- **Top 10 Most Sold Product Categories:**
 
| Rank | Category | Orders |
|---|---|---|
| 1 | Bed, Bath & Table | 11,115 |
| 2 | Health & Beauty | 9,670 |
| 3 | Sports & Leisure | 8,641 |
| 4 | Furniture & Decor | 8,334 |
| 5 | Computers & Accessories | 7,827 |
| 6 | Housewares | 6,964 |
| 7 | Watches & Gifts | 5,991 |
| 8 | Telephony | 4,545 |
| 9 | Garden Tools | 4,347 |
| 10 | Auto | 4,235 |
 
- **Bottom 5 Least Sold Categories:**
- <img width="570" height="412" alt="image" src="https://github.com/user-attachments/assets/8241468e-837b-4c4e-b977-1d696912d237" />

 
| Category | Orders |
|---|---|
| Security & Services | 2 |
| Fashion Children's Clothes | 8 |
| La Cuisine | 14 |
| CDs/DVDs/Musicals | 14 |
| Arts & Craftmanship | 24 |


### Insight
> Home & lifestyle categories (bed/bath, health/beauty, sports) dominate demand. The bottom categories represent niche markets but could be growth opportunities with targeted marketing. The fact that every product was ordered at least once is a strong sign of catalogue health.
 
---
 
## 5. Customer Review & Satisfaction Analysis
 
### Findings
- Reviews analyzed: **96,361** (for delivered orders only)
- **Best reviewed product categories (avg. score):**
 
| Category | Avg. Score |
|---|---|
| Fashion Children's Clothes | 5.00 |
| CDs, DVDs & Musicals | 4.64 |
| Books (General Interest) | 4.51 |
| Books (Imported) | 4.51 |
| Construction Tools | 4.44 |

<img width="757" height="448" alt="image" src="https://github.com/user-attachments/assets/6c1c0b43-cf95-4c96-b5b5-a4adf8c04925" />

 
- **Worst reviewed product categories (avg. score):**
 
| Category | Avg. Score |
|---|---|
| Security & Services | 2.50 |
| Diapers & Hygiene | 3.38 |
| Office Furniture | 3.52 |
| Home Comfort 2 | 3.63 |
| Fashion Male Clothing | 3.76 |

<img width="757" height="444" alt="image" src="https://github.com/user-attachments/assets/12ce7325-7afd-4f08-af05-0c027ca8e47f" />


- **Undelivered orders with reviews (2,863 orders):**
  - Shipped (not yet delivered): 1,043
  - Cancelled: 609
  - Unavailable: 597
 
### Insight
> Fashion and books consistently earn the highest satisfaction scores, likely due to clear expectations and good condition on delivery. Security services and hygiene products score the lowest — indicating either quality issues, delivery damage, or unmet expectations. Office Furniture's low rating aligns with its long delivery times (20 days avg.), suggesting a direct correlation between late delivery and poor reviews.
 
---
 
## 6. Seller Distribution Analysis
 
### Findings
- **Top cities by seller activity (orders fulfilled):**
 
| City | Orders from Sellers |
|---|---|
| São Paulo | 27,983 |
| Ibitinga | 7,750 |
| Curitiba | 3,016 |
| Santo André | 2,964 |
| Belo Horizonte | 2,593 |

<img width="719" height="453" alt="image" src="https://github.com/user-attachments/assets/0508e281-077a-4236-b355-91191760aba7" />

 
- São Paulo sellers alone account for **~25% of all order items**
- **Ibitinga** (a small city in SP state) is the #2 seller hub — likely a textile/clothing manufacturing cluster
- Seller concentration mirrors customer concentration: SP state dominates on both demand and supply sides
 
### Insight
> The marketplace supply chain is heavily São Paulo-centric. This explains why late deliveries are highest in cities far from SP — long last-mile distances. Expanding seller networks in under-served regions (North/Northeast) could significantly reduce delivery times and improve satisfaction in those areas.
 
---
 
## 7. Pricing Analysis by Category
 
### Findings
- **Most expensive categories (avg. unit price):**
 
| Category | Avg. Price (R$) |
|---|---|
| Computers | 1,098.34 |
| Small Appliances (Home Oven) | 624.29 |
| Home Appliances 2 | 476.12 |
| Agro Industry & Commerce | 342.12 |
| Musical Instruments | 281.62 |

<img width="812" height="408" alt="image" src="https://github.com/user-attachments/assets/cb7e358e-411a-49bf-8565-9b971be63375" />

- **Most affordable categories (avg. unit price):**
 
| Category | Avg. Price (R$) |
|---|---|
| Home Comfort 2 | 25.34 |
| Flowers | 33.64 |
| Diapers & Hygiene | 40.19 |
| CDs/DVDs/Musicals | 52.14 |
| Food & Drink | 54.60 |

 <img width="767" height="446" alt="image" src="https://github.com/user-attachments/assets/e096dde3-040b-4058-a811-d44a973f67a9" />


### Insight
> High-ticket items like computers and large appliances have a natural fit with the credit card installment payment behavior observed (up to 24 installments). There's a clear pricing ecosystem at play — affordable everyday goods drive volume while expensive electronics drive revenue value.
 
---
 
## 8. Key Business Insights Summary
 
| # | Insight | Impact |
|---|---------|--------|
| 1 | 97% delivery success rate — strong operational baseline | ✅ Positive |
| 2 | 42% of customers are in São Paulo state alone | ⚠️ Geographic risk/opportunity |
| 3 | 74% of payments are by credit card with installments | 💡 Revenue lever |
| 4 | 8% of orders arrive later than estimated | ❌ Satisfaction risk |
| 5 | Bed/Bath/Health/Beauty dominate sales volume | 💡 Category strength |
| 6 | Office furniture has the worst delivery (20 days) AND low reviews (3.52) | ❌ Correlated pain point |
| 7 | All 32,951 products sold at least once — full catalogue utilization | ✅ Positive |
| 8 | Seller concentration mirrors customer concentration (SP-heavy) | ⚠️ Supply chain risk |
| 9 | Security & Services has worst reviews (2.50 avg.) | ❌ Category quality issue |
| 10 | Voucher payments have the smallest basket size (R$ 65.70) | 💡 Promotion lever |
 
---
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
