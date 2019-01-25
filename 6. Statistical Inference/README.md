# Reproducible Research

![picture](picture.jpg)

[Course Link](https://www.coursera.org/learn/statistical-inference)

Statistical inference is the process of drawing conclusions about populations or scientific
 truths from data. There are many modes of performing inference including statistical modeling,
 data oriented strategies and explicit use of designs and randomization in analyses.
 Furthermore, there are broad theories (frequentists, Bayesian, likelihood, design based, …)
 and numerous complexities (missing data, observed and unobserved confounding, biases) 
for performing inference. A practitioner can often be left in a debilitating maze of 
techniques, philosophies and nuance. This course presents the fundamentals of inference
 in a practical approach for getting things done. After taking this course, students
 will understand the broad directions of statistical inference and use this information
 for making informed choices in analyzing data.

**SKILLS YOU WILL GAIN** :

1. Statistics
2. Statistical Inference
3. Statistical Hypothesis Testin
2. Data Analysis



## Peer-graded Assignment: Course Project
The project consists of two parts:

1. A simulation exercise.
2. Basic inferential data analysis.

**Part 1: Simulation Exercise Instructions**
In this project you will investigate the exponential distribution in R and compare it
 with the Central Limit Theorem. The exponential distribution can be simulated in R with
 rexp(n, lambda) where lambda is the rate parameter. The mean of exponential distribution
 is 1/lambda and the standard deviation is also 1/lambda. Set lambda = 0.2 for all of the simulations.
 You will investigate the distribution of averages of 40 exponentials.
 Note that you will need to do a thousand simulations.

Illustrate via simulation and associated explanatory text the properties of the
 distribution of the mean of 40 exponentials. You should

1. Show the sample mean and compare it to the theoretical mean of the distribution.
2. Show how variable the sample is (via variance) and compare it to the theoretical variance of the distribution.
3. Show that the distribution is approximately normal.

In point 3, focus on the difference between the distribution of a large collection of random exponentials and the distribution of a large collection of averages of 40 exponentials.

As a motivating example, compare the distribution of 1000 random uniforms

```{r}
hist(runif(1000))
```

and the distribution of 1000 averages of 40 random uniforms

```{r}
mns = NULL
for (i in 1 : 1000) mns = c(mns, mean(runif(40)))
hist(mns)
```


**Part 2: Basic Inferential Data Analysis Instructions**
Now in the second portion of the project, we're going to analyze the ToothGrowth data in the R datasets package.

1. Load the ToothGrowth data and perform some basic exploratory data analyses
2. Provide a basic summary of the data.
3. Use confidence intervals and/or hypothesis tests to compare tooth growth by supp and dose. (Only use the techniques from class, even if there's other approaches worth considering)
4. State your conclusions and the assumptions needed for your conclusions.

