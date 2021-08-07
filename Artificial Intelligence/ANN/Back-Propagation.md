
When we use a feedforward neural network to accept an input $z$ and produce an output $\hat{y}$, information flows forward through the network. The input $x$ provide the initial information that then propagates up to the hidden units at each layer and finnally produces $\hat{y}$. This is called **forward propagation**. 
During tranining, forward propagation can continue onward until it produces a scalar cost $J(\theta)$.

The **back-propagation** algorithm, often simply called *backprop*, allows the information from the cost to then flow backwards through the network, in order to compute the gradient.

> The algorithm is used to effectively train a neural network through a method called chain rule. In simple terms,  after each forward pass through the network, backpropagatin performs a backward pass while adjusting the model's parameters. [[Weights and Bias]]

Computing an analytical expression for the gradient is straight-forward, but numerically evaluating such an expression can be computationally expensive. The *back-propagation* algorithm does so using a simple and inexpensive procedure.

The term back-propagation is often misunderstood as meaning the whole learning algorithm for multi-layer neural networks. Actually, back-proagation refers only to the method for computing the gradient, while another algorithm, such as [[Stochastic Gradient Descent]], is used to perform learning using this gradient. 

Furthermore, back-propagation is often misunderstood as being speciic to multi-layer neural networks, but in principle in can compute derivatices of any function ( for some functions, the correct response is to report that the derivatice of the function is undefined. )

## General Back-Propagation

The back-propagation algorithm is very simple. To compute the gradient of some scalar $z$ with respect to one of its ancestors $x$ in the graph, we begin by observing that the gradient with respect to $z$ is given by $\frac{dz}{az} =1$. We can then compute the gradient with respect to each parent of $z$ in the graph by multiplying the current gradient by the Jacobian of the operation that produced $z$. We continue multiplying by Jacobians travelling backwards through the graph in this way until we reach $x$. For any node that may reached by going backwards for $z$ through two or more paths, we simply sum the gradients arriving from different path at the node.
	
More 


## Convergence and Local Minima
Back-propagation implements a gradient descent search through the space of possible network [weights](Weights.md), iteratively reducing the error $E$ betweeen training example target values and the network outputs.

Because the error surface for multilayer networks may contain many different [local minima](Local_Minima.md), gradient descent can become trapped in any of these. As a result, Back-propagation over multilayer networks in only guaranted to converge toward some local minimum in $E$ and not neccessarily to the global minimum error.

Despite the lack of assured convergence to the global minimum error, back-propagation is a highly effective function approximation method in practice. In many practical applications the problem of local minima has not been found found to be as severe as one might fear. To develop some intuition here, consider that networks with large numbers of weights correspond to error surface in very high dimensional spaces (one dimension per weight). When gradient descent falls into a local minium with respect to one of these weights. In fact, more weights in the network, the more dimension that might provide "escape routes" for gradient descent to fall away from the local minimum with respect to this single weight.