# The .Net

### Key Benefits of the .Net Platform
- Suppport for numerous programming languages
	.Net application can be created using any number of programming languages ( C#, Visual Basic, F#, etc)
	
- .Net support cross-language inheritance, cross-language exception handling, and cross-language debugging of code. ( For example, a class can be defined in C# and extended the type in Visual Basic )

 ### Building block of the .Net platform ( CLR, CTS and CLS )

We can understand that .NET as a runtime environment and a comprehensice base class library. The runtime layer is properly referred to as the `Common Language Runtime, or the CLR`.
Then we have the `Common Type System, or the CTS`.

```
Common Language Runtime - Have the primary role of locate, load and manage .NET objects on the behalf of programmers. It also takes care of a number of low-level such as memory management , application hosting , coordinating threads, and performing security checks (among other low-level details)

Common Type System - It fully describes all possible data types and all programming constructs supported by the runtime,specifies how these entiies can interact with each other, and details how they are represented in the .NET metadata format. 

```

Next, we have the `Common Language Specification, or the CLS`, it is the related specification that defines a subset of common tyes and programming constructs that all .NET programming languages can agree on. 
