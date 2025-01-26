# Chapter 2: Probability

## Table of Contents

- [Chapter 2: Probability](#chapter-2-probability)
  - [Table of Contents](#table-of-contents)
  - [Objectives](#objectives)
  - [2.1 Sample Spaces and Events](#21-sample-spaces-and-events)
    - [Sample Spaces](#sample-spaces)
    - [Events](#events)
      - [Event Combinations](#event-combinations)
      - [Concepts](#concepts)
      - [Some properties](#some-properties)

## Objectives

1. Understand and describe sample spaces and events for random experiments with graphs, tables, lists, or tree diagrams.
2. Interpret probabilities and use the probabilities of outcomes to calculate probabilities of events in discrete sample spaces.
3. Use permutations and combinations to count the number of outcomes in both an event and the sample space.
4. Calculate the probabilities of joint events such as unions and intersections from the probabilities of individual events.
5. Interpret and calculate conditional probabilities of events.
6. Determine the independence of events and use independence to calculate probabilities.
7. Use Bayes’ theorem to calculate conditional probabilities.
8. Understand random variables.

## 2.1 Sample Spaces and Events

- **Probability**: the chance or likelihood that an uncertain event will occur (always between 0 and 1)
- Probability of 0 means the event is impossible to occur, while 1 means the event is certain to occur.
- **Random Experiment**: a process of obtaining outcomes for uncertain events, might lead to different results even though it is repeated in exactly the same way every time (measuring the current in a thin copper wire).
- Our goal is to understand, quantify, model the types of variations (randomness) that we encounter while doing an experiment. We then can make informed judgments from the results that are not invalidated by the variation.
- **Sample Space**: the set of all possible outcomes. ($S$ or $\omega$)
- **Elementary Events** OR **Sample Points** are the individual elements in the sample space.
- **Events** are possible outcomes from simple experiments that are a subset of the sample space.
- **Joint Events** are events that have two or more characteristics.

### Sample Spaces

- In general, there are 2 types of sample spaces:
  - Discrete sample space: 
    - the values are countable even if infinite
    - e.g.: number of sand grains, $S = \{HH, HT, TH, TT\}$
  - Continuous sample space:
    - the values are uncountable (interval)
    - e.g.: $S = \{x | x <= 4 \}$
- You can represent a sample space graphically as a tree diagram.

<img src="images/tree-diagram.png" alt="tree diagram" style="display: block; margin: 0 auto; width: 400px;"/>

### Events

- A subset of the sample space of a random experiment

#### Event Combinations

1. Union
   - all outcomes in one event OR the other ($A \cup B$)
2. Intersection
   - all outcomes in one event AND the other ($A \cap B$)
3. Complement
   - the set of outcomes in sample space that are NOT in event ($A^c$, $A'$, $\bar{A}$)

#### Concepts

1. Mutually Exclusive Events
   - cannot occur together ($A \cap B = \phi$) or ($P(A \cap B) = 0$)
2. Collectively Exhaustive Events
   - contain the whole sample space ($A \cup B = \omega$) or ($P(A \cup B) = 1$)
3. Independent and Dependent Events
   - independent: occurrence of one does not affect the other
   - dependent: occurrence of one affects the other

#### Some properties

<img src="images/events-properties.png" alt="events properties" style="display: block; margin: 0 auto; width: 400px;"/>