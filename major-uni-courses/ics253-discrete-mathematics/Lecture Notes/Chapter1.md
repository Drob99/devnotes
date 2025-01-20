# Chapter 1: Logic

## Table of Contents

- [Chapter 1: Logic](#chapter-1-logic)
  - [Table of Contents](#table-of-contents)
    - [1.1 Propositions and Logical Operations](#11-propositions-and-logical-operations)
      - [Compound Propositions](#compound-propositions)
    - [1.2 Evaluating Compound Propositions](#12-evaluating-compound-propositions)
      - [Example](#example)
    - [1.3 Conditional Statements](#13-conditional-statements)
      - [Important Terms](#important-terms)
      - [The Biconditional Operation](#the-biconditional-operation)
    - [1.4 Logical Equivalence](#14-logical-equivalence)
      - [De Morgan's Laws](#de-morgans-laws)
    - [1.5 Laws of Propositional Logic](#15-laws-of-propositional-logic)

---

### 1.1 Propositions and Logical Operations

- Logic is a set of rules in which we can analyze something. Formally, it is the study of formal reasoning.
- A proposition is a *statement* that is *either true or false*. It is the most basic element of logic.
- *All humans have two eyes.*: an example of a false proposition (exceptions exist)
- All questions, commands, requests, and exclamations are NOT propositions.
- Even if you don't know the exact truth value, the proposition is still a proposition.
  - e.g.: *Monday will be cloudy.* (unknown)
  - e.g.: *The movie was funny.* (matter of opinion)
- We denote propositions with variables, e.g., $p$, $q$, or $r$ to make it simpler to represent.
- A **truth table** shows the truth value of all the possible combinations of the variables. Every row is a single combination. The total number of combinations is $2^n$, where $n$ is the number of variables.

#### Compound Propositions

  1. **Conjunction**
      - *logical operation*: $\land$
      - *example*: $p \land q$ read as "$p$ and $q$"
      - *explanation*: Only true when all operands are true.
  2. **Disjunction (Inclusive Or)**
      - *logical operation*: $\lor$
      - *example*: $p \lor q$ read as "$p$ or $q$"
      - *explanation*: Only false when all operands are false.
  3. **Exclusive Or (XOR)**
      - *logical operation*: $\oplus$
      - *example*: $p \oplus q$ read as either "$p$ or $q$"
      - *explanation*: Only true when an odd number of operands is true.
  4. **Negation**
      - *logical operation*: $\neg$
      - *example*: $\neg\:p$ read as "not $p$"
      - *explanation*: Flips the truth value of the variable after it.

---

### 1.2 Evaluating Compound Propositions

- Order of operations: NAO (not, and, then or)
- This section is mostly calculations, and could be easily checked for outside sources. Below, there is an easy example. If I find harder examples in the future, I will hopefully include them.

#### Example

Evaluate $(p \land q) \lor (\neg p \land r)$, where:

- $p = \text{True}$
- $q = \text{False}$
- $r = \text{True}$

Steps:

1. $p \land q = \text{False}$ (since $q = \text{False}$)
2. $\neg p = \text{False}$ (since $p = \text{True}$)
3. $\neg p \land r = \text{False}$
4. $\text{False} \lor \text{False} = \text{False}$

Result:
$(p \land q) \lor (\neg p \land r) = \text{False}$


### 1.3 Conditional Statements

- The **conditional operation** is written as $\rightarrow$.
- $p \rightarrow q$ is read "if $p$, then $q$"
- It is only false if $p$ is true and $q$ is false.
- A compound proposition that uses a conditional operation is a **conditional proposition**
- $p$ is the **hypothesis** and $q$ is the **conclusion**.
- Truth Table:
<div align="center">

| $p$ | $q$ | $p \rightarrow q$ |
|:---:|:---:|:------------------:|
| $\text{T}$ | $\text{T}$ | $\text{T}$ |
| $\text{T}$ | $\text{F}$ | $\text{F}$ |
| $\text{F}$ | $\text{T}$ | $\text{T}$ |
| $\text{F}$ | $\text{F}$ | $\text{T}$ |

</div>
- A tricky thing might be is that conditional statements are ALWAYS true when the hypothesis is false.

<img src="images/conditional-image.png" alt="conditional statement illustrated"  style="display: block; margin: 0 auto; width: 400px;" />

- The following are different ways to express conditional operations:
  - If $p$, then $q$.
  - If $p$, $q$
  - $q$ if $p$
  - $p$ implies $q$
  - $q$ whenever $p$
  - $p$ only if $q$ (if conclusion is false, the hypothesis cannot be true, otherwise the conditional statement would be false)
  - $p$ is sufficient for $q$
  - $q$ is necessary for $p$

#### Important Terms

- **Converse**: Just flip it.
- **Contrapositive**: Flip and Negate
- **Inverse**: Just negate it.

#### The Biconditional Operation

- $p \leftrightarrow q$ is read as $p$ if only and only if $q$
- Truth Table:

<div align="center">

| $p$ | $q$ | $p \leftrightarrow q$ |
|:---:|:---:|:------------------:|
| $\text{T}$ | $\text{T}$ | $\text{T}$ |
| $\text{T}$ | $\text{F}$ | $\text{F}$ |
| $\text{F}$ | $\text{T}$ | $\text{F}$ |
| $\text{F}$ | $\text{F}$ | $\text{T}$ |

</div>

- It is only true when both the hypothesis and conclusion have the same values.
- $p$ is necessary and sufficient for $q$
- **iff**

### 1.4 Logical Equivalence

- **Tautology**: when a compound proposition is always true, regardless of the truth value of the propositions within.
- **Contradiction**: when a compound proposition is always false, regardless of the truth value of the propositions within.
- Simply, one example is enough to counter the claim that a proposition is a tautology or a contradiction, hence it is referred to as the *counterexample*.
- Two compound propositions are **logically equivalent** if they have the same truth value regardless of the truth value of their propositions within. (denoted as $\equiv$)

#### De Morgan's Laws

- logical equivalences showing how to correctly distribute negation operations on a parenthesized expression.

1. $\neg (p \lor q) \ \ \equiv\ \  (\neg p \land \neg q)$
2. $\neg (p \land q) \ \ \equiv\ \  (\neg p \lor \neg q)$

### 1.5 Laws of Propositional Logic
