# R Cheatsheet

### Data selection
```
df[row,col]
df[,col]
df[row,]
df$col
```

### Env preperation
```
set.seed(420)
if (!require("pacman")) install.packages("pacman")
library("pacman")

if (!require('ggplot2')) install.packages('ggplot2'); library('ggplot2')

setwd(path)
pwd<-getwd()
read.csv(file,sep,header) # pd.read_csv()
read_excel(file,col_names)
```

### Usefull R functions (# pandas equivalents)
```
str() # dtypes attr 
? # select_dtypes(int)
summary() # describe method
dim(df) # shape method/attr?
length(df) # n-wierszy
nrow(df)
na.omit(df) # dropna method
na.approx(df,na.rm = FALSE) //interpolacja
complete.cases(df)
colnames(df) <- c("col1","col2")
rownames(df) <- series
as.numeric(), as.factor()
cbind(vector1, vector2)
cbind.data.frame(name1=df1, name2=df2)
table()
shift(series, n)
paste("string ","1")
ifelse(series1 == "ok",0,1)
lm(Y~.,data)
seq()
predict(model, df_test)
```

### Plotting

```
par(mfrow=c(1,2)) # ?
plot(x,y,col,type) # plt.figure(figsize=(12,8))  or plot method
plot.ts() 
lines()
hist() # hist method
boxplot() #?
ggplot(df, aes(x, y, shape, color) + geom_point() #plt.?
```

### Train/test split
```
idx <- sample(seq_len(nrow(df)), size = floor(nrow(df)/3))
train <- df[-idx,]
test <- df[idx,]
```
Warto sprawdzić, czy rozkłady *train* i *test* są podobne i odpowiednio zbilansowane (np. describe).

### Loop in R
```
for (i in 1:100){
  print(i)
}
```

### Usefull packages
```
library("ggplot2") # better plots
library("tictoc") # tic() to start the timer, toc() to stop
library("caret") # Classification And REgression Training, hyperparameters tuning
```
---
###### Zapalski Mikolaj, [@thezapalsky](https://thezapalsky.github.io)