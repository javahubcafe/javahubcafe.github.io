## 3.1	What is the difference between processes and threads ?

A process is an execution of a program, while a Thread is a single execution sequence within a process. A process can contain multiple threads. A Thread is sometimes called a lightweight process.

## 3.2	Explain different ways of creating a thread. Which one would you prefer and why ?
There are three ways that can be used in order for a Thread to be created:

•	A class may extend the Thread class.<br>
•	A class may implement the Runnable interface.<br>
•	An application can use the Executor framework, in order to create a thread pool.<br>

The Runnable interface is preferred, as it does not require an object to inherit the Thread class. In case your application design requires multiple inheritance, only interfaces can help you. Also, the thread pool is very efficient and can be implemented and used very easily.

## 3.3	Explain the available thread states in a high-level.

During its execution, a thread can reside in one of the following states:

•	Runnable: A thread becomes ready to run, but does not necessarily start running immediately.<br>
•	Running: The processor is actively executing the thread code.<br>
•	Waiting: A thread is in a blocked state waiting for some external processing to finish.<br>
•	Sleeping: The thread is forced to sleep.<br>
•	Blocked on I/O: Waiting for an I/O operation to complete.<br>
•	Blocked on Synchronization: Waiting to acquire a lock.<br>
•	Dead: The thread has finished its execution.<br>
 


## 3.4	What is the difference between a synchronized method and a synchronized block ?
In Java programming, each object has a lock. A thread can acquire the lock for an object by using the synchronized keyword. The synchronized keyword can be applied in a method level (coarse grained lock) or block level of code (fine grained lock).

## 3.5	How does thread synchronization occurs inside a monitor ? What levels of synchronization can you apply ?
The JVM uses locks in conjunction with monitors. A monitor is basically a guardian that watches over a sequence of synchronized code and ensuring that only one thread at a time executes a synchronized piece of code. Each monitor is associated with an object reference. The thread is not allowed to execute the code until it obtains the lock.

## 3.6	What’s a deadlock ?

A condition that occurs when two processes are waiting for each other to complete, before proceeding. The result is that both processes wait endlessly.

## 3.7	How do you ensure that N threads can access N resources without deadlock ?

A very simple way to avoid deadlock while using N threads is to impose an ordering on the locks and force each thread to follow that ordering. Thus, if all threads lock and unlock the mutexes in the same order, no deadlocks can arise.