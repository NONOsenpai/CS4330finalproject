
## C++
* reference：
  A reference variable is an alias, that is, another name for an already existing variable. Once a reference is initialized     with a variable, either the variable name or the reference name may be used to refer to the variable.
* value：
  C++ is a strongly-typed language, and requires every variable to be declared with its type before its first use. This informs the compiler the size to reserve in memory for the variable and how to interpret its value. The syntax to declare a new variable in C++ is straightforward: we simply write the type followed by the variable name (i.e., its identifier).


## JAVA
* reference：
  There are 4 types of references in JAVA:
  – Strong References
  – Soft References
  – Weak References
  – Phantom References

  Those references differ only by the way the garbage collector manages them. If you’ve never heard of them, it means that you  were only using the strong ones. Knowing the difference can help you, especially if you need to store temporary objects and can’t use a real caching library like eHcache or Guava.

* value：
  Our mantra is “codes like a class, works like an int.” Of course, the devil is in the details; there are going to be features of classes that do not make sense for value types. Some questions we might want to ask about value classes are as follows, with tentative answers where appropriate. Where a comparison with primitives would make sense, the answers for these questions for values are the same as they would be for primitives.

## Compared:
In C++ I can do something like this...

String s = "abc";
char c = s[i]; // works fine...
But in Java, if I try doing the same, it throws an error. Why?.

In java, to achieve the above, I have to do :

s.toCharArray(); 
