# PA1. Reproducible Research, by Coursera
# amaurandi@um.es
# 5.Junio.2014
----------------------------------------




# Loading and processing the data

Exploration of the data and data structure.  
  

```r
df <- read.table("activity.csv", sep = ",", header = T)
sdf <- summary(df)
xt <- xtable(sdf)

print(xt, type = "html")
```

<!-- html table generated in R 3.1.0 by xtable 1.7-3 package -->
<!-- Fri Jun  6 12:11:40 2014 -->
<TABLE border=1>
<TR> <TH>  </TH> <TH>     steps </TH> <TH>         date </TH> <TH>    interval </TH>  </TR>
  <TR> <TD align="right"> 1 </TD> <TD> Min.   :  0   </TD> <TD> 2012-10-01:  288   </TD> <TD> Min.   :   0   </TD> </TR>
  <TR> <TD align="right"> 2 </TD> <TD> 1st Qu.:  0   </TD> <TD> 2012-10-02:  288   </TD> <TD> 1st Qu.: 589   </TD> </TR>
  <TR> <TD align="right"> 3 </TD> <TD> Median :  0   </TD> <TD> 2012-10-03:  288   </TD> <TD> Median :1178   </TD> </TR>
  <TR> <TD align="right"> 4 </TD> <TD> Mean   : 37   </TD> <TD> 2012-10-04:  288   </TD> <TD> Mean   :1178   </TD> </TR>
  <TR> <TD align="right"> 5 </TD> <TD> 3rd Qu.: 12   </TD> <TD> 2012-10-05:  288   </TD> <TD> 3rd Qu.:1766   </TD> </TR>
  <TR> <TD align="right"> 6 </TD> <TD> Max.   :806   </TD> <TD> 2012-10-06:  288   </TD> <TD> Max.   :2355   </TD> </TR>
  <TR> <TD align="right"> 7 </TD> <TD> NA's   :2304   </TD> <TD> (Other)   :15840   </TD> <TD>  </TD> </TR>
   </TABLE>


He have arround 288 observations per day.

# What is mean total number of steps taken per day?



```r
# no account of misssign values
df1 <- na.omit(df)
su <- tapply(df1$steps, df1$date, sum)
su <- as.numeric(su)
```


Histogram of total number of steps per day

```r
hist(su, main = "Histogram of the total steps by day", breaks = 50, freq = T)
```

<img src="figure/histograma.png" title="plot of chunk histograma" alt="plot of chunk histograma" style="display: block; margin: auto;" />






The mean of the total step per day is 10766.189 and the median is 10765.

# What is the average daily activity pattern?






















# Imputing missing values


# Are there differences in activity patterns between weekdays and weekends?












```r
sessionInfo()
```

R version 3.1.0 beta (2014-03-28 r65330)
Platform: i686-pc-linux-gnu (32-bit)

locale:
 [1] LC_CTYPE=es_ES.UTF-8       LC_NUMERIC=C              
 [3] LC_TIME=es_ES.UTF-8        LC_COLLATE=es_ES.UTF-8    
 [5] LC_MONETARY=es_ES.UTF-8    LC_MESSAGES=es_ES.UTF-8   
 [7] LC_PAPER=es_ES.UTF-8       LC_NAME=C                 
 [9] LC_ADDRESS=C               LC_TELEPHONE=C            
[11] LC_MEASUREMENT=es_ES.UTF-8 LC_IDENTIFICATION=C       

attached base packages:
[1] stats     graphics  grDevices utils     datasets  methods   base     

other attached packages:
[1] xtable_1.7-3 knitr_1.5   

loaded via a namespace (and not attached):
[1] evaluate_0.5.3 formatR_0.10   stringr_0.6.2  tools_3.1.0   


















