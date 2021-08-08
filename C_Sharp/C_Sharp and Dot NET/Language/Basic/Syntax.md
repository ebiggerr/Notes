## Identifiers and Keywords

By convention, parameter, local variables and private fields should be in camel case.
And all other identifiers should be in Pascal case. 

### Reserved keywords
When intending to use as identifier that clashed with a reserved keywords, do so by qualifying it with the @ prefix

```

Event @event // because 'event' is a reserved keyword

```

The @ symbol doesn's form part of the identifier itself. So `@myVariable` is the same as `myVariable`.

### Contextual keywords

```
//some examples

async
var 
await
```
With contextual keywords, ambiguity cannot arise within the context in which they are used.

