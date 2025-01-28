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
A retail organization ingests 100GB of raw data into S3 from its global storefronts on a daily basis. This raw data needs to be eventually cleaned, prepared and analyzed daily so that sales reports can be sent out to the business stakeholders.

Which option takes the least effort to make this raw data available for SQL queries?

- [ ] Setup a daily Glue ETL job to write the incremental S3 data into RDS and have it available for SQL queries
- [x] Configure Glue crawlers to set up Athena tables that read raw data from S3. The daily raw data is then readily available for SQL queries in Athena as soon as it arrives
- [ ] Setup a daily Glue ETL job to write the incremental S3 data into DynamoDB and have it available for SQL queries
- [ ] Setup a daily Glue ETL job to write the incremental S3 data into Redshift and have it available for SQL queries

**Question 3**
When you create a training job with the SageMaker API, Amazon SageMaker replicates the entire dataset from S3 to ML compute instances by default.

What of the following options would you use to replicate only a subset of the data on each ML compute instance?

- [x] Set the S3DataDistributionType field to ShardedByS3Key
- [ ] Set the S3DataDistributionType field to FullyReplicated
- [ ] Set the S3Uri field to ShardedByS3Key

Set the S3DataDistributionType field to FullyReplicated - If you want Amazon SageMaker to replicate the entire dataset on each ML compute instance that is launched for model training, specify FullyReplicated.

**Question 4**
An Analytics Consulting Firm would like to capture and analyze the real time metrics for a cab hailing service. The Firm would like to identify “demand hotspots” in real time so that additional cabs can be dispatched to meet the sudden spurt in demand.

Which of the following solutions would require the LEAST development and maintenance effort to build a real time analytics solution for this use case?

- [x] Ingest the data into Kinesis Data Streams and immediately write the stream into Kinesis Data Analytics for SQL based analysis so that appropriate alerts can be sent to the drivers. Once processing is done, the streams are dumped into S3 using Kinesis Data Firehose
- [ ] Ingest the source data directly into Kinesis Data Analytics so that real time analytics can be done without any processing delay. Once processing is done, the streams are dumped into S3 using Kinesis Data Firehose

**Question 5**
The data engineering team at a social media company ingests the clickstream data into the Kinesis Data Streams using the PutRecord API in the source system. Now, the team wants to ingest this data into Kinesis Data Firehose instead and they want to use the PutRecord API for Firehose.

Which of the following represents the key differences between the PutRecord API call for Kinesis Data Stream v/s that of Kinesis Data Firehose?

- [x] Kinesis Data Streams PutRecord API uses name of the stream, a partition key and the data blob whereas Kinesis Data Firehose PutRecord API uses the name of the delivery stream and the data record
- [ ] Kinesis Data Firehose PutRecord API uses name of the stream, a partition key and the data blob whereas Kinesis Data Streams PutRecord API uses the name of the delivery stream and the data record

Kinesis Data Streams PutRecord API uses name of the stream, a partition key and the data blob whereas Kinesis Data Firehose PutRecord API uses the name of the delivery stream and the data record

For Amazon Kinesis Data Firehose, PutRecord  writes a single data record into an Amazon Kinesis Data Firehose delivery stream. To write multiple data records into a delivery stream, use PutRecordBatch. By default, each delivery stream can take in up to 2,000 transactions per second, 5,000 records per second, or 5 MB per second. If you use PutRecord and PutRecordBatch, the limits are an aggregate across these two operations for each delivery stream.

You must specify the name of the delivery stream and the data record when using PutRecord for Kinesis Data Firehose.

For Amazon Kinesis Data Streams, PutRecord writes a single data record into an Amazon Kinesis data stream. Call PutRecord to send data into the stream for real-time ingestion and subsequent processing, one record at a time. Each shard can support writes up to 1,000 records per second, up to a maximum data write total of 1 MiB per second.

You must specify the name of the stream that captures, stores, and transports the data; a partition key; and the data blob itself when using PutRecord for Kinesis Data Streams.

The partition key is used by Kinesis Data Streams to distribute data across shards. Kinesis Data Streams segregates the data records that belong to a stream into multiple shards, using the partition key associated with each data record to determine the shard to which a given data record belongs.

**Question 6**
A financial services company wants to migrate its data architecture from a data warehouse to a data lake. It wants to use a solution that takes the least amount of development time and needs no infrastructure management.

What options would you recommend to transfer the data from AWS Redshift to Amazon S3? (Select two)

- [x] AWS Glue ETL job
- [x] AWS Data Pipeline

AWS Data Pipeline - AWS Data Pipeline is a web service that makes it easy to schedule regular data movement and data processing activities in the AWS cloud. Using AWS Data Pipeline, you can quickly and easily provision pipelines that remove the development and maintenance effort required to manage your daily data operations, letting you focus on generating insights from that data. Simply specify the data sources, schedule, and processing activities required for your data pipeline. AWS Data Pipeline handles running and monitoring your processing activities on a highly reliable, fault-tolerant infrastructure. Additionally, to further ease your development process, AWS Data Pipeline provides built-in activities for common actions such as copying data between Amazon Amazon S3 and Amazon RDS, or running a query against Amazon S3 log data.

AWS Glue ETL job - AWS Glue is a serverless data integration service that makes it easy to discover, prepare, and combine data for analytics, machine learning, and application development. You should use AWS Glue to discover properties of the data you own, transform it, and prepare it for analytics. Glue can automatically discover both structured and semi-structured data stored in your data lake on Amazon S3, data warehouse in Amazon Redshift, and various databases running on AWS. It provides a unified view of your data via the Glue Data Catalog that is available for ETL, querying and reporting using services like Amazon Athena, Amazon EMR, and Amazon Redshift Spectrum. Glue automatically generates Scala or Python code for your ETL jobs that you can further customize using tools you are already familiar with.

![image](glueetl.img)

**Question 7**
An e-commerce company wants to optimize the cost structure for its Redshift data warehouse by moving out some of the infrequently accessed data to S3.

Which of the following solutions requires minimum maintenance and development effort, so that the company can still access this infrequently accessed data from Redshift whenever required?

- [x] Use Redshift Spectrum so that the infrequently accessed data in S3 can be queried from Redshift

Use Redshift Spectrum so that the infrequently accessed data in S3 can be queried from Redshift

Using Amazon Redshift Spectrum, you can efficiently query and retrieve structured and semistructured data from files in Amazon S3 without having to load the data into Amazon Redshift tables. Redshift Spectrum queries employ massive parallelism to execute very fast against large datasets. Much of the processing occurs in the Redshift Spectrum layer, and most of the data remains in Amazon S3. Multiple clusters can concurrently query the same dataset in Amazon S3 without the need to make copies of the data for each cluster.

Redshift Spectrum is a built-in feature of Amazon Redshift, and your existing queries and BI tools will continue to work seamlessly. Under the covers, AWS manages a fleet of thousands of Redshift Spectrum nodes spread across multiple Availability Zones. These are transparently scaled and allocated to your queries based on the data that you need to process, with no provisioning or commitments. Redshift Spectrum is also highly concurrent—you can access your Amazon S3 data from any number of Amazon Redshift clusters.

**Question 8**
A machine learning company uses a hybrid architecture where it has some servers on-premises and others on the AWS cloud. The company receives data on a daily basis collected from other companies to train and deploy custom machine learning models.

The company wants to use a manageable, automated service which could move data over the network, while handling encryption, between their on-premises storage and AWS storage services, and also between their AWS storage services.

Which service should the company use?

- [x] AWS DataSync.

**Question 9**
A leading news portal seeks to deliver personalized article recommendations by daily training a machine learning model using historical clickstream data. The volume of incoming data is consistent but experiences substantial spikes during major elections, leading to increased site traffic. Which architecture would ensure the most cost-effective and reliable framework for accommodating these conditions?

- [x] Capture clickstream data using Amazon Kinesis Data Firehose to Amazon S3. Process the data with Amazon SageMaker for model training using Managed Spot Training. Publish results to Amazon DynamoDB for instant recommendation serving.
- [ ] Direct clickstream data to Amazon S3 using Amazon Kinesis Data Firehose, conducting nightly analysis with AWS Glue DataBrew and Amazon SageMaker using On-Demand Instances for model training. Deploy results to DynamoDB for real-time recommendations.

