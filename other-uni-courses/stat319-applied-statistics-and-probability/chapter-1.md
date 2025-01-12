# Chapter 1: The Role of Statistics in Engineering (Outside the Syllabus)

---

## Table Of Contents

- [Chapter 1: The Role of Statistics in Engineering (Outside the Syllabus)](#chapter-1-the-role-of-statistics-in-engineering-outside-the-syllabus)
  - [Table Of Contents](#table-of-contents)
    - [Introduction](#introduction)
    - [The Engineering Method and Statistical Thinking](#the-engineering-method-and-statistical-thinking)
    - [Collecting Engineering Data](#collecting-engineering-data)
    - [Mechanistic and Empirical Models](#mechanistic-and-empirical-models)
    - [Probability and Probability Models](#probability-and-probability-models)

---

### Introduction

> Just a quick note, I include a summary for this chapter, for it provides an overview of the course even though it is not explicitly in the syllabus.

- **Statistics** is a science that helps us make decisions and draw
conclusions in the presence of variability.
- Probability models that can be used to solve problems despite variability will be discussed in Chapters 2 through 5.
- Variability basically mean that it differs from a person to another, e.g, waiting times of patients in an emergency department.
- Producing a model to relate variables together could be done via regression analysis, discussed in Chapters 11 and 12.

### The Engineering Method and Statistical Thinking

- An engineer is someone who solves problems of interest to society by the efficient application of scientific principles. Usually, they do that by either refining an existing product or process or by designing a new product or process that meets customers’ needs.
- **The Engineering Method**
    1. Describe the problem.
    2. Identify the factors that affect or may play a role in solving it.
    3. Propose a model and state limitations or assumptions.
    4. Conduct experiments and collect data to test or validate.
    5. Refine model based on observed data.
    6. Manipulate model to assist in developing a solution.
    7. Conduct an experiment to confirm solution.
    8. Draw conclusions.
- Statistics is the science of data.
- By variability, we mean that successive observations of a system or phenomenon do not produce exactly the same result.
- Sources of variability
- A **random variable** is one that exhibits variability, like the waiting times mentioned above.

> A convenient way to think of a random variable, say $X$, that represents a measurement is by using the model:
>
>$$
>X = \mu + \epsilon
>$$
>
> where $\mu$ is a constant and $\epsilon$ is a random disturbance. We often want to ultimately reduce variability.

- In order to know that certain decisions would work and not disturb our data or previous findings, we use sampling in order to predict population behavior. This kind of reasoning is referred to as **statistical inference**. But of course, there are proper ways to choose the sample.

---

### Collecting Engineering Data

- A **census** is when the data is all the population observations.
- Three basic methods of collecting data are
  - retrospective study (historical data)
    - Solid and reliable explanations are often difficult to obtain. The study may involve a significant amount of data but with little useful information about the problem.
  - observational study 
  - designed experiment (deliberate change of controllable variables)
    - We sometimes want to compare results using hypothesis testing discussed in Chapter 9 and 10. It might be single-sample or two-sample.
    - Each factor is given a value known as a factor level. All combinations of factor levels are recommended to be tested to form a **factorial experiment**. It gives about insights of interactions between factors.
    - Unnecessary adjustments (over-control or tampering) can increase variability.
    - The use of a control charts is an invaluable way to examine the variability in time-oriented data.
    - The center line on the control chart is just the average of the concentration measurements for the first 20 samples. The upper control limit and the lower control limit are a pair of statistically derived limits that reflect the inherent or natural variability in the process. These limits are located 3 standard deviations of the concentration values above and below the center line. If the process is operating as it should without any external sources of variability present in the system, the concentration measurements should fluctuate randomly around the center line, and almost all of them should fall between the control limits.

---

### Mechanistic and Empirical Models

- **Mechanistic models** are built from our underlying knowledge of the basic physical mechanism that relate these variables.
- We can add a term to show variability like $\mu$.
- **Empirical Models** use our engineering and scientific knowledge of the phenomenon, but they are not directly developed from our theoretical understanding. A *regression model* is a famous example.

---

### Probability and Probability Models

- **Probability Models** help quantify the risks involved in statistical inference, i.e, the risks involved in decisions made every day.
- The probability that a particular process change is detected can be calculated with a probability model for concentration measurements. Models for continuous measurements are developed based on plausible assumptions for the data and a result known as the central limit theorem, and the associated normal distribution is a particularly valuable probability model for statistical inference.