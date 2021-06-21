# IoC (Inversion of Control)

**IoC** is also known as **dependency Injection**(DI).

Dependency Injection

- a process whereby `objects` define their dependencies (that is ,the other `objects` they work with) only through **constructor arguments, arguments to a factory method, or properties that are set on the object instance** after it is constructed or returned from a factory method.

The container then injects those dependencies when it creates the bean. This process is fundamentally the inverse (*hence the name, Inversion of Control)* of the bean itself controlling the instantiation or location of its dependencies by using direct construction of classes or a mechanism such as the `Service Locator` pattern.

### Packages

#### `org.springframework.beans`

The `BeanFactory` interface provides an advanced configuration mechanism capable of managing any type of object.

#### `org.springframework.context`

`ApplicationContext` is a sub-interface of `BeanFactory`. It adds:

- Easier integration with Spring's AOP features
- Message resource handing ( for use in **i18n** )
- Event publication
- Application-layer specific context such as the `WebApplicationContext` for use in web applications.

In Spring, the objects that form the backbone of your application and that are managed by the Spring IoC container are called `beans`. A `bean` is an object that is instantiated, assembled, and managed by a Spring IoC container. Otherwise, a `bean` is simply one of many objects in your application. `Beans`, and the dependencies among them, are reflected in the configuration metadata used by a container.