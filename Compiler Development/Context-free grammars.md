Like [[Regular Expressions]], **context-free grammars** describes sets of strings, for examples, languages. Additionally, a context-free grammar also defines structure on the strings in the language it defines. A language is defined over some alphabettt, for example the set of tokens produdced by a lexer or the set of aplhanumeric characters. The symbols in the alphabet are called **terminals**.

A context-free grammars recursively defines several sets of strings. Each set is denoted by a name, which is called a **nonterminal**. The set of nonterminals is disjoint from the set of terminals. One of the nonterminals are chosen to denote the language described by the grammar. This is called the start symbol of the grammar. The sets are described by a number of **productions**. Each production describes some of the possible strings that are contained in the set denoted by a nonterminal. 
A production has the form

> N -> X<sub>1</sub> ... X<sub>n</sub>

where
- N is a nonterminal
- X<sub>1</sub> ... X<sub>n</sub> are zero or more symbols, each of which is either a terminal or a nontermianal.

The intended meaning of this notation is to say that the set denoted by N contains strings that are obtained b concatenating strings from the sets denoted by X<sub>1</sub> ... X<sub>n</sub>. In this setting, a terminal denotes a singleton set, just like alphabet characters in regular expressions. 

We can define grammer equivalent to the regular expression a* by the two productions
>B ->
>B -> aB

where the first production indicates that the empty string is part of the set B.

