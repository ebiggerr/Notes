A formal specification should contain a significant amount pf prose; this should relate the mathematical objects to features of the design: system states, data structures, properties and operations. 

In the Z notation, there are several ways of defining an object. We may simply `declare`, we may define by `abbreviation`, or we may define by `axiom`. In addition, there are special mechanisms for `free types` and `schemas`. 



## Axiomatic definitions

A third form of definition includes a constraints upon the object being introduced. Such definitions are said to be `axiomatic`, as the constraints is assumed to hold whenever the symbol is used: it is an axiom for the object.

In Z notation, an axiomatic definitions takes the form 

```
|declaration
|--------------
| predicate

```

where the predicate expressed the constraints upon the object or objects introduced in the declaration.

## Generic definitions
A generic form of axiomatic definitions may be used to define a family of global constants, parameterised by some set `X`. The definition

```
---[X]------------
| x: X
-----------------
|p
|
```