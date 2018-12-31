# R Programming

![picture](picture.jpg)

[Course Link](https://www.coursera.org/learn/r-programming?specialization=jhu-data-science)

In this course you will learn how to program in R and how to use R for effective data analysis.
You will learn how to install and configure software necessary for a statistical programming 
environment and describe generic programming language concepts as they are implemented in a high-level
statistical language. The course covers practical issues in statistical computing which includes programming in R,
reading data into R, accessing R packages, writing R functions, debugging, profiling R code, and organizing
and commenting R code. Topics in statistical data analysis will provide working examples.

## SKILLS YOU WILL GAIN
1. Data Analysis
2. Debugging
3. R Programming
4. Rstudio

##Practical R Exercises in Swirl
During this course we'll be using the swirl software package for R in order to illustrate some key concepts.
The swirl package turns the R console into an interactive learning environment. Using swirl will also give you
the opportunity to be completely immersed in an authentic R programming environment. In this programming assignment,
you'll have the opportunity to practice some key concepts from this course.

**1. Install R** :

swirl requires R 3.1.0 or later. If you have an older version of R, please update before going any further.
If you're not sure what version of R you have, 
type R.version.string at the R prompt. 
You can download the latest version of R from (https://www.r-project.org/.)


Optional but highly recommended: Install RStudio.
You can download the latest version of RStudio at (https://www.rstudio.com/products/rstudio/.)

**2. Install Swirl** : 

Since swirl is an R package, you can easily install it by entering
a single command from the R console:


```{r}

install.packages("swirl")

```

If you've installed swirl in the past make sure you have version 2.4.2 or later.
You can check this with:

```{r}

packageVersion("swirl")

```



**Load swirl** :

Every time you want to use swirl, you need to first load the package. From the R console:


```{r}

library(swirl)

```

** Install the R Programming Environment course** :

swirl offers a variety of interactive courses, but for our purposes, you want the one called

The R Programming Environment. Type the following from the R prompt to install this course:


```{r}

install_course("R Programming")

```



**Start swirl and complete the lessons** :

Type the following from the R console to start swirl:

```{r}

swirl()

```

Then, follow the menus and select the R Programming course when given the option. For the first part of this course you should complete the following lessons:

1. Basic Building Blocks
2. Workspace and Files
3. Sequences of Numbers
4. Vectors
5. Missing Values
6. Subsetting Vectors
7. Matrices and Data Frames



##Peer-graded Assignment: Programming Assignment : Lexical Scoping
>programming assignment will require you to write an R function is able to cache potentially
time-consuming computations. For example, taking the mean of a numeric vector is typically a
fast operation. However, for a very long vector, it may take too long to compute the mean,
especially if it has to be computed repeatedly (e.g. in a loop). If the contents of a vector are not changing,
it may make sense to cache the value of the mean so that when we need it again, it can be looked up
in the cache rather than recomputed. In this Programming Assignment will take advantage of the scoping rules
of the R language and how they can be manipulated to preserve state inside of an R object.

**Assignment: Caching the Inverse of a Matrix**:
>Matrix inversion is usually a costly computation and there may be some benefit
to caching the inverse of a matrix rather than compute it repeatedly (there are also alternatives to matrix inversion that we will not discuss here).
Your assignment is to write a pair of functions that cache the inverse of a matrix.

Write the following functions:

1. makeCacheMatrix: This function creates a special "matrix" object that can cache its inverse.
2. cacheSolve: This function computes the inverse of the special "matrix" returned by makeCacheMatrix above. If the inverse has already been calculated (and the matrix has not changed), then the cachesolve should retrieve the inverse from the cache.
 Computing the inverse of a square matrix can be done with the solve function in R. For example, if X is a square invertible matrix, then solve(X) returns its inverse.

For this assignment, assume that the matrix supplied is always invertible.

[Link to Assignment Repo](https://github.com/athos2113/ProgrammingAssignement2)
