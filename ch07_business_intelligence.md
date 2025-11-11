---
marp: true
theme: default
class: default
size: 16:9
paginate: true
header: 國立陽明交通大學 電子與光子學士學位學程
headingDivider: 1
style: |
  section::after {
    content: attr(data-marpit-pagination) '/' attr(data-marpit-pagination-total);
  }
  
  .columns {
    display: grid;
    grid-template-columns: repeat(2, minmax(0, 1fr));
    gap: 1rem;
  }
  .columns img {
    width: 50%;
  }
  .middle-grid {
    display: grid;
    grid-template-columns: repeat(2, minmax(0, 1fr));
    gap: 1rem;
  }
  .middle-grid img {
    width: 75%;
  }
  .grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 10px;
  }
  .grid img {
    width: 100%;
  }
  .red-text {
    color: red;
  }
  
  .blue-text {
    color: blue;  
  }
  .yellow-text {
    color: yellow;  
  }

  .small-text {
    font-size: 0.50rem;
  }

---
# Business Intelligence (BI)
>BI is the process of collecting, analyzing, and transforming raw business data into meaningful insights that help organizations make data-driven decisions.

![bg right:60% w:90%](https://www.altexsoft.com/static/blog-post/2023/11/56ccc776-6fa5-4ed3-9f3c-8080318b4fbd.jpg)

# RFM Analysis
- RFM analysis is a marketing analysis tool used to identify and segment customers based on their **purchasing behavior**.
- Businesses can understand customer value and tailor marketing strategies accordingly.
- RFM stands for Recency, Frequency, and Monetary Value.

| Letter | Meaning   | Describes                                                 |                  
|--------|-----------|-----------------------------------------------------------|
| R      | Recency   | How recently a customer made a purchase (最近一次消費的時間) |       
| F      | Frequency | How often they purchase (消費的頻率)                        | 
| M      | Monetary  | How much they spend (消費的金額)                            |

# RFM Analysis Results
| Support           | Example|
|------------------ | ------ |
|Target marketing   | Send promotions to recent, frequent, and high-spending customers
|Retention strategy | Re-engage customers who haven’t purchased recently
|Loyalty program    | Reward top customers
|Forecasting        | Predict which segments will respond best to new offers


# RFM Analysis Example
[`RFM_sales_data.ipynb`](file/code/RFM_sales_data.ipynb)

# RFM Customer Segmentation
![bg right:70% w:90%](file/image/RFM_customer_seqment.jpg)

# Summary
- RFM analysis is a powerful tool for understanding customer behavior and segmenting customers based on their purchasing patterns.
- By analyzing recency, frequency, and monetary value, businesses can tailor their marketing strategies to different customer segments, improving customer retention and maximizing revenue.
- RFM analysis can be applied across various industries, including retail, e-commerce, and services, to enhance customer relationship management and drive business growth.

# Homework
HW5 - RFM (Recency, Frequency, Monetary) 客戶價值分析

# Review
# What does RFM stand for, and what does each component represent?
# How can RFM analysis help businesses improve their marketing strategies?