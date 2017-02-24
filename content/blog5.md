Title: Copy in Python
Date: 2017-01-10 10:20
Category: Review

One thing that might be very helpful is to know that "Assignment statements in python do not copy objects, they create bindings between a target and an object". To make it clear what I mean by this, I provide an example. Assume you create a list called a:
``` python
a = [1,2,3,4]
```
if you want to have a copy of it you can assign it to a new variable:
``` python
b = a
```
Now if you make a change to your variable a, you do not expect variable b be affected. However, this is not the case in python. So, for example if you append an entry to the list a, it will be added to b as well as follow:
``` python
a.append(5)
print b
[1, 2, 3, 4, 5]
```

This happens due to above mentioned fact that you didn’t copy the list referenced by a. You just created a new tag called b and attached it to the list a’s memory address. And a and b really do point to the same memory address. So, to assign a new memory address for the list you are copying, you should do:
``` python
b = a [:] 
# or 
b = copy.copy(a) 
b = copy.deepcopy(a)
```
First returns a shallow copy of a and second one returns a deep copy of a.

The difference between shallow and deep copying is only relevant for objects that contain other objects (compound objects like lists or class instances)

