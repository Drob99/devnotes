# Lecture 3: Main OO Concepts - Part 1

## Table of Contents

- [Lecture 3: Main OO Concepts - Part 1](#lecture-3-main-oo-concepts---part-1)
  - [Table of Contents](#table-of-contents)
  - [The Concepts](#the-concepts)
    - [Abstraction](#abstraction)
    - [Encapsulation](#encapsulation)
    - [Inheritance](#inheritance)
    - [Polymorphism](#polymorphism)

## The Concepts

1. Abstraction
2. Encapsulation
3. Inheritance
4. Polymorphism

### Abstraction

- Dividing the system into fine-grained components until you don't need to describe them in details.
- When we hear the word, we focus on the essential qualities of it rather than one specific example.
- When I say the word table, I don't mean a specific table but rather the idea of a table. People hearing me will understand what I am talking about and will probably think about a specific example they saw before.
- The example of the table is basically what a class does. It combines all the related logic of an object without giving specific examples.
- This concept supports the other OOP concepts.

### Encapsulation

- Putting related contents together + protecting them
- We bundle our attributes and methods into a class and protect our attributes by making them private.
- The principle is that objects should not reveal anything about themselves except what's absolutely necessary for the application to work.
- To achieve that, by convention, we put all the attributes as private and create getters and setters to control the logic of accessing them.
- The 'deprecated' word is a way of showing users that some functionality changed and that alternatives exist. Otherwise, breaking the users' code would be a terrible idea.
- Sometimes, the responsibility of a class is to show the user that there is an error by throwing it to him. For example, in withdraw functionality if the balance is less than the amount withdrawn, the class throws an error. It is up to the user to deal or present this error in a GUI as they please.
- Hiding attributes also helps us when we want to change them. For example, changing balance to dollars and cents should be very easy given that we adjust the class properly.
- It is not only about being secretive, but also about reducing dependencies among the application parts.
- The rule is -> **Hide as much as possible.**

### Inheritance

- A form of code reuse
- Instead of rewriting a new class from scratch, we base it on another existing class.
- For example, a customer is also a person. A Customer class could inherit the Person instead of rewriting the common logic.
- Inheritance takes all public and protected attributes and methods but NOT private.
- The depth of inheritance refers to the number of parents a child has, or basically the number of arrows to the highest parent class in a class diagram. As an example, given the following inheritance sequence: Object <- Component <- Container <- Window <- Dialog <- FileDialog, the depth is 5.
- To override properly, we must use same signature from parent and declare additional properties in child constructor.

### Polymorphism

- Automatically selects the correct behavior based on the currently selected object.
- The addition operator could add two integers and concatenate two strings. One thing for many uses.
- There are 4 key concepts that must be there to fully utilize Polymorphism:
    1. Inheritance
    2. Methods (overriding)
    3. Collections (anything that captures many objects)
    4. Loops / iterations (spoil yourself)
- You should differentiate between the compiler (before runtime checks syntax) and the virtual machine (checks while runtime).

```java
/* The left side is called a declaration, while the right one is instantiation. 
If shape is an abstract class, the compiler has a problem with the instantiation part 
since it requires a concrete type.*/
Shape s1 = new Shape();

/* A compiler has no problems with the under syntax. But, it is not polymorphism.
Out of the 4 key conditions, we only have inheritance and usage of a method.*/
Shape s1 = new Line();
s1.draw();


/* Ok, now we have a collection and we iterate through it,
utilizing our inherited method. Inside the loop, we could add
logic related to a certain class using instanceOf and casting.*/
Shape[] myShapes;
myShapes[0] = new Line();
myShapes[1] = new Circle();
// etc.

// foreach loop
for (Shape s : myShapes) {
    s.draw(); // only methods of parent class Shape appear
}

```

- A lot of if statements in your code is a sign of bad design.
- It is NOT recommended to use 'instanceof' extensively. It kills performance.
- Most of the classes do not need it. It will come naturally. You just need to be aware.
