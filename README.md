# Customer Purchase Behaviors on Google Merchandise Store in 2017

🔗 **BigQuery Dataset**: [Link]([https://console.cloud.google.com/bigquery](https://console.cloud.google.com/bigquery?sq=59475521650:be1ba7d02b83428da2194f8e6d0a6983))


## 1. Project Overview
- Project utilizing the BigQuery Public Dataset: Google Analytics Sample (ga_sessions_2017), a real-world dataset simulating user behavior on an e-commerce website.
- Developed a series of SQL queries to analyze customer behavior, marketing channel performance, and sales effectiveness.
## 2. Analysis

### Example 1: Total visits, pageviews, transactions (Jan–Mar 2017)
```sql
SELECT
  FORMAT_DATE('%Y%m', PARSE_DATE('%Y%m%d', date)) AS month,
  SUM(totals.visits) AS visits,
  SUM(totals.pageviews) AS pageviews,
  SUM(totals.transactions) AS transactions
FROM `bigquery-public-data.google_analytics_sample.ga_sessions_2017*`
WHERE _table_suffix BETWEEN '0101' AND '0331'
GROUP BY month
ORDER BY month;
```
**Result:**

![Query Result Table](1.png)
