# Home_Sales

This assignment  entailed the utilization of Big Data and SparkSQL for the examination and interrogation of data related to home sales. The analytical procedures encompassed the following steps:

## Package Importation:
The project commenced with the importation of essential packages, such as findspark for initializing Spark and pyspark.sql for SparkSQL operations.

## SparkSession Establishment:
 A SparkSession was generated using SparkSession.builder.appName("SparkSQL").getOrCreate() to establish a connection with Spark.

## Data Reading: 
Home sales data was retrieved from an AWS S3 bucket into a DataFrame using the provided URL.

## Temporary View Creation:
 A temporary view named "my_table" was generated for the DataFrame using createOrReplaceTempView(), facilitating the execution of SQL queries on the DataFrame.

## Data Querying: 
Various SQL queries were executed to scrutinize the home sales data. This included computations like the average price for a four-bedroom house sold each year and the average price of homes based on factors like bedrooms, bathrooms, and square footage.

## Data Caching:
 The temporary table "home_sales_df" was cached using spark.catalog.cacheTable() to enhance query performance by storing data in memory.

## Query Runtime Comparison: 
The runtime of a specific query was compared between the cached version and the version using Parquet data. Start times were recorded using time.time() before executing each query, and time differences were calculated for runtime measurement.

## Parquet Data Writing:
 The formatted home sales data was written to Parquet format with partitioning based on the "date_built" field using the partitionBy().parquet() method.

## Parquet Data Reading:
 Parquet data was read into a DataFrame for further analysis.

## Temporary Table Creation for Parquet Data:
 A temporary table named "parquet_table" was created for the Parquet DataFrame using createOrReplaceTempView().

## Parquet Data Querying:
 SQL queries were executed on the Parquet DataFrame to filter out view ratings with an average price greater than or equal to $350,000. The runtime was measured and compared to the cached version.

## Uncaching the Temporary Table: 
The temporary table "home_sales" was uncached using spark.catalog.uncacheTable() to release memory resources.

## Caching Status Check: 
The caching status of the table "home_sales" was verified using spark.catalog.isCached() to confirm whether it was still cached.

In summary, this project showcased the application of SparkSQL for reading, querying, caching, and analyzing home sales data, providing insights into average prices based on various criteria.