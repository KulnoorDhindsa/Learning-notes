# Cnditional Statements (Decision Making)
## `if` statement
- Runs if condition stated is `True`
```python
n=int(input("Enter a number: "))
if n%2==0:
    print(n, "is even!")
```
## `else` statement
- Executes when `if` statement concludes `False`
```python
n=int(input("Enter a number: "))
if n%2==0:
    print(n, "is even!")
else:
    print(n, "is odd!")
```
## `elif` statement
- Used when *one of many* possible clauses has to be executed
- Is an `else if` that follows another `if` or `elif` and executes only when stated condition holds `True`
```python
n=int(input("Enter a number: "))
if n>0:
    print(n, "is positive!")
elif n<0:
    print(n, "is negative!")
else:
    print(n, "is zero!")
```
- `elif` condition is checked only if the `if` condition concludes to be `False`. `else` runs only if `elif` also returns `False`.
- So, least amount of conditions are checked in above code
```python
if n>0:
    print(n, "is positive!")
if n<0:
    print(n, "is negative!")
if n==0:
    print(n, "is zero!")
```
- In above code, all 3 conditions are checked, regardless if one holds `True` or `False`.
---
# Looping Statements (Iteration)
## `while` loop
- Block of code is executed over and over again untill a certain condiiton holds true
```python
i=1;
n=int(input("Enter a number: "))
print("First", n, "natural numbers are : ", end=' ')
while i<=n:
    print(i, end=' ')
    i+=1
```
>To run a loop infinite amount of times, and stop only when user types something specific:
```python
friends_names=[]
while True:
    print("Enter friend's names, and nothing() to stop:")
    name=input()
    if name=="":
        break
    friends_names+=[name] #concatenation
```
## `for` loop
- Executes block of code for a *fixed* number of times
```python
n=int(input("Enter a number: "))
for i in range(1,11):
    print(n, "x", i, "=", n*i)
```
- In above code, i=1 and goes till i=10 (1 less than upper limit of range)
>Codes in `while` loop can also be written using `for` loop.
>>Prefer `for` loop when number of iterations to be made is known and use `while` loop when number of iterations is unknown.

```python
for i in range(1,11):
    print(i, end=' ')
```
- `i` is increased by 1 by default
```python
for i in range(1,11,2):
    print(i, end=' ')
```
- `i` starts from 1, increased by 2 and goes till '1 less than upper limit of range'
```python
for i in range(x,y,z)
```
- `i` starts from x, goes uptill `y-1` (1 less than upper limit of range) by intervals of `z`
> `z` can be positive or negative.
---
# Loop Control Keywords (Jumping)
## `break` statements
- Used *inside* loops
- Shortcut to get program to stop execution of a loop
```python
n=1
while n<6:
    if n==4:
        break
    else:
        print(n, end=' ')
        n+=1
```
## `continue` statements
- Used *inside* loops
- Program execution jumps back to the start on encountering a `continue` statement

>`sys.exit()` abruptly exits entire code (like `break` does for a loop)
```python
import sys
while True:
    print("Do you want to exit? (y/n)")
    response=input()
    if response==y:
        sys.exit()
    else:
        print("You typed", response)
```
- The above block of code inside while always holds `True`, *an infinite loop*.