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