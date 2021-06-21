Every language expression, *r*, corresponds to an abstract machine that recognized *`L(r)`*. We call these recognizer *[[Finite Automata]]*.

For example, in a lexical analyzer for assembly code, we might find the regular expression

> r digit digit*

The recognizer for this regular expressions could be represented, pictorially, as


![[State diagram for a RE.png]]

The diagram incorporates all the information neccessary to understand the recognizer or to implement it.

Each circle represent a `state`; by convention, the recognizes starts in state s<sub>0</sub> 
Each arrow represents a `transition`; the label on the transition speficies the set of inputs that cause the recognizer to make that transitiion.

Thus, if the recognizer was in state s<sub>0</sub> when it encountered the input character *r*, it would make the transition to state s<sub>1</sub>. In state s<sub>2</sub>, any digit takes the recognizer back to s<sub>2</sub>. The state s<sub>2</sub> is designated as a final stated, drawn with the double circle.

Formally, this recognizer is an example of a *[[Finite Automata]]*

## Precedence Rules
When we combine different construtor symbols in the regular expression. For example,
> a|ab*

It is not a prioro clear how the different subexpressions are grouped. Thus, we use precedence rules

Conventions:
- \* binds tighter than concatenation which binds tighter than alternative ( | )

Hence 
> a|ab* is equivalent to a|(a(b\*))

The | operator is **associative** and **commutative** (as it is based on set union, which has these properties)
Concatenation is **associative** (but obviously not commutative) and distributes over | .



## Shorthands
The large number of different digits or alphabets make a regular expression rather verbose, therefore we will often use extra shorthands for convenience.

For example, we user \[ab01] as a shorthand for a|b|0|1. Additionally, we can use interval notation to abbreviate \[0123456789] to \[0-9]. We can combine several intervals within one bracket and for example write \[a-zA-Z] to denote all alphabetic letters in both lower and uppper case.

When using intervals, we must be aware of the ordering for the symbols involved. When using such notation in lexer generators, standard [ASCII] or [ISO 8859-1] characters sets are usually used, with the hereby implied ordering of symbols.