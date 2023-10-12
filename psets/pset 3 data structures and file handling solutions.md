


#### Sorting

1. Given the following list of courses, create a function that sorts the courses first by their numeric component and then alphabetically by their department code.
```python
courses = ["ENGL105", "PHYS301", "MATH205", "CS110", "CHEM450"]
```

Write a function to sort these courses by their numeric component.
```python
def sort_courses(course_list):
    return sorted(course_list, key=lambda x: (int(''.join(filter(str.isdigit, x))), x))

sorted_courses = sort_courses(["ENGL105", "PHYS301", "MATH205", "CS110", "CHEM450"])
```

 ---
#### List Comprehensions

1. Produce the following lists using list comprehensions:
	1. `[3, 6, 9, 12, 15, 18, 21, 24, 27]`
	2. `['A-', 'B-', 'C-', 'D-', 'E-']`
	3. `[(4, 8), (5, 10), (6, 12), (7, 14)]`
	4. `[4, 5, 6, 4, 5, 6, 4, 5, 6]`
	5. `[4, 4, 4, 5, 5, 5, 6, 6, 6]`

```python
list1 = [i*3 for i in range(1, 10)]
list2 = [f"{chr(i+64)}-" for i in range(1, 6)]
list3 = [(i, i*2) for i in range(4, 8)]
list4 = [i for i in range(4, 7) for _ in range(3)]
list5 = [i for _ in range(3) for i in range(4, 7)]
```



---

#### Grouping Strings by Length

For the given list of words:
```python
phrases = ["hello", "world", "data science", "python", "machine learning"]
```
Generate a dictionary where keys are the lengths of phrases and values are lists of phrases of that length.

```python
phrases = ["hello", "world", "data science", "python", "machine learning"]
grouped_phrases = {len(phrase): [] for phrase in phrases}
for phrase in phrases:
    grouped_phrases[len(phrase)].append(phrase)
```

---

#### Distinct Elements in a String

Create a function that takes a sentence and returns a set containing all the distinct words in that sentence, ignoring punctuation.

```python
import string

def distinct_words(sentence):
    translator = str.maketrans('', '', string.punctuation)
    cleaned_sentence = sentence.translate(translator)
    return set(cleaned_sentence.split())
```


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

```python
def add_country(capitals_dict):
    country = input("Enter the name of the country: ")
    capital = input("Enter the capital of the country: ")
    capitals_dict[country] = capital

capitals = {"USA": "Washington, D.C.", "UK": "London", "France": "Paris", "Germany": "Berlin"}
add_country(capitals)
```



---

#### Manipulating Sets

Create a set of your favorite books. Write functions to add a book, remove a book, and check if a book is in your set.
```python
favorite_books = {"Pride and Prejudice", "1984", "The Great Gatsby"}

def add_book(book):
    favorite_books.add(book)

def remove_book(book):
    favorite_books.discard(book)

def check_book(book):
    return book in favorite_books
```


---

#### Pairing Elements

For a given list of numbers:
```python
values = [9, 8, 7, 6, 5, 4, 3, 2]
```
Convert this list into pairs like so: `[(9, 8), (7, 6), (5, 4), (3, 2)]`

```python
values = [9, 8, 7, 6, 5, 4, 3, 2]
paired_values = [(values[i], values[i+1]) for i in range(0, len(values), 2)]
```


---

#### Flattening Data

For the given list of pairs:
```python
pairs = [(10, 11), (12, 13), (14, 15), (16, 17)]
flattened_list = [item for pair in pairs for item in pair]
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

```python
def compute_scores(file_name):
    student_scores = {}
    quiz1_scores, quiz2_scores, final_scores = [], [], []

    with open(file_name, 'r') as file:
        next(file)  # skip header
        for line in file:
            data = line.strip().split(',')
            student, quiz1, quiz2, final_exam = data[0], float(data[1]), float(data[2]), float(data[3])
            
            final_score = quiz1 * 0.25 + quiz2 * 0.25 + final_exam * 0.5
            student_scores[student] = final_score
            
            quiz1_scores.append(quiz1)
            quiz2_scores.append(quiz2)
            final_scores.append(final_exam)

    avg_quiz1 = sum(quiz1_scores) / len(quiz1_scores)
    avg_quiz2 = sum(quiz2_scores) / len(quiz2_scores)
    avg_final = sum(final_scores) / len(final_scores)

    return student_scores, avg_quiz1, avg_quiz2, avg_final
```

