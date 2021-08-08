In a formal specification, it is oftern necessary to describe relationships between objects.

## Binary relations
Relations that express linkes between pair of objects. In our mathematical language, a relation is a set of ordered pairs, a subset of a Cartesian product.

If `X` and `Y` are sets, then `X` <-> `Y` denotes the set of all relations between `X` and `Y`. The relation symbol may be deined by generic abbreviation:


$$X\longleftrightarrow Y ==  \mathbb{P} (X \times Y)$$

Any elements of $X\longleftrightarrow Y$ is a set of ordered pairs in which the first element is drawn form `X`, and the second from `Y`: that is, a subset of the Cartesian product set $X \times Y$.

## Domain and Range

A relation may contain a great deal of information; often, we require only a small part. To extract the information we need, a number of basic functions are included in our mathematical language. The simplest examples are the `domain` and `range` functions.

If `R` is relation of type $X\longleftrightarrow Y$, then the domain of `R` is the set of elements in `X` related to something in `Y`:

$$ dom R = \{x: X; y: Y\ |\ x \mapsto y  \in R \bullet x \} $$

The range of `R` is the set of elements of `Y` to which some elements of `X` is related:

$$ ran R = \{x: X; y: Y\ |\ x \mapsto y  \in R \bullet y \} $$

//TODO


