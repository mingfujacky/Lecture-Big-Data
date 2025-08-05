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
# Data Science in a Big Data World
- <span class="yellow-text">**Big data**</span> is a term for any collection of data sets so large or complex that it becomes difficult to process them using traditional data management techniques, such as relational database management systems.
- <span class="yellow-text">**Data science**</span> involves using methods to analyze massive amounts of data and extract the knowledge it contains. 

# Benefits and Uses of Data Science and Big Data

| **Benefit Area**                  | **Use Case / Application**|
|-----------------------------------|---------------------------|
| Business intelligence & marketing | Targeted advertising      |
|                                   | Campaign optimization     |
| Operations, risk & finance        | Fraud detection           |
|                                   | Operations optimization   |
| Public services & social good     | Government analytics & open data |
|                                   | National security & surveillance |
| Education & research              | Online learning analytics (MOOCs)|
|                                   | Scientific research acceleration |
# Characteristics of Big Data
- **Volume**: How much data is there?
- **Variety**: How diverse are different types of data?
- **Velocity**: At what speed is new data generated?
- **Veracity**: How accurate is the data? 
>The 4V make big data different from the data found in traditional data management tools.
>Big data calls for specialized techniques to capture, store, search, analyze data and extract the insights.
![bg right:35% w:90% The FOUR V's of Big Data](https://pbs.twimg.com/media/GNKWpaSWEAEeFVz.png)

# Volume of Data
- By 2025, global data is projected to reach 181 zettabytes, with significant contributions from AI-driven content, social media, IoT devices, and cloud computing.
- Units of data size: kilobytes (KB), megabytes (MB), gigabytes (GB), terabytes (TB), petabytes (PB), exabytes (EB), and zettabytes (ZB).
- 1 ZB = 250 billion DVDs

# Variety of Data
- <span class="yellow-text">**Structured data**</span> is data that depends on a data model and resides in a fixed field within a record.
- <span class="yellow-text">**Unstructured data**</span> is information that is not organized in a pre-defined data model or schema.
- <span class="yellow-text">**Semi-structured data**</span> is information that doesn’t follow a strict tabular structure of relational databases, but still contains organizational properties (eg. tags) that make it easier to analyze than unstructured data.

# Data Type Comparison Table

| **Type**            | **Structure**              | **Example Formats**                 |
|---------------------|----------------------------|-------------------------------------|
| Structured          | Rigid schema (tables)      | SQL databases (ed. MySQL), XLSX     |
| Unstructured        | No predefined schema       | TXT, MP3, MP4, JPG, PDF, DOCX       |
| Semi-structured     | Loose schema (tags/keys)   | JSON, XML, NoSQL (e.g., MongoDB)    |

[How is Big Data classified?](https://youtu.be/mnoqT8nihT8?si=KWAc5Fb7iRABHHio)

# Iterative Data Science Process
![bg right:50% w:90%](file/image/fig1_5.jpg)
1. why, what, how, when
2. where to get data
3. clean, integrate, transform data
4. data understanding
5. statistics, machine learning, neural networks
6. data visualization and production

# The Big Data Ecosystem
![bg right:60% w:65%](file/image/fig1_6.jpg)

# Distributed File System (DFS)
- DFS can store files larger than any one disk.
- DFS can replicate data across multiple servers for redundancy or parallel operations.
- DFS scales easily, scale out instead of scale up.
- Hadoop Distributed File System (HDFS) is an example.
![bg right:50% w:90%](file/image/HDFS-working.jpg.webp)