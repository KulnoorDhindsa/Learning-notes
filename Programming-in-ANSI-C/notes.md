# Notes

## Chapter 1 - Introduction to Computing
Computer is an electronic device capable to perform arithmetic and logical calculations.

Components of a computer:
***CPU (Central Processing Unit)**:
All processing activities take place in it. Its a VLSI circuit consisting of ALU and CU.

---
## Chapter 4 - Operators and Expressions

### 4.1 Operators
Symbols that tell the computer to perform logical or mathematical operations to manipulate data and variables.
### 4.1.1 Arithmetic Operators
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

### 4.1.2 Relational Operators
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

### 4.1.3 Logical Operators
Operators that evaluat **boolean conditions** and return either 1(true) or 0(false).

|Operator|Logical Name|Syntax|Returns 1 when|
|--------|----|------|--------------|
|`&&`|AND|`A && B`|**Both** A and B are true|
|`\|\|`|OR|`A \|\| B`|**At least one** of A or B is true|
|`!`|NOT|`!A`|A **is zero**.|

>`&&` never evaluates right side if left side is false.

>`||` never evaluates right side if left side is true.

*Double Negation* i.e. `!5` and `!!5` returns 0 and 1 respectively.

### 4.1.4 Assignment Operators
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

#### 4.1.5 Increment and Decrement Operators
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

### 4.1.6 Conditional Operators
Its a shorthand for if-else in one line.

`exp1 ? exp2 : exp3` read as - ***If exp1 is true, give me exp2, otherwise give me exp3**.

Only **one** of exp2 or oxp3 is ever run, like in **if-else**.

### 4.1.7 Bitwise Operators
Operators that manipulate data at the binary level.

**NOT** applicable to **float** or **double**.

### 4.1.8 Special Operators
|Operator|What it does|
|--------|------------|
|`,`| |
|`sizeof`|`m = sizeof(operand);` , gives number of bytes occupied by operand|
---

>variable=expression;

The expression is evaluated first and then that value is given to the variable.

All variables used should have be declared prior in the code.
---

### 4.2 Precedence of Operators
( ) expression within () is guven **HIGHEST PRIORITY** from left to right.
If () are nested, evaluation starts from inner most ().

>HIGH PRIORITY: `*` > `/` > `%`

>LOW PRIORITY: `+` > `-`

High priority operators are evaluated first followed by lower priority operators.
---

### 4.3 Type Conversions
### 4.3.1 Implicit Type Conversion
Automatic conversion of intermediate values to proper type for evaluation.
During evaluation, the *lower* type is converted to the *higher* type.

**Conversion Hierarchy**
Long Double > Double > Float > Unsigned Long Int > Long Int > Unsigned Int > Int > ( Short = Char )

Final result of expression is converted to match type of variables on left of the assignment sign.

During final assignment:
- **float** to **int** truncates fractional part.
- **double** to **float** rounds off digits.
- **long int** to **int** causes dropping of excess higher order bits.

### 4.3.2 Explicit Conversion
Local conversion.s

**(type-name) expression**

---
## Chapter 6 - Decision Making and Branching

### 6.1. IF Statement
Evaluates the given expression, based on the output, if true (non-zero) or false (zero), it transfers control to a statement.

```c
if (test expression)
{
    statement-block;
}
statement-x;
```
### 6.2 IF...Else Statement
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

### 6.3 Nesting of If...Else
Another `If...Else` can be nested in a larger `If...Else` along with indentation for better understanding of the code.

## Chapter 8 - Array








for loop: when you know how many times you hvae to run the loop
do/while loop: when you dont know how many times to run the loop