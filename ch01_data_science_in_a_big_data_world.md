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

# Characteristics of Big Data
- **Volume**: How much data is there?
- **Variety**: How diverse are different types of data?
- **Velocity**: At what speed is new data generated?
- **Veracity**: How accurate is the data? 
>The 4V make big data different from the data found in traditional data management tools.
>Big data calls for specialized techniques to capture, store, search, analyze data and extract the insights.
![bg right:35% w:90% The FOUR V's of Big Data](https://pbs.twimg.com/media/GNKWpaSWEAEeFVz.png)