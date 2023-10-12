


#### Sorting

1. Given the following list of courses, create a function that sorts the courses first by their numeric component and then alphabetically by their department code.
```python
courses = ["ENGL105", "PHYS301", "MATH205", "CS110", "CHEM450"]
```

Write a function to sort these courses by their numeric component.
 
 ---
#### List Comprehensions

1. Produce the following lists using list comprehensions:
	1. `[3, 6, 9, 12, 15, 18, 21, 24, 27]`
	2. `['A-', 'B-', 'C-', 'D-', 'E-']`
	3. `[(4, 8), (5, 10), (6, 12), (7, 14)]`
	4. `[4, 5, 6, 4, 5, 6, 4, 5, 6]`
	5. `[4, 4, 4, 5, 5, 5, 6, 6, 6]`

---

#### Grouping Strings by Length

For the given list of words:
```python
phrases = ["hello", "world", "data science", "python", "machine learning"]
```
Generate a dictionary where keys are the lengths of phrases and values are lists of phrases of that length.


---

#### Distinct Elements in a String

Create a function that takes a sentence and returns a set containing all the distinct words in that sentence, ignoring punctuation.

---

#### Working with Dictionaries

Using the following data:
```python
capitals = {"USA": "Washington, D.C.", 
            "UK": "London",
            "France": "Paris",
            "Germany": "Berlin"}
```
Write a function that lets a user add a new country and its capital to the dictionary.

---

#### Manipulating Sets

Create a set of your favorite books. Write functions to add a book, remove a book, and check if a book is in your set.


---

#### Pairing Elements

For a given list of numbers:
```python
values = [9, 8, 7, 6, 5, 4, 3, 2]
```
Convert this list into pairs like so: `[(9, 8), (7, 6), (5, 4), (3, 2)]`


---

#### Flattening Data

For the given list of pairs:
```python
pairs = [(10, 11), (12, 13), (14, 15), (16, 17)]
```
Flatten this list to get: `[10, 11, 12, 13, 14, 15, 16, 17]`


---


#### Processing Grade Data

Assume a file named `scores.dat` has the following format:
```
student_name,quiz1,quiz2,final_exam
```

Design a program that:

- Computes the final score for each student, where `final_exam` is 50% of the grade, and `quiz1` and `quiz2` are 25% each.

- Determines the class average for each component (`quiz1`, `quiz2`, and `final_exam`).