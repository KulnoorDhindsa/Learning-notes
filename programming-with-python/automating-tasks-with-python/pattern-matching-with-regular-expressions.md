**Regular Expressions**: Regular Expressions , *regex* are description for a pattern of text.
- `\d` in *regex* is used for identifying *digits* (0-9). So, `\d\d\d-\d\d\d-\d\d\d\d` represents 3 digits, followed by '-', another 3 digits with '-', followed by 4 digits.
- `\d\d\d-\d\d\d-\d\d\d\d` is same as `\d{3}-\d{3}-\d{4}`, matching the pattern thrice, thrice and four times.
>`\` is used for *escape characters*, where certain characters in python, if used without `\` would result in error in the code.
```python
print("The members of the "New Order" have left the castle.") #error
print("The members of the \"New Order\" have left the castle.") #no error
```
```python
import re #import regex module
phonenumberregex=re.compile(r'\d{3}-\d{3}-\d{4}') #creating regex with raw string (re.compile(r''))
num=phonenumberregex.search('Hi! Call me at 415-415-4155') #passing string to search()
print('Phone number:', num.group()) #calling group(): Match or None of the string
```
- `re` module contains all **regex** expressions of python, and is used in code by `import re` at the start of code.
- `search()` searches the string for matches to the created regex and returns `None` and `Match` accordingly.
- `Match` objects have *groups*, which is called by `num.group()`.
