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
# Data Science in a Big Data World
- <span class="blue-text">**Big data**</span> is a term for any collection of data sets so large or complex that it becomes difficult to process them using traditional data management techniques, such as relational database management systems.
- <span class="blue-text">**Data science**</span> involves using methods to analyze massive amounts of data and extract the knowledge it contains. 

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

# Big Data in Manufacturing
![w:750](https://nextgeninvent.com/wp-content/uploads/2024/07/Big-Data-in-Manufacturing-Use-Cases.jpg)

https://nextgeninvent.com/blogs/use-cases-of-big-data-in-manufacturing/

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
- <span class="blue-text">**Structured data**</span> is data that depends on a data model and resides in a fixed field within a record.
- <span class="blue-text">**Unstructured data**</span> is information that is not organized in a pre-defined data model or schema.
- <span class="blue-text">**Semi-structured data**</span> is information that doesn’t follow a strict tabular structure of relational databases, but still contains organizational properties (eg. tags) that make it easier to analyze than unstructured data.

# Data Type Comparison Table

| **Type**            | **Structure**              | **Example Formats**                 |
|---------------------|----------------------------|-------------------------------------|
| Structured          | Rigid schema (tables)      | SQL databases (ed. MySQL), XLSX     |
| Unstructured        | No predefined schema       | TXT, MP3, MP4, JPG, PDF, DOCX       |
| Semi-structured     | Loose schema (tags/keys)   | JSON, XML, NoSQL (e.g., MongoDB)    |

<span class="blue-text">How is Big Data classified?</span>
[![How is Big Data classified?](https://i.ytimg.com/vi/mnoqT8nihT8/mqdefault.jpg)](https://youtu.be/mnoqT8nihT8?si=KWAc5Fb7iRABHHio)
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
- A file in DFS will be divided into small blocks and stored on different servers. Hence, <span class="blue-text">DFS can handle large files</span>.
- DFS can replicate data across servers for <span class="blue-text">fault tolerance or parallel operations</span>.
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
  - <span class="blue-text">Hadoop Distributed File System (HDFS)</span>: A distributed file system that stores data across multiple machines.
  - <span class="blue-text">MapReduce</span>: A programming model for processing large datasets in parallel.
  - <span class="blue-text">YARN (Yet Another Resource Negotiator)</span>: A resource management layer for Hadoop that manages and schedules resources across the cluster.

# Hadoop Introduction
Hadoop In 5 Minutes: What Is Hadoop and Hadoop Ecosystem
[![Hadoop In 5 Minutes](https://i.ytimg.com/vi/aReuLtY0YMI/mqdefault.jpg)](https://youtu.be/aReuLtY0YMI?si=LTkJOQUQdB6Ib-m6)


# Scalability
Scalability is the ability of a system to handle a growing amount of work, or its potential growth.
- <span class="blue-text">Scale up</span> (vertical scaling): adding more power (CPU, RAM) to an existing machine.
- <span class="blue-text">Scale out</span> (horizontal scaling): adding more machines to a pool of resources
<br>
<div class="columns">

**Scale Up vs. Scale Out Data Storage**
[![Scale Up vs. Scale Out Data Storage](https://i.ytimg.com/vi/W7S7dQgvS4c/default.jpg)](https://youtu.be/W7S7dQgvS4c?si=YHojS_YExApNFoKq)

**Differences of scaling methods**
[![Vertical Vs Horizontal Scaling: Key Differences You Should Know](https://i.ytimg.com/vi/dvRFHG2-uYs/default.jpg)](https://youtu.be/dvRFHG2-uYs?si=xXppSLvtj_1MUk4o)
</div>

# Data Integration Framework
Data integration is the process with tools of combining data from multiple sources to provide a single, unified view.
- Data Extraction: pulling data from each source
- Data Transformation: cleaning, formatting, and mapping data into a consistent schema
- Data Loading: storing data in a target system
![w:350](https://estuary.dev/static/0eea2debd9d8130824e2b76ca45cb174/afeb4/773441_Traditional_ETL_769231de23.webp)

# Machine Learning Framework
A machine learning (ML) framework is a software library or platform that simplifies the process of building ML models by providing pre-built algorithms, data preprocessing tools, and model evaluation metrics. Examples include TensorFlow, PyTorch, and Scikit-learn.
<br>
<div class="columns">

**AI, Machine Learning, Deep Learning**
[![一圖解說人工智能、機器學習、深度學習](https://i.ytimg.com/vi/OZkVmsLNKl4/mqdefault.jpg)](https://youtu.be/OZkVmsLNKl4?si=aJETdpISe579b0ts)

**Machine Learning Explained in 100 Seconds**
[![ML explained in 100 seconds](https://i.ytimg.com/vi/PeMlggyqz0Y/mqdefault.jpg)](https://youtu.be/PeMlggyqz0Y?si=zOsi99AdQK0xBbIU)

</div>

# Failure of Traditional Database in Handling Big Data
- The Relational Database Management Systems (RDBMS) was the most common data storage medium until recently to store the data generated by the organizations
- To store exponential increase data volume, the RDBMS increased the number of processors and added more memory units, which in turn increased the cost.
- Almost 80% of the data fetched were of semi-structured and unstructured format, which RDBMS could not deal with.
- RDBMS could not capture the data coming in at high velocity.

# Compare Traditional Data and Big Data

| Attributes      | Traditional Data             | Big Data.                           |
|-----------------|------------------------------|-------------------------------------|
| Data store      | Relational database (RDB)    | Not only SQL (NoSQL)                |
| Data volume     | gigabytes to terabytes       | petabytes to zettabytes             |
| Organization    | centralized                  | distributed                         |
| Data type       | structured                   | unstructured and semi-structured    |
| Hardware type   | high-end model                | commodity hardware                 |
| Updates         | read/write many times         | write once, read many times        |

How is Big Data stored and processed [![How is Big Data stored and processed](https://i.ytimg.com/vi/Sc9N_xkCYcY/default.jpg)](https://youtu.be/Sc9N_xkCYcY?si=dwKLXOwAkwBPnRRH)


# NoSQL Database
NoSQL (Not Only SQL), a category of databases designed to handle large-scale, unstructured, semi-structured data. It does not use relational model to manipulate data.
- Schema-less or flexible schema – You can store data without predefined table structures.
- Horizontal scalability – Easily add more servers to handle more data/traffic.
- High performance – Optimized for read/write speed at scale.
- Variety of data models – Key-value, document, column-family, graph.

# Compare RDB and NoSQL
Attribute | RDB                                  | NoSQL                                                                               |
|---------|--------------------------------------|-------------------------------------------------------------------------------------|
|Data model | Structured data with a rigid schema| Structured, Unstructured, Semi-Structured data with a flexible schema               |
|Storage structure| Storage in rows and columns  | Data stored in Key/Value DB, Columnar DB, Document DB, Graph DB|
|Scalability| Scale up                           | Scale out                                                                           |
|Example| Oracle, MySQL              | Redis, Cassandra, MongoDB, Neo4j                                                    |
|Query  | SQL language                   | Solution-specific method                                                            |

Battle of SQL and NoSQL [![Battle of SQL and NoSQL](https://i.ytimg.com/vi/8QK_RNLFfZM/default.jpg)](https://youtube.com/shorts/8QK_RNLFfZM?si=msfp04YhHhw0nlPd)

# Scheduling Tools
Scheduling tools are used to automate the execution of tasks or workflows in a big data environment. They help manage dependencies, monitor job status, and ensure that tasks run at the right time.

# Benchmarking Tools
Benchmarking tools are used to measure the performance of big data systems and applications. They help identify bottlenecks, optimize resource usage, and ensure that systems meet performance requirements.

# System Deployment
System deployment involves the process of making a big data application or system operational in a production environment. This includes configuring hardware and software, setting up data pipelines, and ensuring that the system can handle real-world workloads.

# Service Programming
Service programming involves writing code to create and manage services that run on big data platforms. This includes developing APIs, microservices, and other components that enable data processing, analysis, and visualization.

# Security
Security in big data involves protecting data from unauthorized access, ensuring data integrity, and maintaining privacy. This includes implementing encryption, access controls, and monitoring tools to safeguard sensitive information.

# Hadoop EcoSystem
HDFS: Hadoop Distributed File System
YARN: Yet Another Resource Negotiator
MapReduce: Distributed data processing programming model
Spark -> In-memory distributed data processing
HBase -> NoSQL data store
Mahout, Spark MLlib -> machine learning
Zookeeper -> Managing cluster
Oozie -> Job scheduling
Flume, Sqoop -> Data ingesting services
Ambari -> Provision, monitor and maintain cluster

# Hadoop Ecosystem Frameworks
<div class="columns">

![w:600](https://d1jnx9ba8s6j9r.cloudfront.net/blog/wp-content/uploads/2016/10/HADOOP-ECOSYSTEM-Edureka.png)

[![ML explained in 100 seconds](https://i.ytimg.com/vi/RFzRJIT08dg/hqdefault.jpg)](https://youtu.be/RFzRJIT08dg?si=BdD4rxyGv6fO-hWK)

</div>

# Summary
<span class="small-text">

- Big data is a blanket term for any collection of data sets so large or complex that it becomes difficult to process them using traditional data management techniques. They are characterized by the four Vs: velocity, variety, volume and veracity.
- Data science involves using methods to analyze small data sets to the gargantuan ones big data is all about.
- The big data landscape is more than Hadoop alone. It consists of many different technologies that can be categorized into the following:
  – File system
  – Distributed programming frameworks
  – Data integration
  – Databases
  – Machine learning
  – Security
  – Scheduling
  – Benchmarking
  – System deployment
  – Service programming
- Not every big data category is utilized heavily by data scientists. They focus mainly on the file system, the distributed programming frameworks, databases, and machine learning. They do come in contact with the other components, but these are domains of other professions.
- Data can come in different forms. The main forms are
  – Structured data
  – Unstructured data
  – Semi-structured data
</span>

# Review

# 1. Which of the following best describes Big Data?
A. Small datasets stored in relational databases
B. Data sets so large or complex that they are difficult to process using traditional methods
C. Data that only exists in text format
D. Data stored exclusively in spreadsheets

# 2. Which of the following is NOT part of the 4Vs of Big Data?
A. Volume
B. Variety
C. Velocity
D. Visualization

# 3. What is an example of semi-structured data?
A. MP3 audio file
B. JSON file
C. Excel table
D. SQL database

# 4. In a Distributed File System (DFS), data is:
A. Stored on a single centralized machine
B. Divided into blocks and stored across multiple servers
C. Only stored in the cloud
D. Encrypted and hidden by default

# 5. Which component of the Hadoop ecosystem stores data across multiple machines?
A. YARN
B. MapReduce
C. HDFS
D. Spark

# 6. Which scaling method means adding more machines to a system?
A. Scale up
B. Scale out
C. Scale in
D. Scale deep

# 7. Which of the following is an example of a Big Data processing framework?
A. MySQL
B. Hadoop MapReduce
C. Excel
D. SQLite

# 8. Which is a correct statement about NoSQL databases?
A. They require a rigid, predefined schema
B. They can store structured, semi-structured, and unstructured data
C. They cannot scale horizontally
D. They store data only in relational tables

# 9. Which part of the Hadoop ecosystem is used for job scheduling?
A. Oozie
B. Spark
C. Flume
D. HBase

# 10. Which of the following is an example of unstructured data?
A. XLSX spreadsheet
B. XML file
C. MP4 video file
D. JSON file
