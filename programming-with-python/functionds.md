# Functions
*Function* is mini-program within a program.
```python
def sum(x,y):
    sum=x+y
    print(x, "+", y, "=", sum)
def main():
    n1=int(input("Enter n1: "))
    n2=int(input("Enter n2: "))
    sum(n1,n2)
main()
```
- `def` function defines a function of user's choice
- A function `sum` which will take *arguments* stored in *parameters* `x` and `y` from `main` has been defined and called later in `main` function by the command `sum(n1,n2)`
- `main()` calls the `main` function defined above
>Value stored in parameters is forgotten as soon as function ends; so same parameters can be used in multiple functions.
---
## Return Values
- The value that a called function evaluates to is *return value*.
```python
def ask_name():
    name=input("What is your name? ")
    return(name)
def main():
    name=ask_name()
    print("Hi", name, "! I'm a machine!!")
main()
```
>Value stored by `name` variable in `ask_name` function ends as soon as `ask_name` funciton ends, thus `name` variable can be used in other functions as well.
- This is usefull when the *return value* is to be used further down the code and not just to be printed on the screen
- *return statements* return the *return values*, which is then stored by equating the called function to a variable, and can be used further down the code.
---
## Local and Global Scope
**Local Scope**: Parameteres and variables assigned in a called function exist in that function's *local scope*.
- Local Scope is destroyed when called function ends; valus stored by local variables is lost.
- Local Scopes **can't** use variables form other local scopes.

>A local variable has to be assigned a value first before using it.

**Global Scope**: Variables assigned outside all the functions are in *global scope*.
- Global Scope is destroyed at the end of the programme; all globals variables lose their values.
>Local scope can access global variables but not vica versa.
```python
def veg_list():
    l2='apples'
    l3='pears'
    l4='grapes'
l3='blue berries'
veg_list()
print(l3)
```
- `print(l3)` prints `pears` as, the `veg_list` is declared first, but called **after** `l3='blue berries'`, so any changes made to *global variable* `l3`

>To modify value stored in global variable, a global statement has to be made.
---
## `try` and `except`
```python
def div(x):
    return 20/x
print(div(1))
print(div(2))
print(div(0))
print(div(5))
```
- Above code shows error when `print(div(0))` runs and shows `ZeroDivisionError`.
```python
def div(x):
    try:
        return 20/x
    except ZeroDivisionError:
        print("Error: Invalid Argument")
print(div(1))
print(div(2))
print(div(0))
print(div(5))
```