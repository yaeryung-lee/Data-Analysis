# Olist E-commerce Analysis
1. Data Profiling: 99,441 orders from 96,096 unique customers
   - Repeat Rate = 3.12% → 96.9% of customers never came back.
2. Defining the Key Question: "Why do 97% of customers never return, and what can be done to improve customer lifetime value?"
3. Building Hypothesis
   | Branch | Hypothesis | 
   |----------|----------|
   | Product  | Poor product quality drives dissatisfaction | 
   | Delivery | Shipping delays cause negative experiences | 
   | Platform | Payment friction or UX issues | 
   | Seller   | Unreliable sellers damage platform trust | 
4. Testing Each Branch
   - Product → Product quality was not the differentiator.
   - Delivery → Confirmed by the correlation with average review score.
   - Platform → Not a major factor.
   - Seller → Secondary risk.
5. Quantifying the Impact: Improving repeat rate from 3% to 10% could generate ~$2.1M in additional GMV.
6. The Causal Chain:
   - Carrier Bottleneck → Delivery Delay → Review Score Collapse → Customer Does Not Return → Growth Depends Entirely on New Acquisition
7. Strategic Recommendations:
   - #1: Fix Delivery - Enforce carrier SLA with P90 target of 15 days (currently 22). Replicate SP's logistics model (8.3 days avg) in underperforming states (RJ: 14.7 days, BA: 18.8 days). Establish monthly OTDR monitoring dashboard.
     - KPI: OTDR 93.4% → 95%
   - #2: Convert First-Time Buyers - Category-based product recommendation emails at 2 weeks post-purchase. 10% discount coupon at 3 weeks. Reminder at 4 weeks. A/B test timing for optimization.
     - KPI: Repeat Rate 3.12% → 10%
   - #3: Manage Seller Quality - Automated monthly seller scorecard. Prioritize sellers with Review < 3.5 AND GMV top 20%. Apply visibility restrictions after 3 consecutive months below threshold.
     - KPI: Bottom 10% seller avg review → 3.5★

Tools, Skills, Analytical Frameworks:
- Excel: Power query, Power pivot, Pivot tables, Data modeling, Formulas, Dashboard
- Power BI: DAX measures, Star schema, Dashboards
- AARRR Funnel, Marketplace Flywheel, RFM Segmentation, Prioritization Matrix, Pareto Analysis
