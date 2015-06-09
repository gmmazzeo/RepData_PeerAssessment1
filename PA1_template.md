# Reproducible Research: Peer Assessment 1


## Loading and preprocessing the data

First unzip data and load them into a data table

```r
library(data.table)
f <- unzip("activity.zip")
dt <- data.table(read.csv(f))
```
Then the uncompressed file can be deleted

```r
invisible(file.remove(f))
```
Let's look a the structure of the file

```r
str(dt)
```

```
## Classes 'data.table' and 'data.frame':	17568 obs. of  3 variables:
##  $ steps   : int  NA NA NA NA NA NA NA NA NA NA ...
##  $ date    : Factor w/ 61 levels "2012-10-01","2012-10-02",..: 1 1 1 1 1 1 1 1 1 1 ...
##  $ interval: int  0 5 10 15 20 25 30 35 40 45 ...
##  - attr(*, ".internal.selfref")=<externalptr>
```
The date needs to be converted, since it is represented as factor. Then, it can be set as key of the table.

```r
dt$date <- as.Date(dt$date, format = "%Y-%m-%d")
setkey(dt, date)
str(dt)
```

```
## Classes 'data.table' and 'data.frame':	17568 obs. of  3 variables:
##  $ steps   : int  NA NA NA NA NA NA NA NA NA NA ...
##  $ date    : Date, format: "2012-10-01" "2012-10-01" ...
##  $ interval: int  0 5 10 15 20 25 30 35 40 45 ...
##  - attr(*, ".internal.selfref")=<externalptr> 
##  - attr(*, "sorted")= chr "date"
```
## What is mean total number of steps taken per day?



## What is the average daily activity pattern?



## Imputing missing values



## Are there differences in activity patterns between weekdays and weekends?
