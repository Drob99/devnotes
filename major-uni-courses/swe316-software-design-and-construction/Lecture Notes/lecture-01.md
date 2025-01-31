# Lecture 01: Introduction to Software Design

## Table of Contents

- [Lecture 01: Introduction to Software Design](#lecture-01-introduction-to-software-design)
  - [Table of Contents](#table-of-contents)
  - [Objectives](#objectives)
  - [Introduction](#introduction)
  - [Architectural Design Phase](#architectural-design-phase)
  - [Detailed Design Phase](#detailed-design-phase)
  - [Functional Decomposition](#functional-decomposition)
  - [Three Paradigms of Programming](#three-paradigms-of-programming)

---

## Objectives

- Primacy of Design
- Architectural Vs Detailed Design
- Structured Vs OO Design

---

## Introduction

- Software Design is a crucial preparation part that prevents later headaches.
- Design is the step that lies between Requirements and Development.
- There are miscellaneous tools that help in this stage, but simply an empty paper or a place to sketch is as effective as anything else.
- Especially for large systems, it usually makes sense to divide the design phase into two parts: **architectural design phase** & **detailed design phase**.

## Architectural Design Phase

- High-level overview of the system
- Main components, properties external to them, and relationships among components
- Main source: Functional & nonfunctional requirements and technical consideration

## Detailed Design Phase

- Finer level of detail
- Main source: Architectural phase & functional requirements
- All functional requirements have to be addressed by at least one module in the detailed design.
- The purpose of design is to help rather than waste time, so only map or design what helps you and saves your time.
- One-to-one mapping is ideal.

## Functional Decomposition

- It is applying the idea of divide and conquer to dominate and control your code.
- Basically, you decompose modules into smaller ones. Every designer has their way of refining modules. There is NO right or wrong.

## Three Paradigms of Programming

1. Structured: Just lines and jumping between lines to have function-like behaviors (spaghetti code)
2. Procedural: The code is divided into functions, each one having 1 job
3. Object-oriented: The idea of classes and objects being instances of those classes.
