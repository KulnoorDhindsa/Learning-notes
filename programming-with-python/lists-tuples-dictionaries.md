# Data Type - List
- **List** data type contains multiple values (of various data types) in ordered sequence.
- *list value* refers to the entirity of the list (e.g. `["cat", "mouse", "monkey", 2, 0, -1, 0.90]`)
- `cat`, `mouse`, `0` etc are *items*.
```python
veggie_list=["carrot", "tomato", "tori"]
print(veggie_list[2]) #prints tori
```
- `veggie_list[0]`="carrot", `veggie_list[1]`="tomato", `veggie_list[2]`="tori" (the integer in the `[]` is *index*)
>`IndexError` appears when index is bigger than total number of items in the list.
```python
list1=[[1,2,3,4,5], ['cats', 'mice'], 56, 'cheese']
print(list1[0][4]) # first index dictactes which list value to use, second index dictactes the value within that list.
```
```python
animals=["cat", "tiger", "mouse", "elephant"]
print(animals[-1]) #prints 1st element from the back
print(animals[0:4]) #prints elements from i=0 to i=4-1=3
print(len(animals)) #prints number of items in list i.e. 4
```
## Loops with lists
```python
friends_list=[] #defines the list
while True:
	friend=input("Enter your friend's names, and nothing to stop: ")
	if friend=="":
		break
	friends_list+=[friend] #catenation of list
print("Your friends are: ")
for i in range(len(friends_list)):
	print(friend, end=" ")
```
- The above code uses `while` in an *infinite loop*, untill the user enters a specific input.
```python
grocery_list=[]
while True:
    l_entry=input("Enter grocery item, or nothing to stop: ")
    if l_entry=="":
        break
    grocery_list+=[l_entry]
for i in range(len(grocery_list)):
    print(str(i), "in list is", grocery_list[i])
```
- Use `for` loop with `list` when number of iterations required are known.
## `in` and `not`
- `in` and `not` operators are used to check if a list item actually exists in the list.
```python
books=["ACOTAR", "Fourth Wing", "The Ballad of Never After"]
print("ACOTAR" in books) #prints True
print("Shatter Me" in books) #prints False
print("Fourth Wing" not in books) #prints False
```
## Multiple Assignments
```python
house_a=["large", "rural", "cream-white"]
size, region, color =house_a
```
is same as
```python
size=house_a[0]
region=house_a[1]
color=house_a[2]
```
## `index()` Method
```python
colors=["red", "orange", "blue", "violet"]
print(colors.index("red")) #prints 0
```
## `append()`, `insert()`, `del` and `remove()`
```python
colors=["red", "orange", "blue", "violet"]
colors.append("black") #adds "black" in the last as index 4
colors.insert(2, "white") #inserts white as index 2, so 3rd element
del colors[0] #removes "red"
colors.remove("orange") #removes "orange"
print(colors) #prints ['white', 'blue', 'violet', 'black']
```
- `colors.append("black")` adds "black" as list item in the end, i.e. gives it *index 4*  in list *colors*
- `colors.insert(2, "white")` adds "white" as list item with *index 2* in list *colors*
- `colors.remove("orange")` removes orange as a list item from list *colors*
>`insert()` and `append()` only work with **lists** and not with normal variables (they can't convert a normal variable into a list)

## Sorting of lists
- `sort` works only for lists having **only** number values or string values, **not both**.
```python
number=[1,2,3,4,-1,-3,-23,0,56,78]
animals=["cat", "badger", "hedgehog"]
number.sort()
animals.sort()
animals.sort(reverse=True)
number.sort(reverse=True)
```
```python
fruit="Mango"
print(fruit[0]) #prints M
print(fruit[3]) #prints g
for i in range(len(fruit)): #for i in range of length of fruit
    print(fruit[i], end=" ") #prints letters of 'mango' with spaces
```
---
# Data Type - Tuples
- Lists are *mutable*, i.e. list items can be modifed (added, deleted, etc), but *tuples* are *immutable* like strings.
- To modify strings:
```python
name="Victor Doom"
newname = name[0:6] + " Von " + name[7:11] #adds " Von " after index 5 (in range, i starts from lower limit, goes 1 before upper limit) i.e. "r" and then adds i=7 i.e. "D" upto i=10 "m" which is 1 before upper limit of 11
print(newname)
```
>i in range starts from lower limit and goes upto 1 less that upper limit.

- A *new string* is made to update the old string.
## Defining a tuple:
```python
name=("harry", "potter", 0.34) #defines a tuple "name"
print(name[2]) #prints 3rd element of index 2 i.e. 0.34
name[2] = 0.35 #attempt to change 3rd element of tuple, shows error because tuples are immutable
```
- `()` used instead of `[]` used in strings.
## Conversions
```python
print(str(90)) #convert int 90 to '90' as a string
print(list(("hi", "this", "is", "converions", "23"))) #converts tuple(using ()) to list (with [])
print(tuple([1,2,3,4,5])) #converts list to tuple and then prints it
```
```python
spam=[0,1,2,3,4,5]
cheese=spam
cheese[3]=90 #changes the value at index 3 in the list 'cheese' to 90
print(spam) #change is observed
print(cheese) #change is observed
```
- In `spam=[0,1,2,3,4,5]`, a *reference id* is made stored in *spam* that id's the list[0,1,2,3,4,5].
>Python uses *reference id* internally only.
- In `cheese=spam`, the *reference id* is copied to `cheese`
- Any changes made in `cheese`, are changed made in the *reference id*, meaning, they are changes made in `spam` which stores the same *reference id*.

>Reference id's are used and stored in variables holding data types that are **mutable** like `list` ad `dictionaries`, not int or str.
## copy()
```python
import copy
names=["harry", "potter"]
names2=copy.copy(names)
print(names2.append("James")) #shows `none` as it modified the list in-place, but didnt return a value
print(names2) #new value appended in the list is not stored in names2, now we can print it
```
>`deepcopy()` copes lists in lists as well.
