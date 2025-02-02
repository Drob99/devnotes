# Lecture 6: Principles of Class Design

## Table of Contents

- [Lecture 6: Principles of Class Design](#lecture-6-principles-of-class-design)
  - [Table of Contents](#table-of-contents)
  - [Introduction](#introduction)
  - [Single-Responsibility Principle](#single-responsibility-principle)
  - [Open-Closed Principle](#open-closed-principle)

## Introduction

In the previous lectures, we talked about the principles of designing.
Now, we will discuss the principles of design (SOLID):

  1. Single-Responsibility Principle
  2. Open Closed Principle
  3. Liskov Substitution Principle
  4. Interface Segregation Principle
  5. Dependency Inversion Principle

## Single-Responsibility Principle

A class should have ONLY one job. Functions could also implement this principle.
Responsibility is having only ONE reason to change. This basically ensures that changes do not affect other modules or classes.

Let us see the following code as an example

```java

public class Book {
    // The following should be private to ensure encapsulation
    public String title;
    public String author;

    // constructor
    public Book(String title, String author) {
        this.title = title;
        this.author = author;
    }

    // getters & setters
    public String getTitle() {
        return this.title;
    }

    public void setTitle(String title) {
        this.title = title;
    }

    public String getAuthor() {
        return this.author;
    }

    public void setAuthor(String author) {
        this.author = author;
    }

    // search for book
    public void searchBook(String title) {
        // some code
    }
}
```

In order to search, I would need a collection of books to add. If I change the attributes of book, I might have
to deal with the BookCollection differently. Hence, this is NOT a single-responsibility class. Note the class diagram below

> Classes:
>
> - Book [String title, String author]
> - LibApp -> we have Data Logic + GUI Logic
>
> Relationships
>
> - LibApp 1 -> n Book

Let us move all the functionalities on a collection of books in another class. Now, we have the current class diagram:

> Classes:
>
> - Book [String title, String author]
> - LibApp -> now only GUI logic, the data logic is reduced effectively
> - BookCollection [Book[] myBooks, search(), sort(), ...]
>
> Relationships
>
> - LibApp 1 -> n Book
> - BookCollection 1 -> n Book
> - LibApp 1 -> 1 BookCollection

We want to add a GUI logic and utilize both classes. So, let us add a LibApp.java class (where our main will be)

> Classes:
>
> - Book [String title, String author]
> - BookCollection [Book[] myBooks, search(), sort(), ...]
> - LibApp [Data Logic]
>
> Relationships
>
> - BookCollection 1 -> n Book

## Open-Closed Principle

Whenever you deliver something, there is always a room for enhancements & new features. The concept of reaching a final version does NOT exist.

Therefore, the big idea is **A module should be open for extension but closed for modification.**

So, you should be able to extend your code via inheritance and other OOP features. However, you should reduce modifications as much as possible as they affect other code and might cause a lot of headaches.

One good example of this is in Chrome extensions. You simply add an extension without touching the code or even knowing how it's working. This is a WOW factor that you should aspire as a developer to apply.

As a general rule of thumb, target the upper level of your classes to ensure smooth and extensible software.

Let us take an example to get the point home.
Assume a store wants to hand out cookbooks at a discounted price.

Our developer writes the following code just to get the task done:

```java
class CookbookDiscount {
    String getCookbookDiscount() {
        String discount = "30% between Dec 1 and 24.";
        return discount;
    }
}

class DiscountManager {
    void processCookbookDiscount (CookbookDiscount discount) {

    }
}
```

Given the above code, as a compiler, everything is fine. As a designer, the least you can say is that the code is *horrible*. By the way, note that App.java is there even though we don't explicitly show it.

To prove that this code is badly designed, let us add another feature (remember, we said this could be called a maintenance scenario). We want to have another discount on biographies. Our developer, still carelessly, writes the code below.

```java
class BiographyDiscount {
    String getBiographyDiscount() {
        String discount = "50% on the subject's birthday.";
        return discount;
    }
}

// To process this new kind of discount, the developer was forced to modify the DiscountManager class
class DiscountManager {
    void processCookbookDiscount (CookbookDiscount discount) {

    }
    void processBiographyDiscount(BiographyDiscount discount) {

    }
}
```

To add this new feature, the developer has added 1 class (BiographyDiscount) and modified 2 (DiscountManager & App.java). 
Remember, in Open Closed Principle, our goal is to reduce modifications. Clearly, we have violated the Open Closed Principle in this example.
Recall, we said that dealing with a higher level usually solves all these problems. This might give us a hint that adding a layer of abstraction that represents all discounts might be the solution. And this is precisely the idea!

```java
public interface BookDiscount {
    String getBookDiscount();
}

class CookbookDiscount implements BookDiscount {
    @Override
    String getBookDiscount() {
        String discount = "30% between Dec 1 and 24.";
        return discount;
    }
}

class BiographyDiscount implements BookDiscount {
    @Override
    String getBookDiscount() {
        String discount = "50% on the subject's birthday.";
        return discount;
    }
}

// To process this new kind of discount, the developer was forced to modify the DiscountManager class
class DiscountManager {
    void processBookDiscount (BookDiscount discount) {

    }
}
```

In the beautiful code written above, when we added the BiographyDiscount we added 1 class (BiographyDiscount) and modified only the App.java

Notice that our DiscountManager deals with the higher level, which gives us a hint that we are in the right direction. Notice how visually appealing and beautiful the code above is.

With more effort, we can even add new features without having to modify the App.java! This brilliancy is what happens when you install Chrome extensions, That is why it was a WOW feature.
