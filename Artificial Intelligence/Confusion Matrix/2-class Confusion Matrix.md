## 2-class Confusion Matrix

Take a look at the 2-class confusion matrix below, when the classifier gives binary result, such as "true" or "false" and "yes" or "no".

|  |  | Actual Value | Actual Value
|-|-|:-:|:-:|
|||0|1|
|Predicted Value| 0 | True Positive | False Positive |
|Predicted Value| 1 | False Negative | True Negative |

To understand this easily, Let's use a spam filter as an example.

There are emails which are spam (0) and not-spam (1). The spam filter will classfiy the emails into this:

1. True Positves (TP) - The email ==is a spam==, ==classified as spam==.
2. True Negatives (TN) - The mail is is ==not a spam==, ==classified as not-spam==.
3. False Postives (FP) - The mail is ==not a spam==, but ==classified as spam==.
4. False Negatives (FN) - The mail is a ==spam==. but ==classified as not-spam.==

- True Negatives (TN) and True Positives (TP) are correct prediction of the spam filter.

For a 2-class confusion matrix, the accuracy of it can be calculated by 

$$ Accuracy = (TN + TP)  / ( TP+TN+FP+FN) $$

  while ( TP+TN+FP+FN ) means the total number of predictions.



---
> Correctly Classified Instances = (TP + TN )

> Incorrectly Classified Instances = (FP + FN )

### Metrics
[[Accuracy,Precision and Recall]]

** Accuracy**
- The ratio of correct predictions to the total predictions made.
- As mentioned before, accuracy can be calculated by 
	$$Accuracy = ( TP+TN ) / All ~Predictions $$
	
---

**Sensitivity / Recall(REC) / (TP rate)**
- The number of correct positive predictions divided by the total number of positives.
	 ![[sensitivity.png]]
 
> TP/ (TP+ FN) 

---

**Specificity ( TN rate ) **
- The number of correct negative predictions divided by the total number of negatives.
- The best specificity is 1.0 and the worst is 0.0
![[specificity.png]]

>=TN / ( TN + FP )


---
**False Positive Rate (1-specificity)**
- The number of incorrect positive predictions divided by the total number of negatives.
- The best FP rate is 0.0 whereas the worst is 1.0
- It can also be calculated as 1 - specificity.
> = FP / ( FP + TN )

---

**False Negative Rate**
- The proportion of the positive class got incorrectly classified by the classifier.
> =FN / ( FN +TP )

---

**Precision**
- The number of correct positive predictions divided by the total number of positive predicitions. It is also caleed positive predictive rate (PPV)
- The best precision is 1.0 whereas the worst is 0.0
![[precision.png]]
 > = TP / ( TP + FP )

---

## Choosing among metrics
These values derived from the confusion matrix , some are preffered according to the business problem in hand.

[[Confusion Matrix Evaluation]]

---
## AUC-ROC curve
[[Confusion Matrix Evaluation#AUC-ROC curve]]

https://www.analyticsvidhya.com/blog/2020/06/auc-roc-curve-machine-learning/
