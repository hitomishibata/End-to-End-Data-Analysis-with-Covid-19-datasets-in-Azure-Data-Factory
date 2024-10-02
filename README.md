![image](https://github.com/user-attachments/assets/6ab8b783-d94a-4849-a8dd-97e0e3070b85)
# Introduction 
In this data engineering project, I worked on building ETL pipelines with open large dataset.  
The major part is from the assinment guideline of an Udemy's course but I changed some parts for extra challenge.  
Course name: Azure Data Factory For Data Engineers - Project on Covid19
The activities involved in the project are:
1. Building data pipelines for data ingestion and transformatioin
2. Visualization in PowerBI
3. Pipeline CL/CD in Azure DevOps
 

# Getting Started
Tools that are used in this project:
1.	Azure Data Lake
2.	Azure Data Factory
3.	Azure Databricks
4.	Azure SQL Datbase
5.	Microsoft Power BI

I used publically available datasets from European Centre for Disease Prevention and Control (https://www.ecdc.europa.eu/en/data-dashboards-and-databases). 
Hospital admissions data format is json while others are csv. This is simply to practice ingesting different data formats.
1. Covid-19 new cases and deaths by Country (csv)
2. Covid-19 Hospital admissions & ICU cases (json)
3. Covid-19 Testing Numbers (csv)
4. Country Response to Covid-19 (csv)

The first step is building pipeline to ingest all dataset from the website. I created a json file to list up source base URL, source relative URL, and sink file name. Look up function can get the information and pass it to For Each function in which you can copy the each file one by one. I made a pipeline for ingesting the hospital admission file separetelly as it has a different data format from others.

After successfully ingesting the dataset, some pipelines were built to process each file.
1. Pipeline with dataflow
- Dataset: Covid-19 new cases and deaths by Country (csv)
- Goal: have the dataset that
  - contains only records from Europe
  - have new columns from the values in a column with aggregated data
  - drop certain columns    
- Used functions: filter rows, select columns, pivot row values into columns, sort rows

2. pipeline with Databricks
- Dataset: Covid-19 Hospital admissions & ICU cases (json)
- Goal: have the dataset that
  - extract new columns from look up files
  - is divided into two dataframes vased on the values in a column
  - have new columns from the values in a column with aggregated data
  - drop certain columns

# Build and Test
You can download ARM templates and change the values (subscription ID, Data Factory name, etc). Then, attach them to release pipeline and run it with configuration files (json and YAML files).

# Contribute
Feel free to leave comments on my codes. I would love to have feedback to improve my pipeline skills.

