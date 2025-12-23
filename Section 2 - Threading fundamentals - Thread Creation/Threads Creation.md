## Threads Creation - Part 1, Thread Capabilities & Debugging

````java
Thread thread = new Thread();
````

````java

/*
The thread object itself is empty by default, so we need to pass it an object of a class that implements the runnable interface into its constructor.
Whatever code we write inside this run method is going to be run on that new thread as soon as it's scheduled by the operating system.
*/

Thread thread = new Thread(new Runnable(){
  @Override
  public void run(){
    // Code that will run in a new thread
    System.out.println("Hello from new thread");
  }
});


// In Java eight and above, we can actually collapse this into a lambda, which makes the code more compact and readable.

Thread thread = new Thread(() -> {
  // Code that will run in a new thread
  System.out.println("Hello from new thread");
});


/*
To actually start the thread by calling the start method on the thread object. 
This will instruct the JVM to create a new thread and pass it to the operating system.
*/

thread.start();

````
