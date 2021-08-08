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
The building blocks of Domain Layer:

[[Entities]]
An entity is an object with its own properties(state, data) and methods that implements the business logic that is executed on these properties. 

==Value Object==
Another kind of domain object that is identified by its own properties rather than a unique identifier(ID). Two value objects with same properties are considered as the same object.

==Aggregate & Aggregate Root==
Cluster of objects ( entities and value objects) bound together by an Aggregate Root object. The `Aggregate Root` is a specific type of entity with some addtional responsibilites.

==Repository==*(Inteface)*
Collection-like interface that is used by the Domain and Application layers to access to the data persistence system (the database). It hides the complexity of the DBMS from the business code. Domain layer contains the interfaces of the repositories.

[[Domain Services]]
Stateless service that implements core business rules of the domain. It is useful to implement domain logic that depends on multiple aggregate(entity) type or some external services.

==Specification==
Used to define named, reusable, and combinable filters for entities and other business objects.

[[Domain Event]]
A way of informing other services in a loosly coupled manner, when a domain specific event occurs.



#### Application Layer

[[Application Services]]
Stateless service that implements use cases of the application. An application service typically gets and return DTOs. 

==DTO==
Simple object without any business logic that is used to transfer state(data) between the Application layer and Presentation layer.

==UOW==
Atomic work that should be done as a transaction unit. All the operations inside a UOW should be commited on succes or rolled back on a failure.

