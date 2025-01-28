**Question 1:**

1. You are creating a classification model using one of the Amazon SageMaker built-in algorithms and you want to use GPUs for both training and inference.

Which of the following steps would you follow to meet this requirement? (Select two)

Correct Options:
- [x] Select a built-in algorithm that supports GPUs for both training and inference
- [x] Select the correct instance type that supports GPUs

**Question 2:**
A healthcare company runs machine learning (ML) models on sensitive health data for its customers and the company is concerned about data security. The company is looking out for a solution to protect the data at rest as well as in-transit while running the Machine Learning specific processes on this data. The company uses Amazon SageMaker as its primary data science environment.

As an AWS Certified Machine Learning Specialist, which of the following options would you combine to address the given use case? (Select three.)

- [x] Use AWS Key Management Service (AWS KMS) to manage encryption keys for encrypting data at rest and use TLS for encrypting data in transit.

- [x] Enable network isolation for training jobs and models
- [x] Connect to the SageMaker API or to the SageMaker Runtime through an interface endpoint in your Virtual Private Cloud (VPC)

**Question 3**
Which of the following SageMaker algorithms can be used both as a built-in-algorithm as well as a framework to run your own customized scripts?

- [x] XGBoost

**Question 4**
ou have launched a new Jupyter Notebook instance and you want to make sure that you don’t lose any files and data when the notebook instance restarts.

Where should you save your files and data so that they are not overwritten when the instance restarts?

- [x] /home/ec2-user/SageMaker

/home/ec2-user/SageMaker

Only files and data saved within the /home/ec2-user/SageMaker folder persist between notebook instance sessions. Files and data that are saved outside this directory are overwritten when the notebook instance stops and restarts.

**Question 5**
As a security policy, the data science team at an e-commerce company does not want Amazon SageMaker to provide external network access to the training or inference containers, so network isolation is enabled for all containers.

Which of the following Amazon SageMaker containers do NOT support network isolation? (Select two)

- [x] Chainer
- [x] Amazon SageMaker Reinforcement Learning

Chainer

Amazon SageMaker Reinforcement Learning

If you enable network isolation, the containers can't make any outbound network calls, even to other AWS services such as Amazon S3. Additionally, no AWS credentials are made available to the container runtime environment. In the case of a training job with multiple instances, network inbound and outbound traffic is limited to the peers of each training container. SageMaker still performs download and upload operations against Amazon S3 using your SageMaker execution role in isolation from the training or inference container.

Network isolation is NOT supported by the following managed Amazon SageMaker containers as they require access to Amazon S3:

Chainer

Amazon SageMaker Reinforcement Learning

**Question 6**

Which of the following is correct regarding an inference pipeline on Amazon SageMaker?

- [x] Within an inference pipeline model, Amazon SageMaker handles invocations as a sequence of HTTP requests

- [ ] Within an inference pipeline model, Amazon SageMaker handles invocations as a sequence of HTTPS requests

**Question 7**
An electronics goods company wants to do sentiment analysis of the customer feedback for its latest product recently launched in France. However, the customer feedback is only available in the form of recorded audio snippets in the French language.

As an AWS ML specialist, which of the following AWS AI services would you use to build the simplest solution with the least development effort?

- [x] Transcribe -> Comprehend
- [x] Transcribe -> Translate -> Comprehend

Transcribe -> Translate -> Comprehend - Comprehend supports multiple languages for sentiment analysis, so there is no need for adding the Translate service, unless there is a need to store the transcribed text based customer feedback in French language to another language such as English.

**Question 8**
Only three of the built-in SageMaker algorithms support incremental training. Can you identify those three algorithms? (Select three)

- [x] Semantic Segmentation
- [x] Object Detection
- [x] Image Classification

**Question 9**
An autonomous vehicle technology company is seeking an AWS solution capable of classifying street sign images with minimal latency, handling thousands of images each second. Which AWS services would most effectively fulfill this requirement?

- [x] Amazon SageMaker, Neo, Greengrass
- [ ] Amazon Rekognition, Lambda, IoT Core

**Question 10**
In Amazon Elastic File System (EFS), when monitoring performance metrics indicates that the IOPS usage is nearing 100%, which of the following actions should be taken to effectively manage the file system's performance?

- [x] Increase the provisioned throughput of the EFS file system if it is in the provisioned mode.
- [ ] Reconfigure attached EC2 instances to use Elastic Block Store (EBS) instead of EFS.

1. For Bursting Throughput Mode: If `PercentIOLimit` is approaching 100%, increasing the total storage size will automatically raise the baseline performance and burstable IOPS capacity. This option leverages the natural scaling feature of Bursting Throughput mode.



2. For Provisioned Throughput Mode: Alternatively, if the file system is already in Provisioned Throughput mode or if a more immediate and predictable performance enhancement is needed, manually adjust the `ProvisionedThroughput` setting. This direct intervention ensures performance does not degrade as the `PercentIOLimit` approaches its maximum.

**Question 11**
A company aims to enhance the security and management of its machine learning projects by restricting access to Amazon SageMaker notebook instances to certain IAM groups. What method should be employed to ensure that only designated IAM groups have the necessary permissions to access and interact with SageMaker notebooks?

- [x] Create an IAM policy with specific permissions for SageMaker, and attach it to the designated IAM groups, ensuring only members of those groups have the necessary permissions.

Overall explanation
The correct approach is to manage access to SageMaker notebook instances using IAM policies. By creating an IAM policy that specifically defines permissions for accessing SageMaker notebooks (such as sagemaker:CreateNotebookInstance, sagemaker:StartNotebookInstance, and sagemaker:StopNotebookInstance), you can ensure that only the IAM groups that have this policy attached can access and interact with the notebooks. This method provides fine-grained control over who can use SageMaker and is a core AWS security best practice for managing resources.

**Question 12**
A healthcare analytics firm is leveraging Amazon SageMaker to train machine learning models on sensitive patient data. To comply with strict data privacy regulations, the training jobs are configured to run within a Virtual Private Cloud (VPC) that lacks direct internet access. What method should be employed to ensure these training jobs can securely access training data stored in an Amazon S3 bucket?

- [x] Utilize VPC endpoints to allow direct, private connections to Amazon S3 from the VPC
- [ ] Configure an Internet Gateway in the VPC for SageMaker to access S3 buckets over the internet.

VPC endpoints facilitate secure and private communications between AWS services without traversing the public internet, making it the most suitable option for accessing S3 from a VPC without internet access. This aligns with AWS best practices for accessing S3 from private VPCs securely.

AWS Direct Connect is used to establish a private connection between an on-premises network and AWS, not within AWS services. Moreover, it's more complex and not required for the scenario of accessing S3 from SageMaker within a VPC.

**Question 13**
A data scientist has recently initialized a new Amazon SageMaker notebook instance for a predictive modeling project, utilizing the default IAM role provided during setup. Considering the need to access datasets stored in an Amazon S3 bucket, what method governs the notebook instance's ability to interact with S3 data?

- [x] Access is limited to S3 buckets with "sagemaker" in the name, unless S3FullAccess is added.

**Question 14**
A financial services firm is leveraging Amazon SageMaker to train a distributed deep learning model for fraud detection. The model training utilizes highly sensitive financial data, necessitating that data security is maintained while in-transit within a Virtual Private Cloud (VPC). What approach should be adopted to ensure that the data remains secure during its transit?

- [x] Enable SSL/TLS encryption for data in-transit between SageMaker and data sources within the VPC.
- [ ] Apply an IAM policy to SageMaker instances granting them permissions to encrypt data at rest, ensuring in-transit data security.

Overall explanation
Focus on methods that specifically secure data in-transit, differentiating between encryption, network infrastructure, and access control mechanisms.



Correct Choice: Enable SSL/TLS encryption for data in-transit between SageMaker and data sources within the VPC.



SSL/TLS encryption is a standard practice for securing data as it moves between systems, effectively meeting the requirement for in-transit data protection. This method directly addresses the concern of securing data in-transit without affecting data at rest or requiring changes to network topology.



Incorrect Choice: Apply an IAM policy to SageMaker instances granting them permissions to encrypt data at rest, ensuring in-transit data security.



IAM policies govern permissions and access control, not data encryption. While important for overall security, they do not directly secure data in-transit; instead, they are more relevant to controlling who can perform actions on specific AWS resources.

**Question 15**
An AI startup is developing a sophisticated image recognition model using TensorFlow on Amazon SageMaker. Due to the large volume of image data and the complexity of the model, training on a single GPU instance proves insufficient. How can the team scale their TensorFlow training job to efficiently utilize multiple GPUs within Amazon SageMaker?

- [x] Write your model with the Horovod distributed training framework, supported by SageMaker.
- [ ] Deploy your model to multiple EC2 P3 instances, allowing SageMaker to manage distribution.
