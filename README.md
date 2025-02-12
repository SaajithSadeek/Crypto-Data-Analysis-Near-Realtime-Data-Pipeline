# Crypto Data Analysis Near Realtime Data Pipeline

## 📌 Project Overview

The **Crypto Data Analysis Near Realtime Data Pipeline** is an industrial project designed to process cryptocurrency transaction data in near real-time. This project leverages AWS services to efficiently capture, transform, and store the data for further analysis using AWS Athena.

## 🏗 Tech Stack

- Programming Language: Python
- AWS Services:
  - AWS DynamoDB
  - AWS Kinesis
  - AWS Data Firehose
  - AWS Lambda
  - AWS S3
  - AWS Glue (Glue Crawler, Glue Catalog, Glue Triggers, Glue Jobs)
  - AWS Athena
- Framework:
  - Apache Hudi
  - Apache Spark

## 🔄 Data Pipeline Workflow

1. Setup AWS DynamoDB & Kinesis Data Stream.
    - Create a **DynamoDB table** to store cryptocurrency transactions.
    - Enable **Change Data Capture (CDC)** stream on DynamoDB.
    - Configure **AWS Kinesis Data Stream** to capture CDC changes.
      
2. AWS Data Firehose & Lambda Transformer.
    - Setup **AWS Data** Firehose to deliver processed CDC data to AWS **S3**.
    - Use an **AWS Lambda function** as a transformer to clean and enrich data before loading into S3.
      
3. AWS Glue Crawler & Glue Catalog.
    - Configure an **AWS Glue Crawler** to scan JSON files in S3.
    - Automatically create a table in **AWS Glue Catalog** based on schema detection.
      
4. AWS Glue Job with Apache Hudi.
     - Develop an **AWS Glue Job** to process raw S3 data and perform **upsert operations** on Apache Hudi tables.
       
5. AWS Glue Triggers for Automation.
    - Setup AWS Glue **triggers** to automatically run the **Glue Crawler and Glue Job** in sequence every 15 minutes.
      
6. Data Analysis with AWS Athena.
     - Query processed Hudi tables using **AWS Athena** for analysis.
       
  
## 📈 Expected Outcome

- Near real-time ingestion and transformation of cryptocurrency transaction data.
- Efficient upserts on **Apache Hudi tables**.
- On-demand querying using **AWS Athena**.
