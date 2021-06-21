# Modus Ponens, Modus Tollens
#ArtiificialIntelligence

[[Modus Ponens, Modus Tollens#Modus Ponens]]
[[Modus Ponens, Modus Tollens#Modus Tollens]]
[[Modus Ponens, Modus Tollens#Universal forms of Modus Ponens and Modus Tollens]]

[[#Modus Ponens]] and [[#Modus Tollens]] in propositional logic, two types of inference that can be drawn from a hypothetical proposition- `i.e.`,from a proposition of the form "If A, then B" (symbolically A ⊃ B, in which ⊃ signifies "If...then...").

- Modus Ponens refers to the inference of the form A ⊃ B;A, therefore B.
- Modus Tollens refers to the inferences of the form A ⊃ B;~B, therefore ~A (~signifies"not"/negation)

# Modus Ponens
Consider the following argument:

- "If you have a current password, then you can log on to the network"

- "You have the current password"

Therefore:

- "You can log on to the network"  

==This has the form of:==

p→q (p implies q)
p
∴ q

This form of argument is calls **Modus Ponens** ( latin for "mode that affirms" )

> ∴ Note that an argument can be valid, even if one of the premises is false.

---

Consider this argument:

- "You can't log into the network"

- "If you have the current password, then you can log into the network"

Therefore:

- "You don't have the current password"

Now, in real life, we might say: that is not a valid argument. For example, maybe you can't log into the network because of 

	- your Ethernet cable is broken
	- the network is down
	- and any one of a zillion other reasons

But in fact, this is a **valid argument in logic.** If we accept the two premises, then the conclusion follows. One of the premises is "If you have current password, you can log into the network. There is no if*s, ands, or* *buts*.

> When working with logic problems it is important to take the statements literally and at face value.
# Modus Tollens
- "If you have a current password, then you can log on to the network"

According to this statement, a current password is sufficient for you to be able to log in.

So if we assume this to be true, as we do in the argument below, and we assume that you can't log into the network, then we can definitely conclude: you don't have the current password. So here it is  again:

- "You can't log into the network"

- "If you have a current password, then you can log into the network"

Therefore:
- "You don' have the current password"

==This is an argument of the for:==

-q
p→q 
∴-p

This form of argument is calls **Modus Tollens** ( latin for "mode that denies" )

---

# Universal forms of Modus Ponens and Modus Tollens

Both **modus ponens** and **modus tollens**  have "universal forms"

- Universal modus ponens:

    ∀x((P(x)→Q(x))

    P(a), where a ∈ {domain of the predicate P}

    ∴Q(a)

    > E.g. All fish have scales. This salmon is a fish. Therefore, this salmon has scales.


- Universal modus tollens:

    ∀x((P(x)→Q(x))

    ¬Q(a), where a ∈ {domain of the predicate P}

    ∴¬P(a)

    > E.g. All surfers are hot. Conrad is not hot. Therefore Conrad is not a surfer.