ABP framework provides an infrastructure to make DDD based development easier to implement.

### Domain Driven Design
An approach to software development for complex needs by connecting the implementation to an evolving model. The premise of DDD is the following:

-	Placing the project's primary focus on the core domain and domain logic.
-	Basing complex designs on a model of the domain
-	Initiating a creative collaboration between technical and domain experts to iteratively refine a conceptual model that addresses particular domain problems.

![[DDD layer.png]]

### Layers

Four fundamental layers:

1. **Presentation Layer** : Provides an interface to the user.
2. **Application Layer** :  Mediates between the `Presentation Layer` and `Domain Layer`. Orchestrates business objects to perform application tasks.
3. **Domain Layer** : Includes business objects and the core(domain) business rules. Heart of the application.
4. **Infrastructure Layer** : Provides generic technical capabilities that support higher layers mostly using 3rd-party libraries.

#### Domain Layer

[[Entities]]
[[Domain Services]]

#### Application Layer

[[Application Services]]