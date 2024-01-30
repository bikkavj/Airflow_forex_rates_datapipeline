# Airflow_forex_rates_datapipeline

The "forex_data_pipeline" is designed to streamline the entire process of handling foreign exchange (forex) data. It seamlessly integrates various components, ranging from data retrieval and processing to storage and notification triggers. By leveraging Airflow's DAG (Directed Acyclic Graph) architecture, the pipeline orchestrates the execution of tasks in a logical and efficient manner.

## Sensors:
The pipeline begins with sensors like is_forex_rates_available and is_forex_currencies_file_available to ensure that prerequisite data and files are accessible before proceeding.

##Data Download and Processing:
The downloading_rates Python task encapsulates the logic for downloading forex rates from an API, processing the data, and saving it in a structured format (JSON).

## Storage and HDFS Operations:
The saving_rates Bash task is responsible for creating an HDFS directory and transferring the processed data to the Hadoop Distributed File System (HDFS).

## Hive Table Creation:
The creating_forex_rates_table Hive task creates an external Hive table named "forex_rates" with predefined columns, facilitating efficient data organization.

## Spark Processing:
The forex_processing Spark task submits a Spark application for further data processing, leveraging the capabilities of Apache Spark.

## Email Notification:
The pipeline concludes with the send_email_notification Email task, providing notifications when the entire workflow is triggered.
