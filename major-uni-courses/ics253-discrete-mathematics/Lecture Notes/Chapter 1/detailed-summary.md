# Chapter 1: Logic

## Table of Contents

- [Chapter 1: Logic](#chapter-1-logic)
  - [Table of Contents](#table-of-contents)
    - [1.1 Propositions and Logical Operations](#11-propositions-and-logical-operations)
      - [Compound Propositions](#compound-propositions)
    - [1.2 Evaluating Compound Propositions](#12-evaluating-compound-propositions)
      - [Example](#example)

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
