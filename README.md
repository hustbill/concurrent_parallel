
#ExecutorService
*ExecutorService* is an interface that extends Executor class and represents an asynchronous execution. It provides us mechanisms to manage the end and detect progress of the asynchronous tasks.

In this example we are going to see some basic functionalities of ExecutorService, as well as handle the Future object, the result of asynchronous computation.

## Create the Runnable  
We are going to create a Runnable that is intended to be executed by the ExecutorService. Create a java class named myThread and paste the following code.
  

The functionality of the Runnable is very simple. It computes a sum from the giving argument and it sleeps for a specified time.  

## Code the ExecutorService

In this example we will use a factor method of ExecutorService that creates a thread pool of fixed number of threads. For this reason, newFixedThreadPool() method is used where we specify the number of threads in the pool. To execute the thread, we can use either execute() method or submit(), where both of them take Runnable as a parameter. execute() method is depending on the implementation of the Executor class and may perform the Runnable in a new thread, in a pooled thread, or in the calling thread. submit() method extends execute(), by returning a Future that represents the submitting task.
The Future can be used to indicate the termination of execution of the thread. For instance, get() method waits for the completion of the computation. If the returning value is null, the task has finished correctly. Otherwise, cancel() method can be called in order to end the execution of this task. It is worth to mention that for bulk or a collection of thread execution, invokeAll() and invokeAny() are used respectively, although there are not used in this example.
To close down the ExecutorService, there are many methods that can be used. In our example we use shutdown() method, in which the submitted tasks are executed before the shutting down but new tasks can not be accepted. Another approach is shutdownNow() method, which stops the executing tasks, pause the waiting ones and returns the list of the awaiting ones. Moreover, awaitTermination() can be used in order to wait until all threads are terminated.


For further understanding of the main functionality of ExecutorService, have a look at the code below. Create ExecutorServiceTest.java file and paste the following.


ExecutorServiceTest.java:


