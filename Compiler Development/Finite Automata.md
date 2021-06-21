# Overview
A finite automaton is, in the abstract sense, a machine that has a finite number of states and a finite number of transitions between these. A transition between states is usually labelled by a character from the input alphabet, but we will also use transitions marked with ε, the so called *epsilon transtions*.

Finite automata (FA) are recognizers.

Finite automata come in two flavors:
- Non-deterministic finite automata (NFA) have no restrictions on the labels of their edges. A symbol can label several edges out of the same state, and ε, the empty string, is a possible label.
- Deterministic finite automata (DFA) have, for each state, and for each symbol of its input alphabet exactly one edge with that symbol leaving that state.

## Non-deterministic Finite Automata (NFA)

An *non-deterministic finite automaton* is represented, mathematically as a five-tuple
```
(Q, ∑, δ, q0, F)
```

- `Q` is **the set of states** in the automation, represented by circles in the diagram.
- ``∑`` is the **alphabet of characters that can legally occur in the input stream**. Typically, is the union of the edge lables in the diagram. We assume that ε, which stands for empty string, is never a member of ∑.
- `δ` is the **transition function**.
- q<sub>0</sub>  is the **starting state or initial state of the Finite Automata**.
- `F` is the set of states that are considered ==final or accepting states==. States in F are recognizable in the diagram becase they are drawn wih a **double circle**.

A finite automaton can be used to decide if an input string is a member on some particular set of strings. To do this, we select one of the states of the automaton as the *starting state*. We start in this state and in each step, we can do one of the following:

- Follow an epsilon transition to another state, or 
- Read a character from the input and follow a transition labelled by that charater.


## Deterministic Finite Automata
A deterministic finite automata (DFA) is a special case of an NFA where:
- There are no moves on input ε, and
- For each state `s` and input symbol `a`, there is exactly one edge out of `s` labelled `a`.

If we are using transition table to represent a DFA, then each entry is a single state.
	
While the NFA is an abstract representation of an algorithm to recognize the strings of a certain language, the DFA is a simple, concrete algorithm for recognizing strings. Every regular expression and every NFA can be converted to a DFA accepting the same language.

DFA is the one that we really implement or simulate when builidng lexical analyzers.

## Subset Construction of a DFA from a NFA
