# R Practical Exercises

This README organizes the original content into separate practicals, cleans up/standardizes the code, fixes obvious typos, and makes examples easier to read and copy.

Table of contents
- Practical 1 — Basic data types and variables
- Practical 2 — Control structures and loops
- Practical 3 — Working with data frames
- Practical 4 — R data structures (lists, matrices, factors)
- Practical 5 — Basic plots (pie, line, bar, histogram)
- Practical 6 — Tidyverse example
- Practical 7 — Data transformation with tidyr/dplyr
- Practical 8 — ggplot2 examples

---

## Practical 1 — Basic data types and variables

Description: creating variables of different types and checking their types.

```r
# Numeric (double)
num_var <- 10.5
cat("1. Numeric variable\n")
cat("value:", num_var, "\n")
cat("type:", typeof(num_var), "\n\n")

# Integer
int_var <- 7L
cat("2. Integer variable\n")
cat("value:", int_var, "\n")
cat("type:", typeof(int_var), "\n\n")

# Character
char_var <- "Hello R!"
cat("3. Character variable\n")
cat("value:", char_var, "\n")
cat("type:", typeof(char_var), "\n\n")

# Logical
log_var <- TRUE
cat("4. Logical variable\n")
cat("value:", log_var, "\n")
cat("type:", typeof(log_var), "\n\n")

# Complex
comp_var <- 2 + 3i
cat("5. Complex variable\n")
cat("value:", comp_var, "\n")
cat("type:", typeof(comp_var), "\n\n")

# Convert numeric to integer (note truncation)
num_var2 <- 10.99
int_converted <- as.integer(num_var2)
cat("6. Convert numeric to integer\n")
cat("original numeric:", num_var2, "\n")
cat("converted to integer:", int_converted, "\n\n")

# List with mixed types
list_example <- list(1, "hello", TRUE, 3.14)
cat("7. Data types in a list\n")
cat("type:", typeof(list_example), "\n")
cat("Each element can have a different type in a list!\n\n")
```

Notes:
- as.integer() truncates toward zero; it does not round.
- Use TRUE / FALSE for logicals (not true/false).

---

## Practical 2 — Control structures and loops

Contains conditional examples: grading, odd/even check, palindrome check.

```r
# 1) Grade based on marks
marks <- as.numeric(readline(prompt = "Enter your marks: "))
if (marks >= 90) {
  grade <- "A"
} else if (marks >= 70) {
  grade <- "B"
} else if (marks >= 60) {
  grade <- "C"
} else {
  grade <- "F"
}
cat("Your grade is:", grade, "\n")

# 2) Check odd or even
num <- as.numeric(readline(prompt = "Enter your number: "))
if (num %% 2 == 0) {
  cat(num, "is even\n")
} else {
  cat(num, "is odd\n")
}

# 3) Check palindrome (string-based)
num_str <- readline(prompt = "Enter a number or string: ")
is_palindrome <- num_str == paste(rev(strsplit(num_str, NULL)[[1]]), collapse = "")
if (is_palindrome) {
  cat(num_str, "is a palindrome\n")
} else {
  cat(num_str, "is not a palindrome\n")
}
```

Notes:
- strsplit returns a list; use [[1]] to access the character vector.
- paste(..., collapse="") rebuilds the string from reversed characters.

---

## Practical 3 — Working with data frames

Create and manipulate data frames.

```r
# Simple dataframe
name <- c("Jhon", "Emma", "Liam")
age <- c(25, 30, 22)
marks <- c(85, 92, 78)
students <- data.frame(Name = name, Age = age, Marks = marks)
print(students)

# Longer example with roll numbers
roll_no <- c(101, 102, 103, 104)
name <- c("Jhon", "Emma", "Liam", "Chirag")
age <- c(21, 20, 22, 19)
marks <- c(88, 96, 90, 85)
students <- data.frame(Rollno = roll_no, Name = name, Age = age, Marks = marks)
cat("students dataframe:\n")
print(students)

# Accessing a column
cat("Only names:\n")
print(students$Name)

# Adding a new column
students$Grade <- c("A", "B", "C", "D")
cat("Updated dataframe of students:\n")
print(students)
```

Notes:
- Use consistent variable names and check for typos when creating vectors.

---

## Practical 4 — R data structures: lists, matrices, factors

```r
# a) Creating a named list
my_list <- list(name = "XYZ", age = 20, score = c(85, 90, 88))
print(my_list)

# b) Creating a matrix (2 rows, 3 columns)
my_matrix <- matrix(c(1, 2, 3, 4, 5, 6), nrow = 2, ncol = 3)
print(my_matrix)

# c) Creating factors (categorical data)
gender <- factor(c("Male", "Female", "Female", "Male"))
print(gender)
print(levels(gender))
```

---

## Practical 5 — Basic plots (pie, line, bar, histogram)

Below are the exact few lines you supplied for Practical 5 (cleaned into R code blocks). Each example is self-contained and ready to run in an interactive R session or an R script. Comments added for clarity.

```r
# 🥧 1. Pie Chart
# Sample Data
slices <- c(30, 20, 25, 25)
labels <- c("Math", "Science", "English", "History")

# Plot
pie(slices,
    labels = labels,
    main = "Subject Wise Distribution",
    col = rainbow(length(slices)))
```

```r
# 📈 2. Line Plot
# Sample Data
x <- c(1, 2, 3, 4, 5)
y <- c(3, 5, 2, 8, 7)

# Plot
plot(x, y,
     type = "o",
     col = "blue",
     xlab = "Time",
     ylab = "Score",
     main = "Score Over Time")
```

```r
# 📊 3. Bar Plot
# Sample Data
subjects <- c("Math", "Science", "English", "History")
marks <- c(80, 90, 75, 85)

# Plot
barplot(marks,
        names.arg = subjects,
        col = "green",
        main = "Marks in Subjects",
        ylab = "Marks",
        xlab = "Subjects")
```

```r
# 📉 4. Histogram
# Sample Data
scores <- c(50, 55, 60, 65, 70, 75, 80, 85, 90, 95, 100)

# Plot
hist(scores,
     col = "hotpink",
     main = "Score Distribution",
     xlab = "Scores",
     breaks = 5)
```

Notes:
- Each plotting example uses base R graphics. For larger projects or publication-quality figures, consider ggplot2.
- If running in RStudio, plots will appear in the Plots pane; in plain R, a graphics device will open.

---

## Practical 6 — The tidyverse package

Install and load tidyverse; create a tibble and use dplyr verbs.

```r
# Install if needed (uncomment to run)
# install.packages("tidyverse")

library(tidyverse)

students <- tibble(
  Name = c("Anjali", "Rahul", "Priya", "Aman", "Sneha", "Ravi"),
  Age = c(20, 22, 19, 21, 20, 23),
  Gender = c("F", "M", "F", "M", "F", "M"),
  Marks = c(85, 78, 92, 88, 95, 60)
)

# a) select Name and Marks
selected_data <- students %>% select(Name, Marks)
print("selected name and marks:")
print(selected_data)

# b) filter students who scored above 85
high_scores <- students %>% filter(Marks > 85)
print("Students with marks above 85:")
print(high_scores)

# c) mutate: add a Results column
students_with_results <- students %>% mutate(Results = ifelse(Marks >= 75, "Pass", "Fail"))
print("Data with result column:")
print(students_with_results)

# d) group_by and summarise: average marks (example overall)
avg_marks <- students %>% summarise(Average_Marks = mean(Marks))
print("Average marks:")
print(avg_marks)
```

Notes:
- Fixed typos: filter(Marks > 85) (was f ilter/marks).
- Use consistent capitalization for column names (Marks vs marks).

---

## Practical 7 — Data transformation with tidyr/dplyr

Example using pivot_longer/unite/separate (tidyr).

```r
library(tidyr)
library(dplyr)

data <- data.frame(
  Name = c("Alice", "Bob"),
  Math = c(80, 85),
  Science = c(85, 88)
)

print("Original data:")
print(data)

# Using pivot_longer (modern replacement of gather)
long_data <- data %>%
  pivot_longer(cols = c(Math, Science), names_to = "Subject", values_to = "Marks")
print("Data after pivot_longer():")
print(long_data)

# unite columns
united_data <- data %>%
  unite(col = "Name_math", Name, Math, sep = "-")
print("Data after unite():")
print(united_data)

# separate columns back
separated_data <- united_data %>%
  separate(col = "Name_math", into = c("Name", "Math"), sep = "-")
print("Data after separate():")
print(separated_data)
```

---

## Practical 8 — ggplot2 examples

Two example ggplot2 snippets (scatter plots). Ensure column names match.

```r
library(ggplot2)

# Example 1: synthetic student_data (ensure column names are correct)
student_data <- data.frame(
  ID = 1:5,
  name = c("aman", "nikhil", "lia", "norman", "mia"),
  age = c(20, 25, 22, 21, 24),
  gender = c("Male", "Female", "Male", "Female", "Male"),
  marks = c(80, 85, 90, 95, 99)
)
print(student_data)

ggplot(student_data, aes(x = age, y = marks, color = gender)) +
  geom_point(size = 3) +
  facet_wrap(~ gender) +
  labs(
    title = "Students: marks vs age",
    x = "Age of students",
    y = "Marks scored",
    color = "Gender"
  ) +
  theme_dark()

# Example 2: iris dataset
ggplot(data = iris, aes(x = Sepal.Length, y = Sepal.Width, color = Species)) +
  geom_point(size = 3) +
  facet_wrap(~ Species) +
  labs(
    title = "Sepal length vs sepal width",
    x = "Sepal Length",
    y = "Sepal Width",
    color = "Flower Species"
  ) +
  theme_minimal()
```



