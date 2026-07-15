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
## Local and Global Scope
