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
- **Internal sources**: Databases, logs, ERP, CRM.
- **External sources**:  
  - Public datasets (e.g., Kaggle, data.gov)  
  - APIs (e.g., Twitter API, OpenWeather)  
  - Purchased data
- Evaluate:
  - Data availability
  - Data quality
  - Licensing

**Python Example — API Data Retrieval**:
```python
import requests

url = "https://api.github.com/repos/pandas-dev/pandas"
response = requests.get(url)
data = response.json()
print("Repo Name:", data['name'])
print("Stars:", data['stargazers_count'])