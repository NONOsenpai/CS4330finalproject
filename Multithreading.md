
## Java

* Every Java thread has a priority that helps the operating system determine the order in which threads are scheduled.
* Java thread priorities are in the range between MIN_PRIORITY (a constant of 1) and MAX_PRIORITY (a constant of 10). By default, every thread is given priority NORM_PRIORITY (a constant of 5).
* Threads with higher priority are more important to a program and should be allocated processor time before lower-priority threads. However, thread priorities cannot guarantee the order in which threads execute and are very much platform dependent.
* How to accomplish multitasking?
* Create a Thread by Implementing a Runnable Interface.
```java
// File Name : DisplayMessage.java
// Create a thread to implement Runnable

public class DisplayMessage implements Runnable {
   private String message;
   
   public DisplayMessage(String message) {
      this.message = message;
   }
   
   public void run() {
      while(true) {
         System.out.println(message);
      }
   }
}
```

* Create a Thread by Extending a Thread Class.
```java
// File Name : GuessANumber.java
// Create a thread to extentd Thread

public class GuessANumber extends Thread {
   private int number;
   public GuessANumber(int number) {
      this.number = number;
   }
   
   public void run() {
      int counter = 0;
      int guess = 0;
      do {
         guess = (int) (Math.random() * 100 + 1);
         System.out.println(this.getName() + " guesses " + guess);
         counter++;
      } while(guess != number);
      System.out.println("** Correct!" + this.getName() + "in" + counter + "guesses.**");
   }
}
```

## C++
* C++ does not contain any built-in support for multithreaded applications. Instead, it relies entirely upon the operating system to provide this feature.


*  We can write multi-threaded C++ program using POSIX. POSIX Threads, or Pthreads provides API, which are available on many Unix-like POSIX systems such as FreeBSD, NetBSD, GNU/Linux, Mac OS X and Solaris.

* Creating a POSIX thread


``` C++
#include <pthread.h> pthread_create (thread, attr, start_routine, arg) 
```
* Terminating a POSIX thread
``` C++
#include <pthread.h> pthread_exit (status) 
```

* This simple example code creates 5 threads with the pthread_create() routine. Each thread prints a "Hello World!" message, and then terminates with a call to pthread_exit().
```C++
#include <iostream>
#include <cstdlib>
#include <pthread.h>

using namespace std;

#define NUM_THREADS     5

void *PrintHello(void *threadid) {
   long tid;
   tid = (long)threadid;
   cout << "Hello World! Thread ID, " << tid << endl;
   pthread_exit(NULL);
}

int main () {
   pthread_t threads[NUM_THREADS];
   int rc;
   int i;
	
   for( i=0; i < NUM_THREADS; i++ ){
      cout << "main() : creating thread, " << i << endl;
      rc = pthread_create(&threads[i], NULL, PrintHello, (void *)i);
		
      if (rc){
         cout << "Error:unable to create thread," << rc << endl;
         exit(-1);
      }
   }
	
   pthread_exit(NULL);
}
```
