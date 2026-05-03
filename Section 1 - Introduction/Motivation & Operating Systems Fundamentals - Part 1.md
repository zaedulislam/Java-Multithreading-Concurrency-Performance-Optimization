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

![](https://github.com/zaedulislam/Java-Multithreading-Concurrency-Performance-Optimization/blob/main/images/image_1.png)
