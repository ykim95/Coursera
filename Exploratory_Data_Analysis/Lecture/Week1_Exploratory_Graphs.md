#Exploratory Graphs

## Why do we use graphs in data analysis?
    - To understand Properties
    - To find patterns in data
    - To suggest modeling strategies
    - To "Debug" analysis
    - To communicate results

## Characteristics of Exploratory Graphs
    - Quickly
    - Large number are made
    - Goals : personal understanding
    - Axis/legend : cleaned up
    - Colar/size : primarily used for info
    
### Air Pollution in the US
    
    pollution<-read.csv("data/avgpm25.csv", colClasses = c("numeric", "character", "factor", "numeric", "numeric"))
    head(pollution)

###  want to Check standard > 12 micro/m^3

###Simple Summaries of Data
    One dim : Five-number summary, Boxplots, Histograms, Density plot, Bar plot

### Five Number Summary
    summary(pollution$pm25)
### Box plot
    boxplot(pollution$pm25, col="blue")
    abline(h = 12) #horizontal line leve=12

    hist(pollution$pm25, col ="green", breaks=100) #shape of dist
    rug(pollution$pm25)                #more detail!

    abline(v = 12, lwd = 2)
    abline(v = median(pollution$pm25), col = "magenta", lwd =4)

    *v   : location of the line
    *col : color of the line
    *lwd : thickeness of the line

    barplot(table(pollution$region), col = "wheat", main = "Number of the certification")
