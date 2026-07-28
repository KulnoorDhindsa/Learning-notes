# Regular Expressions
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
---
### Grouping with ()
- Adding `()` creates *groups* in regex `(\d{3})-(\d{3}-\d{4})` where `(\d{3})` is *group 1* and `(\d{3}-\d{4})` is *group 2*.
```python
import re
phonenumberregex=re.compile(r'(\d\d\d)-(\d\d\d-\d\d\d\d)')
num=phonenumberregex.search('Hi! Call me at 123-456-7890')
areacode, number =num.groups()
print(areacode) #prints 123
print(number) #prints 456-7890
print(num.group()) #prints 123-456-7890
print(num.group(1)) #prints 123
print(num.group(2)) #prints 456-7890
print(num.group(0)) #prints 123-456-7890
```
### Grouping with |
```python
import re
nameregex=re.compile(r'Tina|Thomas')
g1=nameregex.search('Hi! My name is Tina. This is Thomas, my neighbour.')
print(g1.group())

g2=nameregex.search('Hi! My name is Thomas. This is Tina, my neighbour.')
print(g2.group())
```
- `|` *pipeline* allows the `search()` to only look for *either* Tina or Thomas and in case of both, looks for the first one only.
### Optional Matching with ?
```python
import re
find=heroregex.search('Hey! Its Ironman.')
print(find.group()) #prints Ironman
print(find.group(1)) #None, as there is only 1 main group

find2=heroregex.search('Where is Ironwoman?')
print(find2.group()) #prints Ironwoman
print(find2.group(1)) #prints wo
```
### Optional Matching with *
- The group preceding `*`, can be iterated as many number of times or even zero, and will still be included in the group.
```python
import re
regex1=re.compile(r'l(o)*(v)*(e)*')
result=regex1.search('I love my job!')
print(result.group())
result2=regex1.search('I looooooove my job!')
print(result2.group())
result3=regex1.search('I looovvveee my job!')
print(result3.group())
```
