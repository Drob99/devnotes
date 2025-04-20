# Lecture 7: Good Software Design

## Table of Contents

- [Lecture 7: Good Software Design](#lecture-7-good-software-design)
  - [Table of Contents](#table-of-contents)
  - [Introduction](#introduction)
  - [DP 1: Divide and Conquer](#dp-1-divide-and-conquer)
    - [Dividing](#dividing)
  - [DP 2: Increase Cohesion Where Possible](#dp-2-increase-cohesion-where-possible)
  - [DP 3: Reduce Coupling Where Possible](#dp-3-reduce-coupling-where-possible)
    - [Content](#content)
    - [Control](#control)
    - [Stamp](#stamp)
  - [DP 4: Abstraction as high as possible](#dp-4-abstraction-as-high-as-possible)
  - [DP 5: Increasing reusability where possible](#dp-5-increasing-reusability-where-possible)
  - [DP 6: Reuse Existing Designs and Code](#dp-6-reuse-existing-designs-and-code)

## Introduction

In this chapter, we will discuss some good design principles. The slides discuss 11 different design principles (DPs).
However, we will focus only on a few of them. You will notice that most of them are straightforward and may appear obvious,
but many developers sadly don't follow them.

The overall *goals* of good design:

1. Increasing profit by reducing cost (time and effort you spend on the development) and increasing revenue
2. Ensuring that we follow the requirements (Recall that every design component points to a requirement.)
3. Accelerating development (The better your design, the faster you code. Sometimes even you just need to translate your design to code.)
4. Increasing qualities (usability, reliability, reusability, maintainability, efficiency, ...etc.)

## DP 1: Divide and Conquer

You will notice a big improvement in your code performance and quality when you divide large systems to small entities.
By separating large things, you can think about every specific functionality by itself and thus do it faster.
This is even more productive when a large team is working on some software.

### Dividing

system -> subsystems (e.g. clients and servers) -> packages -> classes -> methods

You need to write code with the mentality that you are CREATING packages. Think about how to make life easier to those using your code later on.

## DP 2: Increase Cohesion Where Possible

Cohesion is a measure of how a thing is focusing on ONE thing. The more it does that, the higher cohesion it has.

DP 1 also helps me achieve cohesion. Some software have cohesion factor measured numerically to display how cohesive your code is.

Don't worry about the types, just read them and know what each one is briefly.

One of them is Functional Cohesion: related computations are grouped together (e.g. Math Class).

One of the effective ways of achieving cohesion is separating into layers. Each layer worries about a different part of the logic.

## DP 3: Reduce Coupling Where Possible

Coupling basically happens when modules depend on (or use) one another. When you change in one place, you will need to change in another.
Circular references is a bad design because it conflicts DP 3.
Also, modifying function signatures in a class that is used by others is a terrible idea. You will have to modify it in all of the related classes.
The more arrows are entering a class in a class diagram, the higher responsibility it has to maintain good design.

We will only focus on the following types:

### Content

This is the worst type of coupling, solved by one of the easiest principles: **Encapsulation**.
Basically, a module SHOULD NEVER modify internal data in another component.

### Control

Occurs when a procedure calls another using a flag or a command.

Look at this example

```java
public void routineX(String command) {
    if (command.equals("drawCircle")) {
        drawCircle();
    } else {
        drawRectangle();
    }
}
```

I hope you can see what terrible mistake we are doing in the code above. What if the user does not write 'drawCircle' but instead writes 'DrawCircle'?
Or maybe what about adding other functionalities? This coupling is simply solved by the magic of **Polymorphism**.
One function used by all the classes in different forms and is called through the upper interface (refer to definition of [polymorphism](lecture-03.md#polymorphism)).

### Stamp

This happens whenever a class is declared as an argument type in a method.

Notice the code below

```java
public class Emailer {
    public void sendEmail (Employee e, String text) {
        // Code
    }
}
```

So, you are establishing an unneeded link between the Emailer class and the Employee class.
You are throwing an object to a very generic class. Emailer should send an email regardless if I am en employee or not.
The only thing it needs is an email address NOT an object. Don't pollute a very strong class like Emailer with a link to a very specific class like Employee.

Note how this simple solution is much better:

```java
public class Emailer {
    public void sendEmail (String email, String text) {
        // Code
    }
}
```

## DP 4: Abstraction as high as possible

We have been doing this and will do it more often in this course. Good abstraction hides information and helps you understand the big picture.
Remember that when you hear the word car, you don't think about a specific car but rather you sketch a generic car in your head (4 wheels, driver, gas, speed, ...etc.)

Fewer public methods, all variables as private, superclasses, and interfaces are all ways of increasing abstraction.

## DP 5: Increasing reusability where possible

While developing, think about reuse. You are building libraries, not individual code. Generalize the design as much as possible.
Follow DP 2-4. Simplify your design keeping the user in your picture always.

Design your system with hooks -> basically allowing other designers to add functionality to your design easily and without suffering.

## DP 6: Reuse Existing Designs and Code

Take advantage of what others did before you. Don't reinvent the wheel, but rather use it in your own system and extend its functionality.
Of course, reusing a component requires a component to follow DP 5.