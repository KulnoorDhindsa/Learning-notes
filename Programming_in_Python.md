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
|`==`|Equal to|

**Precedence of Operators**:
`**` > `*` > `/` > `//` > `%` > `+` > `-`
>() are evaluated before any operation.

## Data Types
|Data Type|Examples|
|---------|--------|
|Integers (`int`)|-2, 0, +1|
|Floating-point (`float`)|0.24, -8.9|
|Strings (`str`)|'apple', 'gello','2 cakes', ' ' (blank string)|

```python
print('Stacey'+'Millers')
print('Stacey','Millers')
```
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