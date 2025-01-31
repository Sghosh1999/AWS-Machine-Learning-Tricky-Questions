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

**Question 16**
A hypermarket wants to construct a computer vision model to classify different product images into 40 unique products in order to organize their warehouse using robots. An image dataset was already collected by the hypermarket and a machine learning specialist was hired for this role.

The specialist trained the model on Amazon Sagemaker using its ready-made Pytorch container. The model should be deployed on a Sagemaker endpoint in which the hypermarket could request it anytime from any of its branches. The model does not use intensive GPU, however, sometimes it needs a moderate GPU processing power.

What is the cheapest and most appropriate instance type that the specialist should use to deploy the model?

- [x] inf2.xlarge
- [ ] P3.2xlarge

**Question 17**
A well-known company wants to automate the process of filtering their applicants due to the large number of applicants applying each day. The company receives over 150 resumes per day. The resume includes the applicant’s name, previous/current work, previous/current education, and some other information. The company saves these resumes on an S3 bucket in the company’s VPC cloud. The company wants to extract personally identifiable information, locations, organizations, and dates from the resumes. However, the resumes are provided in PDF format not text format.

Which combination of services should the company use to extract the information from the PDF resumes?

- [x] Use Amazon Textract to recognize the text from the image, then use Amazon Comprehend to extract the information required.
- [ ] Use Amazon Comprehend to recognize the text from the image, then use Amazon Textract to extract the information required.

Amazon Textract is a machine learning service that automatically extracts text, handwriting and data from scanned documents that goes beyond simple optical character recognition (OCR) to identify and extract data from forms and tables.

Amazon Comprehend is an NLP service that could extract key phrases, entities, and sentiments and much more.

**Question 18**
An ML engineer has built a deep learning model and now wants to deploy it using the SageMaker Hosting Services. For inference, the engineer wants a cost-effective option that guarantees low latency but still comes at a fraction of the cost of using a GPU instance for the endpoint.

As an AWS ML Specialist, which of the following would you recommend for the given use case?

- [x] Elastic Inference
- [ ] Inference Pipeline
- [ ] Automatic Scaling

Overall explanation
Correct option:

**Elastic Inference**

ML inference is the process of using a trained machine learning model to make predictions. By using Amazon Elastic Inference (EI), you can speed up the throughput and decrease the latency of getting real-time inferences from your deep learning models that are deployed as Amazon SageMaker hosted models, but at a fraction of the cost of using a GPU instance for your endpoint. Elastic Inference is supported in EI-enabled versions of TensorFlow, Apache MXNet, and PyTorch.


**Incorrect options:**

SageMaker Neo - Amazon SageMaker Neo enables developers to optimize machine learning (ML) models for inference on SageMaker in the cloud and supported devices at the edge.

After training a model for high accuracy, developers often spend a lot of time and effort tuning the model for high performance. For inference in the cloud, developers often turn to large instances with lots of memory and powerful processing capabilities at higher costs to achieve better throughput. For inference on edge devices with limited compute and memory, developers often spend months hand-tuning the model to achieve acceptable performance within the device hardware constraints.

Amazon SageMaker Neo automatically optimizes machine learning models for inference on cloud instances and edge devices to run faster with no loss in accuracy.

SageMaker Neo cannot be used to accelerate real-time inferences calls for deep learning models that are deployed as Amazon SageMaker hosted models.

**Automatic Scaling** - Amazon SageMaker supports automatic scaling (autoscaling) for your hosted models. Autoscaling dynamically adjusts the number of instances provisioned for a model in response to changes in your workload. When the workload increases, autoscaling brings more instances online. When the workload decreases, autoscaling removes unnecessary instances so that you don't pay for provisioned instances that you aren't using.

Autoscaling cannot be used to accelerate real-time inferences calls for deep learning models that are deployed as Amazon SageMaker hosted models.

**Inference Pipeline** - An `inference pipeline` is a Amazon SageMaker model that is composed of a linear sequence of two to fifteen containers that process requests for inferences on data. You use an inference pipeline to define and deploy any combination of pretrained SageMaker built-in algorithms and your own custom algorithms packaged in Docker containers.

Inference pipeline cannot be used to accelerate real-time inferences calls for deep learning models that are deployed as Amazon SageMaker hosted models.

Reference:

https://docs.aws.amazon.com/sagemaker/latest/dg/ei.html

**Question 19**
You have disabled direct internet access to your Amazon SageMaker notebook instance while connecting to your VPC in order to prevent unauthorized access to your data. As there is no data access via the internet, the notebook instance is not able to train or host models.

Which of the following solutions can be used to address this issue? (Select two)

- [x] Setup NAT gateway for your VPC and configure Security Groups for your VPC that allow outbound connections
- [ ] Setup NAT gateway for your VPC along with Security Groups for your VPC that allow inbound connections
- [ ] Setup S3 gateway for your VPC
- [x] Create a VPC interface endpoint to use PrivateLink for your notebook instance and then configure Security Groups for your VPC that allow outbound connections 

*Overall explanation*
Correct options:

Create a VPC interface endpoint to use PrivateLink for your notebook instance and then configure Security Groups for your VPC that allow outbound connections

You can connect to your notebook instance from your VPC through an interface endpoint in your Virtual Private Cloud (VPC) instead of connecting over the public internet. When you use a VPC interface endpoint, communication between your VPC and the notebook instance is conducted entirely and securely within the AWS network.

Setup NAT gateway for your VPC and configure Security Groups for your VPC that allow outbound connections

The instances in a private subnet can access the internet by using a network address translation (NAT) gateway that resides in the public subnet.

As the notebook instance is in a VPC, so the internet access is disabled. The notebook instance won't be able to train or host models unless your VPC has an interface endpoint (PrivateLink) or a NAT gateway and your security groups allow outbound connections.

**Question 210**
A company has sensitive data of its customers residing in a kms-encrypted S3 bucket. A machine learning engineer should build a classifier using Amazon SageMaker for pre-processing, training, and deployment of the model. The S3 bucket and SageMaker notebook are both located within the same VPC. The company demands that all traffic should be secured and within a private connection in the VPC.

Which solution is the most appropriate to begin experimenting with the model on SageMaker?

- [x] Create a VPC gateway endpoint to allow connection between S3 endpoint and SageMaker. Assign an IAM role to SageMaker and grant it read access permissions to the S3 bucket and KMS key policy.
- [ ] Create a VPC gateway endpoint to allow connection between S3 endpoint and SageMaker. Assign an IAM role to SageMaker and grant it read access permissions to the S3 bucket.

A VPC endpoint enables private connections between a virtual private cloud (VPC) and supported services. Therefore, your VPC is not exposed to the public internet. A gateway endpoint is a gateway that is a target for a route in your route table used for traffic destined to either Amazon S3 or DynamoDB. Amazon SageMaker cannot access the S3 bucket without having the appropriate role. Also, the S3 bucket is secured using Amazon KMS, therefore granting the role read permission into S3 is not enough. A KMS key policy permission should be granted to decrypt the data in S3 and begin reading it.