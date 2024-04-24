# SC1015- Refining Credit Risk Models

# ❓ About
This is a Mini-Project for SC1015 (Introduction to Data Science and Artificial Intelligence) which focuses on Credit Risk Level from Kaggle's Loan Dataset: [Loan Dataset](https://www.kaggle.com/datasets/somyaagarwal69/loan-data-2015/data)

# 🔎 Problem Definition
* What should we do to effectively predict whether a person taking the loan has a high risk of defaulting
* What are some main factors that affects a person credit risk?

# 💪 Motivation 
In today's financial landscape, taking out loans has become a standard practice for investors and individuals alike, whether for investment purposes or other needs. Nevertheless, banks are witnessing an uptick in loan defaults, prompting a need to enhance their credit risk evaluation methods to more accurately predict potential defaults.

# 🚀 Models used
1. Multi-variate Logistic Regression (SKLearn)
2. Random Forest Regression (SKLearn)
3. Deep Learning Neural Network (Tensorflow)

# 🚶 Steps we took
**1. Data Preparation** <br>
<pre><code>- Dropping Data: Dropped columns that are deemed irrelevant and useless to the model
- Regrouping Variable: For column 'loan_status', we decided to drop rows with Current/In Grace Period/Issued
- Addressing NA Values: Filling NA values with the median of the original data
- Removing outliers: Data points which are +- 1.5 IQR from Q1 and Q3 were considered to be outliers
- Encoding of Category Variables: Label Encoder and One Hot Encoder to encode all the categorical variable based on the number of unique value it has</code></pre>

**2. Data Visualisation & Exploratory Data Analysis** <br>
<pre><code>- Plotted the distribution of all variables using a boxplot, histogram and violinplot for all 32 variables
- Scatterplot of all predictor variables against Credit Risk
- Generate Data-driven insights
</code></pre>

**3. SKLearn Random Forest Classification** <br>
<pre><code>- We ran a train-test split of 70-30 
- Made used of 100 as our estimator in order to generate a more reliable model
- Obtained an initial classification accuracy of 100% on the train set but only 99.83% in the test model.
- Obtained 0% in both FP and FN in train set but 0.61% FN in test set.
- Hence, we removed the outliers and ran the model again which later return improved results with 99.93% and 99.97% in classification for both train and test set. Reduced FN rate of 0.25% and 0.12% in train and test respectively.
</code></pre>

**4. SKLearn Logistic Regression** <br>
<pre><code>- Ran a train-test split of 70-30
- Fitted the model and plotted the classifcation report and confusion matrix
- Obtained an initial classification accuracy of 99.88% in train set and 99.87% in test set.
- Obtained a FN rate of 0.43% in train set and 0.46% FN rate in test set.
- Hence, we removed the outliers and ran the model again which later return a lower FN in train set of 0.36%  
</code></pre>

**5. Artificial Neural Network Regression using TensorFlow** <br>
<pre><code>- Ran a train-test split of 70-30
- Used 20 epochs for our model so that runtime will not be too long.
- Obtained an initial classfication accuracy of 99.97% and 99.78% for train and test set
- Obtained a FN rate of 0.76% in train set and 0.80% FN rate in test set.
- Hence, we removed the outliers and ran the model again which later return an increase of FP rate but lower FN rate in both train and test.
</code></pre>

# 💡 Conclusion & Recommendations
From our 3 models, Logistic regression has the lowest False Positive and Negative rates on test dataset.
| Model  | FP & FN on Test Data Set (2 d.p) |
| ------------- | ------------- |
| Random Forest Regression   | 0.09% and 0.36% |
| Logistic Regression   | 0.00% and 0.12% |
|Artifical Neural Network Regression with TensorFlow | 1.01% and 0.12% |

Logistic Regression maybe more effective due to the <b>datatype of the dataset</b>. It strength in modelling a binary dependent variable suits our dataset as we are predicting the credit risk which is a categorical data.

Depending on the banks decision, we should consider changing the threshold probability if the model is showing high rates of false positives or false negatives. 

For example, if the model is classifying many False Positives, it may cause a high number of unapproved loans for creditworthy applicants. In this case, the bank might want to change the decision boundary to be more lenient, resulting in fewer false positives and more loans being approved. On the other hand, if the model is classifying many False Negatives, it may be cause a high level of loan defaults and financial loss for the lender. In this case, the lender might want to change the decision boundary to be more strict, resulting in fewer false negatives and more defaults being identified.

Therefore, it is important to consider the business and regulatory context in which the model will be used when deciding on the threshold value.

# 📚 New Content Learnt
* Deep Learning using TensorFlow and Keras library
* Random Forest and determining best number of estimators
* Feature Importance using Random Forest
* Git and Github Usage

# References
* [Loan Dataset](https://www.kaggle.com/datasets/somyaagarwal69/loan-data-2015/data) <br>
* [Regression with TensorFlow](https://www.tensorflow.org/tutorials/keras/regression)
