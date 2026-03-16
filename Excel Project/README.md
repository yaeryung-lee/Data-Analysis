# Olist E-commerce Analysis
1. Key Questions & Findings
2. Dashboard Previews
3. Project Overview:
   1) EDA: Profiled all 9 tables - row counts, blanks, 
   unique values, descriptive statistics. 
   ([See full profiling →])
   - Key discovery: 99,441 orders from 96,096 unique customers
   2) #### Key Question: "Why do 97% of customers never return, and what can be done to improve customer lifetime value?"
      
   3) Data Cleaning ([See full profiling →])
      
   4) Building Hypothesis
   
   | Branch | Hypothesis |
   |--------|-----------|
   | Product | Poor product quality drives dissatisfaction |
   | Delivery | Shipping delays cause negative experiences |
   | Platform | Payment friction or UX issues |
   | Seller | Unreliable sellers damage platform trust |
   
   5) Testing Each Branch
   - Product → Product quality was not the differentiator.
   - Delivery → Confirmed by the correlation with average review score.
   - Platform → Not a major factor.
   - Seller → Secondary risk.
     
   6) Quantifying the Impact: Improving repeat rate from 3% to 10% could generate ~$2.1M in additional GMV.
      
   7) The Causal Chain:
   - Carrier Bottleneck → Delivery Delay → Review Score Collapse → Customer Does Not Return → Growth Depends Entirely on New Acquisition
     
   8) Strategic Recommendations:
   - #1: Fix Delivery - Enforce carrier SLA with P90 target of 15 days (currently 22). Replicate SP's logistics model (8.3 days avg) in underperforming states (RJ: 14.7 days, BA: 18.8 days). Establish monthly OTDR monitoring dashboard.
     - KPI: OTDR 93.4% → 95%
   - #2: Convert First-Time Buyers - Category-based product recommendation emails at 2 weeks post-purchase. 10% discount coupon at 3 weeks. Reminder at 4 weeks. A/B test timing for optimization.
     - KPI: Repeat Rate 3.12% → 10%
   - #3: Manage Seller Quality - Automated monthly seller scorecard. Prioritize sellers with Review < 3.5 AND GMV top 20%. Apply visibility restrictions after 3 consecutive months below threshold.
     - KPI: Bottom 10% seller avg review → 3.5★
5. RFM Segmentation Summary
6. Key Metrics

   Revenue & Sales

| Metric | Value | 
|--------|-------|
| GMV | $15,876,443 |
| AOV | $159.66 |
| Basket Size (UPT) | 1.13 | 

   Customer

| Metric | Value |
|--------|-------|
| CLV (proxy) | $165.21 |
| Repeat Purchase Rate | 3.12% |
| Churn Rate | 96.88% (= 1 - Repeat Rate) |

   Supply Chain / Operations

| Metric | Value | 
|--------|-------|
| On-Time Delivery Rate (OTDR) | 93.4% |
| Order Cycle Time | 12.0 days avg | 
| Fulfillment Time (Seller) | 2.4 days avg | 
| Shipping Time (Carrier) | 8.7 days avg | 
| P90 Delivery | 22 days | 
| P95 Delivery | 29 days | 
| SLA Breach Rate | 6.6% | 

   Other

| Metric | Value | 
|--------|-------|
| RFM Segmentation | 6 segments | 
| Correlation (Delivery vs Review) | r = −0.30 | 
| Revenue Concentration (Seller) | Top 18% = 80% GMV | 
| Revenue Concentration (Category) | Top 18 categories = 81% GMV | 
| Customer Satisfaction (Review) | 4.02 avg | 
| Time-to-Second-Purchase (median) | 34 days | 
| Time-to-Second-Purchase (mean) | 87.3 days | 
| GMV per Repeat Customer | $315.39 | 
| First-time vs Repeat GMV Split | 94% vs 6% | 

6. Detailed Analysis ([See full profiling →])

Limitations:
- GMV ≠ Olist revenue. Olist's take rate (commission %) is unknown.
- Correlation ≠ causation. Delivery → review relationship (r = −0.30) is correlational, not causal.
- Customer identity. Different emails = different customers. True repeat rate may be slightly higher than 3.12%.
- No demographics. Age, gender, income unavailable — segmentation limited to RFM.
- No marketing cost data. CAC unknown; retention campaign ROI cannot be precisely estimated.
- Limited time range. Effective period: 2017 Q1 – 2018 Q3 (21 months).
- Cohort retention analysis was not performed due to the extremely low repeat rate (3.12%); cohort matrices would be near-empty and add limited analytical value.

Tools, Skills, Frameworks:
   - Excel: Power query, Power pivot, Pivot tables, Data modeling, Formulas, Dashboard
   - Power BI: DAX measures, Star schema, Dashboards
   - AARRR, Marketplace Flywheel, RFM Segmentation, Prioritization Matrix, Pareto Analysis
   
Data Source: Olist Brazilian E-commerce Dataset — 9 tables, 100K+ orders, Sept 2016 – Oct 2018.
