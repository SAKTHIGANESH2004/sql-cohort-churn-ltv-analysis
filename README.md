# "Advanced Customer Segmentation Using SQL Window Functions & Percentile Analysis"

## Overview
End-to-end SQL analysis of customer behavior, retention, and customer lifetime value (CLV) for an e-commerce business, using PostgreSQL to uncover actionable insights that improve customer retention, reduce churn, and maximize revenue.

## Business Questions
1. **Customer Segmentation:** Who are our most valuable customers, and how should we prioritize retention efforts by segment?
2. **Cohort Analysis:** How does customer-generated revenue evolve across different acquisition cohorts over time?
3. **Retention Analysis:** Which customers are at risk of churn, and how can we proactively re-engage them?

## Clean Up Data

**🖥️ Query**: [0_create_view.sql](0_create_view.sql)

- Engineered a reusable SQL view combining transactional and customer-level data for downstream analysis
- Aggregated raw sales data into revenue and order-level metrics
- Derived first purchase dates per customer to enable cohort-based segmentation

## Analysis

### 1. Customer Segmentation

**🖥️ Query**: [1_customer_segmentation.sql](1_Customer_segment.sql)

- Built a customer lifetime value (LTV) segmentation model using SQL window functions and aggregate metrics
- Classified customers into High, Mid, and Low-value tiers based on total revenue contribution
- Calculated segment-level KPIs including total revenue, customer count, and average spend

**📈 Visualization:**

 ![1_customer_segment](/images/1_customer_segment.png)

📊 **Key Findings:**
- High-value segment (25% of customers) drives 66% of revenue ($135.4M)
- Mid-value segment (50% of customers) generates 32% of revenue ($66.6M)
- Low-value segment (25% of customers) accounts for 2% of revenue ($4.3M)

💡 **Business Insights**
- High-Value (66% revenue): Launch a premium membership/VIP program for 12,372 high-value customers to protect against revenue concentration risk, since losing even one customer has outsized impact
- Mid-Value (32% revenue): Design personalized upgrade campaigns to shift mid-tier spend toward the high-value tier, representing a potential $66.6M → $135.4M revenue opportunity
- Low-Value (2% revenue): Deploy targeted re-engagement and price-sensitive promotions to lift purchase frequency and convert dormant spenders

### 2. Customer Revenue by Cohort
**🖥️ Query**: [2_cohort_analysis.sql](2_cohort_analysis.sql)

- Built cohort-based SQL queries to track revenue and customer counts by acquisition year
- Grouped customers into cohorts using first purchase date
- Benchmarked cohort performance over time to identify long-term revenue trends

**📈 Visualization:**

![customer_first_purcahse](/images/1_cohort_first_purchase.png)

Customer Revenue by Cohort (Adjusted for time in market) - First Purchase Date 



Investigate Monthly Revenue & Customer Trends (3 Month Rolling Average)

📈 **Visualzation:**
 ![Investigate_Month_reavenue](/images/3_month%20rolling-avg.png)

📊 **Key Findings:**  
- Customer revenue is declining over time: older cohorts (2016-2018) spent ~$2,800+ per customer, while the 2024 cohort's spend dropped to ~$1,970  
- Revenue and customer acquisition peaked in 2022-2023 before trending downward in 2024  
- High volatility in revenue and customer count, including sharp drops in 2020 and 2024, signals emerging retention challenges  

💡 **Business Insights:**  
- Prioritize retention and re-engagement campaigns for recent cohorts (2022-2024) with personalized offers to prevent early-stage churn  
- Stabilize revenue volatility by introducing loyalty programs or subscription models that encourage consistent spending  
- Benchmark and replicate the strategies driving high-spending cohorts (2016-2018) to lift performance in newer cohorts  

### 3. Customer Retention
🖥️ Query: [3_retention_analaysis.sql](3_retention_analaysis.sql)

- Developed SQL-based churn and retention metrics to flag at-risk customers
- Analyzed recency of last purchase to segment active vs. lapsed customers
- Calculated customer-specific retention indicators to support proactive intervention

**📈 Visualization:**

![retention_analysis](/images/3_churn_cohort_year.png)

📊 **Key Findings:**  
- Cohort churn stabilizes at ~90% after 2-3 years, revealing a predictable long-term retention curve  
- Retention rates remain consistently low (8-10%) across all cohorts, indicating a systemic retention issue rather than a cohort-specific one  
- Newer cohorts (2022-2023) are tracking the same churn trajectory as older cohorts, signaling that without intervention, retention will continue to decline  

💡 **Business Insights:**  
- Strengthen early-lifecycle engagement in the first 1-2 years through onboarding incentives, loyalty rewards, and personalized offers to improve long-term retention  
- Prioritize win-back campaigns for high-value churned customers, since reactivating high-CLV users delivers stronger ROI than broad retention spend  
- Build a proactive churn-prediction framework using customer-specific warning indicators to intervene before customers lapse  

## Strategic Recommendations

1. **Customer Value Optimization** (Customer Segmentation)
   - Launch a VIP program for 12,372 high-value customers driving 66% of total revenue
   - Build personalized upgrade paths for the mid-value segment, targeting a $66.6M → $135.4M revenue opportunity
   - Design price-sensitive, frequency-driving promotions for the low-value segment

2. **Cohort Performance Strategy** (Customer Revenue by Cohort)
   - Target 2022-2024 cohorts with personalized re-engagement offers to counter declining spend
   - Implement loyalty/subscription programs to stabilize revenue volatility
   - Apply proven strategies from high-spending 2016-2018 cohorts to newer customer segments

3. **Retention & Churn Prevention** (Customer Retention)
   - Strengthen first 1-2 year engagement with onboarding incentives and loyalty rewards
   - Focus win-back campaigns on high-value churned customers for maximum ROI
   - Implement a proactive, indicator-based churn intervention system

## Skills & Tools Demonstrated
- **SQL:** Window functions, CTEs, views, aggregation, cohort/time-series analysis, customer segmentation (RFM-style), churn/retention analysis
- **Database:** PostgreSQL
- **Analysis Tools:** PostgreSQL, DBeaver
- **Visualization:** ChatGPT
- **Core Competencies:** Customer lifetime value (CLV) modeling, cohort analysis, churn prediction, data-driven business recommendations, revenue analytics

## Technical Details
- **Database:** PostgreSQL
- **Analysis Tools:** PostgreSQL, Dbeaver
- **Visualization:** ChatGPT