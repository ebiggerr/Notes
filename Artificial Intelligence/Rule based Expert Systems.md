The human mental process is internal, and it is too complex to be represented by an algorithm. However, most experts are capable of expressing their knowledge in the form of rules for problem solving.

The basic syntax of a rule is:
```
IF		<antecedent>
THEN	<consequent>
```

In general, a rule can have multiple antecedents joined by the keywords `AND` (conjunction), `OR` (disconjunction) or a combination of both.

Rules can represent 

- Relations
```
IF				the 'fuel tank' is empth
THEN			the car is dead
```

- Recommendation
```
IF				the seson is autumn
AND				the sky is cloudy
AND				the forecase is drizzle 
THEN			the advice is 'take an umbrella'
```

- Directive
```
IF 				the car is dead
AND				the 'fuel tank' is empty
THEN			the aaction is 'refuel the car'
```

- Strategy
```
IF				the card is dead
THEN			the action is 'check the fuel tank';
				step1 is complete

IF				step1 is complete
AND				the 'fuel tank' is full
THEN			the action is 'check the battery';
				step2 is complete
```

- Heuristic
```
IF 				the spill is liquid
AND				the 'spill pH' < 6
AND				the 'spill smell' is vinegar
THEN			the 'spill material' is 'acetic acid'
```

# Structure of a Rule-based Expert System

(Newell and Simon, 1972) model

Five components
- Knowledge base
- The Database
- Inference Engine
- Explaination Facilties 
- User Interface



