<h3 align="center"><a href="../table_of_contents.md">👈 Back to Table of Contents</a></h3>

---------------------------------------

# ✍️ Notes for List Comprehension in Python

- List comprehension is an elegant way to define and create a list in python.
- A list comprehension generally consist of these parts :
  - Output expression,
  - Input sequence,
  - A variable representing a member of the input sequence and
  - An optional predicate part.

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
