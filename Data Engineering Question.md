**Question 1:**

A media company needs to ingest and store a near real-time stream of social media data. The source data is in JSON format. The company does not want to manage the underlying infrastructure and it wants the data to be immediately available for ad-hoc analysis. The solution must be cost efficient and scalable.

As an ML specialist, what is your recommendation?

- [x] Ingest the data using Kinesis Firehose that further transforms the data into Parquet format while writing to S3. Use an AWS Glue Crawler to read this data via an Athena table for ad-hoc analysis

Ingest the data using Kinesis Firehose that further transforms the data into Parquet format while writing to S3. Use an AWS Glue Crawler to read this data via an Athena table for ad-hoc analysis

Kinesis Firehose can transform data to Parquet format and store it on S3 without provisioning any servers. Also this transformed data can be read via an Athena Table (created by using a Glue Crawler) and then the underlying data is readily available for ad-hoc analysis.

Incorrect options:

Ingest the data using Kinesis Data Streams and use a Lambda function to write the stream into S3. Launch a Glue ETL Job every 15 minutes to convert the data from JSON format to Parquet format. Use an AWS Glue Crawler to read this data into an Athena table for ad-hoc analysis

Ingest the data into S3 using Kinesis Firehose. Launch a Glue ETL Job every 15 minutes to write S3 data into RDS. Perform ad-hoc query analysis once data is ingested into RDS

Although Glue ETL Job can transform the source data to Parquet format, it is best suited for batch ETL use cases and it’s not meant to process near real-time data. Therefore both these options are incorrect.

Ingest the data using a Spark Streaming application running on an EMR cluster. The output data is written in Parquet format on S3. Use an AWS Glue Crawler to read this data into an Athena table for ad-hoc analysis - Using EMR cluster is not an option, as the company does not want to manage the underlying infrastructure.


**Question 2:**