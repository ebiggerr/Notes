The k-means clustering algorithm divides the training data set into `k` different clusters of examples that are near each other. 
	
We can thus think of the algorithms as providing a $k$-dimensional one-hot code vector $h$ representing an input $x$. If $x$ belongs to cluster $i$ then $h_i=1$ and all other entreis of the representation $h$ are zero.
The one-hot code provided by k-means clustering is an example of a sparse representation, because the majority of its entries are zero for every input. 

