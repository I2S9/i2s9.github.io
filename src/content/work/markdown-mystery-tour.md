---
title: Breast Cancer Detection
publishDate: 2024-16-03 00:00:00
img: /assets/breast-cancer.jpeg
img_alt: Breast Cancer Detection
description: |  
  Data analysis and improvement of breast cancer detection ML model 
  
tags:
  - Health
  - Machine Learning
  - Data Analysis
---

##### 1. Introduction

Breast cancer is the most common cancer among women worldwide. Accounting for 25% of all cancer cases and affected 2.1 million people in 2015. Early diagnosis significantly increases the chances of survival. A key challenge of cancer detection is how to classify tumors into malignant or benign.

ML (Machine Learning) techniques can dramatically improve the accuracy of diagnosis. 91% correct diagnosis is achieved using machine learning techniques

Objective of this project : classify tumors into malignant or benign tumors using features obtained from several cell images

##### 2. Cancer diagnosis procedure

* FNA process which consist of extracting some of the cells out of the tumor, at this stage we don't know if that tumor is malignant ou benign

* The malignant (= cancerous, we need to intervene) tumor it matches the image at the top and the benign ( = tumor is kind of not spreading accross the body, the patient is safe somehow) tumor, at the image below

* As we extracted all the images and we wanted to specify if that cancer out of these images is malignant or benign

* Features means some of the characteristics of the image such as radius, for example of the cells, texture, perimeter area, smoothness and so one and then we feat all of the features for our machine learning model


##### 3. Dataset in Machine Learning terms

We are using a dataset from sklearn : [Go to the dataset](https://scikit-learn.org/stable/modules/generated/sklearn.datasets.load_breast_cancer.html)

We have a dataset with 569 number of instances and for the class distribution, we have 212 malignant & 357 benign

We have 30 features to feat them into the classifier (= machine learning model)

##### 4. Techniques used

Support vector machine method to find the best line that separate the two classes
That best line, in this case, we are going to rely on mainly two points and these two points in our study, we're gonna call it the supported vectors

We have the maximum margin hyperplane which is the hyperplane or the line that separates mainly the two classes

In order to get this line, we used a distance what we call the maximum margin distance and that's the objective of supportive vector machine classifier is to find or maximize that maximum margin distance between the two classes. In order to do this we use these two mainly points and in this case, we call them support vectors.

**Support vectors**

Support vectors are the points that we assume that these points are kind of on the boundary or a kind of on a grey area. That means that they are not fully malignant in this case or benign in this case. It's kind of between where human or physician eyes r example might be able to detect if the cancer is malignant or benign for example if that image is a cat or a dog.

Support vector machines are very powerful techniques because it's a kind of an extreme algorithm, it doesn't classify : it just focus on the supportive vectors or the points on the boudary and separate them somehow

##### 5. Model Evaluation

One of the key features or one of the key objectives of our machine learning techniques is that we want these models to generalize the data. By generalization, we mean that we want the machine learning strategy to train or not train our model specificially r this training dataset. We wanted a model to be general to basically look at the most of the images moving rward of cancer data or images and tell us if it's malignant or benign even if the images haven't been seen bere during training.

The model is an overfitted model which means that the model has learned all the characteristics out of only training data, we want a model to be as general as possible.

To evaluate the model, we are using a confusion matrix where the rows show the predictions and all the columns show all the true classes

We have what we call a type I error and type II error. Type I error indicates that the prediction must tell us that the patient has a disease. However r the true class, he actually didn't which is again, it's still an error and we call it a type I error because the patient still ok. However, type II error that's a huge problem and we wanted to avoid it at all costs especially if it's a life-threatening disease like cancer. Here, if we have our true class said it's positive that mean the patient had cancer but we said no, the ML model said that the patient is ok. 

##### 6.Improving the model

* Data normalization method: we're gonna use what we call it unity based normalization which is we wanted to get all the data to be from between 0 and 1.

* Feature scaling (Unity-based normalization) brings all values into range [0,1]

Other optimization for our model: SVM Parameters Optimization. C parameter : controls trade-off between classifying training points correctly and having a smooth decision boundary/

* Small C (loose) makes cost (penalty) of misclassification low (soft margin)

* Large C (strict) makes cost of misclassification high (hard margin); forcing the model to explain input data stricter and potentially over fit

Gamma parameters: controls how far the influence of a single training set reaches

* Large gamma: close reach (closer data points have high weight)

* Small gamma: far reach (more generalized solution)

##### References

[[EN] Github Source Code](https://github.com/I2S9/Breast-cancer)

[[EN] Breast Cancer Detection | ResearchGate](https://www.researchgate.net/publication/271907638_Breast_Cancer_Detection_with_Reduced_Feature_Set)

[[EN] Breast Cancer Screenings | Cancer Reseach UK](https://khayyam.developpez.com/articles/algo/genetic/)

[[EN] Support Vector Machines](https://link.springer.com/book/10.1007/978-3-540-73190-0)