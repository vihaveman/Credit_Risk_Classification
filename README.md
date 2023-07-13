#Analysis Overview

##Purpose 

This analysis aims to develop a machine-learning model that can accurately predict loan credit risks based on a given set of features. The dataset for this analysis contains historical information about various aspects of borrowers from a peer-to-peer lending group, such as loan size, loan rate, borrowers' income, borrowers' debt ratio, loan status and other relevant factors. This report outlines the steps taken to preprocess the data, select and train a suitable model, evaluate its performance, and make a recommendation based on the results.

##Data Processing

In this section, I explored the data to ensure it is processed and cleaned in a manner suitable for machine learning. Secondly, I used exploratory data analysis techniques to gain insights into the data distribution and identify patterns or correlations. Once the data was deemed suitable, I split the dataset into training and testing sets. 

## Model Selection

Typically, in the real world, the analytics team considers several regression models for their machine learning task, including but not limited to linear and logistic regression, decision trees, random forests, and gradient boosting. The team will then discuss each model's strengths, weaknesses, and suitability for the problem. The team bases their final choice on the model's performance on the validation set and its ability to capture the underlying complexity of the data. Given that this is an assignment and the task is to use a logistic regression model, I did not evaluate other models.

##Model Training 

High-risk loans comprised less than 5% of the dataset; in the second model, I used 'random oversampling' to compensate for my imbalanced dataset to prevent biased model training and poor performance. 

Random Over Sampling is a technique used to address this issue by artificially increasing the number of instances in the minority class. The Random Over Sampler randomly selects samples from the minority class and duplicates them until the class distribution is more balanced. This technique aims to provide the model with a more balanced training set, helping to alleviate the impact of class imbalance and improve the model's performance.

#Results 

## Machine Learning Model 1 (Original Data)

*###Accuracy: The accuracy score measures the overall proportion of correctly predicted samples. This model's prediction has an accuracy score of 99%, meaning that 1% of the predictions were incorrect. 

*###Precision: Precision score measures the proportion of true positives and false negatives predicted by the model. The 100% and 85% scores for healthy and high-risk loans, respectively, indicate that the model has a very high precision for healthy loans, which accurately predicts the majority class. However, the precision for high-risk loans is slightly lower, indicating that the model may have more false negatives for the high-risk loans, as shown below:
*56 FALSE POSITIVES --> The actual loans are healthy; however the model predicted them as high-risk
*102 FALSE NEGATIVES --> The actual loans are high-risk, but the model predicted them as healthy.
* ###Recall: Recall scores measure the proportion of true positives out of all actual positive samples. This model predicts 99% for healthy loans and 91% for high-risk loans. These scores indicate that the model has a high recall for both classes, indicating that it effectively identifies healthy and unhealthy loans.
## Machine Learning Model 2 (Oversampled Data)

*###Accuracy Score: Like the first model, this model's prediction has an accuracy score of 99%, meaning that 1% of the predictions were incorrect. 

*###Precision:  While the precision score for healthy loans remains 100%, the score dropped by 1% to 84% for high-risk loans, respectively, indicating that the model has a very high precision for healthy loans, meaning that it also accurately predicts the majority class. However, the precision for high-risk loans is slightly lower, indicating that the model may have more false negatives for the high-risk loans, as shown below:
*4 FALSE POSITIVES --> The actual loans are healthy; however, the model predicted them as high-risk. This value dropped significantly. 
*116 FALSE NEGATIVES --> The actual loans are high-risk, but the model predicted them as healthy. This value increased by 14 loans but still less than 1% of the total dataset.
* ###Recall:  This model predicts a 99% for both healthy and high-risk loans. These scores indicate that the model has a high recall for both classes, indicating that it is also effective at identifying healthy and unhealthy loans.
#Conclusion/Recommendation 
Both machine learning model successfully predicts house prices with 99% accuracy. Model 2 (oversampled model) outperformed model 1 (original data) in precision and recall value, providing a much lower level of false positives for healthy loans. This low false positive is important for the bank to build lasting customer relationships and expand its loan portfolio with new customers. What this means is if the bank uses Model 2, it has a very low probability that it will decline a loan for a customer who will repay the loan and maintain a healthy standing with the bank; as such, the bank can retain its relationship with its current customers and attract new customers for loans. 
Notably, the prediction score dropped by 1% in Model 2, resulting in a slightly higher number of false positives for healthy loans. The bank certainly does not want to increase its credit-risk-loses by giving out high-risk loans when it thinks it's a healthy loan; however, it is important to note the level of accuracy remains at 99%—additionally, not all high-risk loans results in credit losses since customers' financial situation changes over time. 
Banks need to retain their current customers to survive and maintain a competitive edge. According to Landis (2022), acquiring a new customer costs 5x more than retaining an existing customer and can increase profits from 25% to 95%; therefore, I recommend model 2 for predicting loan default probability. With low false positives, this model will allow the bank to maintain a high customer retention rate where the benefits outweigh of credit losses associated with the false negatives.
#Resources
Landis, T. (2022, April 12). Customer Retention Marketing vs. Customer Acquisition Marketing | OutboundEngine. Https://Www.outboundengine.com/. https://www.outboundengine.com/blog/customer-retention-marketing-vs-customer-acquisition-marketing/#:~:text=Acquiring%20a%20new%20customer%20can

