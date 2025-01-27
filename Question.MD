**Question 1:**

A Machine Learning Specialist is using an Amazon SageMaker notebook instance in a private subnet of a corporate VPC. The ML Specialist has important data stored on the Amazon SageMaker notebook instance's Amazon EBS volume, and needs to take a snapshot of that EBS volume. However, the ML Specialist cannot find the Amazon SageMaker notebook instance’s EBS volume or Amazon EC2 instance within the VPC.

Why is the ML Specialist not seeing the instance visible in the VPC?

- [ ] Amazon SageMaker notebook instances are based on the EC2 instances within the customer account, but they run outside of VPCs.
- [ ] Amazon SageMaker notebook instances are based on the Amazon ECS service within customer accounts.
- [x] Amazon SageMaker notebook instances are based on EC2 instances running within AWS service accounts.
- [ ] Amazon SageMaker notebook instances are based on AWS ECS instances running within AWS service accounts.

**Answer(s): C**

**Reference:**
https://docs.aws.amazon.com/sagemaker/latest/dg/gs-setup-working-env.html

**Question 2:**

A manufacturing company has structured and unstructured data stored in an Amazon S3 bucket. A Machine Learning Specialist wants to use SQL to run queries on this data.

Which solution requires the LEAST effort to be able to query this data?

- [ ] Use AWS Data Pipeline to transform the data and Amazon RDS to run queries.
- [x] Use AWS Glue to catalogue the data and Amazon Athena to run queries.
- [ ] Use AWS Batch to run ETL on the data and Amazon Aurora to run the queries.
- [ ] Use AWS Lambda to transform the data and Amazon Kinesis Data Analytics to run queries.

**Answer(s): B**

**Question 3:**

A Machine Learning Specialist is developing a custom video recommendation model for an application. The dataset used to train this model is very large with millions of data points and is hosted in an Amazon S3 bucket. The Specialist wants to avoid loading all of this data onto an Amazon SageMaker notebook instance because it would take hours to move and will exceed the attached 5 GB Amazon EBS volume on the notebook instance.

Which approach allows the Specialist to use all the data to train the model?

- [x] Load a smaller subset of the data into the SageMaker notebook and train locally. Confirm that the training code is executing and the model parameters seem reasonable. Initiate a SageMaker training job using the full dataset from the S3 bucket using Pipe input mode.

**Answer(s): A**

**Question 4:**
A Machine Learning Specialist has completed a proof of concept for a company using a small data sample, and now the Specialist is ready to implement an end-to-end solution in AWS using Amazon SageMaker. The historical training data is stored in Amazon RDS.

Which approach should the Specialist use for training a model using that data?

- [ ] Write a direct connection to the SQL database within the notebook and pull data in
- [x] Push the data from Microsoft SQL Server to Amazon S3 using an AWS Data Pipeline and provide the S3 location within the notebook.
- [ ] Move the data to Amazon DynamoDB and set up a connection to DynamoDB within the notebook to pull data in.
- [ ] Move the data to Amazon ElastiCache using AWS DMS and set up a connection within the notebook to pull data in for fast access.

**Question 5:**
A Machine Learning Specialist at a company sensitive to security is preparing a dataset for model training. The dataset is stored in Amazon S3 and contains Personally Identifiable Information (PII).

The dataset:
•Must be accessible from a VPC only.
•Must not traverse the public internet.

How can these requirements be satisfied?

- [x] Create a VPC endpoint and apply a bucket access policy that restricts access to the given VPC endpoint and the VPC.
- [ ] Create a VPC endpoint and apply a bucket access policy that allows access from the given VPC endpoint and an Amazon EC2 instance.
- [ ] Create a VPC endpoint and use Network Access Control Lists (NACLs) to allow traffic between only the given VPC endpoint and an Amazon EC2 instance.
- [ ] Create a VPC endpoint and use security groups to restrict access to the given VPC endpoint and an Amazon EC2 instance
Answer(s): A

**Question 6:**
A Machine Learning Specialist is packaging a custom ResNet model into a Docker container so the company can leverage Amazon SageMaker for training. The Specialist is using Amazon EC2 P3 instances to train the model and needs to properly configure the Docker container to leverage the NVIDIA GPUs.

What does the Specialist need to do?

- [ ] Bundle the NVIDIA drivers with the Docker image.
- [x] Build the Docker container to be NVIDIA-Docker compatible.
- [ ] Organize the Docker container's file structure to execute on GPU instances.
- [ ] Set the GPU flag in the Amazon SageMaker CreateTrainingJob request body.

**Question 7:**
A Machine Learning Specialist trained a regression model, but the first iteration needs optimizing. The Specialist needs to understand whether the model is more frequently overestimating or underestimating the target.

What option can the Specialist use to determine whether it is overestimating or underestimating the target value?

- [ ] Root Mean Square Error (RMSE)
- [x] Residual plots
- [ ] Area under the curve
- [ ] Confusion matrix

**Question 8:**
When submitting Amazon SageMaker training jobs using one of the built-in algorithms, which common parameters MUST be specified? (Choose three.)

- [x] The training channel identifying the location of training data on an Amazon S3 bucket.
- [ ] The validation channel identifying the location of validation data on an Amazon S3 bucket.
- [ ] The IAM role that Amazon SageMaker can assume to perform tasks on behalf of the users.
- [ ] Hyperparameters in a JSON array as documented for the algorithm used.
- [x] The Amazon EC2 instance class specifying whether training will be run using CPU or GPU.
- [x] The output path specifying where on an Amazon S3 bucket the trained model will persist.

**Question 9:**
A Data Science team is designing a dataset repository where it will store a large amount of training data commonly used in its machine learning models. As Data Scientists may create an arbitrary number of new datasets every day, the solution has to scale automatically and be cost-effective. Also, it must be possible to explore the data using SQL.

Which storage scheme is MOST adapted to this scenario?

- [x] Store datasets as files in Amazon S3.
- [ ] Store datasets as files in an Amazon EBS volume attached to an Amazon EC2 instance.
- [ ] Store datasets as tables in a multi-node Amazon Redshift cluster.
- [ ] Store datasets as global tables in Amazon DynamoDB.

**Question 10:**
A Data Science team within a large company uses Amazon SageMaker notebooks to access data stored in Amazon S3 buckets. The IT Security team is concerned that internet-enabled notebook instances create a security vulnerability where malicious code running on the instances could compromise data privacy. The company mandates that all instances stay within a secured VPC with no internet access, and data communication traffic must stay within the AWS network.

How should the Data Science team configure the notebook instance placement to meet these requirements?

- [ ] Associate the Amazon SageMaker notebook with a private subnet in a VPC. Place the Amazon SageMaker endpoint and S3 buckets within the same VPC.
- [ ] Associate the Amazon SageMaker notebook with a private subnet in a VPC. Use IAM policies to grant access to Amazon S3 and Amazon SageMaker.
- [x] Associate the Amazon SageMaker notebook with a private subnet in a VP Ensure the VPC has S3 VPC endpoints and Amazon SageMaker VPC endpoints attached to it.
- [ ] Associate the Amazon SageMaker notebook with a private subnet in a VPC. Ensure the VPC has a NAT gateway and an associated security group allowing only outbound connections to Amazon S3 and Amazon SageMaker.

**Question 11:**
A Data Scientist needs to migrate an existing on-premises ETL process to the cloud. The current process runs at regular time intervals and uses PySpark to combine and format multiple large data sources into a single consolidated output for downstream processing.

The Data Scientist has been given the following requirements to the cloud solution:
•Combine multiple data sources.
•Reuse existing PySpark logic.
•Run the solution on the existing schedule.
•Minimize the number of servers that will need to be managed.

Which architecture should the Data Scientist use to build this solution?

Which architecture should the Data Scientist use to build this solution?

- [ ] Write the raw data to Amazon S3. Schedule an AWS Lambda function to submit a Spark step to a persistent Amazon EMR cluster based on the existing schedule. Use the existing PySpark logic to run the ETL job on the EMR cluster. Output the results to a “processed” location in Amazon S3 that is accessible for downstream use.
- [x] Write the raw data to Amazon S3. Create an AWS Glue ETL job to perform the ETL processing against the input data. Write the ETL job in PySpark to leverage the existing logic. Create a new AWS Glue trigger to trigger the ETL job based on the existing schedule. Configure the output target of the ETL job to write to a “processed” location in Amazon S3 that is accessible for downstream use.
- [ ] Write the raw data to Amazon S3. Schedule an AWS Lambda function to run on the existing schedule and process the input data from Amazon S3. Write the Lambda logic in Python and implement the existing PySpark logic to perform the ETL process. Have the Lambda function output the results to a “processed” location in Amazon S3 that is accessible for downstream use.
- [ ] Use Amazon Kinesis Data Analytics to stream the input data and perform real-time SQL queries against the stream to carry out the required transformations within the stream. Deliver the output results to a “processed” location in Amazon S3 that is accessible for downstream use.
Answer(s): B

**Question 12:**

A Machine Learning team runs its own training algorithm on Amazon SageMaker. The training algorithm requires external assets. The team needs to submit both its own algorithm code and algorithm-specific parameters to Amazon SageMaker.

What combination of services should the team use to build a custom algorithm in Amazon SageMaker? (Choose two.)

- [ ] AWS Secrets Manager
- [ ] AWS CodeStar
- [x] Amazon ECR
- [ ] Amazon ECS
- [x] Amazon S3
Answer(s): C,E

**Question 13:**
A trucking company is collecting live image data from its fleet of trucks across the globe. The data is growing rapidly and approximately 100 GB of new data is generated every day. The company wants to explore machine learning uses cases while ensuring the data is only accessible to specific IAM users.

Which storage option provides the most processing flexibility and will allow access control with IAM?

- [ ] Use a database, such as Amazon DynamoDB, to store the images, and set the IAM policies to restrict access to only the desired IAM users.
- [x] Use an Amazon S3-backed data lake to store the raw images, and set up the permissions using bucket policies.
- [ ] Setup up Amazon EMR with Hadoop Distributed File System (HDFS) to store the files, and restrict access to the EMR instances using IAM policies.
- [ ] Configure Amazon EFS with IAM policies to make the data available to Amazon EC2 instances owned by the IAM users.

# Domain : Modeling
**Question 14:**
A retail organization wants to forecast the sales of its flagship products for the upcoming festive season. They have the last 5 years of sales data for these products.

As an ML specialist, which algorithm would you use to implement the forecasting solution?

- [x] Linear Learner
- [ ] Random Cut Forest

**Random Cut Forest** - Amazon SageMaker Random Cut Forest (RCF) is an unsupervised algorithm for detecting anomalous/fraud detection data points within a data set. These are observations which diverge from otherwise well-structured or patterned data. Anomalies can manifest as unexpected spikes in time series data, breaks in periodicity, or unclassifiable data points. They are easy to describe in that, when viewed in a plot, they are often easily distinguishable from the "regular" data. Including these anomalies in a data set can drastically increase the complexity of a machine learning task since the "regular" data can often be described with a simple model.
With each data point, RCF associates an anomaly score. Low score values indicate that the data point is considered "normal." High values indicate the presence of an anomaly in the data. The definitions of "low" and "high" depend on the application but common practice suggests that scores beyond three standard deviations from the mean score are considered anomalous.

**IP Insights**
Amazon SageMaker IP Insights is an unsupervised learning algorithm that learns the usage patterns for IPv4 addresses. It is designed to capture associations between IPv4 addresses and various entities, such as user IDs or account numbers. You can use it to identify a user attempting to log into a web service from an anomalous IP address, for example.

**Factorization Machines** - The Factorization Machines algorithm is a general-purpose supervised learning algorithm that you can use for both classification and regression tasks. It is an extension of a linear model that is designed to capture interactions between features within high dimensional sparse datasets economically. For example, in a click prediction system, the Factorization Machines model can capture click rate patterns observed when ads from a certain ad-category are placed on pages from a certain page-category. Factorization machines are a good choice for tasks dealing with high dimensional sparse datasets, such as click prediction and item recommendation.


# Domain : Exploatory Data Analysis
**Question 15:**
The data engineering team at a medical research company has handed over the cleaned and prepared dataset for DNA sequencing to the Machine Learning team. The ML team wants to use this dataset for building a regression model based on the SageMaker Linear Learner algorithm.

Which of the following represents the first step that the ML team needs to follow for the entire dataset?

- [x] Shuffle the dataset
- [ ] Create training set, validation set and test set

# Domain : Data Engineering

**Question 1:**
An analytics company wants to create a text summarization model based on the SageMaker seq2seq algorithm. However the training data is in the form of 1TB of flat files whereas seq2seq only expects RecordIO-Protobuf format.

As an ML Specialist, which of the following solutions would you recommend?

- [x] Spin-up an Apache Spark EMR cluster to transform the data from flat files into RecordIO-Protobuf format and save it on S3. This data can be used by seq2seq based model for training
- [ ] Use AWS Step function with Lambda to write the data in RecordIO-Protobuf format on S3. This data can be used by seq2seq based model for training

**Question 2:**
An e-commerce company is looking for a solution that detects anomalies in order to identify fraudulent transactions. The company utilizes Amazon Kinesis to transfer JSON-formatted transaction records from its on-premises database to Amazon S3. The existing dataset comprises 200-column wide records for each transaction. To identify fraudulent transactions, the solution needs to analyze just 20 of these columns.

Which of the following would you suggest as the lowest-cost solution that needs the least development work and offers out-of-the-box anomaly detection functionality?

- [x] Transform the data from JSON format to Apache Parquet format using an AWS Glue job. Configure AWS Glue crawlers to discover the schema and build the AWS Glue Data Catalog. Leverage Amazon Athena to create a table with a subset of columns. Set up Amazon QuickSight for visual analysis of the data and identify fraudulent transactions using QuickSight's built-in machine learning-powered anomaly detection

For the given use case, you can use an AWS Glue job to extract, transform, and load (ETL) data from the data source (in JSON format) to the data target (in Parquet format). You can then use an AWS Glue crawler, which is a program that connects to a data store (source or target) such as Amazon S3, progresses through a prioritized list of classifiers to determine the schema for your data, and then creates metadata tables in the AWS Glue Data Catalog.

**Amazon Athena** is an interactive query service that makes it easy to analyze data directly in Amazon Simple Storage Service (Amazon S3) using standard SQL. Athena is serverless, so there is no infrastructure to set up or manage, and you pay only for the queries you run, thereby making this solution really low cost. You can also use Athena to build a table with only the subset of columns that are required for downstream analysis.



**Question 3:**
Which of the following represent the correct statements regarding the IAM features available with Amazon SageMaker? (Select two)

- [x] With IAM identity-based policies, you can specify allowed or denied actions and resources as well as the conditions under which actions are allowed or denied for Amazon SageMaker
- [x] Amazon SageMaker supports authorization based on resource tags

Amazon SageMaker supports authorization based on resource tags - You can attach tags to SageMaker resources or pass tags in a request to SageMaker. To control access based on tags, you provide tag information in the condition element of a policy using the sagemaker:ResourceTag/key-name, aws:RequestTag/key-name, or aws:TagKeys condition keys.

With IAM identity-based policies, you can specify allowed or denied actions and resources as well as the conditions under which actions are allowed or denied for Amazon SageMaker - With IAM identity-based policies, you can specify allowed or denied actions and resources as well as the conditions under which actions are allowed or denied. SageMaker supports specific actions, resources, and condition keys. Administrators can use AWS JSON policies to specify who has access to what. That is, which principal can perform actions on what resources, and under what conditions. The Action element of a JSON policy describes the actions that you can use to allow or deny access in a policy.

**Question 4:**
How many shards would a Kinesis Data Streams application need if the average record size is 500KB and 2 records per second are being written into this application that has 7 consumers?

- [x] 4
```
Overall explanation
number_of_shards = max (incoming_write_bandwidth_in_KB/1000, outgoing_read_bandwidth_in_KB/2000)

incoming_write_bandwidth_in_KB = average_data_size_in_KB multiplied by the number_of_records_per_seconds. = 500 * 2 = 1000

outgoing_read_bandwidth_in_KB = incoming_write_bandwidth_in_KB multiplied by the number_of_consumers = 1000 * 7 = 7000

So, number_of_shards = max(1000/1000, 7000/2000) = max(1, 3.5) = 4
```

**Question 5:**
The data science team at an email marketing company has created a data lake with raw and refined zones. The raw zone has the data as it arrives from the source, however, the team wants to de-duplicate the data before it is written into the refined zone.

What is the best way to accomplish this with the least amount of development time and infrastructure maintenance effort?

- [x] Invoke an AWS Glue ML Transforms job when new data arrives into raw zone so that de-duplicated records can be written into the refined zone