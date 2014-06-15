## Reproducible Research: Peer Assessment 1

### Initial Preparation
Before we get started on answering the questions, make sure of the following:

- Fork the RepData_PeerAssessment1 directory at github
- Use the `setwd("path/where/the/files/are/located")`
- Unzip the activity.zip file to obtain activty.csv file


### Loading and preprocessing the data

Load the data into R:


```r
activity <- read.csv("activity.csv", header=T)
```

To see what kind of variables are listed in the activity data frame


```r
str(activity)
```

```
## 'data.frame':	17568 obs. of  3 variables:
##  $ steps   : int  NA NA NA NA NA NA NA NA NA NA ...
##  $ date    : Factor w/ 61 levels "2012-10-01","2012-10-02",..: 1 1 1 1 1 1 1 1 1 1 ...
##  $ interval: int  0 5 10 15 20 25 30 35 40 45 ...
```

The variables are steps, date and interval. Note that date variable is a factor. And there are 61 levels. Therefore the total number of days are 61.

### What is mean total number of steps taken per day?

To get the average number of steps per day we sum the total number of steps and divide that number by the number of levels in the date variable.


```r
totalSteps <- sum(activity$steps, na.rm=TRUE)  # Total number of steps
avgSteps <- totalSteps/nlevels(activity$date)  # Divide the total by the number of days
print(avgSteps)
```

```
## [1] 9354
```
The mean total number of steps taken per day is 9354.2295.

### What is the average daily activity pattern?



### Imputing missing values



### Are there differences in activity patterns between weekdays and weekends?


Convert the date variable into a proper R date variable


```r
activity[,2] <- as.Date(activity[,2]) # The second column is the date variable
class(activity$date)                  # To ensure that the date variable is the date format
```

```
## [1] "Date"
```
