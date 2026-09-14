# Saas-Dashboard-Tableau-Project

## The Project
 
Two Tableau dashboards built on a SaaS subscription dataset (RavenStack), looking at overall business health and, more specifically, why customers churn.
 
**Live dashboards:**
- [SaaS Subscription Dashboard (Overview)](https://public.tableau.com/views/SaasSubscriptiondashboard/SaasSubscriptionDashboard?:language=en-GB&:sid=&:redirect=auth&:display_count=n&:origin=viz_share_link)
- [Churn Dashboard](https://public.tableau.com/views/SaasChurnDashboard/ChurnDashboard?:language=en-GB&:sid=&:redirect=auth&:display_count=n&:origin=viz_share_link)
## Dataset
 
I used the RavenStack SaaS dataset found in kaggle created by River @ Rivalytics — a fictional stealth-mode SaaS startup with accounts, subscriptions, and churn data.
 
I used three of the five available tables:
- `accounts` — one row per customer, with plan tier, industry, country, signup date, referral source
- `subscriptions` — billing records with MRR, ARR, and plan changes
- `churn_events` — why and when accounts left, including reason codes
I left out `support_tickets` and `feature_usage` to keep the project focused — they'd be a good basis for a future, separate project.
 
## Page 1: SaaS Subscription Dashboard (Overview)
 
**What's on it:**
- KPI cards: Total Accounts, Monthly Recurring Revenue, Annual Recurring Revenue
- Monthly Signups (line chart)
- Active Users by Plan Tier (bar chart)
- Active Users by Country (map)
- Filters: Plan Tier, Industry, Signup Date range, Country
  
**Finding:** 500 total accounts generating 11.3M MRR (136.1M ARR). Pro is the most popular plan tier, followed by Basic and Enterprise. Signups fluctuated month to month but trended upward overall.
 
## Page 2: Churn Dashboard
 
**What's on it:**
- Churn by Reason (bar chart)
- Churn by Plan Tier (bar chart)
- Downgrade Before Churn (pie chart)
- Churn by Industry (bar chart)
- Filters: Plan Tier, Industry, Signup Date range, Country
  
**Key findings:**
- Features are the top reason customers leave — ahead of budget, support, and pricing (pricing is actually the *lowest* reason, which surprised me since it's often assumed to be the biggest driver of churn).
- Churn from Pro tier accounts is the highest, followed by Enterprise, then Basic.
- Most churned customers cancel outright — only 8.83% downgraded to a cheaper plan first before leaving entirely.
- DevTools has the highest churn by industry; EdTech has the lowest.
## Skills used
 
- Tableau (data relationships across multiple tables, calculated fields, dashboard filters)
- Calculated fields: Churn Rate, Is Churned
- Dashboard design: KPI cards, filters applied across multiple worksheets, floating layout containers
- Data validation: caught and fixed a data blending discrepancy that was silently undercounting MRR by comparing dashboard output against the raw CSV totals
## A note on data accuracy
 
While building this, my MRR figure didn't match what I calculated by hand from the raw CSV. I traced it to a Tableau data blending issue (mixing measures from two data sources without a shared dimension on the view), and fixed it by rebuilding the KPI as its own worksheet using a single, unblended data source. Every number on both dashboards has been checked against the raw CSV totals.
 
## How to view
 
Both dashboards are published live on Tableau Public — links at the top of this README. They're fully interactive: use the filters to slice by plan tier, industry, country, or signup date range.
 
## Author
 
**Godwill Mandou**
 
Part of my data analytics portfolio, built to practice Tableau for dashboard design, multi-table data modeling, and business reporting.
