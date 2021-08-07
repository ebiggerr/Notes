# Decision Tree
A flowchart-like tree structure, where each `internal node (non-leaf node` dentes a test on an attribute, each `branch` represents an outcome of the test, and each `leaf node (or terminal node)` holds a class label. The topmost node in a tree is the `root node`.

Some decision tree algorithms produce only binary tree (where each internal node branches to exactly two child nodes , see [[Binary Classification]] ]), where some can produce non-binary tree (See [[Multi-class Classification]] )

Given a tuple `X`, for which the associated class label is unknown, the attributes values of the tuple are tested against the decision tree. A path is traed from the root to a leaf node, which holds the class prediction for that tuple. Decision tree can easily be converted to classification rules.

##### Classification Rule (Example)
```

IF age=youth THEN loan_decision=risky
IF income=high THEN loan_decision=safe
IF age=middle_aged AND income=low
THEN loan_decision=risky

```

## Decision Tree Induction

Decision Tree Induction is the `learning of decision trees from class-labelled training tuples`

ID3 (Iteratice Dichotomiser) developed by J.Ross Quinlan during the late 1970s and early 1980s.

C4.5 (Sucessor of ID3, J.Ross Quinlan)

Both of the algorithms adopt a greedy (i.e non-backtracking) approach in which decision trees are constructed in a top-down recursive divide-and-conquer manner.

Most of the algorithms for decision tree induction also follow a top-down approach, which starts with a training set of tuples and their associated class labels. The training set is recursively partitioned into smaller subsets as the tree is being built. 

The algorithm (ID3 or C4.5) called with 3 parameters
- *D*
	- refer as the data partition ( it is the complete set of training tuples and their associated class labels)
- *attribute_list*	
	- List of attributes describing the tuples
- *Attributre_selection_method*
	- Specifies a heuristics procedure for selectiong the attribute that "best" discriminates the given tuples according to class

Attibute Selection employs an attribute selection measure such as [[#Information gain]] or the [[#Gini Index]]. (Gini Index enforce the resulting tree to binary ,while information gain does not ,therein allowing multiway splits, meaning two or more branches to be grown from a node)

## Attribute Selection Measures
An attribute selection measure is a heuristic for selecting the splitting criterion that “best” separates a given data partition, D, of class-labeled training tuples into individual classes. If we were to split D into smaller partitions according to the outcomes of the splitting criterion, ideally each partition would be pure (i.e., all the tuples that fall into a given partition would belong to the same class). 

Attribute selection measures are also known as splitting rules because they determine how the tuples at a given node are to be split.

The attribute selection measure provides a ranking for each attribute describing the given training tuples. The attribute having the best score for the measure is chosen as the splitting attribute for the given tuples.

If the splitting attribute is continuous-valued or if we are restricted to binary trees, then, respectively, either a split point or a splitting subset must also be determined as part of the splitting criterion. 

The tree node created for partition D is labeled with the splitting criterion, branches are grown for each outcome of the criterion, and the tuples are partitioned accordingly.

### Information Gain
ID3 used information gain as its attribute selection measure.

Let node `N` represent tuples of partition D. The attribute with the highest information gain is chosen as the splitting attribute for node `N`. This attribute minimized the information needed classify the tuples in the resulting partitions and reflects the least randomness or "impurity" in these partitions. This approach minimizes the expected number of tests needed to classify a given tuple and guarantees that a simple ( not neccessarily the simplest) tree is found.

The expected information needed to classify a tuple in D is given by

$$ Info(D) = - \sum\limits_{i=1}^m p_i log_2(p_i) $$

where $p_i$ is the non-zero probabilty that an arbbitary tuple in D belongs to class $C_i$ and is estimated by $|C_i,_D|/|D|$. A log function to the base 2 is used, because the information s encoded in bits. $Info(D)$ is just the average amount of information needed to identitfy the class label of a tuple in D. 
Note that, at this point, the information we have is based solely on the proportions of tuples of each class. $Info(D)$ is also known as the `entropy` of D.

Now, suppose we were to partition the tuples in `D` on some attribute `A` having `v` distinct values, {a<sub>1</sub>, a<sub>2</sub>, ... , a<sub>v</sub>}, as observed from the training data. If `A` is discrete-valued, these values correspond directly to the `v` outcomes of a test on `A`. Attribute `A` can be used to split `D` into `v` partitions or subsets, {D<sub>1</sub>, D<sub>2</sub>, ... , D<sub>v</sub>} , where $D_j$ contains those tuples in `D` that have outcome $a_j$ of `A`. These partitions would correspond to the branches grown from node `N`. Ideally, we would like this partitioning to produce an exact classification of the tuples. That is, we would like for each partition to be pure. However, it is quite likely that the partitions will be impure (e.g., where a partition may contain a collection of tuples from different classes rather than from a single class).

How much more information would we still need (after the partitioning) to arrive at an exact classification? This amount is measured by

$$ Info_A(D) =  \sum\limits_{j=1}^v \frac {|D_j|}{|D|} \times Info(D_j) $$ 

The term $\frac {|D_j|}{|D|}$  acts as the weight of the *jth* partition. $Info_A(D)$ is the expected information required to classify a tuple from D based on the partitioning by A. The smaller the expected information (still) required, the greater the purity of the partitions.

Infomation gain is defined as the difference between the original information requirement (i.e based on just the proportiion of classes ) and the new requirement ( i.e obtained after partitioning on A). That is, 

$$ Gain(A) = Info(D) - Info_A (D)$$

In other word, $Gain(A)$ tells us how much would be gained by branching on `A`. it is the expected reduction in the information requirement caused by knowing the value of `A`. The attribute `A` with the highest information gain, $Gain(A)$ is chosen as the splitting attribute at node `N`. This is equivalent to saying that we want to partition on the attribute `A` that wold do the "best classification", so that the amount of information still required to finish classifying the tuples is mininal (i.e minimal $Info_A(D)$ ) 

### Gain Ratio

Extension to information gain which aims to overcome the bias that information gain measure is biased towards tests with many outcomes. 

### Gini Index
Used in CART. It measures the impurity of A, a data partition or set of training tuples, as 

$$ Gini(D) = 1 - \sum\limits_{i=1}^m p_i^2 $$

where $p_i$ is the probability that a tuple in D belongs to a class $C_i$ and is estimated by $|C_i,_D|/|D|$. The sum is computed over m classes.



