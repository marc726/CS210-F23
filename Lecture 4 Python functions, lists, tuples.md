
#### Lists:

Example:
```python
mylist = [1, 3, 5, 7]
```

**`len`**:
The `len` function returns the number of items in an object. When used with a list, it returns the number of elements in that list.
```python
lst = [1, 2, 3, 4]
print(len(lst))  # Output: 4
```

**`list('hello')`**:
The `list` function can be used to convert an iterable into a list. When a string is passed as an argument to the `list` function, it returns a list of individual characters from that string.
```python
print(list('hello'))  # Output: ['h', 'e', 'l', 'l', 'o']
```

**`in`**:
The `in` keyword is used to check if an item exists in a list (or any other iterable). It returns `True` if the item is found in the list, otherwise `False`.
```python
lst = [1, 2, 3, 4]
print(3 in lst)  # Output: True
print(5 in lst)  # Output: False
```

**`max`, `min`**:
The `max` function returns the largest item in a list (or any other iterable), while the `min` function returns the smallest item.
```python
lst = [1, 2, 3, 4]
print(max(lst))  # Output: 4
print(min(lst))  # Output: 1
```

**`for`**:
The `for` loop is used to iterate over the items of a list (or any other iterable). Each item in the list is accessed one at a time and can be processed or used in some way.

```python
lst = [1, 2, 3, 4]
for item in lst:
    print(item)
```



**List Operations**

**`lst.count(3)`**:
The `count` method returns the number of times the specified value appears in the list.
```python
lst = [1, 2, 3, 3, 4]
print(lst.count(3))  # Output: 2
```
In this example, the number `3` appears twice in the list, so the method returns `2`.


**`lst.index('a')`**:
The `index` method returns the index of the first occurrence of the specified value in the list. If the value is not found, it raises a `ValueError`.
```python
lst = ['b', 'a', 'c', 'a']
print(lst.index('a'))  # Output: 1
```
Here, the first occurrence of `'a'` is at index `1`.


**`lst.insert(2, 'a')`**:
The `insert` method inserts the specified value at the specified index. The first argument is the index at which the value should be inserted, and the second argument is the value to be inserted.
```python
lst = [1, 2, 4]
lst.insert(2, 'a')
print(lst)  # Output: [1, 2, 'a', 4]
```


**`lst.remove('a')`**:
The `remove` method removes the first occurrence of the specified value from the list. If the value is not found in the list, it raises a `ValueError`.
```python
lst = ['b', 'a', 'c', 'a']
lst.remove('a')
print(lst)  # Output: ['b', 'c', 'a']
```
The list is reversed, so the last item becomes the first, the second-to-last becomes the second, and so on.


#### Strings

**Convert string to list:**
You can convert a string to a list of its individual characters using the `list()` function.
```python
s = "hello"
lst = list(s)
print(lst)  # Output: ['h', 'e', 'l', 'l', 'o']
```

**Convert list to string:**
You can convert a list of characters back to a string using the `join()` method. The string on which `join()` is called is used as a delimiter.
```python
lst = ['h', 'e', 'l', 'l', 'o']
s = ''.join(lst)
print(s)  # Output: "hello"
```

**`s.split()`**:
The `split()` method of a string is used to split the string into a list of substrings based on a specified delimiter. If no delimiter is provided, it defaults to splitting on whitespace.
```python
s = "hello world"
lst = s.split()
print(lst)  # Output: ['hello', 'world']
```
You can also specify a delimiter. For example:
```python
s = "apple,banana,orange"
lst = s.split(',')
print(lst)  # Output: ['apple', 'banana', 'orange']
```

**`s.join()`**:
The `join()` method is used to concatenate a list of strings into a single string using a specified delimiter. The string on which `join()` is called is used as the delimiter.
```python
lst = ['apple', 'banana', 'orange']
s = ','.join(lst)
print(s)  # Output: "apple,banana,orange"
```
Another example:
```python
lst = ['hello', 'world']
s = ' '.join(lst)
print(s)  # Output: "hello world"
```


#### Nested lists

```python
myList = [[1, 2, 3], 
		  [4, 5, 6], 
		  [7, 8, 9]]
```


**Problem:**

Write a program to produce a list of tuples of the form (𝑥, 𝑥2 ), where 1 ≤ 𝑥 ≤ 10

```python
# Using list comprehension to generate the list of tuples
result = [(x, x**2) for x in range(1, 11)]

print(result)
```

**`for x in range(1, 11)`**:

This is a loop that iterates over each value of `x` from `1` to `10` (inclusive). The `range(1, 11)` function generates numbers from `1` up to (but not including) `11`.
**`(x, x**2)`**:

For each value of `x` from the loop, this creates a tuple. The first element of the tuple is `x`, and the second element is `x**2`, which is `x` raised to the power of `2` (squared).
**`[(x, x**2) for x in range(1, 11)]`**:

The entire expression creates a new list. For each value of `x` from `1` to `10`, it adds a tuple to the list. The tuple contains two elements: the current value of `x` and its square.

Note: `**` is exponential operator. For example: `2**3` = $2^3$


Given two lists xs and ys, produce all (x, y) pairs where $x\ne y$


```python
xs = [1, 2, 3]
ys = [2, 3, 4]

result = [(x, y) for x in xs for y in ys if x != y]
print(result)
```
n this example, the list comprehension iterates over each element `x` in `xs` and each element `y` in `ys`. It then checks if `x` is not equal to `y` using the condition `if x != y`. If the condition is true, the pair $(x,y)$ is added to the `result` list.







Write a recursive function that concatenates two lists.

```python
def concatenate_recursive(list1, list2):
    # Base case: If list1 is empty, return list2
    if not list1:
        return list2
    # Recursive case: Add the first element of list1 to the result of concatenating the rest of list1 with list2
    return [list1[0]] + concatenate_recursive(list1[1:], list2)

# Example usage:
list1 = [1, 2, 3]
list2 = [4, 5, 6]
result = concatenate_recursive(list1, list2)
print(result)  # Output: [1, 2, 3, 4, 5, 6]
```

- The base case checks if `list1` is empty. If it is, it returns `list2` since there's nothing left to concatenate.
- In the recursive case, the function takes the first element of `list1` and concatenates it with the result of the recursive call, which concatenates the rest of `list1` with `list2`. This process continues until `list1` is empty, at which point the base case is triggered.

**Note**: When you see `list1[1:]`, it means: 
- Start from the element at index `1` (which is the second element, since indexing starts at `0`).
- Go until the end of the list.