# Peer-graded Assignment: Course Project 2

>Have total emissions from PM2.5 decreased in the United States from 1999 to 2008? Using the base plotting system, make a plot showing the total PM2.5 emission from all sources for each of the years 1999, 2002, 2005, and 2008. Upload a PNG file containing your plot addressing this question.

![plot1](plot1.PNG)


>Copy and paste the R code file for the plot uploaded in the previous question.

```{r}
#Reading the source file
NEI <- readRDS("summarySCC_PM25.rds")

#loading "dplyr" package
library(dplyr)

#Summarising the data, grouping them based on 'year'
total_emission <- summarise(group_by(NEI,year),Emissions=sum(Emissions))

color <- c("Purple","Red","Green","Black")

#plotting the basic graph
pl <- barplot(height=total_emission$Emissions/1000, names.arg=total_emission$year,
xlab="YEARS", ylab="Total Emission of PM2.5 in kilotons",col=color)

#saving the graph as a png file
dev.copy(png,file="Plot1.png")
dev.off()

```

>Have total emissions from PM2.5 decreased in the  Baltimore City, Maryland (fips == 24510) from 1999 to 2008? Use the base plotting system to make a plot answering this question.

>Upload a PNG file containing your plot addressing this question.

![plot2](plot2.PNG)

>Copy and paste the R code file for the plot uploaded in the previous question.

```{r}
#Reading the source file
NEI <- readRDS("summarySCC_PM25.rds")

#loading "dplyr" package
library(dplyr)

#filtering only the data for Baltimore City
NEI <- filter(NEI,fips == "24510")

##Summarising the data, grouping them based on 'year'
total_emission <- summarise(group_by(NEI,year),Emissions=sum(Emissions))

color <- c("Purple","Red","Green","Black")

#plotting the basic graph
pl <- barplot(height=total_emission$Emissions/1000, names.arg=total_emission$year,
xlab="YEARS", ylab="Total Emission of PM2.5 in kilotons",col=color,main="Total PM2.5 Emission in Baltimore City in kilotons",ylim=c(0,4))

#saving the graph as a png file
dev.copy(png,file="plot2.png")
dev.off(

```

>Of the four types of sources indicated by the type (point, nonpoint, onroad, nonroad) variable, which of these four sources have seen decreases in emissions from 1999–2008 for Baltimore City? Which have seen increases in emissions from 1999–2008? Use the ggplot2 plotting system to make a plot answer this question.

>Upload a PNG file containing your plot addressing this question.

![plot3](plot3.PNG)

>Copy and paste the R code file for the plot uploaded in the previous question.

```{r}
#Reading the source file
NEI <- readRDS("summarySCC_PM25.rds")

#Reading the "dplyr" and "ggplot2" package
library(ggplot2)
library(dplyr)

#Filtering the data: selecting only the data for Baltimore City
baldata <- filter(NEI,fips == "24510")

#Grouping the data based on year and type
total_emission <- summarise(group_by(baldata,year,type), Emissions=sum(Emissions))

#Plotting the ggplot graph
g <- ggplot(total_emission, aes(x=factor(year), y=Emissions,fill=type,label=round(Emissions,2)))

#Adding more components to the graph
g <- g+ geom_bar(stat="identity")+facet_grid(.~type)+xlab("year")+ylab("total PM2.5 Emission in tons")
g <- g + ggtitle("PM 2.5 Emissions in Baltimore")+ geom_label(aes(fill=type),color="white")

print(g)

#Saving the graph as a png file
dev.copy(png,title="plot3.png")
dev.off()
```


>Across the United States, how have emissions from coal combustion-related sources changed from 1999–2008?

>Upload a PNG file containing your plot addressing this question.

![plot4](plot4.PNG)

>Copy and paste the R code file for the plot uploaded in the previous question.

```{r}
#Reading the source files
NEI <- readRDS("summarySCC_PM25.rds")
SCC <- readRDS("Source_Classification_Code.rds")

#Loading the "dplyr" and "ggplot2" package
library(ggplot2)
library(dplyr)

#Using 'grepl' function to find coal combusting related sources
coal <- grepl("Fuel Comb.*Coal", SCC$EI.Sector)
coal <- SCC[coal,]

#Grouping the data based on year
total_emission <- summarise(group_by(coal_emission,year),Emissions=sum(Emissions))

#Plotting the graph using 'ggplot' function
g <- ggplot(total_emission,aes(x=factor(year),y=Emissions/1000,fill=year, label=round(Emissions/1000,2)))
g <- g + geom_bar(colour="black", stat="identity") + xlab("Years") + ylab("Emission of PM2.5") + ggtitle("Coal Combustion-related Sources Changes from 1999?2008")
print(g)

#Saving the graph as a png file
dev.copy(png,file="plot4.png") 
dev.off()
```


>How have emissions from motor vehicle sources changed from 1999–2008 in Baltimore City?

>Upload a PNG file containing your plot addressing this question.

![plot5](plot5.PNG)

>Copy and paste the R code file for the plot uploaded in the previous question.

```{r}
#Reading the source files
NEI <- readRDS("summarySCC_PM25.rds")

#Loading the "dplyr" package
library(dplyr)

#Selecting Emissions from Baltimore City from motor vehicle sources
data <- filter(NEI, fips=="24510" & type=="ON-ROAD") 

color <- c("Purple","Red","Green","Black")

#Grouping the data based on year
total_emission <- summarise(group_by(data,year), emission=sum(Emissions))

#Plotting the basic graph
pl <- barplot(height=total_emission$emission,ylim=c(0,400), names.arg=total_emission$year,col=color, xlab="Years", ylab="PM 2.5 Emission",main="Emissions
From Motor Vehicle Sources ranging from 1999 to 2008 in Baltimore City")

#Saving the graph as a png file
dev.copy(png,file="plot5.png") 
dev.off()
```


>Compare emissions from motor vehicle sources in Baltimore City with emissions from motor vehicle sources in Los Angeles County, California (fips==06037). Which city has seen greater changes over time in motor vehicle emissions?

>Upload a PNG file containing your plot addressing this question.

![plot6](plot6.PNG)

>Copy and paste the R code file for the plot uploaded in the previous question.

```{r}
#Loading the "dplyr" and "ggplot2" package
library(dplyr)
library(ggplot2)

#Reading the source file
NEI <- readRDS("summarySCC_PM25.rds")

#Selecting Emissions from Baltimore City from motor vehicle sources
baltimore <- filter(NEI, fips=="24510" & type=="ON-ROAD")

#Selecting Emissions from Los-Angeles from motor vehicle sources
los <- filter(NEI, fips=="06037" & type=="ON-ROAD")

#Summarisng and Grouping the Emission based on year
total_emission_bal <- summarise(group_by(baltimore,year), emission=sum(Emissions))
total_emission_los <- summarise(group_by(los,year), emission=sum(Emissions))

#Joining the rows of Total Emission of Baltimore and Los-Angeles
total_emission_mrg <- rbind(total_emission_bal,total_emission_los)

#Adding a new column "County"
total_emission_mrg$county <- c(rep("BALTIMORE",4),rep("LOS ANGELES",4))

#Converting the County rows to Factor class
total_emission_mrg$county <- as.factor(total_emission_mrg$county)

#Plotting the ggplot and adding more layers in each step
g <- ggplot(total_emission_mrg, aes( x=factor(year), y=emission, label=round(emission,2), fill=year))
g <- g + geom_bar(stat="identity")
g <- g+ facet_grid(county~.)
g <- g+ xlab("Years") + ylab("PM 2.5 Emission in tons") + ggtitle("Motor Vehicle Emissions in Baltimore and Los Angeles in tons ")
g <- g+ facet_grid(.~county,scales="free")


print(g)

#Saving the plot as a png file
dev.copy(png,file="plot6.png") 
dev.off()
```