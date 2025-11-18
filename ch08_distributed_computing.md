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
# Distributed Computing
- Distributed computing is the method of making **multiple computers work together** to solve a common problem. It makes a computer network appear as a powerful single computer that provides large-scale resources to deal with complex challenges.
- Distributed computing is to **break down** a large task and distribute it across multiple computers (nodes) to work together collaboratively.

# Why Distributed Computing?
- To solve the problem of processing **Big Data** and **complex computations** that a single machine cannot handle.
- Three Major Advantages
  - High Scalability: ability to add nodes at any time to accommodate data growth
  - High Performance: significantly reducing processing time through parallel processing
  - High Fault Tolerance: partial node failures in the system do not affect overall operation

[![分散式架構，就是網站部署到多台主機](https://i.ytimg.com/vi/nugvkYs4lNE/default.jpg)](https://youtu.be/nugvkYs4lNE?si=s31ZpmqjlImZQaS0)

# Distributed Computing Architecture
- **Cluster Computing**: a group of interconnected computers (nodes) working together as a single system to perform tasks.
- **Cloud Computing**: provides on-demand access to computing resources (servers, storage, databases, networking, software) over the internet.
- **Grid Computing**: a geographically distributed computer networks work together to perform common tasks. You can make grid computing from computing resources which belong to multiple individuals or organizations.
[![Distributed Computing: Cluster, Cloud and Grid Computing](https://i.ytimg.com/vi/HJiXLDItJSY/default.jpg)](https://youtu.be/HJiXLDItJSY?si=iR_IEip35ACx7by9)
[![Grid Computing](https://i.ytimg.com/vi/QHWy94eBfis/default.jpg)](https://youtu.be/QHWy94eBfis?si=2wzFxSigMlasyLwV)


# Data Processing Types
- Batch Processing: process data periodically in batches. eg. Payroll System
- Real-Time (streaming) Processing: process data as it arrives. eg. Sensor monitoring
[![Batch processing vs real-time processing](https://i.ytimg.com/vi/M1Gq53Hf0_Y/default.jpg)](https://youtu.be/M1Gq53Hf0_Y?si=E1EHbwCsQCMOZC1t)
[![What is Stream Processing?](https://i.ytimg.com/vi/ya4298V8Mqo/default.jpg)](https://youtu.be/ya4298V8Mqo?si=xXTRwXMdGZ3NWHYJ)
[![Batch vs Real time Processing](https://i.ytimg.com/vi/2VJLWot9T7Y/default.jpg)](https://youtu.be/2VJLWot9T7Y?si=V6pd4kLJ90mWQzQ_)


# Distributed Computing Framework: MR and Spark
- **MapReduce (MR)**: developed by Google and divides tasks into two phases: Map and Reduce.
  - **Map Phase**: each node processes a portion of the data and produces intermediate key-value pairs.
  - **Reduce Phase**: the intermediate results are aggregated to produce the final output.
- **Spark**: open-source and provides an **in-memory** data processing engine.
  - High speed and ease of use, supports Scala, Java, Python, and R.
>**Spark** provides a more flexible and efficient way to handle big data processing tasks compared to MapReduce.

# MapReduce
![MapReduce](https://miro.medium.com/v2/resize:fit:4800/format:webp/1*1gx5I6RbBoJieKjT-mzRzA.png)

# MR: Foundation of Distributed Batch Processing
- Proposed by **Google**, it was the standard model for processing large-scale datasets in the early days of big data.
- The data processing workflow is abstracted into two simple, parallelizable functions
  - **Map (Mapping)**: Processes input data and transforms it into a series of intermediate key-value pairs `(key, value)`.
  - **Reduce (Aggregation)**: Receives all values associated with the same key, performs aggregation and computation, and produces the final result.
- Key limitation: Intermediate results must be written to **disk (Disk I/O)**, which makes multi-step or iterative computations inefficient.

# MapReduce Workflow (1/2)
The MapReduce workflow consists of five main stages:
```
Input → Map → Shuffle & Sort → Reduce → Output
```
- **Input**: the original dataset is split into multiple partitions and distributed to individual Map tasks.

- **Map**: each node independently executes the Map function, transforming input data into intermediate key-value pairs `(key, value)`.

- **Shuffle & Sort**: system collects all values associated with the same key and distributes them to the responsible Reduce node. This stage involves huge network transmission and disk I/O.

# MapReduce Workflow (2/2)

- **Reduce**: Each node executes the Reduce function, aggregating all values for the same key.
- **Output**: The final result.
> Performance Bottleneck: <u>Shuffle & Sort Stage</u>
The Shuffle stage involves extensive network transmission and disk I/O, making it the primary performance bottleneck in MapReduce.

# MapReduce Word Count Example
[![深入浅出讲解 MapReduce](https://i.ytimg.com/vi/Rz8JCS9TfOQ/default.jpg)](https://youtu.be/Rz8JCS9TfOQ?si=XR8oWLC7Ky_4VBc5&t=111)

[map_reduce_word_count.ipynb](./file/code/map_reduce_word_count.ipynb)

# Spark
![Spark](https://upload.wikimedia.org/wikipedia/commons/thumb/f/f3/Apache_Spark_logo.svg/1024px-Apache_Spark_logo.svg.png?20210416091439)

# Spark: In-Memory Computing Framework
- A general-purpose cluster computing system for large-scale data processing.
- Developed at UC Berkeley's AMPLab and donated to Apache Software Foundation.
- Key Features:
  - **In-Memory Computing**: Stores intermediate results in memory, significantly speeding up iterative computations.
  - **Unified Engine**: Supports batch processing, streaming, SQL queries, machine learning, and graph processing.
  - **Rich APIs**: Provides high-level APIs in Scala, Java, Python (PySpark), and R.  
  - **Performance Improvement**: 10 ~ 100x faster
# In-Memory Computing
![In-Memory Computing](https://www.datasciencecentral.com/wp-content/uploads/2021/10/image-17-2.png)

# Unified Engine and Rich APIs
![bg right:40% w:100%](https://miro.medium.com/v2/resize:fit:1400/format:webp/1*ep6UOAKIndF1-g6PcF28aQ.png)

Apache Spark provides a unified framework supporting multiple data processing scenarios:
- **Code** - Batch data processing
- **Streaming** - Streaming data processing
- **SQL** - Structured data querying
- **MLlib** - Distributed machine learning
- **GraphX** - Graph computation and analysis

APIs: Scala, Java, Python, R

# Spark RDD and Framework
<img src="https://www.cloudduggu.com/spark/rdd-introduction/rdd-operation.png" width="45%">
<img src="https://www.databricks.com/wp-content/uploads/2018/05/Spark-Applications.png" width="50%">

# Spark RDD（Resilient Distributed Dataset)
- RDD (彈性分散式資料集) 是 Spark 進行分散式資料處理的基礎抽象資料結構。它可以將大規模資料集分散在多個計算節點上，並實現高效能的平行處理。
- 彈性與容錯性 (Resilient)：RDD 能夠自動從故障中恢復，確保資料處理的可靠性。
- 分散式 (Distributed)：RDD 將資料分散存儲在多個節點上，利用集群進行平行處理。
- 不可變性 (Immutable)：一旦建立，RDD 就不能被修改。任何轉換操作（如 map、filter）都會產生一個新的 RDD。
- 惰性計算 (Lazy Evaluation)：轉換操作不會立即執行，而是記錄下來形成一個執行計畫。只有當觸發一個「行動」（Action）操作（如 count、collect、save）時，才會真正執行計算，這種機制有助於最佳化整體執行效率。

# Spark Overview
[![What exactly is Apache Spark?](https://i.ytimg.com/vi/ymtq8yjmD9I/default.jpg)](https://youtu.be/ymtq8yjmD9I?si=sFoYA3fc7eNFCyOu)




# Data Abstractions (Structure) in Spark
- **RDD (Resilient Distributed Datasets)**: The fundamental abstraction representing a fault-tolerant, parallelizable collection of distributed elements.
- **DataFrame**: A higher-level abstraction that organizes data into a tabular format with named fields (similar to a relational database table or Pandas DataFrame).
- Dataset: A strongly-typed, distributed collection of data that combines the benefits of RDDs and DataFrames, providing type safety and object-oriented programming features.(available only in Scala/Java, not in PySpark)

# RDD (1/2)
RDD (Resilient Distributed Datasets) is a Spark's **fundamental abstraction**, representing a fault-tolerant, parallelizable collection of distributed elements. Similar to Arrays or Lists
```
                ┌──────────────────────────────┐
                │        RDD (Logical View)    │
                │  [1, 2, 3, 4, 5, 6, 7, 8]    │
                └──────────────┬───────────────┘
          ┌────────────────────┼────────────────────┐
          ▼                    ▼                    ▼
 ┌─────────────────┐    ┌─────────────────┐    ┌─────────────────┐
 │ Partition 1     │    │ Partition 2     │    │ Partition 3     │
 │ [1, 2, 3]       │    │ [4, 5, 6]       │    │ [7, 8]          │
 └────────┬────────┘    └────────┬────────┘    └────────┬────────┘
          ▼                      ▼                      ▼
   Worker Node A          Worker Node B          Worker Node C
     (Executor)             (Executor)             (Executor)
```

# RDD (2/2)
- The top box shows the RDD as a single logical dataset from the user’s perspective.
- It is split into multiple partitions (smaller chunks of data).
- Each partition is sent to a different worker node in the cluster for parallel processing.
- If a node fails, Spark can rebuild its partition using the lineage information (that’s the “Resilient” part).

# DataFrame
- A **higher-level abstraction** that organizes data into a tabular format with named fields (similar to a relational database table or Pandas DataFrame).

![DataFrame](https://lam-tran.dev/assets/images/RDD-Dataframe-Dataset-bcdbc9781335a0251713276723599867.svg)

# PySpark: Python API for Apache Spark

- PySpark 是 Python 的一個Spark Library，主要是利用Python語法結合Spark的框架,是現在很主流的一個處理大量資料的框架之一。
- Allows users to directly manipulate Spark DataFrames or RDD in a Python environment.
![PySpark](https://quintagroup.com/services/service-images/apache-spark-python-pyspark.jpg)

# PySpark Operator RDD

![bg right:50% w:80%](https://docs.aws.amazon.com/zh_tw/prescriptive-guidance/latest/tuning-aws-glue-for-apache-spark/images/store-data-memory.png)

**Transformation operations**
  - map, filter, flatMap, reduceByKey
  - Lazily evaluated, not immediately computed. Instead, they build a computation plan.

**Action operations**
  - reduce, collect, count, first, take
  - immediately executed, triggering the computation and returning results to the driver or writing to storage.

# 0. Setup PySpark Environment

```python
from pyspark.sql import SparkSession

# create a Spark session
spark = SparkSession.builder.appName("PySpark_Get_Started").getOrCreate()
```

# Transformation Operations: map, filter, flatMap, reduceByKey
Transformation operations are **lazily evaluated**, not immediately computed. Instead, they build a computation plan.

# 1. map - Mapping Transformation

```python
from pyspark.sql import SparkSession
spark = SparkSession.builder.appName("PySpark_Get_Started").getOrCreate()

# Multiply each element by 2
rdd = spark.sparkContext.parallelize([1, 2, 3, 4])
result = rdd.map(lambda x: x * 2) # Result: [2, 4, 6, 8]
```
**Explanation**: Applies a function to each element in the RDD and returns a new RDD.

# 2. filter - Filtering

```python
from pyspark.sql import SparkSession
spark = SparkSession.builder.appName("PySpark_Get_Started").getOrCreate()

# Keep only even numbers
rdd = spark.sparkContext.parallelize([1, 2, 3, 4, 5])
result = rdd.filter(lambda x: x % 2 == 0) # Result: [2, 4]
```
**Explanation**: Filters elements based on a condition, keeping only those that satisfy it.

# 3. flatMap - Flat Mapping

```python
from pyspark.sql import SparkSession
spark = SparkSession.builder.appName("PySpark_Get_Started").getOrCreate()

# Split each string into words and flatten
rdd = spark.sparkContext.parallelize(["Hello world", "Apache Spark"])
result_map = rdd.map(lambda x: x.split()) # Result: [["Hello", "world"], ["Apache", "Spark"]]
result_flatMap = rdd.flatMap(lambda x: x.split()) # Result: ["Hello", "world", "Apache", "Spark"]
```
**Explanation**: Maps and then flattens the results, commonly used for tokenization or splitting operations.

# 4. reduceByKey - Reduce by Key

```python
from pyspark.sql import SparkSession
spark = SparkSession.builder.appName("PySpark_Get_Started").getOrCreate()

# Count occurrences of each word
rdd = spark.sparkContext.parallelize([("apple", 1), ("banana", 1), ("apple", 1)])
result = rdd.reduceByKey(lambda a, b: a + b) # Result: [("apple", 2), ("banana", 1)]
```
**Explanation**: Aggregates values with the same key.

# Action Operations: reduce, collect, count, first, take
Action operations are **immediately executed**, triggering the computation and returning results to the driver or writing to storage.

# 1. reduce - Aggregation

```python
from pyspark.sql import SparkSession
spark = SparkSession.builder.appName("PySpark_Get_Started").getOrCreate()

# Calculate the sum of all elements
rdd = spark.sparkContext.parallelize([1, 2, 3, 4])
result = rdd.reduce(lambda a, b: a + b) # Result: 10
```
**Explanation**: Aggregates all elements in the RDD into a single value.

# 2. collect - Collect Results

```python
from pyspark.sql import SparkSession
spark = SparkSession.builder.appName("PySpark_Get_Started").getOrCreate()

# Return RDD results to the driver program
rdd = spark.sparkContext.parallelize([1, 2, 3, 4])
result = rdd.collect() # Result: [1, 2, 3, 4]
```
**Explanation**: Collects all elements of the distributed RDD into the driver program's memory.
> **Note**: Use collect() carefully as it loads the entire RDD into the driver's memory, potentially causing memory overflow.

# 3. count - Counting

```python
from pyspark.sql import SparkSession
spark = SparkSession.builder.appName("PySpark_Get_Started").getOrCreate()

# Count the number of elements in the RDD
rdd = spark.sparkContext.parallelize([1, 2, 3, 4, 5])
result = rdd.count() # Result: 5
```
**Explanation**: Returns the total number of elements in the RDD.

# 4. first - Get First Element

```python
from pyspark.sql import SparkSession
spark = SparkSession.builder.appName("PySpark_Get_Started").getOrCreate()

# Get the first element of the RDD
rdd = spark.sparkContext.parallelize([1, 2, 3, 4])
result = rdd.first() # Result: 1
```
**Explanation**: Returns the first element of the RDD.

# 5. take - Get First N Elements

```python
from pyspark.sql import SparkSession
spark = SparkSession.builder.appName("PySpark_Get_Started").getOrCreate()

# Get the first 3 elements of the RDD
rdd = spark.sparkContext.parallelize([1, 2, 3, 4, 5])
result = rdd.take(3) # Result: [1, 2, 3]
```
**Explanation**: Returns the first N elements of the RDD.

# PySpark Word Count Example
[pyspark_word_count.ipynb](./file/code/pyspark_word_count.ipynb)

# PySpark Syntax of RDD, DataFrame and Spark SQL
[py_spark_basic.ipynb](./file/code/pyspark_basic.ipynb)

# PySpark Recap
[![Spark Introduction | PySpark Tutorial for Beginners](https://i.ytimg.com/vi/avdPRFopLNw/default.jpg)](https://youtu.be/avdPRFopLNw?si=AFv6SrO0jslKazys)

# MapReduce vs. Spark Comparison

| Feature | MapReduce | Apache Spark |
|:---|:---|:---|
| Intermediate Result | Disk | Memory|
| Performance | Poor | Excellent|
| Use Cases | simple batch processing | batch, streaming, SQL, ML |
| Development Languages | Java/Scala preferred | Python (PySpark), Scala, Java, R |

# Summary
- Distributed computing enables processing of large-scale data by distributing tasks across multiple machines.
- MapReduce is a foundational distributed computing model with Map and Reduce phases but suffers from performance bottlenecks due to disk I/O.
- Apache Spark is a modern distributed computing framework that utilizes in-memory computing for high performance and supports various data processing scenarios.
- PySpark provides a Python library to work with Spark, allowing users to perform distributed data processing using familiar Python syntax.

# Homework
HW6 - Utilize PySpark RDD and DataFrame

# Review Questions
1. What are the three main advantages of distributed computing?
2. Describe the two main phases of the MapReduce programming model.
3. What is the primary performance bottleneck in MapReduce, and why?
4. List at least three key features of Apache Spark.
5. Explain the difference between RDD, DataFrame, and Dataset in Spark.
6. Provide an example of a transformation operation and an action operation in PySpark.