# Shared Computing Cloud - via R - Practice

#library
```{r}
library(sas7bdat)
```
#to read in a sas7bdat
```{r}
hw4 <- read.sas7bdat("/project/bs803/fhs.sas7bdat")
```
#new var
```{r}
hw4$MAP = hw4$SYSBP/3 + 2*hw4$DIABP/3
```
#summary statistics
```{r}
print(summary(hw4$MAP)["Max."])
print(summary(hw4$MAP)["Min."])
print(summary(hw4$MAP)["Mean"])
print("standard deviation")
print(sd((hw4$MAP)))
```
#linear regression
```{r}
print(lm(MAP~AGE, hw4))
print(lm(MAP~AGE, hw4)$coefficients)
```
#submit job to SCC - computing folder - BS803_Hsu_M
```{r}
print(Sys.getenv('JOB_ID'))
```
