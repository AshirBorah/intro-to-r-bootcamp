---
type: slides
---


## Why R specifically

<center>
<img src="../images/why_R.png" width="60%">
</center>

- Free

- Great for data analysis and visualization

- LOTS of bioinformatics/stats tools available

Downsides?

- It's a hodge-podge

---
## Course goals

- Convince you that R is an accessible and useful tool for you in your research

- Get over initial learning curve

- Prepare you to tackle computational projects next week

---
## Strategy of the course

- Emphasis on practical skills (data wrangling, visualization)

- Flagging areas with technical depth but giving the ‘need-to-know'

- Slides, follow-along workbooks, and emphasis on hands-on practice

---
## I need your help

- I'm winging it (surprise!)

- I'll try to adapt as we go

- PLEASE give me feedback, ask questions!

---
## Acknowledgements

- Sam Meier's 2018 R lectures

- HBC Intro to R [course](https://hbctraining.github.io/Intro-to-R/schedules/1.5-day.html)

- Chester Ismay's DataCamp [slides](https://ismayc.github.io/talks/ness-infer/slide_deck.html#1)

- Hadley Wickham's R for Data Science [e-book](https://r4ds.had.co.nz/)

---
## Course overview

- Review R basics

- Functions

- Data Wrangling basics

- Tidyverse

- (weekend practice)

- Data viz

- More data wrangling, practice, bonus topics

---
## Key Tools

<center>
<img src="../images/Rtools_car.png" width="80%">
</center>

---
- RMarkdown

  - Analysis 'notebooks'

  - Easily share results and methods in different formats

  - Encourages good code and analysis practices

---
## R Studio review

Quick live demo of how to interact with Rstudio

- Different components of Rstudio interface

- R scripts vs Rmd files

- Running code lines

- Running code chunks

- Creating new chunks

---
## Create project directory

- Organize your work as 'Projects' in Rstudio

- Each project has a separate folder, with data, code, results.

- Copy the R_BootCamp_2019 folder from Google Drive to your computer

- Create a 'Project' in Rstudio

---




## R as calculator

List of key math operations

- `*`: multiplication
- `/`: division
- `+`: addition
- `-`: subtraction
- `^`: 'raise to the power'
---
## Logical operations

```{r}
1 + 1 == 2
```

```out
True
```

- `==` Check equals
- `!=` Check not equals
- `>` Greater than, `<` less than
- `>=` Greater than or equal to, etc.
---



## Creating variables

- You can create new variables with `<-`

```{r}
x <- 3 * 4
print(x)
```

```out
12
```

- All object-creation statements have the form:

```{r eval = FALSE}
object_name <- value
```

- You can use `=`, but `<-` makes for better R code

- Use Rstudio shortcut 'Alt' + '-'

---

## Variable types in R {.smaller}

- Numbers

```{r, eval = FALSE}
x <- 1
x <- 1.592E-39
```

- Strings (text)

```{r, eval = F}
x <- 'abc'
x <- "abc"
```

- Logical (true/false)

```{r, eval = F}
x <- TRUE
x <- FALSE
x <- T
```

- Factors (categorical variables)

  - e.g. ('bad', 'OK', 'good', 'great')

  - We will explicitly try to avoid these, but be aware of them.

---

## Variable naming

- Variable names must start with a letter, and can only contain letters, numbers, '`_`', and '`.`'.

- Object naming is **important** for writing good, readable, code

- Make variable names descriptive

`avgClicks`

- Make function names verbs

`calculate_avg_clicks`

---
## Use comments!

- Code readability is huge so others can understand what you've done

  - Including future you!

- In RMarkdown docs, write descriptive text before each code chunk

- Also good to add comments to key lines of code within chunks

---
## R environment

- See info on current variables

- Clearing variables

- View data tables, etc.
---


## Data Structures

- Vectors

- Lists

- Matrix

- Dataframes

---
## Vectors {.smaller}

- Ordered collection of values. Like a sequence of 'buckets'

- Can hold numeric data

<center>
<img src="../images/vector2.png" width="40%">
</center>

- Or text (strings)

<center>
<img src="../images/vector1.png" width="40%">
</center>

- Or boolean data (TRUE/FALSE)

<center>
<img src="../images/vector5-logical.png" width="40%">
</center>

- **All data in a vector has to be the same type!**

---
## Making vectors

Use 'combine' function `c()`

```{r}
num_vec <- c(1, 2, 3, 4)
log_vec <- c(TRUE, TRUE, FALSE, F)
str_vec <- c('this', 'is', 'a', 'vector', 'of', 'strings')
```

Shorthand to create a sequence of integers
```{r}
1:4
```

```{r}
5:10
```
---

## Missing values

- Quick notes on missing values in R (will be important)

- `NA` ('not available') is a special value for missing data that can be included in any type of vector

```{r, eval = FALSE}
c(1, 2, NA)
c('a', 'b', NA)
```
---

## Adding more data on to vectors {.smaller}

`c()` can also be used to add new elements to a vector

```{r}
string_vec <- c("TP53", "PLEC", "DSPP", "PIK3CA")
string_vec2 <- c(string_vec, "BRAF")
string_vec2
```

Adding to the beginning

```{r}
string_vec2 <- c("BRAF", string_vec)
string_vec2
```

Combining two vectors

```{r, eval = FALSE}
c(string_vec, another_string_vec)
```
---

## Lists

- Lists are basically like relaxed vectors, where elements don't have to be the same type

```{r}
z <- list('a', 1, TRUE)
```

- Add to lists the same way as vectors

```{r, eval = FALSE}
z <- c(z, 'morestuff')
```

---


## Matrix

- Like vectors, but arranged in 2d with rows and columns

<center>
<img src="../images/matrix.png" width="40%">
</center>

- Examples:

  - Gene expression data

  - Dependency data

---

## Dataframe

- Most common way of interacting with data

- Each column is a vector, and they can hold different kinds of data

- Like an Excel table.

<center>
<img src="../images/dataframe.png" width="40%">
</center>

---

## Key concepts recap

- Use RMarkdown documents like an experiment notebook

- Creating variables with `<-`

- Vectors, lists, matrices, and dataframes

- Creating/adding to vectors with `c()`

- Making lists with `list()`
