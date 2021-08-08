# Await

Synchronous code blocks the thread executing it from doing any other work. It won't be interrupted while any of the task are in progress.

The `await` keyword provides a non-blocking way to start a task, then continue execution when that task completes.

```

static asyc Task Main(string[] args)
{

	Coffee cup = pourCoffee();
	Console.WriteLine("coffee is ready.");
	
	Egg eggs = await fryEggs(2);
	Console.WriteLine("eggs is ready.");
	
	Bacon bacon = await fryBacon(2);
	Console.WriteLine("bacon is ready.");
	
	Toast toast = await toastBread(2);
	applyButter(toast);
	applyJam(toast);
	
	Console.WriteLine("toast is ready.");
	
	Juice juice = pourJuice();
	Console.WriteLine("juice is ready");
	Console.WriteLine("breakfast is ready.");
	

}

// more ommmited code for the sake for simplicity
```

---
The total elapsed time is roughly the same as the initial synchronous version. The code has yet to take advantage of some of the key features of asynchronous programming.

---

Although the code does not block while the egges or the bacon are cooking. This code won't start any other tasks though.

However, for this scenario, we want more. We don't want each of the component tasks to be executed sequentially. It's better to start each of the component tasks before awaiting the previous task's completion.



# Concurrency

In many scenarios, we want to start several independent tasks immediately. Then, as each task finishes, we can continue other work that's ready.

`System.Threading.Tasks.Task`

We can start a task and hold on to the `Task` object that represents the work. Then `await` each task before working with its result.

```
Coffee cup = PourCoffee();
Console.WriteLine("coffee is ready");

Task<Egg> eggsTask = FryEggsAsync(2);
Task<Bacon> baconTask = FryBaconAsync(3);
Task<Toast> toastTask = ToastBreadAsync(2);

Toast toast = await toastTask;
ApplyButter(toast);
ApplyJam(toast);
Console.WriteLine("toast is ready");
Juice oj = PourOJ();
Console.WriteLine("oj is ready");

Egg eggs = await eggsTask;
Console.WriteLine("eggs are ready");
Bacon bacon = await baconTask;
Console.WriteLine("bacon is ready");

Console.WriteLine("Breakfast is ready!");

```

The asynchronously prepared breakfast would take less time to complete to a extent, it is because some tasks ran concurrently.

We start all the asynchronous tasks at once. We await each task only when we need the results. The preceding code may be similar to code in a web application that makes requests of different microservices, then combines the results into a single page. Make all the requests immediately, then `await` all those tasks and compose the web page.

# Await tasks effciently

The series of `await` statements at the end of the code can be improved by using methods of the `Task` class. One of those APIs is `WhenAll`, which return a `Task` that completes when all the tasks in its argument list have completed.

```
await.Task.WhenAll(eggsTask, baconTask, toastTask);

Console.WriteLine("eggs are ready");
Console.WriteLine("bacon is ready");
Console.WriteLine("toast is ready");
Console.WriteLine("Breakfast is ready!");
```

Another option is to use `WhenAny`, which returns a `Task<Task>` that completes when any of its arguments completes. You can await the returned task, knowing that it has already finished. 

The following code shows how you could use `WhenAny` to await the first task to finish and then process its result. After processing the result from the completed task, you remove that completed task from the list of tasks passed to `WhenAny`.
```

var breakfastTasks = new List<Task> { eggsTask, baconTask, toastTask };
while (breakfastTasks.Count > 0)
{
    Task finishedTask = await Task.WhenAny(breakfastTasks);
    if (finishedTask == eggsTask)
    {
        Console.WriteLine("eggs are ready");
    }
    else if (finishedTask == baconTask)
    {
        Console.WriteLine("bacon is ready");
    }
    else if (finishedTask == toastTask)
    {
        Console.WriteLine("toast is ready");
    }
    breakfastTasks.Remove(finishedTask);
}
```


# Final 

```
using System;
using System.Collections.Generic;
using System.Threading.Tasks;

namespace AsyncBreakfast
{
    class Program
    {
        static async Task Main(string[] args)
        {
            Coffee cup = PourCoffee();
            Console.WriteLine("coffee is ready");

            var eggsTask = FryEggsAsync(2);
            var baconTask = FryBaconAsync(3);
            var toastTask = MakeToastWithButterAndJamAsync(2);

            var breakfastTasks = new List<Task> { eggsTask, baconTask, toastTask };
            while (breakfastTasks.Count > 0)
            {
                Task finishedTask = await Task.WhenAny(breakfastTasks);
                if (finishedTask == eggsTask)
                {
                    Console.WriteLine("eggs are ready");
                }
                else if (finishedTask == baconTask)
                {
                    Console.WriteLine("bacon is ready");
                }
                else if (finishedTask == toastTask)
                {
                    Console.WriteLine("toast is ready");
                }
                breakfastTasks.Remove(finishedTask);
            }

            Juice oj = PourOJ();
            Console.WriteLine("oj is ready");
            Console.WriteLine("Breakfast is ready!");
        }

        static async Task<Toast> MakeToastWithButterAndJamAsync(int number)
        {
            var toast = await ToastBreadAsync(number);
            ApplyButter(toast);
            ApplyJam(toast);

            return toast;
        }

        private static Juice PourOJ()
        {
            Console.WriteLine("Pouring orange juice");
            return new Juice();
        }

        private static void ApplyJam(Toast toast) =>
            Console.WriteLine("Putting jam on the toast");

        private static void ApplyButter(Toast toast) =>
            Console.WriteLine("Putting butter on the toast");

        private static async Task<Toast> ToastBreadAsync(int slices)
        {
            for (int slice = 0; slice < slices; slice++)
            {
                Console.WriteLine("Putting a slice of bread in the toaster");
            }
            Console.WriteLine("Start toasting...");
            await Task.Delay(3000);
            Console.WriteLine("Remove toast from toaster");

            return new Toast();
        }

        private static async Task<Bacon> FryBaconAsync(int slices)
        {
            Console.WriteLine($"putting {slices} slices of bacon in the pan");
            Console.WriteLine("cooking first side of bacon...");
            await Task.Delay(3000);
            for (int slice = 0; slice < slices; slice++)
            {
                Console.WriteLine("flipping a slice of bacon");
            }
            Console.WriteLine("cooking the second side of bacon...");
            await Task.Delay(3000);
            Console.WriteLine("Put bacon on plate");

            return new Bacon();
        }

        private static async Task<Egg> FryEggsAsync(int howMany)
        {
            Console.WriteLine("Warming the egg pan...");
            await Task.Delay(3000);
            Console.WriteLine($"cracking {howMany} eggs");
            Console.WriteLine("cooking the eggs ...");
            await Task.Delay(3000);
            Console.WriteLine("Put eggs on plate");
            
            return new Egg();
        }

        private static Coffee PourCoffee()
        {
            Console.WriteLine("Pouring coffee");
            return new Coffee();
        }
    }
}
```

The final version of the asynchronously prepared breakfast took roughly 15 minutes (synchronous would take 30 minutes) because some tasks ran concurrently, and the code monitored multiple tasks at once and only took action when it was needed.