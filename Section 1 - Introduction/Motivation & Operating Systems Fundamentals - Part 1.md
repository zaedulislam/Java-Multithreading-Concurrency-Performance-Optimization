# Motivation & Operating Systems Fundamentals - Part 1
### Motivation & Intuition - Why do we need Threads?
Two main reasons:
1. Responsiveness
2. Performance

## 1. Responsiveness
### Examples of Poor Responsiveness
These are all examples of poor responsiveness, which we would like to avoid if we want our clients to like our product or our app:
- Waiting for hours on the line for customer service support
- Sending a message to somebody and not hearing back from them for multiple days
- Clicking on the purchase button in an app and not seeing any confirmation

### Responsiveness with a Single Thread
Suppose we have an online store web publication that serves thousands of users. The application stores all information about each user's purchases in a database. If one user makes a large purchase of multiple items, which results in a long operation in the database and in the same time, another user is desperate to complete his purchase. That second user will not get any response until the web app is done in responding to the first request.
![](https://github.com/zaedulislam/Java-Multithreading-Concurrency-Performance-Optimization/blob/main/images/image_1.1.png)

### 1. Responsiveness with Multithreading
With multithreading, we could actually serve multiple users simultaneously, but serving each request on a different thread.
![](https://github.com/zaedulislam/Java-Multithreading-Concurrency-Performance-Optimization/blob/main/images/image_1.2.png)

### 2. Responsiveness in User Interface
Responsiveness is particularly critical when it comes to applications with a user interface. A good example for this can be a movie player application. The application is showing us images, play the audio. And in the same time, we expect that if we move the mouse or click a button, we would get an instant feedback for our actions on the screen. This kind of responsiveness can be achieved by using multiple threads, each thread for a different task. And it's generally very hard to achieve otherwise.
![](https://github.com/zaedulislam/Java-Multithreading-Concurrency-Performance-Optimization/blob/main/images/image_1.3.png)

### Concurrency - Multitasking
By multitasking quickly between different threads, our computer can create an illusion that all those tasks are actually happening in the same time. The term we use for this kind of multitasking is **concurrency**. Note that, we don't even need multiple cores to achieve **concurrency**.
![](https://github.com/zaedulislam/Java-Multithreading-Concurrency-Performance-Optimization/blob/main/images/image_1.4.png)

## 2. Performance
The second reason we need multithreading is performance.
- As mentioned before, using concurrency, we can create an illusion of multiple tasks running in parallel just with single core with multiple threads. 
- we can truly run multiple tasks completely in parallel. 

![](https://github.com/zaedulislam/Java-Multithreading-Concurrency-Performance-Optimization/blob/main/images/image_1.5.png)

### 2. Performance - Impact
- The performance impact of multithreading is the ability to complete a complex task in a fraction of the time, it would take us to complete it otherwise. 
- We can finish much more work in the same period of time than with a single thread.
- And if we're running a high scale service on multiple machines, we will need less machines, which will also mean less expenses on infrastructure and more money in our pocket.

## Multithreading Caveat
Multithreaded programming is fundamentally different than the traditional single threaded sequential programming. And a lot of the intuition we have from single threaded application development will actually break when we introduce multiple threads.

## Introduction to OS
### What Threads are and Where They Live

![](https://github.com/zaedulislam/Java-Multithreading-Concurrency-Performance-Optimization/blob/main/images/image_1.6.png)

![](https://github.com/zaedulislam/Java-Multithreading-Concurrency-Performance-Optimization/blob/main/images/image_1.7.png)
