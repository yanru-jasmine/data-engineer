# data-engineer
After one year experience as a Data Analyst, I am kind of confused with my future career roadmap, and made up my mind to break the ceiling by becoming a Data Engineer, This repo is aimed for keeping track of my learning path of Data Engineer.

# Why
I did a research on May 19th 2024 about different kind of data jobs through job search platforms. In comparison, LinkedIn has better filtered data, so I meanly use it for analysis.

There are five factors that really matter to me: opening, remote, high salary (100K+), entry level and visa sponsorship. I assigned different weight to each factor and here is my result: Data Engineer wins with 39 scores in total, standing out for nearly every factor above. Though Data Analyst has the most opening, only a few company sponsor H1B or Green Card, which is similar to Business Analyst. Data Scientist has good salary and visa policy, but not has many entry level jobs. 

In conclusion, Data Engineer is the best choice for me at current stage.

# What
I summarized common Data Enginner skills in some job descriptions. (order reflect importance)
- ETL pipeline
- data warehousing (AWS Redshift, Google BigQuery, Snowflake)
- data modeling
- data integration (SLA)
- cloud (Azure, AWS, GCP)
- big data (terabyte to petabyte scale)
- database design (schema design)
- scripting (Python, Pyspark, Scala, SQL, Unix Shell scripting)
- data quality (check automation)
- data validation (testing & monitoring)
- streaming technology
- data processing pattern (batch, stream)
- performance optimization
- data goverance
- Agile
- information management
- data visualization/business intelligence
- machine learning
- analytical
- problem-solving
- business acumen

And I assign priority levels according to the difficulty and my proficiency.
- top priority: ETL pipeline, data warehousing, cloud, scripting (Unix, Python), streaming technology, 
- medium: data modeling, big data, database design, scripting (SQL, Pyspark)
- less priority: data visualization, machine learning, analytical, business


数据源->ETL -> 数据仓库存储与管理-> OLAP -> BI工具

1. 先了解数据源，也就是我们的业务产生的数据。一般来源于日志，IOT(前端设备)，或者其他的系统，需要找资料了解各行各业数据的产生、收集的方式及特点。
2. 学习数据存储。传统的关系型数据库：oracle，mysql等。大数据环境下，Hbase是最流行和使用最广的分布式列式数据库，Hive是最经典和常用的数仓工具。SQL的语法与使用也是必不可少的。
3. 学习ETL。推荐学习使用Pentaho Kettle这个开源的ETL工具，另外网上也能找到许多使用Spark这一大数据计算框架进行数据清洗的use case。
4. 学习数据建模。可以阅读一些经典的数据建模方面的著作，同时可以找各行各业在数据建模上的经验与案例进行学习。
5. 学习数据分析理论与工具。相关的数学知识是不可少的，概率与统计、数据分析方法等。可以学下python这门语言，可以通过安装各种数据分析包（Numpy，pandas等），非常方便得通过精简的代码，实现各种复杂场景下的数据分析。在大数据平台上，通过Spark，Flink等计算框架进行数据分析的案例也比比皆是。
6. 学习OLAP。联机分析处理OLAP是用于快速通过计算完成多维度分析性数据查询功能的一种方法，也是数据仓库的一个重要使用功能。在了解了OLAP的逻辑概念，体系结构与基本功能后，可以学习使用下大数据上流行的OLAP工具。如Kylin，Druid。
7. 学习BI工具。商业智能（BI）工具是利用一组方法和技术来准备，呈现和帮助分析数据的工具。推荐学习比较流行的Tableau, SuperSet，都即可以连接传统的数据库，也支持大数据平台。

## Roadmap
https://medium.com/@darshilp/roadmap-for-data-engineering-2023-13f62f85d866
1. computer science fundamentals: Harvard’s CS50. https://www.youtube.com/watch?v=IDDmrzzB14M&list=PLhQjrBD2T380F_inVRXMIHCqLaNUd7bN4
   - Python https://cs50.harvard.edu/python/2022/weeks/0/
   - SQL
   - Linux Command: Unix in a Nutshell
2. data engineering fundamentals
   - data warehouse
     - fundamentals: “The Data Warehouse Toolkit” by Ralph Kimball.
     - data warehouses tools: Snowflake (BigQuery, Redshift) - Udemy
   - data processing framework
     - Batch processing: Apache Spark (practice with Spark on Databrick and use PySpark (Python) as the language)
     - Real-time processing: Apache Kafka, Apache Flink, and Apache Storm (pick one and learn about it)
   - cloud platform: Azure, AWS, GCP
   - ETL pipeline: Apache Airflow
3. advance level skills
   - Modern Data Stack (MDS): understand core use cases
     - DBT (Data Build Tool)
   - understanding security, networking, deployment, and other related topics.
     - Docker or Kubernetes
     - Designing Data-Intensive Applications
     - Fundamentals of Data Engineering
    
# Resources
https://dataengineering.wiki/Concepts/Concepts

BookList
- The Data Warehouse Toolkit: The Definitive Guide to Dimensional Modeling 3rd Edition


