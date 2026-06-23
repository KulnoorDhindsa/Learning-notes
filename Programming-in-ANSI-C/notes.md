# Notes

### Keywords and Identifiers
|Keywords|Identifiers|
|--------|-----------|
|Fixed meanings|User-defined to store vaues of variables, functions and arrays|
|Lowercase|Lowercases and Uppercases|

---
### Operators
Symbols that tell the computer to perform logical or mathematical operations to manipulate data and variables.
1. #### Arithmetic Operators
|Operator|What it does|How its used|Notes|
|--------|------------|------------|---|
|`+`|Addition|a+b||
|`-`|Subtraction|a-b||
|`*`|Multiplication|a*b||
|`/`|Division and returns the quotient|a/b|
|`%`|Modulo division and returns the remainder|a%b|Sign of result is sign of 'a', ALWAYS use `int` type with `%`|

>`%` can't be used on floating point data.

**Integer Arithmetic**: Arithmetic operation where used operands are `int` type.
Yield `int` value.
The decimal part is truncated while using `/` and `%`.

**Real Arithmetic**: Arithmetic operation involving real operands (deciaml or float).

**Mixed-mode Arithmetic**: Arithmetic operation involving mixed operands (real and `int`).

2. #### Relational Operators
Operators used for establishing realtions between variables and constants.

*Relational Expression*: Expression containing relational operators.
Value of relational expression is: 1 is true, 0 if false.

|Operator|What it does|
|--------|-----------|
|`<`|is less than|
|`<=`|is less than or equal to|
|`>`|is greater than|
|`>=`|is greater than or equal to|
|`==`|is equal to|
|`!=`|is not equal to|

>Arithemtic Operators have **higher** priority than relational operators.

3. #### Logical Operators
Operators that evaluat **boolean conditions** and return either 1(true) or 0(false).

|Operator|Logical Name|Syntax|Returns 1 when|
|--------|----|------|--------------|
|`&&`|AND|`A && B`|**Both** A and B are true|
|`\|\|`|OR|`A \|\| B`|**At least one** of A or B is true|
|`!`|NOT|`!A`|A **is zero**.|

>`&&` never evaluates right side if left side is false.

>`||` never evaluates right side if left side is true.

*Double Negation* i.e. `!5` and `!!5` returns 0 and 1 respectively.

4. #### Assignment Operators
Operators used to assign results of expressio to variables.

|Operator|Syntax|What it does|
|--------|------|------------|
|`=`|A = B|Assigns value of B to A|
|`op=`|A op= B||

Shorthand Assigment Operators `op=`
|Operator|Syntax|What it does|
|--------|------|------------|
|`+=`|a += b|a = a + b|
|`-=`|a -= b|a = a - b|
|`*=`|a *= b|a = a * b|
|`/=`|a /= b|a = a / b|
|`%=`|a %= b|a = a % b|

5. #### Increment and Decrement Operators
Operators that add 1 or subtract 1 from a variable.

|Operators|Syntax |a=?|x=?|What they do                         |
|---------|-------|---|---|-------------------------------------|
|`++x`    |a = ++x|x+1|x+1|increments FIRST, then uses the value|
|`x++`    |a = x++|x  |x+1|uses the value first, then increments|
|`--x`    |a = --x|x-1|x-1|decremented FIRST, then uses the value|
|`x--`    |a = x--|x  |x-1|uses the value first, then decrements|

> Example:
>int x = 5;
>int y = ++x;
>// x=6, y=6 (increment FIRST, then usage)
>>int x = 5;
>int y = x++;
>// x=6, y=5 (usage first, then increment)

6. #### Conditional Operators
Its a shorthand for if-else in one line.

`exp1 ? exp2 : exp3` read as - ***If exp1 is true, give me exp2, otherwise give me exp3**.

Only **one** of exp2 or oxp3 is ever run, like in **if-else**.

7. ####  Bitwise Operators
Operators that manipulate data at the binary level.

**NOT** applicable to **float** or **double**.

8. #### Special Operators
|Operator|What it does|
|--------|------------|
|`,`| |
|`sizeof`|`m = sizeof(operand);` , gives number of bytes occupied by operand|

>variable=expression;

The expression is evaluated first and then that value is given to the variable.

All variables used should have be declared prior in the code.

### Precedence of Operators
( ) expression within () is guven **HIGHEST PRIORITY** from left to right.
If () are nested, evaluation starts from inner most ().

>HIGH PRIORITY: `*` > `/` > `%`

>LOW PRIORITY: `+` > `-`

High priority operators are evaluated first followed by lower priority operators.

---
### Type Conversions
Automatic conversion of intermediate values to proper type for evaluation.
During evaluation, the *lower* type is converted to the *higher* type.

**Conversion Hierarchy**
Long Double > Double > Float > Unsigned Long Int > Long Int > Unsigned Int > Int > ( Short = Char )

Final result of expression is converted to match type of variables on left of the assignment sign.

During final assignment:
- **float** to **int** truncates fractional part.
- **double** to **float** rounds off digits.
- **long int** to **int** causes dropping of excess higher order bits.

Conversion can be done in 2 ways: 
1.      ```c
        prod=(float)a*b;
        ```
2.      ```c
        prod=(1.0)a*b;
        ```

---
### Reading, Printing Characters
```c
char ans;
printf("Are you above 18 years old? (Type Y for yes and N for no)");
ans = getchar();
if (ans==Y)
{
    printf("You can vote!");
}
else
{
    printf("Too young to vote!");
}
```
`getchar` stores value entered by user (Y or N) in 'ans'.

```c

```
`isalpha` assumes >0(True) value if entered character includes an alphabet and assumes value 0(False) otherwise.

---
## Decision Making

### IF Statement
Evaluates the given expression, based on the output, if true (non-zero) or false (zero), it transfers control to a statement.

```c
if (test expression)
{
    statement-block;
}
statement-x;
```
### IF...Else Statement
```c
if (test expression)
    {
        True block statement;
    }
else 
    {
        False block statement;
    }
statementx;
```
If test expression is true, then the true block statement is executed. If its false, the false block statement in `else` is executed. After the loop is exited, statement-x and the rest of the code following the loop are executed.

### Else IF Statement
```c
if (test expressio)
{
    True block statement;
}
else if (test expression)
{
    statement;
}
```
Used when another `if` statement is being executed in the `else` block.
---
## Loops

LOOP = CTRL statement + BODY of LOOP

A loop requires 3 things:
1. **Initialisation**
2. **Checking**
3. **Updation**

|Entry Ctrl Loop|Exit Ctrl Loop|
|----------|--------------|
|Ctrl condition is checked before executing the loop for first time|Ctrl condition is checked after executing the loop for first time|

### While Loop
Entry Ctrl Loop

```c
while (test expression)
    {
        body of loop
    }
statement;
```
Executes body of loop untill the test expression holds true.

**Initialisation** takes place before the `while` loop. **Checking** takes place in the 'test expression', and **Updationg** takes place in the body of loop.

### Do Loop
Exit Ctrl Loop

```c
do
{
    body of loop
}
while (test expression);
```
Executes body of loop once before checking then works same way as `while` loop.

### For Loop
Entry Ctrl Loop
```c
for(initialisation; checking; updation)
{
    body of loop;
}
```

>`for` Loop: Used when we know how many times the loop has to be run.
>`do...while` and `while` Loop: Used when we don't know how many times the loop has to be run.

---
## Arrays
Regular variables hold **one** value.
```c
int x=2;
```
Arrays hold **multiple values of same type**.
```c
int x[2];
//array x holds 2 integers
```
2 in bracket is **size**, the total number of elements it can store.

```c
int x[2]; //creates array x holding 2 integer values
x[0] = 1; //first element of array hold value 1
x[1] = 4; //last element of array holds value 4
```
'0' and '1' in [] are *indices* plural and *index* singular.

>If size is `n`, then indices are `0` to `n-1`.

To enter values in array, a loop is used where each time loop runs, it stores one element.
```c
int x[15], i;
for (i=0; i<15; i++)
    {
        scanf("%d", &x[i]);
    }
```
To print an array:
```c
for (i=0; i<15; i++)
    {
        printf("%d", x[i]);
    }
```
**Variable Length Array (VLA)**: Arrays whose size is entered by the user and then stored in the array.
>`/*....*/` is for multi-line comments.
>`//` is for single line comments.

---
## Pointers
Every declared variable lives in the RAM at an **address** - a number.
```c
int x = 8;
```
A *box* is made in the memory at address `1000` and contains value `8`.

**Pointer**: Its a variable that stored an address of a regular value.
```c
int *p = &x; //Read as: Pointer P equals to address of x
```
|Symbol|Eg|Meaning|
|------|---|------|
|`&`|`&x`|at the address of|
|`*`(while declaring)|`int *x`|this is a pointer|
|`*`(after declaring)|`*x`|go to address of x and get value stored there|

```c
int x=2;;
int *p=&x; //declares p as a pointer
printf("%d is value of x", x);
printf("%u is address of %d", *p, x);
printf("%d is address of %d", p, x);
printf("%d is address of %d", &x, x);
printf("%d is value stored at %u", x, *p);

*p=10; //at the address `p`, store the value 10; x is now 10
```

---
## Functions
---
## Structures
Structure (`struct`) is a user-defined data type where in we can have **different data types** under one name.
>Array holds large amount of elements of same data type, struct helps us model real-world entity with mixed data.
```c
struct book 
{
    char title;
    float price;
    int pages;
};
```
The above code defines the **type**, but nothing has been allocated in the memory yet.
### Declaring Structures
```c
struct book
{
    char title;
    float price;
};
struct book b1={"Treasure Island", 500.00}; //declaration and initialisation
struct book b2; //only declares, no initialisation
```
### Accessing Members
**Dot Operator(`.`)** for direct variables
```c
b2.title="Pride and Prejudice";
b2.price=800.00;
```
### Memory Layout
Members of `struct` are stored in **declared order**, continuously.
>Compiler may insert **padding bytes** between members to satisfy alignment requirements.
```c
struct book
{
    char title; // 1 byte
                // padding 3 byte
    int pages; // 4 byte
    float price; // 2 byte
                 // padding 2 byte
};
//since largest byte size is 4, padding of 3 byte and 2 byte is added to title and price respectively to align struct size
// sizeof(struct Example) = 12
```
### Passing Values
```c
void main()
{
    struct book
    {
        char title;
        float price;
    };
    struct book b1={"20,000 Leagues Under the Sea", 250.00}
    Printing_Struct(b1.title, b1.price);
}
void Printing_Struct(char x, float y)
{
    printf("\n%c of price %f", x, y);
}
```
### Nested Structures
```c
struct date_log
{
    int year;
    int month;
    int day;
};
struct Person
{
    char name[5];
    struct date_log birthday;
};
struct Person p1={"Sam", 2003, 12, 25};
printf("\n %c has his birthday on %d/%d/%d", Person.name, Person.date_log.day, Person.date_log.month, Person.date_log.year);
```
### Arrays of Structure
```c
struct Coordinates
{
    int x;
    int y;
}
struct Coordinates[2]={{0,0}, {1,0}};
for (int i=0; i<2>, i++)
{
    printf("\n(%d, %d)", Coordinates[i].x, coordinates[i].y);
}
```