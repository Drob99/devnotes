# Chapter 6: Descriptive Statistics

## Table of Contents

- [Chapter 6: Descriptive Statistics](#chapter-6-descriptive-statistics)
  - [Table of Contents](#table-of-contents)
    - [Introduction \& Terminology](#introduction--terminology)
      - [Data Types](#data-types)
      - [Objectives](#objectives)
    - [6.1: Numerical Summaries of Data](#61-numerical-summaries-of-data)
    - [6.2: Stem-and-Leaf Diagrams](#62-stem-and-leaf-diagrams)
    - [6.3: Frequency Distributions and Histograms](#63-frequency-distributions-and-histograms)
      - [Frequency Table](#frequency-table)

---

### Introduction & Terminology

- The field of statistics consists of two branches, or rather two stages: descriptive statistics and inferential statistics.
- Using data collected from a small group (aka a sample) to draw conclusions about a larger group (aka a population) is known as **inferential statistics**.
- The aspect of statistics that deals with data collection, organization, summarization, and analysis is called **descriptive statistics**.
- As we will see, there are both numeric and graphic techniques that efficiently summarize the data and help the statistician interpret the data and be ready for subsequent analysis.
- Any good statistical analysis of data should always begin with **plotting the data**.
- As hinted above, a population are all the individuals of interest, whereas the sample is a randomly selected part of the population for analysis.
- A summary measure that describes a population characteristic is a **parameter**, whereas one that describes a sample is a **statistic**.
- As a simple example, assume two people wanted to find the number of first honor students in KFUPM.
  - Person A asked all the students in the university (population) about their honor status and came up with a conclusion that 20% of the students are first honor. This measure is a parameter.
  - Person B asked 30 random (we will discuss later how to measure randomness) students and determined that around 5 of those 30 are first honors. This number he found is a statistic that he can use to *estimate* the population parameter.
- To describe any data we usually study 3 features:
  - central tendency (center position in data set, like average)
  - variation (amount of spread in the values, like standard deviation)
  - shape (pattern of distribution of values from lowest to highest)

#### Data Types

- Data are divided into numeric and categorical.
- Numerical data are further divided into discrete and continuous. Discrete data are countable, e.g., the number of first honor students. Continuous data usually need a measuring tool, like time or weight.
- Categorical data are either nominal or ordinal. Nominal ones have no natural order (blood type, eye color, ...etc.), while ordinal ones have a natural order (freshman, sophomore, junior, senior).

#### Objectives

1. Compute and interpret the sample mean, sample variance, sample standard deviation, sample median, and sample range.
2. Explain the concepts of sample mean, sample variance, population mean, and population variance.
3. Construct and interpret visual data displays, including the stem-and-leaf display, the histogram, and the box plot.
4. Explain the concept of random sampling.
5. Construct and interpret normal probability plots.
6. Explain how to use box plots and other data displays to visually compare two or more samples of data.
7. Know how to use simple time series plots to visually display the important features of time-oriented data.
8. Know how to construct and interpret scatter diagrams of two or more variables.

### 6.1: Numerical Summaries of Data

### 6.2: Stem-and-Leaf Diagrams

- useful in organizing **numerical** data **graphically**.
- Suited for data set points with at least 2 digits.
- Steps of drawing one:
  1. Divide each number into two parts: a **stem**, consisting of one or more of the leading digits, and a **leaf**, consisting of the remaining digit.
  2. List the stem values in a vertical column.
  3. Record the leaf for each observation beside its stem.
  4. Write the units for stems and leaves on the display.
- It is usually good to have between 5 to 20 stems.
- They are 3 in 1: a graph (easily changed to bar chart), a table (could be changed to frequency table), and provide exact data values.
- Some stem-and-leaf plots have an extra column called frequency, where for each stem, the number of leaves is mentioned.
- We need a legend that explains the graph to know what to stems refer to (tens, hundreds, or other meanings)
- Sometimes you need to divide the stems into two or more groups to make a graph that visually describes the data better.
- If the leaves are ordered from lowest to highest in every stem, then it is an **ordered stem-and-leaf diagram**.

Below is an example from the book:

<img src="images/stem-and-leaf-example.png" alt="Stem and Leaf Example" style="display: block; margin: 0 auto; width: 400px;" />

### 6.3: Frequency Distributions and Histograms

- used for organizing **numerical data numerically**
- used for both continuous and discrete
- Data is gathered into **bins**, each defined by **class intervals**.

#### Frequency Table

- Steps:
    1. Sort if possible
    2. Find range $(R \approx max - min)$
    3. Find number of classes $(\lceil k \approx \sqrt{n} \rceil)$, where $n$ is num of observations.
    4. Find the width of a class interval $(\lceil C.W \approx \frac{R}{k} \rceil)$

- Notes:
  - must be mutually exclusive (Each value is in only ONE class.)
  - must be inclusive (all data values are represented)
  - different boundaries may provide different pictures for same data
  - When comparing two or more groups with different sample sizes, you must use either a relative frequency or a percentage distribution.

- If it is not clear, point number 4 basically means that it does not make any sense if I am comparing between two samples, where one has 100 and the other has 10 values, and I say that both have 2 values in a certain class. Obviously, 2/100 is NOT equivalent to 2/10. Hence, the use of relative frequency or percentage.
