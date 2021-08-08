# Function

Some relationship can be modelled by a special kind of relation. If each object of one one set is relaed to at most one object of another, then the relation between the two sets is said to be a `function`.

## Partial function
A partial function from `X` to `Y` is a relation that maps each element of `X` to at most one element of `Y`; we write $X⇸Y$ to denote the set of all such relations. 

### Example
An organisation has a system for keeping track of its employees while they are on the premises. Each employess is issued with an `active badge` which reports their current position to a central databsae. If the set of al people is `Person`, and the set of all locations is `Location`, then the information provided by the system may be described by a relation `where_is` of type $Person⇸Location$. It is impossible for an employee to be in two places at one, so this relation will be a partial function

$$where\_is \in Person⇸Location$$

These relations are called `partial functions` because there may be elements of `X` that are not related to any element of `Y`. If each elemen to `X` is related to some element of `Y`, then then function is said to be `total`; we write $X⇸Y$ to denote the set of all total functions from $X⇸Y$, where

$$X⇸Y == \{ f: X⇸Y | dom f = X \}$$

The domain of a total function must be the whole of the source set.

## Properties of functions
It is extremely helpful to categorise functions according to whether or not they are `total`, and whether or not they possess three key properties: injectivity, surjectivity, and bijectivity. 

![[properties_of_functions.png]]