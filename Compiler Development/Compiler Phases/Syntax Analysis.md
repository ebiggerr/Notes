# Overview
Syntax analysis is the second phase of a compiler in which the given input string is checked for the confirmaion of rules and structures of the formal grammar. It analyses the syntactical structure and checks if the given input is in the correct syntax of the programming language or not.

---
By design. every programming language has precise rules that prescribe the syntactic structure of well-formed programs. 

In C, for example, a program is made up of functions, a function out of declarations and statements, a stateent out of expressions, and so on.

The syntax of programming language constructs can be speficified by **context-free grammars** or **BNF (Backus-Naur form)** notation.

---
## The Role of the Parser
When [[Lexical Analysis]] splits the input into tokens, the purpose of syntax analysis ( or *parsing*) is to ==recombine these tokens.== Not back into a list of characters, but ==into something that reflects the structure of the text== which typically is a data structure callled the **syntax tree** of the text. 

The leaves of this three are the tokens found by the lexical analysis, and if the leaves are read from left to right, the sequence of the same as in the input text. In addition to finding the structure of the input text, the syntax analysis must also ==reject invalid texts== by reporting **syntax errors**.

##### Parser Generation
A notation suitable for human understandings is transformed into a machine-like low level notation suitable or efficientt execution.

### [[Context-free grammars]]
The notation we use for human manipulation is *context-free grammars* which is a recursive notation for describing sets of strings and imposing a structure on each such string. This notation can in some cases be translated almost directly into recursive programs, but it is often more convenient to generate [[Stack Automata]]. 
> Similar to the [[Finite Automata]] used for lexical analysis but they ==can additionally use a stack, which allows counting and non-local matching of symbols==

> [[Pushdown Automata]]  is a type of automaton that employs a stack.

[[Stack Automata VS Pushdown Automata]]


---
