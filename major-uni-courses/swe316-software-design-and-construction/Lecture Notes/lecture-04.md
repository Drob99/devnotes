# Lecture 4: Main OO Concepts (2)

## Table of Contents

- [Lecture 4: Main OO Concepts (2)](#lecture-4-main-oo-concepts-2)
  - [Table of Contents](#table-of-contents)
  - [Static / Shared Members](#static--shared-members)
  - [Abstract Classes](#abstract-classes)
  - [Interfaces](#interfaces)
  - [Association](#association)
    - [Aggregation](#aggregation)
    - [Composition](#composition)

## Static / Shared Members

Remember that you always have two roles to work as: the designer and developer.

Technically speaking, you can add any modifier like `final/const` or `static` or `private/protected/public`, but as a designer, you need to be very careful and understand the meaning and use of each one.

If I want to have a member that all my objects of a certain class share. For example, I want to have a *counter* in a *Student* class, where after every object is made the counter increases. In this sense, the member *counter* is related to the whole class rather than a single member.
One way of doing this is to create another class and the *Student* class utilizes that class to increment the counter every time the constructor is called, aka a new object is made.

However, in this way, I have created a new class for just that reason. This is poor design and that is why programming languages have provided the concept of **static members** for specifically this idea.

With every runtime, our virtual machine stores all static variables as unreferenced objects even though we might not need them.

**Exam Question**: It is allowed to call static members within normal methods, but it is NOT allowed to access normal ones inside static methods.

Think of it this way: static means related to the class, so I can call it using just the class name without instantiating any objects. So, how can I have normal members which require an object inside them? Logically, I shouldn't be able to do that, and this is precisely the case.

Hence, we come up with this important conclusion: **Static methods can ONLY use static variables.**

```java
public class SavingsAccount {
    // instance variables omitted

    // private static member
    private static float interestRate;

    // public static getters and setters
    public static float getInterestRate() {
        return this.interestRate;
    }
    public static void setInterestRate(float r) {
        this.interestRate = r;
    }

    // other code omitted
}
```

In UML, static members are shown **underlined**.

## Abstract Classes

Sometimes, you write a class that never gets instantiated, or you notice that in the code. Sometimes, you don't want it to be instantiated probably as a matter of policy enforcement, controlling how others use it.

Both of these situations require a special type of classes. **Abstract Classes** are never instantiated.

Recall that the left side of this statement `Z z = new Z()` is called declaration, while the right side (using new) is the instantiation. If Z was an abstract class, the compiler would flag this as an error because of the instantiation part. Does this mean that we can declare some objects as abstract? *Yes, only in the case where the instantiation is another child class*.

In UML, we show it as either *italics* or by writing **\<<abstract\>>** before or after the class name.

This concept is very important to understand and enforce. You just need to recognize that a class needs to be abstract when you encounter one.

## Interfaces

The first question we need to ask is why an interface. Doesn't it just have an unimplemented method like an abstract class?
There a couple of reasons. First, we can have multiple inheritance in interfaces, while in abstract classes we cannot. Another important reason is that the interface helps us focus on a single task.

To get the idea, let us take an example of the abstract class *Shape*. It has 3 children who inherit it: Line, Rectangle, and Circle. We can have an interface named *Printable* which implies that each one of them is a shape and a printable thing. It basically takes a functionality that is common to all and not really specific to shapes per se and puts it in an interface. Any printable thing even in other projects can still implement it.

In our example, we will have two people working together: a designer --  let us name him Omar -- and a developer -- let us name him Sam. Sam tells Omar that Rectangles and Circles have areas and he wants a functionality that prints them. Omar, being the good designer he is, decides that having a function to calcArea is redundant. He wants to let such shapes that have areas implement an interface called *Areable*.

The developer, hearing the news, writes the code below in App.java

```java
Shape [] myShapes;
// Fill the array

for (Shape s : myShapes) {
    // Sam wants to print the Rec and Circle areas. He knows that lines don't have areas. So, he writes the code below
    if (!s instanceof Line) {
        // calculate area
        s.calculateArea();
    }
}
```

However, the compiler immediately gives him an error. He is calling the calcArea from the abstract class, which does not have this method implemented. He needs to cast.

```java
Shape [] myShapes;
// Fill the array

for (Shape s : myShapes) {
    // Sam wants to print the Rec and Circle areas. He knows that lines don't have areas. So, he writes the code below
    if (!s instanceof Line) {
        // calculate area after casting
        Areable a = (Areable) s;
        a.calculateArea();
    }
}
```

Sam is happy of his work and he thinks he did a good work. Let us test that by initiating a maintenance scenario.
The first scenario they want to add a Point class. Obviously, Omar adds it to the class diagram, and since it does not have an area, it does not implement *Areable*.

Now, if the code aboves runs for a Point, we will get an error from the virtual machine. The Point is not a line, so it enters the if statement. The problem is it cannot be cast to *Areable*. Obviously, Sam did a grave mistake in his code.
After he knows that, he corrects the code into the following.

```java
Shape [] myShapes;
// Fill the array

for (Shape s : myShapes) {
    // Sam makes only Areable things enter this condition
    if (s instanceof Areable) {
        // calculate area after casting
        Areable a = (Areable) s;
        a.calculateArea();
    }
}
```

Another maintenance scenario is we want to add an *Areable* shape called Diamond. By the way, maintenance scenario is a new feature or adjustment that tests how well structured the design and code are. Anyway, Omar adds the Diamond as a child of shape, but he does not make it implement *Areable* by mistake. In this case, the code is perfectly fine, but the designer (Omar) is the one to blame. The simple solution, of course, would be to let it implement *Areable* and everything works as expected.

> **As a general rule, target the upper level of classes and interfaces to build a program in proper logic.**
> **Referring to the lower level (children classes) is the number one reason of errors.**

An interface is just a list of method signatures. No functionality inside.

## Association

It is when there is a relationship between two classes. Usually, we care about three things: multiplicity, direction, and label.

### Aggregation

It is a 'has a' relationship. For example, a classroom has students.

### Composition

It is an aggregation that implies ownership. If an owning object is destroyed, so are the contained objects.