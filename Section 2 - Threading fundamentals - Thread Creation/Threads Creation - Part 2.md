## Thread Creation with ````java.lang.Thread````

### Approach 1 - Thread Creation with ````java.lang.runnable````
<p>
  Create threads by instantiating a Thread class object and passing the Runnable into its constructor.
</p>

````java
public class Main
{
  public static void main( String[] args )
  {
    Thread thread = new Thread( new Runnable()
    {
      @Override
      public void run()
      {
        System.out.printf( "Hello from " + Thread.currentThread().getName() );
      }
    } );

    thread.start();
  }
}
````

<br>

### Approach 2 - Thread Creation with ````java.lang.Thread````

<p>
  Instead of creating a separate object for the thread and another object for the Runnable, we can directly create a new class that extends Thread.
  If we inspect the Thread class, we can see that it actually implements the Runnable interface itself.
</p>

````java
public class Main
{
  public static void main( String[] args )
  {
    Thread thread = new NewThread();

    thread.start();
  }

  private static class NewThread
    extends Thread
  {
    @Override
    public void run()
    {
      System.out.printf( "Hello from " + Thread.currentThread().getName() );
    }
  }
}
````

<br>
<p>
  By putting the logic inside a class that extends Thread, we get access to a lot of data and methods inside the run method that are directly 
  related to the current thread.
</p>

````java
public class Main
{
  public static void main( String[] args )
  {
    Thread thread = new NewThread();

    thread.start();
  }

  private static class NewThread
    extends Thread
  {
    @Override
    public void run()
    {
      this.setPriority( MIN_PRIORITY );
      System.out.printf( "Hello from " + this.getName() );
      System.out.println( " with priority " + this.getPriority() );
    }
  }
}
````



