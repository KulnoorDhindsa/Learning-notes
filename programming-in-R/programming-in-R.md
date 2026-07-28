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
## Vectors
**Vectors** are *strings* of text, sequential or random numbers.
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
`matrix()` takes data inputed, and with specified `ncol` or `nrow` makes a matrix accordingly.
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
```R
for(i in 1:3){
    print(i)
}
```
>In RStudio, only the code selected is run, so select your entire code then click run.