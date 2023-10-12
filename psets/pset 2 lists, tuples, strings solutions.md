
#### Lists

1. Create a list of the first 10 even numbers.
```python
even_numbers = [i*2 for i in range(1, 11)]
```


2. Find the length of the list you created.
```python
length = len(even_numbers)
```


3. Check if the number 12 is in your list.
```python
is_12_present = 12 in even_numbers
```
Returns `bool`

4. Write a function that accepts a list of numbers and returns the average of the numbers.
```python
def average(nums):
    return sum(nums) / len(nums)
```

5. Write a function that accepts a list of words and returns a single string where the words are separated by spaces.
```python
def join_words(word_list):
    return ' '.join(word_list)
```


6. Given a list `[3, 1, 4, 1, 5, 9, 2, 6, 5, 3, 5]`, extract all elements from the 4th to the 8th element (inclusive).
```python
my_list = [3, 1, 4, 1, 5, 9, 2, 6, 5, 3, 5]
extracted_elements = my_list[3:8]
```
`extracted_elements = my_list[3:8]`: This is using Python's list slicing syntax to extract a part of the list.

The slicing syntax `list[start:stop]` extracts elements from the `start` index up to, but not including, the `stop` index. In Python, list indices start at 0.

- The `start` in our slice is `3`, so the extraction begins from the fourth element of the list (since the first element is at index 0).
- The `stop` in our slice is `8`, so the extraction will go up to, but not include, the element at index 8.


---
#### Tuples

1. Create a tuple containing the numbers 10, 20, and 30.
```python
my_tuple = (10, 20, 30)
```


2. Try to modify the second value of the tuple to 25. What happens?

You cannot modify the second value of a tuple. If you try, you will get a `TypeError`.


3. Swap the values of two variables using tuple unpacking.
```python
a = 5
b = 10
a, b = b, a
```

---
#### Strings

1. Convert the string `"Python is great!"` into a list of words.
```python
sentence = "Python is great!"
words = sentence.split()
```
`sentence.split()`: The `split()` method is a string method in Python. When called without any arguments, it splits a string wherever it finds whitespace characters (like spaces, tabs, etc.) and returns a list of substrings.

Given the string in the `sentence` variable, `"Python is great!"`, here's how `split()` works:

- It identifies the first space after the word 'Python' and splits the string there.
- It then identifies the next space after the word 'is' and splits the string again.
- Finally, since there's no more spaces after the word 'great!', that word is taken as the final element.

The result list will be: `['Python', 'is', 'great!']`


2. Join the list `['Python', 'is', 'great!']` into a single string.
```python
word_list = ['Python', 'is', 'great!']
joined_sentence = ' '.join(word_list)
```
`' '.join(word_list)`: The `join()` method is a string method in Python. It takes an iterable (like a list or a tuple) as an argument and concatenates its elements into a single string. The string on which `join()` is called (in this case, `' '`) is used as the delimiter between each element. So, `' '.join(word_list)` takes each word from the `word_list` and joins them into a single string, using a space (`' '`) as the delimiter.

For our given `word_list`, the `join()` method does the following:

- Takes the first word, 'Python', and starts building the final string.
- Inserts a space.
- Adds the second word, 'is'.
- Inserts another space.
- Finally, adds the third word, 'great!'.

This results in the single string `'Python is great!'`.



3. Write a function that counts the number of vowels in a given string.
```python
def count_vowels(s):
    return sum(1 for char in s if char.lower() in 'aeiou')
```
- for every `char` in our word `s`, if the lower case of that `char` is either a,e,i,o,u: then we add to the sum statement +1 for every instance. 

---
#### List Comprehensions

1. Using a list comprehension, generate a list of the squares of the first 10 natural numbers.
```python
squares = [i**2 for i in range(1, 11)]
```


2. Create a list of all even numbers between 1 and 50 using list comprehension.
```python
evens = [i for i in range(1, 51) if i % 2 == 0]
```


3. Using list comprehension, create a list of all numbers between 1 and 100 that are divisible by 3 or 5, but not both.
```python
nums = [i for i in range(1, 101) if (i % 3 == 0) ^ (i % 5 == 0)]
```

`for i in range(1, 101)`: This iterates over all numbers between 1 and 100 (inclusive).

`if (i % 3 == 0) ^ (i % 5 == 0)`: This is the condition that each number `i` must satisfy in order to be included in the resulting list.

Dissecting the condition:
- `i % 3 == 0`: This checks if `i` is divisible by 3.
- `i % 5 == 0`: This checks if `i` is divisible by 5.

- `^`: This is the bitwise XOR (exclusive or) operator. It returns `True` if exactly one of its operands is `True` and the other is `False`, and `False` otherwise.

The condition `(i % 3 == 0) ^ (i % 5 == 0)` will be `True` in two scenarios:

-  `i` is divisible by 3 but not by 5. 
-  `i` is divisible by 5 but not by 3.

However, it will be `False` if `i` is divisible by both 3 and 5, which ensures numbers divisible by both (i.e., divisible by 15) are not included in the resulting list.

---
#### Challenges

1. Given two lists `a = [1, 2, 3]` and `b = [4, 5, 6]`, create a new list that contains the product of elements at corresponding positions (i.e., `[1*4, 2*5, 3*6]`).
```python
a = [1, 2, 3]
b = [4, 5, 6]
product_list = [a[i]*b[i] for i in range(len(a))]
```


2. Write a function that checks if a given word is an anagram of another given word.
```python
def are_anagrams(word1, word2):
    return sorted(word1) == sorted(word2)
```


3. Using list comprehension, generate a list of all prime numbers between 2 and 50.
```python
def is_prime(n):
    if n < 2:
        return False
    for i in range(2, int(n**0.5)+1):
        if n % i == 0:
            return False
    return True

primes = [i for i in range(2, 51) if is_prime(i)]
```

