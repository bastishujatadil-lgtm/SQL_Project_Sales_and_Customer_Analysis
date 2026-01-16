# SQL - Sales & Customer Analysis

## Overview
This project analyzes customer behavior, retention patterns, and lifetime value (LTV) for an e-commerce business. The goal is to uncover actionable insights that improve customer retention, stabilize revenue, and maximize long-term profitability using SQL-driven analysis.

## Business Questions
1. **Customer Segmentation:** Who are our most valuable customers?
2. **Cohort Analysis:** How do different customer groups generate revenue?
3. **Retention Analysis:** Which customers haven't purchased recently?

## Clean Up Data

**🖥️ Query**: [0_create_view.sql](Project/0_create_view.sql)

- Aggregated transactional and customer data into revenue-focused metrics
- Calculated first purchase dates to enable cohort analysis
- Created a unified view combining customer details and sales activity

## Analysis

### 1. Customer Segmentation

**🖥️ Query**: [1_customer_segmentation.sql](Project/1_customer_segmentation.sql)

- Segmented customers by total lifetime value (LTV)
- Classified users into High-, Mid-, and Low-value groups
- Calculated total revenue contribution per segment

**📈 Visualization:**

<img src="Images/1_customer_segementation.png" alt="Customer Segmentation" width="50%">

📊 **Key Findings:**
- High-value customers (25%) generate 66% of total revenue ($135.4M)
- Mid-value customers (50%) contribute 32% of revenue ($66.6M)
- Low-value customers (25%) account for just 2% of revenue ($4.3M)

💡 **Business Insights**
- High-value segment: Introduce a VIP or premium membership program for 12,372 top customers, as churn here has a disproportionate revenue impact
- Mid-value segment: Develop personalized upgrade and cross-sell strategies, unlocking a potential revenue increase from $66.6M to $135.4M
- Low-value segment: Use price-sensitive promotions and re-engagement campaigns to increase purchase frequency

### 2. Customer Revenue by Cohort
**🖥️ Query**: [2_cohort_analysis.sql](Project/2_cohort_analysis.sql)

- Grouped customers into cohorts based on first purchase year
- Tracked revenue and customer count by cohort
- Normalized revenue to account for time in the market

**📈 Visualization:**

Customer Revenue by Cohort (Adjusted for time in market) - First Purchase Date 

<img src="Images/2_customer_revenue_normalized.png" alt="Customer Revenue Normalized" width="50%">

Investigate Monthly Revenue & Customer Trends (3 Month Rolling Average)

<img src="Images/3_monthly_revenue_customers_3mo.png" alt="Monthly Revenue & CustomerTrends" width="50%">  

📊 **Key Findings:**  
- Older cohorts (2016–2018) show significantly higher spending (~$2,800+) compared to the 2024 cohort (~$1,970)  
- Revenue and customer acquisition peaked during 2022–2023 but are declining in 2024  
- Revenue and customer counts exhibit high volatility, with notable drops in 2020 and 2024, indicating retention challenges  

💡 **Business Insights:**  
- Focus retention and re-engagement efforts on recent cohorts (2022–2024) to prevent long-term revenue decline 
- Introduce loyalty programs or subscriptions to reduce revenue volatility 
- Replicate successful strategies from high-performing cohorts (2016–2018) for newer customers

### 3. Customer Retention
🖥️ Query: [3_retention_analysis.sql](Project/3_retention_analysis.sql)

- Identified customers at risk of churn based on last purchase behavior
- Analyzed retention patterns across cohorts
- Calculated customer-level churn indicators

**📈 Visualization:**

<img src="Images/4_customer_churn_cohort_year.png" alt="Customer Churn by Cohort Year" style="width: 50%; height: auto;">

📊 **Key Findings:**  
- Churn stabilizes at approximately 90% after 2–3 years, indicating a predictable long-term pattern  
- Retention rates remain low (8–10%) across all cohorts, suggesting systemic retention issues 
- Recent cohorts (2022–2023) follow the same churn trajectory as older cohorts, signaling future revenue risk  

💡 **Business Insights:**  
- Improve early lifecycle engagement within the first 1–2 years using onboarding incentives and loyalty rewards 
- Prioritize win-back campaigns for churned high-value customers to maximize ROI  
- Implement proactive churn prediction models to intervene before customers lapse

## Strategic Recommendations

1. **Customer Value Optimization** (Customer Segmentation)
   - Launch a VIP program for high-value customers driving 66% of revenue
   - Build personalized upgrade paths for mid-value customers
   - Increase engagement among low-value customers through targeted promotions

2. **Cohort Performance Strategy** (Customer Revenue by Cohort)
   - Re-engage 2022–2024 cohorts with personalized campaigns
   - Introduce subscriptions or loyalty programs to stabilize revenue
   - Apply best-performing strategies from older cohorts to newer ones

3. **Retention & Churn Prevention** (Customer Retention)
   - Strengthen early customer engagement in the first 1–2 years
   - Focus win-back efforts on high-value churned customers
   - Deploy early-warning systems to proactively reduce churn

## Technical Details
- **Database:** PostgreSQL
- **Analysis Tools:** PostgreSQL, Dbeaver
- **Visualization:** ChatGPT