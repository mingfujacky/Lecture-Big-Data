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
- **Veracity**: How the quality and reliability of data? 
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

<span class="yellow-text">How is Big Data classified?</span>
[![How is Big Data classified?](https://i.ytimg.com/vi/mnoqT8nihT8/default.jpg)](https://youtu.be/mnoqT8nihT8?si=KWAc5Fb7iRABHHio)
[]()

# Velocity of Data
- Generate real-time or near-real-time data flow: data streams continuously, not in batches.
- Fulfill high-speed processing requirement: systems must analyze and act on data as it arrives.
- Impact on decision-making: faster insights to perform quicker, more relevant actions.

# Veracity of Data
- Data accuracy: data is correct
- Consistency: data is the same across systems
- Bias & noise: avoid irrelevant, misleading, or biased information
- Source credibility: data collected from reliable channels?



# The Big Data Ecosystem
>Total solutions to meet the challenges of big data like storage, processing, analysis, and visualization.
![bg right:60% w:65%](file/image/fig1_6.jpg)

# Distributed File System
- DFS is similar to a normal file system except that DFS runs on multiple servers at once. 
- You can store, read, delete and secure files via DFS as you do in a standalone machine.
- A file in DFS will be divided into small blocks and stored on different servers. Hence, <span class="yellow-text">DFS can handle large files</span>.
- DFS can replicate data across servers for <span class="yellow-text">fault tolerance or parallel operations</span>.
- Hadoop Distributed File System (HDFS) is an example.
![bg right:40% w:80%](file/image/HDFS-working.jpg.webp)

# Distributed Programming Framework
Instead of one machine doing all the work, distributed programming is a programming model where multiple computers work together on a single task by sharing work and communicating over a network. Hadoop MapReduce is a popular example of distributed programming.
1. Divide the task into smaller subtasks.
2. Distribute the subtasks to different nodes.
3. Execute them in parallel.
4. Communicate and synchronize results between nodes.
5. Combine the results into a final output.

# Hadoop Quick View
- Hadoop is an open-source framework for distributed storage and distributed processing of large datasets.
- It is designed to scale up from a single server to thousands of machines, each offering local computation and storage.
- The core components of Hadoop are:
  - <span class="yellow-text">Hadoop Distributed File System (HDFS)</span>: A distributed file system that stores data across multiple machines.
  - <span class="yellow-text">MapReduce</span>: A programming model for processing large datasets in parallel.
  - <span class="yellow-text">YARN (Yet Another Resource Negotiator)</span>: A resource management layer for Hadoop that manages and schedules resources across the cluster.

# Hadoop Introduction
Big Data In 5 Minutes: What Is Big Data and Big Data Analytics
[![Big Data In 5 Minutes](https://i.ytimg.com/vi/bAyrObl7TYE/default.jpg)](https://youtu.be/bAyrObl7TYE?si=m3a_g25_q52Sdw46)

Hadoop In 5 Minutes: What Is Hadoop and Hadoop Ecosystem
[![Hadoop In 5 Minutes](https://i.ytimg.com/vi/aReuLtY0YMI/default.jpg)](https://youtu.be/aReuLtY0YMI?si=LTkJOQUQdB6Ib-m6)


# Scalability
Scalability is the ability of a system to handle a growing amount of work, or its potential growth.
- <span class="yellow-text">Scale up</span> (vertical scaling): adding more power (CPU, RAM) to an existing machine.
- <span class="yellow-text">Scale out</span> (horizontal scaling): adding more machines to a pool of resources

Scale Up vs. Scale Out Data Storage
[![Scale Up vs. Scale Out Data Storage](https://i.ytimg.com/vi/W7S7dQgvS4c/default.jpg)](https://youtu.be/W7S7dQgvS4c?si=YHojS_YExApNFoKq)
Vertical Vs Horizontal Scaling: Key Differences You Should Know
[![Vertical Vs Horizontal Scaling: Key Differences You Should Know](https://i.ytimg.com/vi/dvRFHG2-uYs/default.jpg)](https://youtu.be/dvRFHG2-uYs?si=xXppSLvtj_1MUk4o)

# Data Integration Framework
Data integration is the process (often with tools, processes, and rules) of combining data from multiple sources to provide a single, unified view.
- Data Extraction: pulling data from each source
- Data Transformation: cleaning, formatting, and mapping data into a consistent schema
- Data Loading: storing data in a target system

# Machine Learning Framework
A machine learning (ML) framework is a software library or platform that simplifies the process of building ML models by providing pre-built algorithms, data preprocessing tools, and model evaluation metrics. Examples include TensorFlow, PyTorch, and Scikit-learn.

一圖解說人工智能、機器學習、深度學習之分別
[![一圖解說人工智能、機器學習、深度學習之分別](https://i.ytimg.com/vi/OZkVmsLNKl4/default.jpg)](https://youtu.be/OZkVmsLNKl4?si=aJETdpISe579b0ts)
Machine Learning Explained in 100 Seconds
[![Machine Learning Explained in 100 Seconds](https://i.ytimg.com/vi/PeMlggyqz0Y/default.jpg)](https://youtu.be/PeMlggyqz0Y?si=zOsi99AdQK0xBbIU)

# NoSQL Database
NoSQL (Not Only SQL), a category of databases designed to handle large-scale, unstructured, semi-structured data. It does not use relational model to manipulate data.
- Schema-less or flexible schema – You can store data without predefined table structures.
- Horizontal scalability – Easily add more servers to handle more data/traffic.
- High performance – Optimized for read/write speed at scale.
- Variety of data models – Key-value, document, column-family, graph.


# Iterative Data Science Process
![bg right:50% w:90%](file/image/fig1_5.jpg)
1. why, what, how, when
2. where to get data
3. clean, integrate, transform data
4. data understanding
5. statistics, machine learning, neural networks
6. data visualization and production