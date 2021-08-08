The ==EventBus== is a singleton object that is shared by other classes to trigger and handle events. To use the event bus, we need to get the reference to it. By 

##### Injection

Property injection is more proper that a construtor injection when injecting the event bus.

NullEventBus implements the [[Null Object Pattern]] When you call its methods, it does nothing at all.
##### Getting the default instance

If injection is not possible, can use `EventBus.Default` ( not recommended as it makes unit testing difficult. )


## Defining Events

An event is represented by a class that is derived from **EventData**. Assume that we want to trigger an event when a task is completed:

```
public class TaskCompletedEventData : EventData
{
    public int TaskId { get; set; }
}
```

