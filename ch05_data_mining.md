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
    font-size: 0.80rem;
  }

math: mathjax
---
# Data mining: A Data Modeling Techniques

<div class="columns">
<div>

**Milestones of data mining**
![w:300](file/image/data_mining_history.png)
</div>

<div>

**What is Data Mining?**
[![Data Mining Process](https://i.ytimg.com/vi/81bm2OsEzbg/default.jpg)](https://youtu.be/81bm2OsEzbg?si=k64OF39aHol-dAs4)
</div>
</div>
<span class="small-text">* KDD: Knowledge Discovery in Database</span><br>
<span class="small-text">* Data mining is to find anomalies, patterns, or correlations among data</span><br>
<span class="small-text">* Data mining comprises three disciplines: statistic, AI, ML</span>

# Data Mining Techniques
<div class="columns">
<div>

![w:500](https://www.mehr-als-durchschnitt.de/img/data-mining.jpeg)
</div>
<div>

<span class="small-text">
<u>Associations & Relationships:</u> Finds patterns of items that frequently occur together.<br>  
<u>Classification Methods:</u> Assigns items into predefined categories based on attributes.<br>  
<u>Anomaly Detection:</u> Identifies unusual data points that don’t fit the general pattern.<br>  
<u>Time Series Analysis:</u> Analyzes data over time to detect trends, cycles, or seasonality.<br>  
<u>Predictive Modeling:</u> Builds models from historical data to forecast future outcomes.<br>  
<u>Text Mining:</u> Extracts useful information and patterns from unstructured text data.<br>
</span>  
</div>
</div>

# Frequent Itemset Mining Method 
- One <span class="blue-text">“pattern discovery” </span> method of associations & relationships techniques to reveal hidden associations in massive data. 
- In real life, we often face large volumes of transaction (like purchase records, credit card logs). These datasets may look messy, but they hide patterns of items that frequently occur together.
- <span class="blue-text">Frequent Itemset Mining</span> helps us to:
  - Find frequent combinations, eg. milk and bread often bought together.
  - Understand customer behaviors, preferences, and habits.
  - Support price setting and product bundling strategies.

# Basic Concept: Market basket analysis
> “Which groups or sets of items are customers likely to purchase on a given trip to the store?”

- Discover a <span class="blue-text">association rule</span>: 
  <u>*computer ⇒ antivirus_software [support= 2%,confidence= 60%]*</u>
- A support of 2% means that 2% of all the transactions under analysis show that computer and antivirus software are purchased together.
- A confidence of 60% means that 60% of the customers who purchased a computer also bought the software.
- Typically, association rules are considered interesting if they satisfy a **minimum support threshold** and a **minimum confidence threshold**. 
- These thresholds can be set by users or domain experts.

# Formula of Support and Confidence
$$
support(A \Rightarrow B) = P(A \cup B) \tag{buy both A and B}
$$
<br>

$$
confidence(A \Rightarrow B) = P(B|A) \tag{buy B given A}
$$
<br>

$$
confidence(A \Rightarrow B) = P(B|A) 
= \frac{support(A \cup B)}{support(A)} 
= \frac{support\_count(A \cup B)}{support\_count(A)}
$$

# Calculate Support and Confidence
Suppose we have 5 transactions, each recording the items a customer purchased:
```
T1: {Milk, Bread, Butter}
T2: {Beer, Bread}
T3: {Milk, Beer, Butter}
T4: {Milk, Bread, Beer}
T5: {Milk, Bread, Butter}
```
Support({Milk} ⇒ {Bread})
= Transactions containing {Milk, Bread} ÷ Total transactions = 3 / 5 = 0.6 (60%)

Confidence({Milk} ⇒ {Bread})
= Transactions containing {Milk, Bread} ÷ Transactions containing {Milk} = 3 / 4 = 0.75 (75%)

# Apriori Algorithm to Find Frequent Itemsets by Confined Candidate
<div class="columns">
<div>

Minimum support = 2
![w:700](file/image/apriori_support.png)

</div>
<div>

Minimum confidence = 70%
![w:700](file/image/apriori_confidence.png)
[![Apriori Algorithm Explained ](https://i.ytimg.com/vi/guVvtZ7ZClw/default.jpg)](https://youtu.be/guVvtZ7ZClw?si=PHcBQFmdUUp6omPW)
</div>
</div>

# Case study: Frequent Itemset Mining
- Objective: identify potential product bundling opportunities.
- Dataset: transaction data from a retail store.
- Methodology
  1. Data Preprocessing: clean and preprocess the transaction data and convert transactions into a one-hot encoded format.
  2. Apply Apriori Algorithm: set minimum support and confidence thresholds and generate frequent itemsets and association rules.
- Marketing Decision Recommendations
   1. Design a “Milk + Bread” breakfast combo set.
   2. Place milk and bread in adjacent areas to increase cross-selling opportunities.
[apriori_association_rule.ipynb](file/code/apriori_association_rule.ipynb)

# Summary
- Data mining is part of Knowledge Discovery in Databases (KDD), integrating statistics, AI, and machine learning to uncover anomalies, patterns, and correlations.
- Key techniques include association analysis, classification, anomaly detection, time series analysis, predictive modeling, and text mining.
- Frequent Itemset Mining (e.g., Apriori algorithm) is widely used in market basket analysis to discover product combinations, measure support & confidence, and guide marketing strategies like bundling and cross-selling.

# Homework

# Review

# 1. Which of the following is NOT a main purpose of Data Mining?
A. Detect anomalies in data
B. Find associations and patterns in data
C. Predict possible future outcomes
D. Reduce database storage size

# 2. Data Mining belongs to which stage of the KDD (Knowledge Discovery in Database) process?
A. Data cleaning
B. Pattern discovery
C. Model evaluation
D. Data visualization

# 3. Which of the following is NOT a typical Data Mining technique?
A. Association & Relationship analysis
B. Classification
C. Regression Testing
D. Anomaly Detection

# 4. In Market Basket Analysis, what does Support mean?
A. The proportion of customers who bought A and also bought B
B. The proportion of all transactions that contain both A and B
C. The difference in occurrence counts between A and B in the database
D. The average number of items purchased per customer

# 5. If a rule {Milk} ⇒ {Bread} has a Confidence = 75%, what does it mean?
A. 75% of all customers bought both milk and bread
B. 75% of all customers bought at least milk or bread
C. 75% of customers who bought milk also bought bread
D. 75% of customers who bought bread also bought milk

# 6. Why do we need to set Minimum Support and Minimum Confidence in Frequent Itemset Mining?
A. To filter out statistically significant rules
B. To reduce computational complexity and noise
C. To avoid over-interpreting rare events
D. All of the above

# 7. What is the main concept of the Apriori Algorithm?
A. Building classification models for prediction
B. Finding seasonal patterns in time-series data
C. Discovering frequent itemsets using a level-wise filtering approach
D. Extracting rules from text data using text mining

# 8. Given the following transactions:
T1: {Milk, Bread, Butter}
T2: {Beer, Bread}
T3: {Milk, Beer, Butter}
T4: {Milk, Bread, Beer}
T5: {Milk, Bread, Butter}

What is Support({Milk} ⇒ {Bread})?
A. 40%
B. 50%
C. 60%
D. 75%

# 9. Which of the following is an application of Frequent Itemset Mining in marketing?
A. Designing product bundles
B. Customer credit risk evaluation
C. Stock price time-series prediction
D. Document classification

# 10. Which of the following is NOT one of the three core disciplines of Data Mining?
A. Statistics
B. Artificial Intelligence (AI)
C. Database Design
D. Machine Learning
