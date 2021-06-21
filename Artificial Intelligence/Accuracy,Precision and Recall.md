## Accuracy
> Overall, how often is the classifier correct?

Conventionally, accuracy is defined as the average number of correct predictions.
Therefore, in 2-class it is 

> ( TN + TP ) / All Predictions

In muti-class it is
> Sum of the the leading diagonal / All predictions

==Leading diagonal is all the TP==

---

## Sensitivity / Recall (REC) / TP rate
> When it's actually yes, how often does it predict yes?

The number of correct positive predictions divided by the total number of positives.

Therefore, in 2-class it is 

> TP/ (TP+ FN) 

In muti-class it is, for a particular class *a*

> REC (a) = TP/ (TP+ FN) 

---


## Specificity (TN rate)
> When it's actually no, how often does it predict no? 

The number of correct negative predictions divided by the total number of negatives.
The best specificity is 1.0 and the worst is 0.0

Therefore, in 2-class it is 

> TN / (TN + FP)

In muti-class it is, for a particular class *a*

>TNR (a) = TN / (TN + FP)

---

## False Positive Rate (1-specificity) / Type I Error
> When it's actually no, how often does it predict yes?

The number of incorrect positive predictions divided by the total number of negatives.
The best FP rate is 0.0 whereas the worst is 1.0
It can also be calculated as 1 - specificity.

Therefore, in 2-class it is 

>  FP / ( FP + TN )

In muti-class it is, for a particular class *a*

> False Positive Rate (a) = FP / ( FP + TN )

#### The relationship between FP rate and TN rate

==FP rate + TN rate(Specificity) = 1.00==

---

## False Negative Rate (Type II Error )
The proportion of the positive class got incorrectly classified by the classifier.
> FN / ( FN +TP )

---
## Precision
> When it predicts yes, how often is it correct? 

The number of correct positive predictions divided by the total number of positive predicitions. It is also called positive predictive rate (PPV). 
The best precision is 1.0 whereas the worst is 0.0

> TP/ ( TP + FP )

---

# Precision Vs Sensitivity(Recall/TP rate)

> Precision tells us how many of the correctly predicted case actually turned out to be positive.

> Recall tells us how many of the actual positive cases we were able to predict correctly with the model.

==Precision== is an useful metric in cases where **False Positive** is a higher concern than **False Negatives**

==Recall== is an useful metric in cases where **False Negatives** trumps **False Positive**
*means that we care more about FN*

![[confusion matrix table.png]]

==Recall== is important in medical cases where it doesn't matter whether we raise a false alarm but the actual positive cases should not go undetected.

In our example above, **Recall** would be a better metric because we don’t want to accidentally discharge an infected person and let them mix with the healthy population thereby spreading the contagious virus.

