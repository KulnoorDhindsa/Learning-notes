# My Mistakes While Programing in C
1. `printf("%d", x);` is for printing decimal integers.
   
   `printf("%f", x);` is for printing `float` characters.
   
   `printf("%c", x);` is for printing `char` characters.

2. `N%10=n1` is less correct compared to `n1=N%10` as in `a=b` in C, a is assigned the value of b and orignal value of a is lost in the process.

>Assignement is from LEFT to RIGHT in C and other programmin languages.
