My First R Markdown File
========================

This is my first R markdown file.

Here, we're going to load some data.


```r
library(datasets)
data(airquality)
summary(airquality)
```

```
##      Ozone          Solar.R         Wind            Temp     
##  Min.   :  1.0   Min.   :  7   Min.   : 1.70   Min.   :56.0  
##  1st Qu.: 18.0   1st Qu.:116   1st Qu.: 7.40   1st Qu.:72.0  
##  Median : 31.5   Median :205   Median : 9.70   Median :79.0  
##  Mean   : 42.1   Mean   :186   Mean   : 9.96   Mean   :77.9  
##  3rd Qu.: 63.2   3rd Qu.:259   3rd Qu.:11.50   3rd Qu.:85.0  
##  Max.   :168.0   Max.   :334   Max.   :20.70   Max.   :97.0  
##  NA's   :37      NA's   :7                                   
##      Month           Day      
##  Min.   :5.00   Min.   : 1.0  
##  1st Qu.:6.00   1st Qu.: 8.0  
##  Median :7.00   Median :16.0  
##  Mean   :6.99   Mean   :15.8  
##  3rd Qu.:8.00   3rd Qu.:23.0  
##  Max.   :9.00   Max.   :31.0  
## 
```

Let's first make a pairs plot of the data.


```r
pairs(airquality)
```

![plot of chunk unnamed-chunk-2](figure/unnamed-chunk-2.png) 

Here is a regression model of ozone on wind, solar rediation, and temperature.


```r
library(datasets)
data(airquality)
fit <- lm(Ozone ~ Wind + Temp + Solar.R, data = airquality)
```


```r
library(xtable)
xt <- xtable(summary(fit))
print(xt, type = "html")
```

<!-- html table generated in R 3.0.2 by xtable 1.7-3 package -->
<!-- Mon Jun 09 14:55:50 2014 -->
<TABLE border=1>
<TR> <TH>  </TH> <TH> Estimate </TH> <TH> Std. Error </TH> <TH> t value </TH> <TH> Pr(&gt;|t|) </TH>  </TR>
  <TR> <TD align="right"> (Intercept) </TD> <TD align="right"> -64.3421 </TD> <TD align="right"> 23.0547 </TD> <TD align="right"> -2.79 </TD> <TD align="right"> 0.0062 </TD> </TR>
  <TR> <TD align="right"> Wind </TD> <TD align="right"> -3.3336 </TD> <TD align="right"> 0.6544 </TD> <TD align="right"> -5.09 </TD> <TD align="right"> 0.0000 </TD> </TR>
  <TR> <TD align="right"> Temp </TD> <TD align="right"> 1.6521 </TD> <TD align="right"> 0.2535 </TD> <TD align="right"> 6.52 </TD> <TD align="right"> 0.0000 </TD> </TR>
  <TR> <TD align="right"> Solar.R </TD> <TD align="right"> 0.0598 </TD> <TD align="right"> 0.0232 </TD> <TD align="right"> 2.58 </TD> <TD align="right"> 0.0112 </TD> </TR>
   </TABLE>
