1. **Examine the “mtcars” dataset using `head` and `summary` functions**
```r
data(mtcars)
head(mtcars)
summary(mtcars)
```
**Attributes and types:**
- Nominal: cyl, vs, am, gear, carb
- Discrete: cyl, gear, carb
- Continuous: mpg, disp, hp, drat, wt, qsec

2. **Create a scatter plot of Sepal.Length and Petal.Length from the iris dataset**
```r
data(iris)
plot(iris$Sepal.Length, col="r", xlab="Index", ylab="Length", main="Sepal and Petal Lengths")
points(iris$Petal.Length, col="b")
legend("bottom", legend=c("Sepal.Length", "Petal.Length"), col=c("r","b"), pch=1)
```

3. **Calculate average mpg by cyl and absolute difference in horsepower**
```r
a<-aggregate(mpg~cyl, data=mtcars, FUN=mean)
print(a)
b<-mean(mtcars$hp[mtcars$cyl==4])
c<-mean(mtcars$hp[mtcars$cyl==8])
d<-abs(b-c)
print(d)
```

4. **Create different types of vectors**
```r
a<-c(1,2,3,4,5)
print(a)
b<-c("a","b","c","d","e")
print(b)
c<-c(T,F,T,F,T)
print(c)
```

5. **Create a data frame with three columns**
```r
a<-data.frame(name=c("John","Jane","Doe"), age=c(25,30,22), is_student=c(T,F,T))
print(a)
```

6. **Create a scatter plot of mpg vs hp using base plotting system**
```r
plot(mtcars$mpg, mtcars$hp, xlab="Miles per Gallon", ylab="Horsepower", main="mpg vs hp")
```

7. **Create a simple ggplot2 scatter plot of mpg vs hp**
```r
library(ggplot2)
ggplot(mtcars, aes(x=mpg, y=hp)) +
geom_point() +
labs(title="mpg vs hp", x="Miles per Gallon", y="Horsepower")
```

8. **Plot a histogram of mpg using base plotting system and ggplot2**
```r
hist(mtcars$mpg, xlab="Miles per Gallon", main="Histogram of mpg")
ggplot(mtcars, aes(x=mpg)) +
geom_histogram(bins=10) +
labs(title="Histogram of mpg", x="Miles per Gallon")
```

9. **Create a box plot of mpg grouped by cyl using base plotting system and ggplot2**
```r
boxplot(mpg~cyl, data=mtcars, xlab="Number of Cylinders", ylab="Miles per Gallon", main="mpg grouped by cyl")
ggplot(mtcars, aes(x=factor(cyl), y=mpg)) +
geom_boxplot() +
labs(title="mpg grouped by cyl", x="Number of Cylinders", y="Miles per Gallon")
```

10. **Create a bar plot of the number of cars with different numbers of cylinders using base plotting system and ggplot2**
```r
barplot(table(mtcars$cyl), xlab="Number of Cylinders", ylab="Number of Cars", main="Number of cars by cylinders")
ggplot(mtcars, aes(x=factor(cyl))) +
geom_bar() +
labs(title="Number of cars by cylinders", x="Number of Cylinders", y="Number of Cars")
```

11. **Create a line plot of mpg vs wt using base plotting system and ggplot2**
```r
plot(mtcars$wt, mtcars$mpg, type="l", xlab="Weight", ylab="Miles per Gallon", main="mpg vs wt")
ggplot(mtcars, aes(x=wt, y=mpg)) +
geom_line() +
labs(title="mpg vs wt", x="Weight", y="Miles per Gallon")
```

12. **Create a scatter plot of mpg vs wt with a regression line using ggplot2**
```r
ggplot(mtcars, aes(x=wt, y=mpg)) +
geom_point() +
geom_smooth(method="lm") +
labs(title="mpg vs wt with regression line", x="Weight", y="Miles per Gallon")
```

13. **Create a scatter plot of mpg vs wt using ggplot2**
```r
ggplot(mtcars, aes(x=wt, y=mpg)) +
geom_point() +
labs(title="mpg vs wt", x="Weight", y="Miles per Gallon")
```

14. **Create a box plot for mpg grouped by cyl using ggplot2**
```r
ggplot(mtcars, aes(x=factor(cyl), y=mpg)) +
geom_boxplot() +
labs(title="mpg grouped by cyl", x="Number of Cylinders", y="Miles per Gallon")
```

15. **Create a box plot for mpg grouped by cyl using base R**
```r
boxplot(mpg~cyl, data=mtcars, xlab="Number of Cylinders", ylab="Miles per Gallon", main="mpg grouped by cyl")
```

16. **Create a scatter plot of mpg vs wt with points colored by cyl and different shapes for gear using ggplot2**
```r
ggplot(mtcars, aes(x=wt, y=mpg, color=factor(cyl), shape=factor(gear))) +
geom_point() +
labs(title="mpg vs wt colored by cyl and shaped by gear", x="Weight", y="Miles per Gallon")
```

17. **Create a scatter plot of mpg vs wt with custom title, axis labels, and subtitle using ggplot2**
```r
ggplot(mtcars, aes(x=wt, y=mpg)) +
geom_point() +
labs(title="Scatter plot of mpg vs wt", subtitle="Custom subtitle", x="Weight", y="Miles per Gallon")
```

18. **Calculate mean mpg for each number of cylinders using dplyr**
```r
library(dplyr)
mtcars %>% group_by(cyl) %>% summarise(mean_mpg=mean(mpg))
```

19. **Create a bar plot of the number of cars for each cylinder count using ggplot2**
```r
ggplot(mtcars, aes(x=factor(cyl))) +
geom_bar() +
labs(title="Number of cars by cylinders", x="Number of Cylinders", y="Number of Cars")
```

20. **Create a pie chart of the cylinder count using base R**
```r
a<-table(mtcars$cyl)
pie(a, main="Pie chart of cylinder counts")
```

21. **Create a histogram of mpg using ggplot2**
```r
ggplot(mtcars, aes(x=mpg)) +
geom_histogram(bins=10) +
labs(title="Histogram of mpg", x="Miles per Gallon")
```

22. **Create a boxplot of mpg grouped by cyl using ggplot2**
```r
ggplot(mtcars, aes(x=factor(cyl), y=mpg)) +
geom_boxplot() +
labs(title="mpg grouped by cyl", x="Number of Cylinders", y="Miles per Gallon")
```

23. **Create a scatter plot of mpg vs wt colored by cyl using ggplot2**
```r
ggplot(mtcars, aes(x=wt, y=mpg, color=factor(cyl))) +
geom_point() +
labs(title="mpg vs wt colored by cyl", x="Weight", y="Miles per Gallon")
```

24. **Create a scatter plot of mpg vs wt with customized legend using ggplot2**
```r
ggplot(mtcars, aes(x=wt, y=mpg, color=factor(cyl))) +
geom_point() +
labs(title="mpg vs wt colored by cyl", x="Weight", y="Miles per Gallon") +
theme(legend.title=element_text(text="Cylinders"), legend.position="bottom")
```

25. **Examine the mpg attribute in more detail**
```r
a<-mtcars$mpg
b<-mean(a)
c<-var(a)
d<-sd(a)
print(b)
print(c)
print(d)
boxplot(a, main="Boxplot of mpg", ylab="Miles per Gallon")
e<-boxplot.stats(a)$out
print(e)
```

26. **Create a histogram for MPG using the MASS library**
```r
install.packages("MASS")
library(MASS)
truehist(a, nbins=10, main="Histogram of mpg", xlab="Miles per Gallon")
```

27. **Examine the relationship between mpg and hp**
```r
a<-mtcars$hp
plot(a, b, xlab="Horsepower", ylab="Miles per Gallon", main="HP vs MPG")
c<-cor(a, b)
print(c)
```
