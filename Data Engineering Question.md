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

**Question 10**
You are training SageMaker's supervised BlazingText using file mode. Which is an example of a properly formatted line within the training file?

- [ ] `__label4 linux ready for prime time, intel says.`
- [x] `__label__4 linux ready for prime time , intel says .`
- [ ] `__label__4 Linux ready for prime time, Intel says.`
- [ ] `__label__4 linux ready for prime time, intel says.`

Attention to detail in data preparation is critical for the successful training of machine learning models, particularly in text classification tasks. In order to evaluate the options, pay attention to the correct line format for training data in Amazon SageMaker's BlazingText supervised mode, adhering to all specified requirements for label prefixing and token separation, including punctuation. In the example provided, the punctuation in the sentence "Linux ready for prime time, Intel says." includes the comma (,) after "prime time" and the period (.) at the end of the sentence.

**Question 11**
When employing Amazon SageMaker and XGBoost for the classification of a vast number of videos into genres, based on attributes of each video, the attribute data necessitates cleaning and conversion into LibSVM format before model training.

- [x] Utilize PySpark alongside the XGBoostSageMakerEstimator to facilitate data preparation via Spark, subsequently transferring control to SageMaker for the training phase.
- [x] Apply Spark on Amazon EMR for data pre-processing and save the refined results in an Amazon S3 bucket, ensuring SageMaker's access for training.

Overall explanation
In the context of classifying millions of videos into genres using Amazon SageMaker and XGBoost, the task demands not only the cleaning and transformation of video attribute data into a specific format but also efficient and scalable processing methods. The selection of appropriate pre-processing techniques is critical to manage the volume of data effectively and to ensure compatibility with the chosen machine learning framework. Two approaches stand out for their ability to parallelize data processing and seamlessly integrate with SageMaker for subsequent model training.


Correct Choice: Utilize PySpark alongside the XGBoostSageMakerEstimator to facilitate data preparation via Spark, subsequently transferring control to SageMaker for the training phase.

The integration of PySpark with SageMaker, particularly using the XGBoostSageMakerEstimator, effectively harnesses the distributed processing capabilities of Apache Spark for data preparation. This approach not only allows for the parallel processing of large datasets but also seamlessly transitions to SageMaker for model training, making it a viable solution for handling massive video attribute data.

Correct Choice: Apply Spark on Amazon EMR for data pre-processing and save the refined results in an Amazon S3 bucket, ensuring SageMaker's access for training.

Using Spark on Amazon EMR for data pre-processing leverages its distributed data processing feature, efficiently preparing the video attribute data. Storing the processed data in an S3 bucket facilitates easy access by SageMaker for subsequent training tasks, aligning with the requirements for efficient handling and transformation of large-scale data.

Incorrect Choice: Deploy AWS Glue ETL to convert the video attribute data into LibSVM format, followed by training the model with SageMaker.

Although AWS Glue ETL is proficient in data transformation tasks, it does not natively support conversion into LibSVM format. This limitation makes it an unsuitable choice for preparing data specifically for XGBoost model training within SageMaker when LibSVM format is required.

**Question 12**

Your organization is ingesting a data feed of subway ridership in near-real-time, where incoming data is timestamped by the minute and includes the total number of riders at each station for that minute. What is the simplest and most efficient approach for automatically sending alerts when an unusually high or low number of riders is observed?

- [x] Ingest the data with Amazon Kinesis Data Firehose, utilize Random Cut Forest (RCF) in Amazon Kinesis Data Analytics for anomaly detection, and employ AWS Lambda to process the output from Kinesis Data Analytics, issuing an alert via Amazon SNS if needed.
- [ ] Ingest the data with Amazon Kinesis Data Streams directly into Amazon S3, use Random Cut Forest in Amazon SageMaker to detect anomalies in real-time, and integrate SageMaker with Amazon SNS to issue alarms.

**Question 13**
A financial services company aims to automate the analysis of daily transaction costs, execution reporting, and market performance. The company has developed its own Big Data tools for this purpose. These tools require efficient scheduling and dynamic configuration of computing resources to manage variable workloads and data volumes. Considering the need for a scalable, flexible solution that minimizes operational overhead, which AWS service should be leveraged to configure the resources dynamically and schedule the data analytic workloads?

- [x] Use AWS Batch to schedule jobs and dynamically provision resources, leveraging its integration with other AWS services for end-to-end data processing workflows.
- [ ] Implement AWS Step Functions to coordinate multiple AWS services into serverless workflows for data processing, using AWS Lambda for dynamic resource allocation.

**Question 14**
An e-commerce company processes substantial volumes of consumer behavior data stored in HDFS by leveraging Apache Spark on Amazon EMR. This task is performed daily, and the volume of data exhibits significant seasonal fluctuations, notably spiking during holidays and major sales events. What is the most cost-effective strategy to manage these variable demands without risking data loss or the need to terminate the entire cluster?

- [x] Utilize EC2 Spot instances for Spark task nodes exclusively, while employing other instance types for core and master nodes.
- [ ] Deploy EC2 Spot instances for both core and task nodes, reserving EC2 Reserved instances for the master node only.
- [ ] Implement EC2 Spot instances across all node types, including master, core, and task nodes.
- [ ] Allocate reserved instances for task nodes, and employ Spot instances for core nodes.

Employing EC2 Spot instances for Spark task nodes presents the most cost-effective and risk-mitigated strategy. Task nodes in an EMR cluster are responsible for processing data and do not store HDFS data, making them tolerant to interruptions. This setup ensures that data processing can scale cost-effectively with demand without risking data loss or necessitating cluster termination.



Incorrect Choice: Allocate reserved instances for task nodes, and employ Spot instances for core nodes.



Using reserved instances for task nodes may lead to higher costs without corresponding benefits, especially during off-peak periods. Spot instances for core nodes introduce a risk of HDFS data loss if the Spot instances are interrupted, as core nodes store data in HDFS.



Incorrect Choice: Deploy EC2 Spot instances for both core and task nodes, reserving EC2 Reserved instances for the master node only.



Applying EC2 Spot instances to both core and task nodes while using Reserved instances for the master node increases the risk of data loss. A Spot interruption on core nodes, which store HDFS data, could lead to data loss, contradicting the requirement to avoid such scenarios.

**Question 15**

A district wants to reduce the crime rate throughout its vicinity. They hired a team of data scientists to create a model to detect sharp knives, automatic guns, pistols, or any dangerous weapon given a video stream. The data scientists used Amazon SageMaker to train 5 models and chose the best model.

The district will setup 4 cameras throughout the vicinity and wants a solution where they are informed, along with the police, immediately if a person is holding a dangerous weapon in order for them to hide.

Which of the following architectures is the most efficient for deployment given that they already have a containerized model, and they want a managed service to determine their compute capacity when applying inference?

- [x] Four cameras sending their streams to four kinesis video streams -> The output is sent to 4 Fargate containers containing the model inference code and artifacts -> The inference output is sent to one Kinesis data streams -> Lambda function processes the output -> If a dangerous weapon is found, lambda will send to the SNS topic where the subscribers will be notified by SMS.
- [ ] Four cameras sending their streams to four kinesis video streams -> The output is sent to 4 EC2 instances containing the model inference code and artifacts -> The inference output is sent to one Kinesis data streams -> Lambda function processes the output -> If a dangerous weapon is found, lambda will send to the SNS topic where the subscribers will be notified by SMS.

One Kinesis video stream cannot stream data from multiple producers; therefore, a kinesis video stream should be setup for every producer. Fargate is used instead of EC2 instances when deploying containerized models as it can compute the capacity needed for inference and it is a managed service as well. One Kinesis Data Streams is sufficient to ingest all the inferences across all the Fargate containers.

![image](fargate_server.img)

**Question 16**
The traffic monitoring authorities at a city want to monitor the traffic at busy intersections and take corrective action at the earliest. An ML solutions company has developed a Proof-of-Concept for processing this video data and now it wants to productionalize it to cover all city intersections.

As an AWS ML specialist, which of the following solutions would you recommend so that it takes the LEAST amount of development effort and ongoing maintenance effort?

- [x] Analyse the incoming video streams using Kinesis Video Streams in real time and then send an alert using a downstream EC2 instance
- [ ] Process the incoming video data using Kinesis Data Analytics to detect anomalies in real time

**Question 17**
An e commerce company wants to launch a new cloud-based product recommendation feature for its web application. Due to data localization regulations, any sensitive data must not leave its on-premises data center, and the product recommendation model must be trained and tested using nonsensitive data only. Data transfer to the cloud must use IPsec. The web application is hosted on premises with a PostgreSQL database that contains all the data. The company wants the data to be uploaded securely to Amazon S3 each day for model retraining.

How should a machine learning specialist meet these requirements?

- [x] Create an AWS Glue job to connect to the PostgreSQL DB instance. Ingest tables without sensitive data through an AWS Site-to-Site VPN connection directly into Amazon S3.

- [ ] Create an AWS Glue job to connect to the PostgreSQL DB instance. Ingest all data through an AWS Site- to-Site VPN connection into Amazon S3 while removing sensitive data using a PySpark job.
- [ ] Use AWS Database Migration Service (AWS DMS) with table mapping to select PostgreSQL tables with no sensitive data through an SSL connection. Replicate data directly into Amazon S3.
- [ ] Use PostgreSQL logical replication to replicate all data to PostgreSQL in Amazon EC2 through AWS Direct Connect with a VPN connection. Use AWS Glue to move data from Amazon EC2 to Amazon S3.

