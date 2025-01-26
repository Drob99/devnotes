# Lecture 4: Main OO Concepts (2)

## Table of Contents

- [Lecture 4: Main OO Concepts (2)](#lecture-4-main-oo-concepts-2)
  - [Table of Contents](#table-of-contents)
  - [Static / Shared Members](#static--shared-members)
  - [Abstract Classes](#abstract-classes)

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

In UML, we show it as either *italics* or by writing **<<static>>** before or after the class name.

This concept is very important to understand and enforce. You just need to recognize that a class needs to be abstract when you encounter one.