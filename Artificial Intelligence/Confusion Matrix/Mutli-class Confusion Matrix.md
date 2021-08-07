### Multi-class Confusion Matrix
As the name implies, it is a confusion matrix that deals with multiple classes. Just like a 2-class confusion matrix, it describes the quality of the output of a multi-class classification model.

Taking an example, a multi-class classification model that classifies images of dog into the following breeds: 
- Greyhound
- Mastiff 
- Samoyed

![[Multi class Confusion Matrix.png]]
	
In this visualisation, we have two sections which have been outlines. We have the **predicted** classifications section which contains three subsections for each of the classes we want to classify into and the **actual** classifications section which has three subsections for each of the classes. 

P<sub>GG</sub> 
Represents the number of the predictions where images of **GreyHound** were correctly classified.
 ==True Positives for GreyHound class==
 
P<sub>MG</sub> 
- Images of a **GreyHound** were incorrectly classified as a **Mastiff**

P<sub>SG</sub> 
- Images of a **GreyHound** were incorrectly classified as a **Samoyed**

P<sub>GM</sub> 
- Images of a **Mastiff** were incorrectly classified as a **GreyHound**


P<sub>MM</sub> 
Represents the number of the predictions where images of **Mastiff** were correctly classified.
 ==True Positives for Mastiff class==

P<sub>SG</sub> 
- Images of a **GreyHound** were incorrectly classified as a **Samoyed**

P<sub>GS</sub> 
- Images of a **Samoyed** were incorrectly classified as a **GreyHound**

P<sub>MS</sub> 
- Images of a **Samoyed** were incorrectly classified as a **Mastiff**

P<sub>SS</sub> 
Represents the number of the predictions where images of **Samoyed** were correctly classified.
 ==True Positives for Samoyed class==
 
 ---
 
 #### True Positives 
 ==Highligted section above==
 
 ---
 
 #### True Negatives
 The TN for a particular class is calculated by taking the sum of the values in every row and column except the row and column of the class we're trying to find the TN for.
 
 ==**GreyHound** class==
 ![[TN for GreyHound class.png]]
 
 We omit the rows and columns belonging to the **GreyHound** class and sum the variables that are left, which are the rows and columns of the other classes ( Mastiff and Samoyed )
 
 Therefore the ==TN== for the **GreyHound** class is 
 TN= P<sub>MM</sub> + P<sub>SM</sub> + P<sub>MS</sub> + P<sub>SS</sub>
 
 ==**Mastiff** class==
 ![[TN for Mastiff Class.png]]
 
  Therefore the ==TN== for the **Mastiff** class is 
 TN= P<sub>GG</sub> + P<sub>SG</sub> + P<sub>GS</sub> + P<sub>SS</sub>
 
==**Samoyed** class==
 ![[TN for Samoyed class.png]]
  Therefore the ==TN== for the **Samoyed* class is 
 TN= P<sub>GG</sub> + P<sub>MG</sub> + P<sub>GM</sub> + P<sub>MM</sub>
 
 ---
 
 
 #### False Positives
 The false positives of a particular class can be calculated by taking the sum of all the values in the colun corresponding to the class except the **True Positives** value.
 
 ==**GreyHound** class==
 ![[FP for GreyHound class.png]]
 We sum all the values in the highlighted area, which is the colun corresponding to the **GreyHound** class with the exception of the variable P<sub>GG</sub>
 which we have earlier identified to be the **True Positives** for the **GreyHound** class.
 
 Therefore, the FP for the **GreyHound** class
 is 
 FP= P<sub>GM</sub> + P<sub>GS</sub> 
 
==**Mastiff** class==
 ![[FP for Mastiff class.png]]
 Therefore, the FP for the **Mastiff** class
 is 
 FP= P<sub>MG</sub> + P<sub>MS</sub> 
 
 ==**Samoyed** class==
 ![[FP for Samoyed class.png]]
 Therefore, the FP for the **Samoyed** class
 is 
 FP= P<sub>SG</sub> + P<sub>SM</sub> 
 
 ___
 #### False Negatives
 
 The FN for a particular class can be calculated by taking the sum of all the values in the row corresponding to that class except the **True Positives** value.
 
 ==**GreyHound** class==
 ![[FN for GreyHound class.png]]
 We sum all the values in the highligted area, which is the row corresponding to the **GreyHound** class with the exception of the variable P<sub>GG</sub> which we had earlier identified to be the TP for the **GreyHound** class.
 
 Therefore, the FN for **GreyHound** class is 
 
  FN= P<sub>MG</sub> + P<sub>SG</sub> 
  
  ==**Mastiff** class==
  ![[FN for Mastiff class.png]]
   Therefore, the FN for **Mastiff** class is 
 
  FN= P<sub>GM</sub> + P<sub>SM</sub> 
  
  ==**Samoyed**== class
  ![[FN for Samoyed class.png]]
  
   Therefore, the FN for **Samoyed** class is 
 
  FN= P<sub>GS</sub> + P<sub>MS</sub> 
  
  ---
  
  # Metrics
  
  ## Accuracy
  The ratio of the number of correct classifications to the total number of classifications.
  
  For a multi-class classifier model, the accuracy is calculated as
  
  $$Accuracy = ( all~~TPs) / All~ Predictions $$
  
  ## Precision
  The measure of the accuracy relative to the prediction of a specfic class. It is calculated as the ratio o the TP of a class in question to the sum off its TP and FP.
  
  **GreyHound** class
  
  $$ Precision(G) = TP / (TP + FP ) $$
  $$ = P_G._G / ( P_G._G (P_G._M + P_G._S) ) $$
  *omit the .*
  
   **Mastiff** class
  
  $$ Precision(M) = TP / (TP + FP ) $$
  $$ = P_M._M / ( P_M._M (P_M._G + P_M._S) ) $$
  *omit the .*
  
   **Samoyed* class
  
  $$ Precision(S) = TP / (TP + FP ) $$
  $$ = P_S._S / ( P_S._S (P_S._G + P_S._M) ) $$
  *omit the .*
  
  ## Recall / Sensitivity / TP rate
  The ratio of the TP of a specific class ot the sum of its TP and FN
  
  **GreyHound** class
  
  TPR (G) = TP / (TP + FN)
​ = PGG / (PGG + (PMG + PSG))

**Mastiff** class:

​ TPR (M) = TP / (TP + FN)
​ = PMM / (PMM + (PGM + PSM))

**Samoyed** class:

​ TPR (S) = TP / (TP + FN)
​ = PSS / (PSS + (PGS + PMS))

## Specificity / TN rate
The ration of the TN of a specific class to the sum of its TN and FP

**Greyhound** class:

​ TNR (G) = TN / (TN + FP)
​ = (PMM + PSM + PMS + PSS) / ((PMM + PSM + PMS + PSS) + (PGM + PGS))

**Mastiff** class:

​ TNR (M) = TN / (TN + FP)
​ = (PGG + PSG + PGS + PSS) / ((PGG + PSG + PGS + PSS) + (PMG + PMS))

**Samoyed** class:

​ TNR (S) = TN / (TN + FP)
​ = (PGG + PMG + PGM + PMM) / ((PGG + PMG + PGM + PMM) + (PSG + PSM))

