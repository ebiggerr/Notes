For a parallel algorithm, there is a need to threads. Each threads would be focused on just that one task. Each thread would be blocked synchronously wating for another task to complete.

The total time taken for a synchronous code to complete, is the sum of each individual statement.

To reduce the time , we can write asynchronous code. When we write client programs, we would want the UI to be responsive to user input. Our application shouldn't make a phone appear frozen while it's downloading data from the web. When we write server programs, we don't want threads blocked. Those threads could be serving other requests. Using synchronous code when asynchronous alternatives exist hurts the ability to scale out less expensively. It is expensive have blocked threads.

[[Async and Await]]