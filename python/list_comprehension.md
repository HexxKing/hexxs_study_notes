<h3 align="center"><a href="https://github.com/HexxKing/hexxs_study_notes#-1">👈 Back to Table of Contents</a></h3>

---------------------------------------

# ✍️ Notes for List Comprehension in Python

```
# The Syntax
newlist = [expression for item in iterable if condition == True]
```

- List comprehension is an elegant way to define and create a list in python.
- List comprehension offers a shorter syntax when you want to create a new list based on the values of an existing list.
- A list comprehension generally consist of these parts :
  - Output expression
    - The expression is the current item in the iteration, but it is also the outcome, which you can manipulate before it ends up like a list item in the new list
    - The expression can also contain conditions, not like a filter, but as a way to manipulate the outcome
  - Input sequence
    - The iterable can be any iterable object, like a list, tuple, set etc.
  - A variable representing a member of the input sequence 
  - An optional predicate part
    - The condition is like a filter that only accepts the items that valuate to True.
      - The condition is optional and can be omitted
- The return value is a new list, leaving the old list unchanged.

```
For example :

lst  =  [x ** 2  for x in range (1, 11)   if  x % 2 == 1] 

here, x ** 2 is output expression, 
      range (1, 11)  is input sequence, 
      x is variable and   
      if x % 2 == 1 is predicate part.
```

---------------------------------------

## 📚 Resources Used in Researching List Comprehension
- [GeeksforGeeks](https://www.geeksforgeeks.org/python-list-comprehension-and-slicing/)
- [w3schools.com](https://www.w3schools.com/python/python_lists_comprehension.asp)

