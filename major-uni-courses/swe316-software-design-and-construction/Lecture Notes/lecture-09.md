# Lecture 9: Singleton Pattern

## Table of Contents

- [Lecture 9: Singleton Pattern](#lecture-9-singleton-pattern)
  - [Table of Contents](#table-of-contents)
  - [Main Motivation \& Lecture Example](#main-motivation--lecture-example)
  - [Intent of Singleton](#intent-of-singleton)
  - [Applicability](#applicability)
  - [Main Structure](#main-structure)
  - [Instantiation Forms](#instantiation-forms)
    - [Lazy Instantiation](#lazy-instantiation)
    - [Early or Eager Instantiation](#early-or-eager-instantiation)
    - [Lazy Instantiation Using the Double Locking Mechanism](#lazy-instantiation-using-the-double-locking-mechanism)
  - [Other Singleton Examples](#other-singleton-examples)
  - [Summary](#summary)

## Main Motivation & Lecture Example

Our main problem in this section is that we have a class that we want to instantiate ONLY once.

Assume you are designing a Database Connector Class. You want to force the users of this class to only instantiate it once.

To approach this problem, think about what is the thing that allows others to create an object of your class? Yes, it is the constructor. Whenever a user calls the `new` keyword, they create a new instance of that class. Also, recall that if it is NOT there, a default empty one is created.

So, the first idea that you might have is that you don't want to allow the user to use the `new` keyword. Simply, this is done by making the constructor `private` and creating our own method of calling. Note the initial example below.

```java
class X {
    // note the usage of private
    private X() {}

    // our OWN constructor
    public X getInstance() {
        
    }
}
```

At this point, we want a way to only initialize once. This can be done by a boolean where if already initialized return the object, else create a new object.
A very important thing also, since we are NOT allowing `new()`, users will refer to our `getInstance()` method using the class name, aka `static`. Note the enhancements below.

```java
class X {
    // introduce a boolean
    boolean isInitialized = false;

    private X() {}

    // it is a static method, since NO objects can be instantiated
    public static getInstance() {
        // If Not initialized, create new, else return our object
        if (isInitialized == false) {
            isInitialized = true;
            return new X(); // we control the usage of new
        }
    }
}
```

BUT, there a couple of problems:

1. We are using a nonstatic member `isInitialized` inside a static method `getInstance()`. So, the boolean must be static.
2. When we call the method for the second time, it will return null, which is wrong.

To solve the null problem, we want to create a new object and return it after initializing. Note the enhancements.

```java
class X {
    // All the members are made static, since they are used in a static method.
    // add an object variable. This is our object that is instantiated
    static X myX = null;
    static boolean isInitialized = false;
    
    private X() {}

    public static getInstance() {
        if (isInitialized == false) {
            isInitialized = true;
            myX = new X();
        }
        return myX; // returns OUR common object
    }
}
```

This is a working solution, BUT there is still room for improvement. Recall that you usually wear two hats: the designer and the developer.
The designer inside you must be screaming why am I using `isInitialized` when I can simply make our object `myX` as the checker. Note the elegant code below.

```java
class X {
    // No need to use two members
    static X myX = null;
    
    private X() {}

    public static getInstance() {
        if (myX == null) {
            myX = new X();
        }
        return myX;
    }
}
```

This beautiful solution is the **Singleton Design Pattern**. A quick note is that in this course when we mention *recursion*, we are referring to a class using itself.
Note that above the class `X` has a member `myX` of the its own type. This is a form of class recursion. The rest of the notes will just quickly summarize the slides.

## Intent of Singleton

Ensuring that a class has ONLY ONE instance and providing a global point of access to it.

## Applicability

It is used if:

- we need a single instance of a certain class, and this instance needs to be accessible to clients from a well-known access point
- the instance should be extensible by sub-classing, and clients should be able to use an extended instance without modifying their code.

## Main Structure

Clients access a Singleton instance via its Instance() Method.

3 Steps:

1. Define a private static member of same class type.
2. Make Constructor private.
3. Define a public static method as a pseudo-constructor.

## Instantiation Forms

Let us look at the example below of a GUI singleton class

```java
public class SingletonFrame extends JFrame {
    private static SingletonFrame myInstance; // 1

    // 2
    private SingletonFrame() {
        this.setSize(400, 100);
        this.setTitle("Singleton Frame. Timestamp:" + System.currentTimeMillis());
        this.setDefaultCloseOperation(JFrame.HIDE_ON_CLOSE);
    }

    // 3
    public static SingletonFrame getInstance() {
        if (myInstance == null)
            myInstance = new SingletonFrame();
        return myInstance;
    }
}
```

Recall that a Singleton's aim is to ensure a SINGLE instance of the class. I claim that the above code is NOT yet a perfect Singleton.

In multi-threaded applications, there are multiple threads running at the same time. To drive the point home, we will talk about the `getInstance()` method in the class above.

Imagine that we have 2 threads running my `getInstance` method at the same time. Thread 1 asks if `myInstance` is null, receives a true answer and enters the if statement.
Thread 2 comes at this time, asks the same question, receives the same answer, and enters the if statement. Thread 1 creates a new instance using the `new` keyword.
The surprising thing is that thread 2 is still *inside* the if statement and **creates another new instance using the new keyword!!!**

We will discuss several solutions to this problem till we reach a version we are happy about.

### Lazy Instantiation

It turns out we have a `synchronized` keyword in java that basically locks our method from being accessed when any given thread accesses it.
So, in the example above, as soon as thread 1 enters the method and is assessing the if statement, the method gets locked from external access.
When thread 2 tries to enter, the JVM (virtual machine) tells it sorry you cannot enter, there is someone using the method. After thread 1 finishes using, thread 2 now
accesses the method and finds the value of the object since it already has been created by thread 1. Note the code below.

```java
public class SingletonFrame extends JFrame {
    private static SingletonFrame myInstance;

    private SingletonFrame() {
        this.setSize(400, 100);
        this.setTitle("Singleton Frame. Timestamp:" + System.currentTimeMillis());
        this.setDefaultCloseOperation(JFrame.HIDE_ON_CLOSE);
    }

    // Note the synchronized
    public static synchronized SingletonFrame getInstance() {
        if (myInstance == null)
            myInstance = new SingletonFrame();
        return myInstance;
    }
}
```

This code looks okay as it solves the previous problem of multi threading. However, the problem arises when we have a lot of threads like 10 or 20.
Every single thread locks the method when it accesses it even though it is not really necessary to lock after the first instantiation.
As you might have imagined, this is a problem in efficiency and is **very very slow.**

### Early or Eager Instantiation

As an attempt of solving the previous problem, let us do the following:

```java
class Singleton {
    // The idea is creating an object early on. Since it is one object anyway.
    private static SingletonFrame myInstance = new Singleton();

    private Singleton() {
        System.out.println("Singleton(): Initializing Instance");
    }

    public static Singleton getInstance() {
        return myInstance;
    }
}
```

This might seem as a brilliant solution, but it simply is inefficient due to a simple fact: there will always be an object for this class
This simply is a **waste of memory**. The virtual machines assigns some space for an object of this class even when you don't use it.
As a designer, this must be a pain for you. So, there must be an even better solution.

### Lazy Instantiation Using the Double Locking Mechanism

This time let us examine the code right away.

```java
class Singleton {
    private static SingletonFrame myInstance;

    private Singleton() {
        System.out.println("Singleton(): Initializing Instance");
    }

    public static Singleton getInstance() {
        if (myInstance == null) {
            synchronized(Singleton.class) {
                if(myInstance == null) {
                    System.out.println("getInstance(): First time");
                    myInstance = new Singleton();
                }
            }
        }

        return myInstance;
    }
}
```

Anyone seeing this code for the first time might think how stupid it is to use two repeated if statements. However, let us discuss the same scenario we addressed before.

We have two threads. Thread 1 accesses the method, passes from the if statement same as before, and enters the synchronized area, which is locked now from any external access. Thread 2 also passes through the first statement but waits till the first thread finishes its job in the synchronized area. After thread 1 finishes its instantiation, the second thread now is refused by the second if statement and just returns the object that was created by thread 1. Not only that, but also any future thread will immediately be refused by the first if statement. So, the delay of having to wait for every access is now eliminated.

## Other Singleton Examples

- Logger Classes
- Configuration Classes
- Accessing resources in shared mode
- Factories (you can combine abstract with singleton and it is common practice)

## Summary

OOP allows creation of many instances of a class, but simply you might not need this feature. For this reason, we have the Singleton Design Pattern.

In multi-threading applications, we need to make sure of the correctness and performance of our implementation.

