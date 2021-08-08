# Entities
One of the core concepts of [[Domain Driven Design]].

A entity is generally mapped to a table in a relational database.


```

public class Student: Entity<Guid>
{
	public string Name { get; protected set; }
	
	public string Address { get: protected set; }
}

```

Entity\<TKey>
- A class that just defines an `Id` property with the given primary key type.

IEntity\<Key>

---
 
If your entity's Id type is `Guid`, there are some good practices to implement:

-   Create a constructor that gets the Id as a parameter and passes to the base class.
    -   If you don't set a GUID Id, **ABP Framework sets it on save**, but it is good to have a valid Id on the entity even before saving it to the database.
    

-   If you create an entity with a constructor that takes parameters, also create a `private` or `protected` empty constructor. This is used while your database provider reads your entity from the database (on deserialization).


-   Don't use the `Guid.NewGuid()` to set the Id 
	- **Use the `IGuidGenerator` service** while passing the Id from the code that creates the entity. `IGuidGenerator` optimized to generate sequential GUIDs, which is critical for clustered indexes in the relational databases.
