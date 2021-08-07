# Bayes Classification Methods

#### Bayesian Classifiers
Statistical classifiers. They predict class membership probabilities such as the probability that a given tuple belongs to a particular class.

Naive Bayesian classifiers assume that the effect of an attribute value on a given class is independent of the values of the other attributes. ( class-conditional independence) Thus the name "naive."

### Bayes' Theorem

Let `X` be a data tuple. In Bayesian term, `X` is considers "evidence". Let `H` be some hypothesis such as that  the data tuple `X` belongs to a specified class `C`. For classification problems, we want determine $P(H|X)$, the probability that the hypothesis $H$ holds given the "evidence" or observed data tuple $X$. In other words, we are looking for the probability that tuple $X$ belongs to class $C$, given that we know the attribute description of $X$.

$P(H|X)$ is the posterior probability, or a posteriori probability, of $H$ conditioned on $X$. 

In contrast, $P(H)$ is the prior probabilty or a priori probability, of $H$.

$P(X|H)$ is the posterior prababilty, of $X$ conditioned on $H$.

$P(X)$ s the prior probability of $X$.

Bayes' theorem is useful in that it provides a way of calculationg the posterior probability, $P(H|X)$ from $P(H)$, $P(X|H)$ and $P(X)$


$$ P(H|X) = \frac{ P(X|H) P(H)}{P(X)}$$


## Naive Bayesian Classification

