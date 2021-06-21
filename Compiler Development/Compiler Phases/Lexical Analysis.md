# Overview
The first phase of a compiler is called *lexical analysis* or *scanning*. The lexical analyzer reads the stream of characters making up the source program and groups the characters into meaningful sequences called ==lexemes==. For each lexeme, the lexical analyzer produces as output a ==token== of the form.

> (token name, attribute value)

that is passes on to the subsequent phase, [[Syntax Analysis]]. [[#Continue]]

Since the lexical analyzer is the part of the compiler that reads the source text, it may perform certain other tasks besides ==identification of lexemes==

Other tasks:
-	 Stripping out ==comments== and ==whitespace== ( blank, newline, takb and perhaps other character that are used to separete tokens in the input)
-	 Correlating error messages generated by the compiler with the source program. ( For instance, the lexical analyzer may keep track of the number of newline character seen, so it can associate a line number with each error message. In some compilers, the lexical analyzer makes a copy of the source program with the error message inserted at the appropriate positions )

Sometimes, lexical analyzer are divided into a cascade of two processe.
- Scanning 
	- Simple processes that do not require tokenization ( deletion of comments, compaction of consecutive whitespace characters into one )
- Lexical analysis [[#Continue]]

---

## Continue..



In the token, the first component `token-name` is an abstract  symbol that is used during syntax analysis, and the second component `attribute-value` points to an entry in the symbol table for this token. Information from the symbol table entry is needed for [[Type Checking_Semantic Analysis]] and [[Machine Code Generation]].

### Operation 

``` 
position = initial + rate * 60

```

1. `position` is a lexeme that would be mapped into  a token (id,1) where `id` is an abstract symbol standing for `identifier` and 1 points to the symbol-table entry for that position. The symbol-tree entry for an identifier holds information about the identifier, such as its name and type.

2. The assignment symbol `=` is a lexeme that is mapped into the token(=). Since this token needs no attribute-value, we have omitted the second component. We could have used any abstract symbol such as `assign` for the token-name, but for notation convenience we have chosen to use the lexeme itself as the name of the abstract symbol.
3. `initial` is a lexeme that is mapped into the token (id,2) where 2 points to the symbol-table entry for `initial`.
4. `+` is a lexeme that is mapped into the token (+)
5. `rate` is a lexeme that is mapped into the token (id,3) where 3 points to the symbol-table entry for `rate`.
6. `*` is a lexeme that is mapped into the token (*).
7. `60` is a lexeme that is mapped into the token (60).

### Output

```
(id,1) <=) (id,2) (+) (id,3) (*) (60)
```


In this representation, the token name =,+ and * are abstract symbols for the assignment, addition and multiplication operators, respectively.

> Technically speaking, for the lexeme `60` we should make up a token like (number,4) where 4 points to the symbol tale for the internal representation of integer 60 but we hall defer the discussion of token for number in [[Chapter 2]] [^1]


## Lexical Analysis Versus [[Syntax Analysis]]
Why the analysis portion of a compiler is normally separated into 
- Lexical Analysis
- Syntax Analysis

1. Simplicity of design is the most importance consideration.
	- The separation of these two often allows us to simplify at least one of these tasks. For example, ==a parser==(syntactic analyzer ) that had to deal with comments and whitespace as syntactic units would be considerably more complex than one that can assume comments and whitespace have already been removed by the lexical analyzer.

2. Compiler efficiency is improved. A separate lexical analyzer allows us to apply specialized techniques that serve the lexical task, not the job of parsing. In addtion, specialized buffering techniques for reading input character can speed up the compiler significantly.

## Tokens, Patterns and Lexemes

`Token` is a pair of consisting of a token name and an optional attribute value.  [[#Continue]]]
The token names are the input symbols that the parses ( Syntax Analyzer ) processes.

`Pattern` is a description of the form that the lexemes of a token may take. In the case of a keyword as a token, the pattern is just the sequence of character that forms the keyword. For `identifiers` and some other tokens, the pattern is more complex structure that is matched by many strings.

`Lexeme` is a sequence of characters in the source program that matches the pattern for a token and is identified by the lexical analyzer as an instance of that token.


## Attributes for Tokens
When more than one lexeme can match a pattern, the lexical analyzer must provide the subsequent phase additional information about the particular lexeme that matched.

For example, the pattern for token `number` matches both 0 and 1, but it is extremely important for the code generator to know which lexeme was found in the source program. ==Thus, in many cases the lexical analyzer returns to the parser not only a token name, but an attribute value that describe the lexeme represented by the token; the token name influences parsing decisions while the attribute value influences translaion of tokens after the parse.==

# Operation on Languages
On lexical analysis, the most important operations on languages are union, concatenation and closure.

| OPERATION | DEFINITION AND NOTATION |
|:-------:| --------|
|Union of L and M| L ∪  M ={s \| s is in L or s is in M }|
|Concatenation of L and M | LM={ st\| s is in L and t is in M}|
|Kleene closure of L | ![[Kleene Closure of L.png]] |
|Positive closure of L|![[Positive closure of L.png]]|

> The Kleene closure of a language L , denoted L* is the set of strings you get by concatenating L zero or more times.

>The positive closure, denoted $$L^+$$ is the same as the Kleene closure, but without the term $$L^0$$. That is empty string will not be in $$L^+$$ unless it is in L itself.

# [[Regular Expressions]]




[^1]:Dragon Book, Compiler: Priniciples, Techniques and Tools 2nd Edition