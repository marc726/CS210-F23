
#### String Slicing

Given the string `r = "Programming is fun!"`, determine what the output will be for 
```python
list(r)[5]
```

---
#### List Comprehensions and Range

What does the following code produce: `[i*2 for i in range(5)]`?

---
#### Set Operations

You have sets `X` and `Y` defined as:
- `X`: Even integers between 2 and 10 (inclusive).
- `Y`: Integers between 4 and 14 that are divisible by 4. 

What is the result of `X & Y`?

---
#### Tuples and Lists

Which of the following statements is FALSE?

- (a) Tuples are immutable, while lists are mutable.
- (b) You can't have a list inside a tuple because tuples are immutable.
- (c) Tuples use parentheses `()`, while lists use square brackets `[]`.
- (d) Both tuples and lists can be used as dictionary keys.

---
#### Dictionary Operations

If `color_map = {"red": "#FF0000", "green": "#00FF00", "blue": "#0000FF"}`, what will the value of `color_map.get("yellow", "#FFFF00")` be?

---
#### Set Modifications

After adding the same element to a set multiple times, what will happen to the size of the set?

--- 

#### File Writing Modes

Consider the following Python code:
```python
with open("testfile.txt", "w") as f:
    f.write("Hello,")
with open("testfile.txt", "a") as f:
    f.write(" World!")
```
What will be the contents of `testfile.txt`?

---

#### Using `defaultdict`

Given the following code:
```python
from collections import defaultdict
counter = defaultdict(int)
words = ["apple", "banana", "apple", "grape", "banana"]
for word in words:
    counter[word] += 1
```

What is the value of `counter["apple"]`?

---
#### Built-in Functions

You have two lists: `a = [1, 2, 3]` and `b = ["one", "two", "three"]`. How can you combine them into a dictionary with keys from `a` and values from `b`?

---

#### List Comprehensions with Conditional Logic

What does the following code produce: `[x for x in range(10) if x%2 == 0]`?