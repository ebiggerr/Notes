# Formal Methods

Formal Specification in Software Development

- Translation of a non-mathematical description (diagrams, table, paragraph/test) into a formal specification language.

A ==formal specification consists of three components==:
- Syntax (grammatical rules to determing if sentences are well formed)
- Semantics (rules for interpreting the sentences in a precise, meaningful way within the domain)
- Proof Theory (rules for inferring useful information from the specification)

#### Purpose of Formal Specification
- To state what system should do without describing how to do it
- To reduce ambiguity (reduce faults)

#### Specification Techniques
- Algebrainc specification
	- The system is specified in terms of its operations and their relationships.

- Model-based specification
	- System is specified in terms of a state model that is constructed using mathematical constructs such as sets and sequences. Operations are defined by modifications to the system's state.


#### Formal Specification Languages

  |  | Sequential | Concurrent
|-|:-:|:-:|
|Algebraic | Larch and OBJ | Lotos |
|Model-based| Z, VDM, and B | CSP and Petri Nets |

[[Z language]]

