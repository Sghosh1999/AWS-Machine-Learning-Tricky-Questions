**Question 1:**

After training a SageMaker XGBoost based model over a huge training dataset, the data science team observed that it has low accuracy on the training data as well as low accuracy on the test data.

As an AWS Certified ML Specialist, which of the following techniques would you recommend to help resolve this problem? (Select two):

- [x] Use more features in the model
- [x] Remove regularization from the model
- [ ] Use less features in the model
- [ ] Add regularization to the model
- [ ] Use less training data

For the given use case, as the model has low accuracy on the training data as well as low accuracy on the test data, it suggests that the model has a bias, or in other words, the model is underfitting. When a model is underfitting, then adding more features to the model or removing regularization can help in addressing the underlying problem. In case of an underfitting model, adding more training data may or may not help.

![Overfitting vs Underfitting](overfit.img)

**Question 2:**

A financial services company has the goal of reducing fraud transactions by 10% over the next financial year. In order to achieve this goal, which of the following is the most relevant model evaluation metric that the data scientists at the company need to focus on (the model’s predicted value of 1 implies that the transaction is predicted to be fraud)?

- [x] Precision-Recall Area-Under-Curve (PR AUC)

**Question3**
You are developing a computer vision system for a factory assembly line. The system can trigger a robotic arm to correct the orientation of the product components whenever it detects a misalignment.

Which SageMaker algorithm should be used in this computer vision system?
- [x] Semantic Segmentation
- [ ] Reinforcement Learning (RL)
- [ ] Object Detection
- [ ] Image Classification

Semantic Segmentation

The SageMaker semantic segmentation algorithm provides a fine-grained, pixel-level approach to developing computer vision applications. It tags every pixel in an image with a class label from a predefined set of classes. Tagging is fundamental for understanding scenes, which is critical to an increasing number of computer vision applications, such as self-driving vehicles, medical imaging diagnostics, and robot sensing.

Because the semantic segmentation algorithm classifies every pixel in an image, it also provides information about the shapes of the objects contained in the image. The segmentation output is represented as a grayscale image, called a segmentation mask. A segmentation mask is a grayscale image with the same shape as the input image.

*Semantic Segmentation is used for pixel level analysis of an image and it can be used in this computer vision system to detect misalignment*

**Question4**
The data science team at an analytics company is working on a linear regression model and it observes that the training error as well as the test error are high, implying that the model has a bias.

Which of the following L1 and L2 regularization optimizations may be done to resolve this issue? (Select two)

- [ ] Increase L1 regularization
- [x] Use L2 regularization and drop L1 regularization
- [ ] L1 and L2 regularization are not required, just get more training data
- [ ] Decrease L1 regularization

**Question 5**
Which of the following statements is true for the Sagemaker Linear Learner algorithm?

- [x] When you use automatic model tuning, the linear learner internal tuning mechanism is turned off automatically. This sets the number of parallel models, num_models, to 1

When you use automatic model tuning, the linear learner internal tuning mechanism is turned off automatically. This sets the number of parallel models, num_models, to 1

Automatic model tuning, also known as hyperparameter tuning, finds the best version of a model by running many jobs that test a range of hyperparameters on your dataset. You choose the tunable hyperparameters, a range of values for each, and an objective metric. You choose the objective metric from the metrics that the algorithm computes. Automatic model tuning searches the hyperparameters chosen to find the combination of values that result in the model that optimizes the objective metric. When you use automatic model tuning, the linear learner internal tuning mechanism is turned off automatically. This sets the number of parallel models, num_models, to 1.

**Question 6**
A company has a history of their access logs stored in their S3 bucket. The company’s data engineer filtered out the dataset to only contain pairs of (user/IP) where it contains the name of the IAM user along with the IP address he used to access a specific service. The company recently suffered from a data breach coming from specific IP addresses which were recorded by the security team.

What approach should the company take to stop further breaches from these specific IP addresses in the least amount of time?

- [x] Use a rule-based solution.
- [ ] Use IP insights with (users/ID) pairs as input in order to output a score in the future that infers how anomalous the pattern of the event is.

Overall explanation
The company wants to stop the breaches from specific IP addresses only. So, using IP insights for training a model is not clearly the best solution.

**Question 7**
A large library decided to shift its activity to be fully internet-based as they will no longer have a physical location. The books will be presented as a soft copy on their newly established website. The library also aims to build a machine learning model to help their users search for books faster. They want to recommend books to a user that are similar to books they have read.

Which type of algorithm should the library use to implement such service?

- [x] Content based filtering.
- [ ] Collaborative filtering.

**Question 8**
You are creating a computer vision application to recognize truck brands. Your application uses Convolutional Neural Networks (CNN) but you do not have enough data to train the model. However, there are pre-trained third-party image recognition models available for similar tasks.

What steps will you take to build your solution in the shortest possible duration?

- [x] Use transfer learning in your CNN by using the pre-trained third-party image recognition model as the convolutional base. Then remove the original classifier from the pre-trained model and add the new classifier for recognizing truck brands.
- [ ] Use transfer learning by retraining the pre-trained third-party image recognition model with your own data.

**Question 9**
A credit card company wants to build a credit scoring model to help predict whether a new credit card applicant will default on a credit card payment. The company has collected data from a large number of sources with thousands of raw attributes. Early experiments to train a classification model revealed that many attributes are highly correlated, the large number of features slows down the training speed significantly, and that there are some overfitting issues.

The Data Scientist on this project would like to speed up the model training time without losing a lot of information from the original dataset.

Which feature engineering technique should the Data Scientist use to meet the objectives?

- [ ] Run self-correlation on all features and remove highly correlated features
- [ ] Normalize all numerical values to be between 0 and 1
- [x] Use an autoencoder or principal component analysis (PCA) to replace original features with new features
- [ ] Cluster raw data using k-means and use sample data from each cluster to build a new dataset

**Question 10**
A fintech company has developed a machine learning model that classifies insurance claims into fraudulent or legitimate. Given the financial implications where the expense of processing a fraudulent claim surpasses the cost associated with investigating a potentially fraudulent claim, which evaluation metric is most appropriate for assessing the performance of this classification model to ensure optimal financial outcomes?
-[x] Employ Amazon SageMaker Model Monitor to optimize for recall, prioritizing the identification of all potential fraudulent claims, even at the risk of higher investigation costs due to false positives.
-[ ] Use Amazon SageMaker's automatic hyperparameter tuning focusing on precision, to decrease the occurrence of false positives in classifying claims as fraudulent.

**Question 11**
A data science team at a media monitoring company is tasked with developing a feature that aggregates and analyzes tweets from various public figures to identify trends and thematic similarities over time. Their objective is to compute embeddings for these tweets that can accurately capture semantic similarities among them, enabling a deeper understanding of the topics and sentiments expressed. Given this context, which AWS tool would be most suited to efficiently and effectively accomplish this task?

-[x] Deploy an Object2Vec model using Amazon SageMaker to process and analyze tweet data.
-[ ] Implement a solution using Amazon SageMaker BlazingText with the Skip-gram model.

Correct Choice: Deploy an Object2Vec model using Amazon SageMaker to process and analyze tweet data.



Object2Vec is a more versatile embedding model that excels at understanding and capturing the complex relationships within texts, making it particularly suitable for tweets. Unlike word-focused models, Object2Vec can process entire tweets as single entities, ensuring that the nuanced context and semantic connections within and between tweets are effectively captured. This capability is crucial for tasks requiring a deep understanding of text semantics, such as analyzing tweets for thematic similarities or sentiment trends, providing a more holistic and accurate representation of the data.



