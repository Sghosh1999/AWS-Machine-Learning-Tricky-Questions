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
