##R commands for Machine Learning (to be continued...)

#Data collection

- setwd("~/Centrale/Machine Learning/Bike")
- train <- read.csv("train.csv")


#First approach

- str(train)
- summary(train)
- head(train)
- names(train) : to get the features


#Data visualization

- library(Amelia) missmap(train, main="Train set - Missings Map", col=c("red", "black"), legend=FALSE) : map of missing values
- hist(train$Age, main = "Age", xlab = NULL, col = "black") : histogram, for continuous numeric values
- barplot(table(train$Sex), main = "Sex", col = "black") : for discrete values
- library(vcd) mosaicplot(train$Pclass ~ train$Survived, main="Effect of Pclass", shade=FALSE, color=TRUE, xlab="Pclass", ylab="Survived") : effect of an explicative discrete variable on the discrete response
- boxplot(train$Age ~ train$Survived, main="Effect of Age", xlab="Survived", ylab="Age") : effect of an explicative continuous variable on the discrete response 


#Missing value

- library(Amelia) missmap(train, main="Train set - Missings Map", col=c("red", "black"), legend=FALSE) : map of missing values
- library(Hmisc) train$Age <- with(train, impute(Age, median))


#Data preparation

- tot <- rbind(train, test)
- tot$season <- factor(tot$season)
- tot$time <- sapply(tot$datetime, function(x){substr(x,12,13)})


#Aggregation

- aggregate(tot[,10:12], by=list(tot$day), FUN=mean)
- library(Hmisc) bystats(train$Age, train$Title,  fun=function(x)c(Mean=mean(x),Median=median(x)))


#Commands for char 

- substr()
- strsplit
- gsub()
- substr()


#Subsetting 

- which(train$Survive == 1)
- is.na(train$Age)
- length(train$Fare[train$Fare==0])
- subset(train, Fare <7, select = c(Pclass,Sex,Age,TTitle))


#Calculus 

- median(train$Age, na.rm = TRUE))
- mean()







