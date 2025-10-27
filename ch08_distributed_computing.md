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
# The Evolution of Distributed Computing
### From MapReduce (MR) to Spark
- Distributed computing is to break down a large computational task and distribute it across multiple computers (nodes) to work together collaboratively.
- Distributed computing is the method of making multiple computers work together to solve a common problem. It makes a computer network appear as a powerful single computer that provides large-scale resources to deal with complex challenges.

# Why Distributed Computing?
- To solve the problem of processing **Big Data** and **complex computations** that a single machine cannot handle.
- Three Major Advantages
  - High Scalability: ability to add nodes at any time to accommodate data growth
  - High Performance: significantly reducing processing time through parallel processing
  - High Fault Tolerance: partial node failures in the system do not affect overall operation

[![分散式架構，就是網站部署到多台主機](https://i.ytimg.com/vi/nugvkYs4lNE/default.jpg)](https://youtu.be/nugvkYs4lNE?si=s31ZpmqjlImZQaS0)

# Distributed Computing Framework: MapReduce and Spark
- **MapReduce (MR)**: developed by Google and divides tasks into two phases: Map and Reduce.
  - **Map Phase**: each node processes a portion of the data and produces intermediate key-value pairs.
  - **Reduce Phase**: the intermediate results are aggregated to produce the final output.
- **Apache Spark**: open-source and provides an **in-memory** data processing engine.
  - High speed and ease of use, supports Scala, Java, Python, and R.
>**Spark** provides a more flexible and efficient way to handle big data processing tasks compared to MapReduce.

# MapReduce
![MapReduce](https://miro.medium.com/v2/resize:fit:4800/format:webp/1*1gx5I6RbBoJieKjT-mzRzA.png)

# MapReduce: The Foundation of Distributed Batch Processing
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
[![深入浅出讲解 MapReduce](https://i.ytimg.com/vi/Rz8JCS9TfOQ/default.jpg)](https://youtu.be/Rz8JCS9TfOQ?si=hI5ZShVOhl9GlSwK
)

[map_reduce_word_count.ipynb](./file/code/map_reduce_word_count.ipynb)

# Spark
![Spark](https://www.bigdatawire.com/wp-content/uploads/2014/10/spark-logo_2.png)

# Spark: A General-Purpose Framework for In-Memory Computing
- A general-purpose cluster computing system for large-scale data processing.
- Developed at UC Berkeley's AMPLab and donated to Apache Software Foundation.
- Key Features:
  - **In-Memory Computing**: Stores intermediate results in memory, significantly speeding up iterative computations.
  - **Unified Engine**: Supports batch processing, streaming, SQL queries, machine learning, and graph processing.
  - **Rich APIs**: Provides high-level APIs in Scala, Java, Python (PySpark), and R.  
  - **Performance Improvement**: 10 ~ 100x faster
# In-Memory Computing
![In-Memory Computing](https://learn.microsoft.com/cs-cz/azure/hdinsight/spark/media/apache-spark-overview/map-reduce-vs-spark-large.svg#lightbox)

# Unified Engine

Apache Spark provides a unified framework supporting multiple data processing scenarios:

- **Batch Processing** - Traditional bulk data processing
- **Streaming** - Real-time data stream processing
- **Spark SQL** - Structured data querying
- **MLlib** - Distributed machine learning
- **GraphX** - Graph computation and analysis

# Rich APIs
![Spark Core Abstractions](https://miro.medium.com/v2/resize:fit:1074/format:webp/1*pDcp95CW4AtS_J6GZ-Blrg.png)

# Data Abstractions in Spark
- **RDD (Resilient Distributed Datasets)**: The fundamental abstraction representing a fault-tolerant, parallelizable collection of distributed elements.
- **DataFrame**: A higher-level abstraction that organizes data into a tabular format with named fields (similar to a relational database table or Pandas DataFrame).
- **Dataset**: A strongly-typed, object-oriented API that combines the benefits of RDDs and DataFrames, providing type safety and optimized execution.

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

Allows users to directly manipulate Spark DataFrames or RDD in a Python environment and execute large-scale MapReduce-style computations.

![PySpark](https://quintagroup.com/services/service-images/apache-spark-python-pyspark.jpg)

# PySpark RDD Practical Examples
### Transformation Operations: map, filter, flatMap, reduceByKey
Transformation operations are **lazily evaluated**, not immediately computed. Instead, they build a computation plan.

### Action Operations: reduce, collect, count, first, take
Action operations are **immediately executed**, triggering the computation and returning results to the driver or writing to storage.

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
rdd = spark.sparkContext.parallelize(["Hello World"])
result = rdd.flatMap(lambda x: x.split()) # Result: ["Hello", "World"]
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

# PySpark Syntax Illustration
[py_spark_basic.ipynb](./file/code/pyspark_basic.ipynb)

# PySpark Recap
[![What exactly is Apache Spark?](https://i.ytimg.com/vi/ymtq8yjmD9I/default.jpg)](https://youtu.be/ymtq8yjmD9I?si=4sdvpou55sJ4aqtn)

[![Spark Introduction | PySpark Tutorial for Beginners](https://i.ytimg.com/vi/avdPRFopLNw/default.jpg)](https://youtu.be/avdPRFopLNw?si=AFv6SrO0jslKazys)

# MapReduce vs. Spark Comparison

| Feature | MapReduce | Apache Spark |
|:---|:---|:---|
| Intermediate Result | Disk | Memory|
| Performance | Poor | Excellent|
| Abstraction Level | Low (Map/Reduce only) | High (RDD, DataFrame, Spark SQL) |
| Use Cases | simple batch processing | batch, streaming, SQL, ML |
| Development Languages | Java/Scala preferred | Python (PySpark), Scala, Java, R |

# Summary

### 1. The Foundational Role of Distributed Computing

Distributed computing is the foundational infrastructure for processing modern **big data**. Through parallel processing, resource sharing, and fault tolerance mechanisms, it overcomes the limitations of single-machine computing.

### 2. MapReduce's Contribution to Programming Models

MapReduce established the standard programming model for distributed **batch processing**. Through the elegant design of Map and Reduce functions, it ushered in a new era of big data processing.

### 3. Spark's Technological Breakthrough

Apache Spark has become the mainstream distributed computing framework through **in-memory computing** and a **unified engine**, supporting multiple scenarios including batch, streaming, SQL, and machine learning.

### 4. PySpark's Democratization Effect

By leveraging Python's ease of use and rich data science libraries, PySpark **significantly lowers the barrier to entry for distributed computing**, empowering the data science and machine learning fields.

# Homework


# Review Questions
1. What are the three main advantages of distributed computing?
2. Describe the two main phases of the MapReduce programming model.
3. What is the primary performance bottleneck in MapReduce, and why?
4. List at least three key features of Apache Spark.
5. Explain the difference between RDD, DataFrame, and Dataset in Spark.
6. Provide an example of a transformation operation and an action operation in PySpark.