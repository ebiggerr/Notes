Domain services aka Services in [[Domain Driven Design]]. It is used to perform domain operations and business rules.

In contrast with [[Application Services]] which interact with [[Data Transfer Objects]], a ==Domain Service== interacts with domain objects (like [[Entities]] and value types).

ABP defines the `IDomainService` interface that is implemented by all domain serviecs conventionally. 
When it is implemented, the domain service is automatically register to the [[Dependency Injection]] system as ==transient==.

---

[Read More](https://aspnetboilerplate.com/Pages/Documents/Domain-Services#how-do-we-force-to-use-of-the-domain-service-)