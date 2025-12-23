## Threads Creation - Part 1, Thread Capabilities & Debugging

````java
Thread thread = new Thread();
````

````java

/*
The thread object itself is empty by default, so we need to pass it an object of a class that implements the runnable interface
into its constructor. Whatever code we write inside this run method is going to be run on that new thread as soon as it's scheduled
by the operating system.
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

````java
public class Main
{
  public static void main( String[] args )
    throws InterruptedException
  {
    Thread thread = new Thread( new Runnable()
    {
      @Override
      public void run()
      {
        // Code that will run in a new thread
        System.out.println("Hello from new thread " + Thread.currentThread().getName());
      }
    } );

    // Print which thread we're currently executing from.
    System.out.println("We are in thread: " + Thread.currentThread().getName() + " before starting a new thread");


    /*
    To actually start the thread by calling the start method on the thread object. 
    This will instruct the JVM to create a new thread and pass it to the operating system.
    */
    thread.start();

    // Print which thread we're currently executing from.
    System.out.println("We are in thread: " + Thread.currentThread().getName() + " after starting a new thread");


    /*
    The thread class also has a static method called sleep(), which puts the current thread to sleep for a given number
    of milliseconds. It's important to point out that this does not spin in a loop or anything like that. Instead,
    the thread sleep method instructs the operating system to not schedule the current thread until that time passes.
    During that time, this thread is not consuming any CPU.
    */

    Thread.sleep(10000);
  }
}


````

<p>
  <em>Output:<br>
  We are in thread: main before starting a new thread<br>
  We are in thread: main after starting a new thread<br>
  Hello from new thread Thread-0</em>
</p>

<p>
  Notice that after we call the thread start method, the new thread hasn't been scheduled yet, as that takes some time, and it happens asynchronously by the OS.
  So the second line we see is also from the main thread. And finally, the code from the new thread is executed, and its name is <strong>Thread-0</strong>.
</p>
