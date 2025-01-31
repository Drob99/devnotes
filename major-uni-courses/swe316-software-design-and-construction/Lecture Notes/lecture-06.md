# Lecture 6: Principles of Class Design

## Table of Contents

- [Lecture 6: Principles of Class Design](#lecture-6-principles-of-class-design)
  - [Table of Contents](#table-of-contents)
  - [Introduction](#introduction)
  - [Single-Responsibility Principle](#single-responsibility-principle)

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
