## Mathematical Operators
|Operator|Operation|
|--------|---------|
|`**`|Exponent|
|`%`|Modulus/Remainder|
|`//`|Integer Division|
|`/`|Division|
|`*`|Multiplication|
|`-`|Subtraction|
|`+`|Addition|
|`=`|Assignment from left to right|

**Precedence of Operators**:
`**` > `*` > `/` > `//` > `%` > `+` > `-`
>() are evaluated before any operation.

## Comparison Operators
|Operator|Operation|
|-------|--------|
|`==`|Equal to|
|`!=`|Not equal to|
|`<`|Less than|
|`>`|Greater than|
|`<=`|Less than or equal to|
|`>=`|Greater than equal to|

## Boolean Operators
|Operator|Operations|
|-------|---------|
|`and`|Returns true if both conditions are true|
|`or`|Returns true if either of the two entered conditions is true|
|`not`|Returns true if neither of the two entered conditions is true|

## Data Types
|Data Type|What it contains|Examples|
|---------|--------|----------|
|Integers (`int`)|All integer values|-2, 0, +1|
|Floating-point (`float`)|All values contaning decimal point `.`|0.24, -8.9|
|Strings (`str`)|Sequence of characters within `''` or `""`|'apple', 'gello','2 cakes', ' ' (blank string)|
|Boolean|Contains only two values|`True` and `False`|

Input:
```python
print('Stacey'+'Millers')
print('Stacey','Millers')
```
Output:
```python
StaceyMillers
Stacey Millers
```
>First print statement **concatenates** the two strings, thus no space. 

>In official documentation of python `,` in `print` statements is used to separate objects. In `print`, `sep=' '` argument separates two objects with a space.

`#` is used for single line comments.

## Functions
### Pre-defined Functions in Python
|Function|What it does|Example|
|--------|-----------|-------|
|`print`|Displays the content in the `()`|`print("Hi!")`|
|`input`|Aks user for input, followed by ENTER|`input("What is your name?")`|
|`len`|counts number of characters in string, or variable containing string|`len("Stacey")`|

>By default, user input entered for `input` function, is treated as a *string*.

## Format Strings (F Strings)
```python
print(2300)
print(f"{2300:,}")
```
In the above code,
1. `print(2300)` prints the number 2300
2. `print(f"{2300:,}")` is a format string, thus according to official documentation of Python on       , this command puts `,` after eery three digits from the ones place, like in the US numerical system.

