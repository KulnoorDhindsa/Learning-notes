# R (Programming Language)
It's the programming language built around matrix and operations.
### Operators
|Operator|What it does|
|--------|------------|
|`+`|Addition|
|`-`|Subtraction|
|`/`|Division|
|`*`|Multiplication|
|`=` or `<-`|Assignement from Left to Right|
|`==`|Equal to|
|`!=`|Not equal to|
|`>=`|Greater than equal to|
|`<=`|Less than equal to|
|`>`|Greater than|
|`<`|Less than|
## Vectors (Mathamatical Vectors)
**Vectors** (different from data type vectors), are *strings* of text, sequential or random numbers.
```R
v1=1:9 #Creates a vector from 1 to 9, stored in variable v1
```
- So, vector created in above example is `1 2 3 4 5 6 7 8 9`.
>Both, the lower limit and upper limit of the range are included.

- By default, in vectors, the gap in between values of vector is 1.
```R
v2=seq(from=1, to=9, by=2) #creates vector from 1 to 9 with gap of 2, and stores it in variable v2
v3=c(0,2,3,-0.9,-23) #creates vector of given values (not following a fixed pattern)
```
- `c` in above example stands for *concatenation*, or including the random numbers into a vector, since by default vector elements in R have a pattern (difference of 1)
### Manipulating Vectors
```R
v1=1:9 #creates vector from 1 to 9 with gap of 1, stores in v1
v2=3:1 #creates vector from 3 to 1 with gap of 1, stores in v2
v3=v1+v1 #same as v3=2*v1 (multiples each element in v1 by 2)
#this addition is possible because size of both vectors is same
v4=v1+v2 #does NOT give warning as larger size vector is multiple of the soze of smaller size vector
```
>In addition of vectors, when sizes are NOT same, **smaller vector is looped again and again to match the size of larger loop**.
```output
v1 = 1 2 3 4 5 6 7  8  9
v2 = 3 2 1 3 2 1 3  2  1
v4 = 4 4 4 7 7 7 10 10 10
```
```output
v5 = 1 2 3 4 5 6 7
v2 = 3 2 1 3 2 1 3
v6 = 4 4 4 7 7 7 10
```
- When sizes aren't equal, terminal gives warning, but adds them anyways.
## Matrix

`matrix()` takes data inputed, and with specified `ncol` or `nrow` makes a matrix accordingly, matrix is a *2-dimensional vector*.
```R
v1=1:9
m1=matrix(v1, ncol=3) #creates matrix of 9 elements with 3 coloumns, so 3 rows
```
```output
     [,1] [,2] [,3]
[1,]  1    4     7
[2,]  2    5     8
[3,]  3    6     9
```
- It converted a *vector* into a *matrix*

### Manipulating Matrix
- Addition of matrix is only possible when their order (row, columns) is same (unlike vectors).
- `t(m1)` displays the *transpose* of a matrix `m1`.
```R
m1=matrix(1:9, nrow=3) #creates matrix of 9 elements in 3x3
x1=m1[2,2] #stores value of [2,2] element from m1 matrix into variable x1
x2=m1[2,] #stores values of 2nd row as a vector in x2
x3=m1[-1,] #removes row 1 and stores new matrix in x3 variable
```
- In `x2=m1[2,]`, `[2,]` means 'all elements of row number 2' 'and `,` is for 'take all elements'
```R
m1[m1>5]=0 #assigns value 0 to all elements of m1 that are greater than 5
x4=m1[m1>5] #creates vector of all elements in m1 greater than 5 and stores them in variable x4
```
## Loops
### `for` loop
```R
for(i in 1:3){
    print(i)
}
```
>In RStudio, only the code selected is run, so select your entire code then click run.
### `while` loop

## Data Types
`class()` of a variable tells us the *data type* or how it should be handled.

|Class|Example|
|-----|-------|
|`numeric`|Numbers (int, float etc; more general class)|
|`integer`|Integers|
|`character`|Text input (broader class)|
|`logical`|Contains "True/False" boolean values|
|`vector`|Can contain any data type (logical, numeric or character), but only one at a time|
|`matrix`|Contains a matrix|
```R
x=2
class(x) #gives output "numeric"
x1=1:4 
class(x1) #gives output "integer" as numeric is more general class, more specific data type is, less memory it stores
x2=c(1,2,5,6)
class(x2) #gives output "numeric", as `c()` function concatenates numeric 1,2,5 and 6 into a string, and a string of numeric, is a numeric
```
```R
x3="Best of Luck!"
class(x3) #gives output "character"
x4=c("best", "of", "luck")
class(x4) #gives output "character" as c() of character entries is still a character
x5=c("HI", 3, -0.9)
class(x5) #gives output "character
```
```R
x6=c(T,F,T,F)
print(x6) #prints True False True False
class(x6) #gives output "logical"
```
```R
v1=vector(mode="logical", 4)
print(v1) #prints False False False False
class(v1) #gives output "logical"

v2=vector(mode="character", 3)
print(v2) #prints "" "" ""
class(v2) #prints "character"
```
```R
m1=matrix(1:16, nrow=4)
class(m1) #prints "matrix" "array"
```
>`c()` function concatenates the numeric 1,2,5 and 6 into a string, and string of numeric will still be numeric data type instead of `vector` data type.

>If numbers and characters are combined, then also their collective class is "character".

-
-
--
-


## Reading Data



## Plotting Data 
Plotting is done by `plot()` function.
### Plotting Point graphs
```R
p1=1:9 #creates mathamatical vector from 1 to 9 with gap 1
plot(p1,p1) #plots graph with p1 (first element) on x axis, and p1 (second element) on the y axis.
#plots points (1,1), (2,2), (3,3) etc

p1=1:9
p2=9:1
plot(p1,p2) #plots grpah with p1 on x axis and p2 on y axis
#plots points (1,9), (2,8),(3,7) etc.
```
```R
p1=(1:9)
p2=(9:1)
plot(p1,p2)
plot(p1,p1)
par(mfrow=c(1,2), bg="grey", bty="n", cex="0.75") #par is for "parameters"
#`mfrow` allows graph area to be split into 1 row and 2 coloumns, so 2 graphs
#`bg="grey"` turns the background color to "gregy"
#`bty="n"` removes the box around the graph
#`cex="0.75"` changes the text size
```
### Plotting line graph
```R
p1=(1:9)
p2=(9:1)
plot(p1,p2, length.out = 1000, type="l", xlim=c(0,10), ylim=c(0,10), xlab="1:9", ylab="9:1", main="Plot of 1:9 to 9:1", col="red", pch=3)
#labelling axis with `xlab` and `ylab`
#`main` for the title of the plot
#color of the plot with `col` and background with `bg`
#`type="l"` to have aline graph instead of by default point graph
#`length.out=1000` divides the x and y limit 0 to 10 into 1000 divisions for a more precise graph
```
>All plots so far have been point plots by default, for line plot, `type="l"` is used.
```R
curve(x^2 - 2*x + 1, from = 0, to = 10, xlab = "x-axis", ylab = "y-axis", ylim = c(0, 10))
#generates curve graphs directly
```
Plotting sin(x) and cos(x) graphs
```R
y=sin(x)
z=cos(x)
par(mfrow=c(2,1), cex=(0.50))
plot(x,z, xlab="x-axis", ylab="y-axis", xlim=c(0, 2*pi), ylim=c(-1, +1), col="red", main="Cos(X)")
plot(x,y, xlab="x-axis", ylab="y-axis", xlim=c(0, 2*pi), ylim=c(-1, +1), col="green", main="Sin(x)")
#`mfrow=c(2,1)` divides graph area into 2 rows 1 column
```

### Plotting Box Graphs
`boxplot()` command is used to create Boxplot graphs in R.
### Plotting Histograms
Histograms are plotted using `hist()` function.