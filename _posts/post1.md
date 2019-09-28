---
layout: post
title: What is Overfitting and How to Avoid It?
---

Overfitting is one of the most common modeling problems in machine learning. It happens when the model fits on the training dataset too well but causes a bad performance when predicting an unseen dataset. To understand overfitting in real life, I will use an analogy to explain it. 
## Analogy of Overfitting
A data scientist, Tony, uses coding languages such as SQL, Python, C++ and Java in his current and previous data scientist job. One day, he decides to change a company, and he starts to look for data scientist jobs. He soon finds that his dream company is hiring data scientists; however, the job description shows that this data scientist job will use SQL, R and Python as coding languages. He believes that this is not a real data scientist job since it does not require C++ and Java, so he decides not to apply. This is a case of overfitting. Assume that each coding language is a feature with binary values "Yes" or "No" as the table below. Tony tries to classify a job between two classes:  "data scientist" and "not data scientist". Based on his experience, he comes up with a model in which a data scientist should at least uses coding language SQL, Python, C++ and Java. The new data scientist job does not require C++ and Java, so he classifies the new job to "not data scientist"; yet, this is a real data scientist job.

| Language        | SQL   | Python | Java  | C++ | R    |
|-----------------|-------|--------|-------|-----|------|
|   Previous Job  | Yes   | Yes    | Yes   | Yes | Yes  |
|   Current Job   | Yes   | Yes    | Yes   | Yes | No   |
|   New Job       | Yes   | Yes    | No    | No  | Yes  |
## Why Should We Care About Overfitting?
In the analogy, Tony gave up his dream company because of his overfitting model. It is crucial to avoid overfitting when we try to do prediction or classification because it will ruin our models. For example, assume we want to classify whether a car has good mileage. We train a machine learning model in a dataset including 5,000 cars with 10 features, and we use this same dataset to test our model to see how it performs. Surprisingly, we get around 99% accuracy. This means that we classify almost everything right. However, does this mean that our model is super powerful? Then, we use the same model to test on a new dataset which we have never seen before, and we get around 50% accuracy. How does this happen? Our model remembers each feature of our car dataset, so the model will just use its memory to make the prediction. It works well for those data in its memory but performs badly when dealing with unseen data.
## How to Avoid Overfitting?
First of all, we can use cross-validation in training to discover whether our model is overfitted. That is, we can split our training data into 10 folds. Then we train the first 9 folds and test it on the last fold which we never used before. Repeat the step 10 times, and we get the mean of the accuracies. If the model is overfitted, there are many ways to resolve it. 

### Increase Training Data
Increase the dataset will give more reference for the model to make a decision. In our analogy case, if Tony looked over more job descriptions, he will see that some data scientist jobs require C++ or Java, and some jobs do not. When he tries to classify the new job, he will have more reference. However, increasing training data is not always working. For example, Assume we want to classify genetic data, and each observation contains more than 4,000 features. As we increase the dataset, the model might not have significant improvements.

### Reduce Number of Features
In the cases of dealing with genetic data, we can do feature selection to remove some less important features. There are multiple techniques to select features. For example, we can use dimension reduction techniques such as filter out features with low correlations or features with high variance. Removing less important features will remove some noises and will make the model more accurate.

### Regulation Methods
Regulation is a popular technique to deal with overfitting problems. In many situations, we cannot figure out which features to remove, so we use regulation to put penalties in parameters. The goal is to minimize the cost function such as mean square error (MSE). 


Overfitting is a serious problem when we are doing model training in data science, so it is important to detect and avoid it. Besides the above methods, there are many other ways to prevent overfitting.


![_config.yml]({{ site.baseurl }}/images/config.png)

The easiest way to make your first post is to edit this one. Go into /_posts/ and update the Hello World markdown file. For more instructions head over to the [Jekyll Now repository](https://github.com/barryclark/jekyll-now) on GitHub.
