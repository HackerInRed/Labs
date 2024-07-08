1. **Examine the “mtcars” dataset using `head` and `summary` functions**
```r
# Load the dataset
data(mtcars)
# Display the first few rows
head(mtcars)
# Summary of the dataset
summary(mtcars)
```
**Attributes and types:**
- Nominal: cyl, vs, am, gear, carb
- Discrete: cyl, gear, carb
- Continuous: mpg, disp, hp, drat, wt, qsec
2. **Create a scatter plot of Sepal.Length and Petal.Length from the iris dataset**
```r
# Load the dataset
data(iris)
# Create scatter plot
plot(iris$Sepal.Length, col = "red", xlab = "Index", ylab = "Length", main = "Sepal and Petal
Lengths")
points(iris$Petal.Length, col = "blue")
legend("bottom", legend = c("Sepal.Length", "Petal.Length"), col = c("red", "blue"), pch = 1)
```
**Explanation:**
- `plot`: Creates the initial plot.
- `points`: Adds points to an existing plot.
- `legend`: Adds a legend to the plot.
3. **Calculate average mpg by cyl and absolute difference in horsepower**
```r
# Average mpg by cyl
avg_mpg_by_cyl <- aggregate(mpg ~ cyl, data = mtcars, FUN = mean)
print(avg_mpg_by_cyl)
# Calculate the absolute difference in horsepower
avg_hp_4_cyl <- mean(mtcars$hp[mtcars$cyl == 4])
avg_hp_8_cyl <- mean(mtcars$hp[mtcars$cyl == 8])
abs_diff_hp <- abs(avg_hp_4_cyl - avg_hp_8_cyl)
print(abs_diff_hp)
```
4. **Create different types of vectors**
```r
# Numeric vector
numeric_vector <- c(1, 2, 3, 4, 5)
print(numeric_vector)
# Character vector
character_vector <- c("a", "b", "c", "d", "e")
print(character_vector)
# Logical vector
logical_vector <- c(TRUE, FALSE, TRUE, FALSE, TRUE)
print(logical_vector)
```
5. **Create a data frame with three columns**
```r
# Create data frame
df <- data.frame(
 name = c("John", "Jane", "Doe"),
 age = c(25, 30, 22),
 is_student = c(TRUE, FALSE, TRUE)
)
print(df)
```
6. **Create a scatter plot of mpg vs hp using base plotting system**
```r
# Base plotting system
plot(mtcars$mpg, mtcars$hp, xlab = "Miles per Gallon", ylab = "Horsepower", main = "mpg
vs hp")
```
7. **Create a simple ggplot2 scatter plot of mpg vs hp**
```r
# Load ggplot2 library
library(ggplot2)
# ggplot2 scatter plot
ggplot(mtcars, aes(x = mpg, y = hp)) +
 geom_point() +
 labs(title = "mpg vs hp", x = "Miles per Gallon", y = "Horsepower")
```
8. **Plot a histogram of mpg using base plotting system and ggplot2**
```r
# Base plotting system
hist(mtcars$mpg, xlab = "Miles per Gallon", main = "Histogram of mpg")
# ggplot2
ggplot(mtcars, aes(x = mpg)) +
 geom_histogram(bins = 10) +
 labs(title = "Histogram of mpg", x = "Miles per Gallon")
```
9. **Create a box plot of mpg grouped by cyl using base plotting system and ggplot2**
```r
# Base plotting system
boxplot(mpg ~ cyl, data = mtcars, xlab = "Number of Cylinders", ylab = "Miles per Gallon",
main = "mpg grouped by cyl")
# ggplot2
ggplot(mtcars, aes(x = factor(cyl), y = mpg)) +
 geom_boxplot() +
 labs(title = "mpg grouped by cyl", x = "Number of Cylinders", y = "Miles per Gallon")
```
10. **Create a bar plot of the number of cars with different numbers of cylinders using base
plotting system and ggplot2**
```r
# Base plotting system
barplot(table(mtcars$cyl), xlab = "Number of Cylinders", ylab = "Number of Cars", main =
"Number of cars by cylinders")
# ggplot2
ggplot(mtcars, aes(x = factor(cyl))) +
 geom_bar() +
 labs(title = "Number of cars by cylinders", x = "Number of Cylinders", y = "Number of Cars")
```
11. **Create a line plot of mpg vs wt using base plotting system and ggplot2**
```r
# Base plotting system
plot(mtcars$wt, mtcars$mpg, type = "l", xlab = "Weight", ylab = "Miles per Gallon", main =
"mpg vs wt")
# ggplot2
ggplot(mtcars, aes(x = wt, y = mpg)) +
 geom_line() +
 labs(title = "mpg vs wt", x = "Weight", y = "Miles per Gallon")
```
12. **Create a scatter plot of mpg vs wt with a regression line using ggplot2**
```r
# ggplot2 scatter plot with regression line
ggplot(mtcars, aes(x = wt, y = mpg)) +
 geom_point() +
 geom_smooth(method = "lm") +
 labs(title = "mpg vs wt with regression line", x = "Weight", y = "Miles per Gallon")
```
13. **Create a scatter plot of mpg vs wt using ggplot2**
```r
# ggplot2 scatter plot
ggplot(mtcars, aes(x = wt, y = mpg)) +
 geom_point() +
 labs(title = "mpg vs wt", x = "Weight", y = "Miles per Gallon")
```
14. **Create a box plot for mpg grouped by cyl using ggplot2**
```r
# ggplot2 box plot
ggplot(mtcars, aes(x = factor(cyl), y = mpg)) +
 geom_boxplot() +
 labs(title = "mpg grouped by cyl", x = "Number of Cylinders", y = "Miles per Gallon")
```
15. **Create a box plot for mpg grouped by cyl using base R**
```r
# Base plotting system
boxplot(mpg ~ cyl, data = mtcars, xlab = "Number of Cylinders", ylab = "Miles per Gallon",
main = "mpg grouped by cyl")
```
16. **Create a scatter plot of mpg vs wt with points colored by cyl and different shapes for
gear using ggplot2**
```r
# ggplot2 scatter plot with colors and shapes
ggplot(mtcars, aes(x = wt, y = mpg, color = factor(cyl), shape = factor(gear))) +
 geom_point() +
 labs(title = "mpg vs wt colored by cyl and shaped by gear", x = "Weight", y = "Miles per
Gallon")
```
17. **Create a scatter plot of mpg vs wt with custom title, axis labels, and subtitle using
ggplot2**
```r
# ggplot2 scatter plot with custom labels
ggplot(mtcars, aes(x = wt, y = mpg)) +
 geom_point() +
 labs(title = "Scatter plot of mpg vs wt", subtitle = "Custom subtitle", x = "Weight", y = "Miles
per Gallon")
```
18. **Calculate mean mpg for each number of cylinders using dplyr**
```r
# Load dplyr
library(dplyr)
# Calculate mean mpg by cyl
mtcars %>%
 group_by(cyl) %>%
 summarise(mean_mpg = mean(mpg))
```
19. **Create a bar plot of the number of cars for each cylinder count using ggplot2**
```r
# ggplot2 bar plot
ggplot(mtcars, aes(x = factor(cyl))) +
 geom_bar() +
 labs(title = "Number of cars by cylinders", x = "Number of Cylinders", y = "Number of Cars")
```
20. **Create a pie chart of the cylinder count using base R**
```r
# Base plotting system
cyl_counts <- table(mtcars$cyl)
pie(cyl_counts, main = "Pie chart of cylinder counts")
```
21. **Create a histogram of mpg using ggplot2**
```r
# ggplot2 histogram
ggplot(mtcars, aes(x = mpg)) +
 geom_histogram(bins = 10) +
 labs(title = "Histogram of mpg", x = "Miles per Gallon")
```
22. **Create a boxplot of mpg grouped by cyl using ggplot2**
```r
# ggplot2 box plot
ggplot(mtcars, aes(x = factor(cyl), y = mpg)) +
 geom_boxplot() +
 labs(title = "mpg grouped by cyl", x = "Number of Cylinders", y = "Miles per Gallon")
```
23. **Create a scatter plot of mpg vs wt colored by cyl using ggplot2**
```r
# ggplot2 scatter
plot
ggplot(mtcars, aes(x = wt, y = mpg, color = factor(cyl))) +
 geom_point() +
 labs(title = "mpg vs wt colored by cyl", x = "Weight", y = "Miles per Gallon")
```
24. **Create a scatter plot of mpg vs wt with customized legend using ggplot2**
```r
# ggplot2 scatter plot with custom legend
ggplot(mtcars, aes(x = wt, y = mpg, color = factor(cyl))) +
 geom_point() +
 labs(title = "mpg vs wt colored by cyl", x = "Weight", y = "Miles per Gallon") +
 theme(legend.title = element_text(text = "Cylinders"), legend.position = "bottom")
```
25. **Examine the mpg attribute in more detail**
```r
# Store mpg in a vector
MPG <- mtcars$mpg
# Calculate mean, variance, and standard deviation
mean_mpg <- mean(MPG)
var_mpg <- var(MPG)
sd_mpg <- sd(MPG)
# Print the results
print(mean_mpg)
print(var_mpg)
print(sd_mpg)
# Create a boxplot
boxplot(MPG, main = "Boxplot of mpg", ylab = "Miles per Gallon")
# Identify outliers
outliers <- boxplot.stats(MPG)$out
print(outliers)
```
26. **Create a histogram for MPG using the MASS library**
```r
# Install and load MASS library
install.packages("MASS")
library(MASS)
# Create histogram using truehist
truehist(MPG, nbins = 10, main = "Histogram of mpg", xlab = "Miles per Gallon")
# Check skewness
```
27. **Examine the relationship between mpg and hp**
```r
# Store hp in a vector
HP <- mtcars$hp
# Create scatter plot
plot(HP, MPG, xlab = "Horsepower", ylab = "Miles per Gallon", main = "HP vs MPG")
# Check correlation
correlation <- cor(HP, MPG)
print(correlation)
```
