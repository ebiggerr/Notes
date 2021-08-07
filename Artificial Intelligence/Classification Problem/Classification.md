# Classification

Classification is a form of data analysis that extracts models describing important data classes. 

## General Approach to Classification
1. Build a classification model based on historical/past data
2. Evaluate the model if it's accuracy is acceptable -> If so, use the model to classify new data. 

A classifier is built describing a predetermined set of data class or concepts. 

##### Learning Step
A classfification algorithms builds the classifier by analyzing or "learning from" a `training set` made up of database tuples and their associated class labels. 

A tuple, `X` is represented by an *n-dimensional* **attribute vector, X= ( x<sub>1</sub>, x<sub>2</sub>,..., x<sub>n</sub>)** , depicting n measurement made on the tuple from `n` database attributes, respectively, ( A<sub>1</sub>, A<sub>2</sub>,..., A<sub>n</sub>). Each tuple, `X` is assumed to belong to a predefined class as determined by another database attributes called as the `class label attribute`. (Discrete valued and unordered) 

Because the class label of each training tuple is provided, this step is also known as [[Supervised Learning]] (the learning of the classifier is "supervised" in that it is told to which class each training tuple belongs ). In contrast with [[Unsupervised Learning]] ( or [[Clustering]]) in which the class lable of each training label is not known, and the number or set of classes to be learned may not be know in advance.

##### Classification Step

Test data are used to estimate the accuracy of the classification rules. If the accuracy of the model is considered acceptabe, the rules can be applied to the classfication of new data tuples.

## Classification VS Prediction

**Classification:**
The model or `classifier` is constructed to predict class (categorical) labels. These categories can be represented by discrete values.

---
**Prediction (Numeric):**
The model or `predictor` is constructed to predict a continuos-valued function, or ordered values.

`Regression analysis` is a statistical methodology that is most ofren used for numeric prediction.



## Types of Classification

[[Binary Classification]]
-	[[Decision Tree]] ( See also [[Decision Tree#Decision Tree Induction]] )
- [[Naive Bayes]]

[[Multi-class Classification]]
[[Multi-label Classification]]

## Evaluating the Classification Model
[[Confusion Matrix]]
