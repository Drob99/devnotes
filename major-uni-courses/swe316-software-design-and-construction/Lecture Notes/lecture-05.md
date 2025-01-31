# Lecture 5: Design Process

## Table of Contents

- [Lecture 5: Design Process](#lecture-5-design-process)
  - [Table of Contents](#table-of-contents)
  - [Introduction \& Main Idea](#introduction--main-idea)
  - [Gathering Requirements](#gathering-requirements)
  - [Describe the application](#describe-the-application)
  - [Identify Objects](#identify-objects)
  - [Identify Responsibilities](#identify-responsibilities)
  - [Building a Class Diagram](#building-a-class-diagram)

## Introduction & Main Idea

In order to make decisions about inheritance and polymorphism, we need to identify our
classes first.

Five Steps

1. Gather Requirements
2. Describe the application
3. Identify the main objects
4. Describe the Interactions
5. Create a Class Diagram

## Gathering Requirements

Functional requirements (what the system does) & NonFunctional Requirements (quality attributes, legal requirements, security, ...etc.)

The bigger the application, the more formal we need to be about the requirements.

## Describe the application

We switch our focus from feature focus to a user focus requirements.

There are many ways to write the description of the application, like *Use Cases* or *User Stories*.

Use cases -> (Title (what is the goal), Actor (who?), Scenario (how?))

## Identify Objects

What are the things or entities in the application. Identify them, start to refine them, and then 
draw them in a simple diagram. We can show associations or interactions.

1. List all the nouns
2. Remove the illogical ones.
3. Sketch a conceptual object model
4. Draw interactions or associations, the most important or interesting one

Is it important to be in the diagram? Does it affect other objects?

## Identify Responsibilities

Look for verb phrases and identify responsibilities. NOT all of them will be behaviors of course.
Maybe combined, maybe split, or maybe not needed.

Use cases are interested in who initiates the use case NOT whose responsibility it is to perform that behavior.

After you extract verb phrases, you assign their responsibilities to the objects.

Avoid Global Master Objects.

## Building a Class Diagram

Attributes are usually easier than behavior to determine.
Avoid building plain data structures.
This will be the focus of the coming lecture.


