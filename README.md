# People_Analytics

HR Analytics: Job change of Data Scientists


**The objective of the project is to predict the probability of a candidate to look for a new job or will work for the company.**


The focus of this project is

* **Visualization**

* **Imbalance of data**


We use python profiling, matplotlib, seaborn to help us visualize data and understand patterns.


The challenge with data is that the data set is imbalanced. To deal with this, Random sampling is performed. SMOTE and Borderline SMOTE is performed and then applying the data for above mentioned classification algorithms to see how this would enhance the performance of the models.

## SMOTE

Sampling with replacement is applied to the minority class to create as many observations as there are in the majority class and the two classes are balanced. This is called oversampling or upsampling the minority class.

Issue: Repetition of the same minority class data leads to overfitting.

SMOTE (Synthetic Minority Oversampling Technique) – Oversampling. SMOTE is a technique that helps deal with imbalanced data sets.

* First split your data first, and

* THEN use SMOTE on the training data only.

DO NOT use SMOTE and THEN split data into train & test sets. This is a mistake because one will get some serious data leakage and end up predicting synthetic results that have just been created.

## Borderline SMOTE

There are many oversampling techniques that one could employ.

A variation of the technique used above is Borderline SMOTE.

If there are observations in the minority class which are outlying and appears in the majority class, it causes a problem for SMOTE, by creating a line bridge with the majority class.

Borderline SMOTE solves the above issue.

* Ignores noise points and normal minority point.

* Use border points for synthetic data generation.

This algorithm starts by classifying the minority class observations. It classifies any minority observation as a noise point if all the neighbors are the majority class and such an observation is ignored while creating synthetic data (Similar to DBSCAN). Further, it classifies a few points as border points that have both majority and minority class as neighborhood and resample completely from these points (Extreme observations on which a support vector will typically pay attention to).

Issue: End up giving more attention to these extreme observations.

#### Observation:

* By using SMOTE, we can increase recall at the cost of precision.


## Conclusion

We have explored and visualized our data in interesting ways.

Also,dealt with null values & performed feature engineering so get a more complete view of our data. Feature scaling is also done while modelling.

Finally, we performed several machine learning algorithms to try to predict whether or not someone would be a job seeker or not.

We looked at:

Logistic Regression Classifier
K Nearest Neighbors Classifier
Support Vector Machines Classifier
Decision Trees Classifier
Random Forests Classifier
Next, we looked at addressing the imbalance in our data.

Using SMOTE, and then re-trained the models, all classifiers mentioned above. Using F1 score as measure of performance, the Decision tree model performed well and those were used as model for predicting.

Using Borderline SMOTE did not have much impact in terms of performance.

Further Improvements can be made

Models can utilize to better hyperparameter tuning and models like Light GBM can used.

Working with catagorical features is difficult, especialy when using One-Hot Encoding, this lead to a messy dataframe and longer computational.

- Detected patterns in the job change of the Data Scientists performing Exploratory Data Analysis and utilized Python profiling, Matplotlib and Seaborn to visualize the data.

- Performed Logistic Regression, K Nearest Neighbors, Support Vector Machines, Decision Trees, Random Forests and retrained models after dealing with the imbalance of the data.

- Performed SMOTE and Borderline SMOTE to deal with the imbalance of the data thereby improving the performance by reducing the misclassification of number of job seekers from 987 to 383 who was predicted as non-job seekers.

- Predicted job seekers accurately 76% of the time using Logistic Regression.


## Reference



> [7 Techniques to Handle Imbalanced Data](https://www.kdnuggets.com/2017/06/7-techniques-handle-imbalanced-data.html).

> https://www.geeksforgeeks.org/ml-handling-imbalanced-data-with-smote-and-near-miss-algorithm-in-python/.

> https://machinelearningmastery.com/smote-oversampling-for-imbalanced-classification/.

> https://towardsdatascience.com/class-imbalance-smote-borderline-smote-adasyn-6e36c78d804.

Referring to others work has helped explore and understand the data and methods performed. 

> Please find analysis of 2 of many available works on Kaggle in doc - Review Others' work.
