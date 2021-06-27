# Propositional Logic

Deals with the statement of alleged facts which must be either true or false, but not both.

---

Symbol | Name | Description
-|:-:|:-:|
$\neg$  | negation | not
$\land$  | conjunction | and
$\lor$  | disjunction | or
$\implies$  | implication | implies
$\iff$ | equivalence |  if and only if 
(arranged in descending order of operator precedence)

---
## Conjunction

Conjunction is commutative.

p $\land$ q **is the same** with q $\land$ p

---

## Disjunction

Disjunction is commutative

p $\lor$ q **is the same** with q $\lor$ p

---
## Implicationn

The implication p $\implies$ q may be viewed as expression an ordering the antecedent `p` and the consequent `q`: it state that the antecedet is stronger than ( or equal to ) the consequent. False is stronger than true; true is weaker than false; anythng is as strong as itself. This gives the truth table


p | q | p $\implies$ q
-|:-:|:-:|
t  | t | t
t  | f | f
f  | f | t
f  | f | t

Thus, the implication is true unless the antecedent is true and the consequent is false.

---
##  Equivalence

The equivalence p $\iff$ q means that `p` and `q`are of the same strength; thus it might also be called bi-implication.  p $\iff$ q means that both p $\implies$ q and q $\implies$ p. Since p and q have the same strength, they must therefore have the same entries in the truth table.

p | q | p $\iff$ q
-|:-:|:-:|
t  | t | t
t  | f | f
f  | f | f
f  | f | t

# Tautologies and contradictions

Propositions which evaluate to `t` in every combination of their propositional variales are known as `tautologies`: they are always true. If, on the other hand, they evalaute to `f` in every combination, then they are known as contradictions. Of course, the negation of a contradiction is a tautology, and vice versa.

## Tautologies

p $\lor$   $\neg$q 
p $\implies$ p
p $\implies$ ( q $\implies$ p )

## Contradictions
p $\land$ $\neg$p
p $\iff$ $\neg$ p
$\neg$ ( p $\implies$ ( q $\implies$ p ) )