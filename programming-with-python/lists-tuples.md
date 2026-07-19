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
---
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
---
## `in` and `not`
- `in` and `not` operators are used to check if a list item actually exists in the list.
```python
books=["ACOTAR", "Fourth Wing", "The Ballad of Never After"]
print("ACOTAR" in books) #prints True
print("Shatter Me" in books) #prints False
print("Fourth Wing" not in books) #prints False
```
---
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
---
## `index()` Method
```python
colors=["red", "orange", "blue", "violet"]
print(colors.index("red")) #prints 0
```
---
## `append()`, `insert()` and `remove()`
```python
colors=["red", "orange", "blue", "violet"]
colors.append("black")
colors.insert(2, "white)
colors.remove("orange")
```
- `colors.append("black")` adds "black" as list item in the end, i.e. gives it *index 4*  in list *colors*
- `colors.insert(2, "white")` adds "white" as list item with *index 2* in list *colors*
- `colors.remove("orange")` removes orange as a list item from list *colors*
>`insert()` and `append()` only work with **lists** and not with normal variables (they can't convert a normal variable into a list)
---
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
---
# Data Type - List Like - Strings
```python
fruit="Mango"
print(Mango[0]) #prints M
print(Mango[3]) #prints g
for i in fruit:
    print(fruit[i], end=" ")
```