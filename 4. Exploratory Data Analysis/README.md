# Exploratory Data Analysis

![picture](picture.jpg)

[Course Link](https://www.coursera.org/learn/exploratory-data-analysis?specialization=jhu-data-science)

This course covers the essential exploratory techniques for summarizing data.
 These techniques are typically applied before formal modeling commences and 
can help inform the development of more complex statistical models. Exploratory techniques
 are also important for eliminating or sharpening potential hypotheses about the world that
 can be addressed by the data. We will cover in detail the plotting systems in R as well
 as some of the basic principles of constructing data graphics. We will also cover some
 of the common multivariate statistical techniques used to visualize high-dimensional data.

**SKILLS YOU WILL GAIN** :
1. Cluster Analysis
2. Ggplot2
3. R Programming
4. Exploratory Data Analysis

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

install_course("Exploratory Data Analysis")

```



**Start swirl and complete the lessons** :

Type the following from the R console to start swirl:

```{r}

swirl()

```

Then, follow the menus and select the Exploratory Data Analysis course when given the option. For the first part of this course you should complete the following lessons:

1. Principles of Analytic Graphs
2. Exploratory Graphs
3. Graphics Devices in R
4. Plotting Systems
5. Base Plotting System

## Peer-graded Assignment: Course Project 1
>This assignment uses data from the UC Irvine Machine Learning Repository, a popular repository for machine learning datasets.
In particular, we will be using the “Individual household electric power consumption Data Set” which I have made available on the course web site:

Dataset: [Electric power consumption](https://d396qusza40orc.cloudfront.net/exdata%2Fdata%2Fhousehold_power_consumption.zip) [20Mb]

>Description: Measurements of electric power consumption in one household with a one-minute sampling rate over a period of almost 4 years.
 Different electrical quantities and some sub-metering values are available.
The following descriptions of the 9 variables in the dataset are taken from the [UCI web site](https://archive.ics.uci.edu/ml/datasets/Individual+household+electric+power+consumption):

1. Date: Date in format dd/mm/yyyy
2. Time: time in format hh:mm:ss
3. Global_active_power: household global minute-averaged active power (in kilowatt)
4. Global_reactive_power: household global minute-averaged reactive power (in kilowatt)
5. Voltage: minute-averaged voltage (in volt)
6. Global_intensity: household global minute-averaged current intensity (in ampere)
7. Sub_metering_1: energy sub-metering No. 1 (in watt-hour of active energy). It corresponds to the kitchen, containing mainly a dishwasher, an oven and a microwave (hot plates are not electric but gas powered).
8. Sub_metering_2: energy sub-metering No. 2 (in watt-hour of active energy). It corresponds to the laundry room, containing a washing-machine, a tumble-drier, a refrigerator and a light.
9. Sub_metering_3: energy sub-metering No. 3 (in watt-hour of active energy). It corresponds to an electric water-heater and an air-conditioner.

[Exploratory Data Analysis Repo](https://github.com/athos2113/ExData_Plotting1)



## Peer-graded Assignment: Course Project 2
>Fine particulate matter (PM2.5) is an ambient air pollutant for which there is strong evidence that it
 is harmful to human health. In the United States, the Environmental Protection Agency (EPA) is tasked with setting national
 ambient air quality standards for fine PM and for tracking the emissions of this pollutant into the atmosphere.
 Approximatly every 3 years, the EPA releases its database on emissions of PM2.5. This database is known as the National Emissions Inventory (NEI).
 You can read more information about the NEI at the EPA National Emissions Inventory web site.

>For each year and for each type of PM source, the NEI records how many tons of PM2.5 were emitted from that source over the course of the entire year.
 The data that you will use for this assignment are for 1999, 2002, 2005, and 2008.

The data for this assignment are available from the course web site as a [single zip file](https://d396qusza40orc.cloudfront.net/exdata%2Fdata%2FNEI_data.zip)


