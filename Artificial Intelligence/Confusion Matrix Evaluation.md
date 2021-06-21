
Using a Bank Loan Defaulters as example in evaluating metrics of a classifier model.

A bank creates a model to predict if a customer is a defaulter or not using its previous database. 

We know that, there the data will splits into 4 categories:
- TP (True Positives)
- TN (True Negatives)
- FP (False Positives)
- FN (False Negatives)

In this case the company will keep an eye on two parameters:

1) True Positive Rate(TPR): A true positive rate also known as sensitivity. In this case it will be, TP/(TP+FN). This metric will show us that out of all actual defaulters how many are predicted correctly. The bank will need a high value for this. Ideally it should be 1, because it will be beneficial for the bank if they can predict a defaulter and reject their application with 100 percent certainty.

3) False Positive Rate(FPR): False positive rate is given by (FP/TN+FP), also known as as 1-specificity. This metric will show us that out of all non-defaulters how many are predicted as defaulters by the ML model. A low value for FPR is preferred. Ideally it should be zero because a high value will mean that the bank will reject potentially good customers if the ML model is implemented, thereby reducing the overall business of the bank.

One thing that we can understand is that Confusion Matrix can be analysed according to the business problem in hand.
![[classification threshold.png]]

We can set a threshold value to classify all the values greater than threshold as 1 and lesser then that as 0. 

That’s how the Y is predicted and we get ‘Y-predicted’. The default value for threshold on which we generally get a Confusion Matrix is 0.50. This is where things start to get interesting. We can alter this threshold value. 

A change in the threshold value will see a change in predicted values of Y, hence the new confusion matrix will be different and more importantly TPR and FPR values will also change. 

Therefore we can visualise that for every unique value of a threshold we’ll get different TPR and FPR value each. When these different TPR(sensitivity) and FPR(1-specificity) values are plotted on a scatter plot and a line is passed through them we get what we is famously called Receiver Operating Characteristic(ROC) curve.

## AUC-ROC curve
The ROC curve is different for different classification machine learning models. Just like sensitivity or accuracy, ==the area under curve(AUC) of ROC curve is treated as a very valuable metric to evaluate the model.==

![[ROC curve.png]]

If we go back and look at our business need, we needed a high TPR and low FPR that is exactly what we are getting from that point on this ROC. The threshold corresponding to that point can be said to be the best threshold value. But in real life scenarios, building a model with a very high AUC is not always possible. This is what a decent classification model’s ROC will look like:

![[decent AUC for a classification model.png]]

Looking at the graph, we can understand that to achieve a good True Positive Rate, False Positive Rate will also have to be raised. Therefore a trade-off has to be done between them. Now coming to the business part, the bank efficiently is balancing between reducing defaulters(increasing TPR) and reducing wrong classification of good customers as probable defaulters(lowering FPR). Therefore the organisation in this case can’t just rely on the accuracy of the model. A deep analysis of the confusion matrix and connecting it with the business problem is required before jumping to any conclusions and making business decisions. Hence, after finalizing the TPR and FPR values the corresponding threshold value can easily be traced back and that will be used for the final prediction of the customer type(Y_pred). We can now understand how different business problems will require different analysis for proper model building.