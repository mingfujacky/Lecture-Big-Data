---
marp: true
theme: default
class: invert
size: 16:9
paginate: true
footer: 國立陽明交通大學 電子與光子學士學位學程
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
# Data Science Process
![w:550](file/image/fig1_5.jpg)

# Iterative, Not Strictly Linear
- Data science process is a structured approach to solving data problems efficiently.
- It improves collaboration and increases project success.
- It consists of <span class="yellow-text">**six steps**</span>
  1. Define goal & communicate project charter (what, how, why) with stakeholder 
  2. Retrieve data by finding suitable data sources and getting access rights
  3. Prepare data and clean, integrate, transform them
  4. Data exploration to look for patterns, correlation, and deviation based on visual and descriptive techniques
  5. Build models via statistic, machine learning, or neural network techniques
  6. Present findings & build applications

# Six Steps of Data Science Process and Their Subtasks
![w:400](file/image/fig2_1.jpg)

# #1: Goal and Project Charter
- Ask key questions to set goal
  - What company expect you to do? 
  - Why is this project important?  
  - How will you achieve the project goals?
- Deliver Project Charter to get authorizes
  - A clear research goal
  - The project mission and context
  - How to perform your analysis
  - What resources you expect to use
  - Proof of concepts
  - Deliverables 
![bg right:40% w:90%](file/image/fig2_2.jpg)


# #2: Retrieve Data
- **Internal sources**: excel, log, databases, data marts, data warehouses, data lakes
- **External sources**:  
  - Open data ([政府資料開放平臺](https://data.gov.tw))
  - APIs ([證交所OpenAPI](https://openapi.twse.com.tw/))  
  - Purchased data ([Semiconductor Market Research Reports](https://www.semi.org))
- Evaluate data veracity:
  - Data availability
  - Data quality
  - Licensing and authorization
![bg right:40% w:90%](file/image/fig2_3.jpg)

# Compare Database, Data Mart, Data Warehouse, Data Lake
![w:800](https://media.licdn.com/dms/image/v2/D5612AQGRZUyNUK-rPw/article-cover_image-shrink_720_1280/article-cover_image-shrink_720_1280/0/1721174296278?e=2147483647&v=beta&t=7t9zL5J-6vIIo_QCOV0VCesz5CNbCCT2UsqVeb3HVr8)

# Python Example — API Data Retrieval
```python
import requests

url = "https://api.github.com/repos/mingfujacky/Lecture-Database"
response = requests.get(url)
data = response.json()
print("Repo Name:", data['name'])
print("Stars:", data['stargazers_count'])
```
# #3: Clean, Integrate and Transform Data
- Clean: Remove duplicates, handle missing values, fix errors.
- Integrate (combine): merge multiple datasets.
- Transform: convert data from one format to another to make it more suitable for analysis, storage, or other uses.

![bg right:40% w:90%](file/image/fig2_4.jpg)

# <span class="yellow-text">Clean</span> Data Errors
- Interpretation errors: date having false value
- Inconsistencies errors: data is inconsistency across different datasets.

![bg right:50% w:90%](file/image/tbl2_2.png)

# Wrong Values
- "Good" vs "God", "O" vs "0", "i" vs "1"
- "FR" vs "FR "
- "Brazil" vs "brazil"
- "USA" vs "U.S.A" vs "United States"
- 2025-01-13 vs 2025/01/13 vs 2025.01.13 vs 01-13-2025 vs 13-01-2025
- "N/A", "None", "Unknown"
- Impossible value: age = 150
- Outliers
![bg right:40% w:90%](file/image/fig2_5.jpg)

# Missing Values
Missing values aren’t necessarily wrong, but you still need to handle them separately; 
![w:600](file/image/tbl2_4.png)

# Other Data Issues
- Duplicated values: same data appears multiple times
- Deviation from a code book: a codebook describes the layout of the data in the data file and describes what the data codes mean
- Different units of measurement: kilometers vs miles
- Different levels of aggregation: daily vs monthly sales
> Correct errors as early as possible

# <span class="yellow-text">Combine</span> Data From Difference Data Sources
- Join: combine two datasets based on a common key
- Append: add rows from one dataset to another
- Derive: create new variables or features from existing ones

<div class="columns">
    <img src="file/image/fig2_7.jpg" alt="join tables">
    <img src="file/image/fig2_8.jpg" alt="append tables">
    <img src="file/image/fig2_10.png" alt="derive column">
</div>

# <span class="yellow-text">Transform</span> Data in a Ready-to-Analysis Shape
- Scale: normalize or standardize numerical features
- Reduce variables: helps to reduce the number of features while retaining key information to avoid over-fitting and slow computation
- Encode: convert categorical variables into numerical format
<div class="columns">
    <img src="file/image/fig2_11.jpg" alt="scale">
    <img src="file/image/fig2_13.jpg" alt="encode">
</div>

# #4: Exploratory Data Analysis (EDA)
EDA refers to the process of performing <u>initial investigations</u> on data with the help of summary statistics and graphical representations.
- Understand the data distribution
- Identify patterns, trends, and anomalies
- Generate summary statistics and visualizations
- Formulate hypotheses and insights for further analysis
![bg right:40% w:90%](file/image/fig2_14.jpg)

# EDA Techniques
![bg right:60% w:90%](file/image/fig2_EDA.png.avif)

# #5: Build the Models
- With clean data in place and a good understanding of the content, you’re ready to build models with the goal of making better predictions, classifying objects, or gaining an understanding of the system that you’re modeling.
- The modeling techniques come from machine learning, data mining, neural network or statistics fields
![bg right:40% w:90%](file/image/fig2_21.jpg)

