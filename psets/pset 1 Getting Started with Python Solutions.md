

#### Command-line parameters

1. **Write a Python script that accepts two command-line parameters and prints their sum.**
```python
import sys

num1 = float(sys.argv[1])
num2 = float(sys.argv[2])
print(f"Sum: {num1 + num2}")
```


2. **Modify the script to handle cases where the command-line parameters are not numbers.**
```python
import sys

try:
    num1 = float(sys.argv[1])
    num2 = float(sys.argv[2])
    print(f"Sum: {num1 + num2}")
except ValueError:
    print("Please provide two valid numbers as command-line parameters.")
```


---

#### Functions

1. Define a function named `square` that takes a number as an argument and returns its square.
```python
def square(num):
    return num * num
```

2. Write a function named `is_even` that checks if a given number is even and returns a boolean value.
```python
def is_even(num):
    return num % 2 == 0
```

3. Given the following code, predict the output:
```python
def g():
    x = 10
def f():
    x = 5
g()
print(x)
```
The output of the provided code is an error. The variable `x` is not defined in the global scope.


4. Consider the following function:
```python
def greet(name="Guest"):
    return f"Hello, {name}!"
```
What will be the output of `greet()` and `greet("Alice")`?
- `greet()` will output `Hello, Guest!`
- For `greet("Alice")`: In this case, you're providing the argument "Alice", so it'll override the default value "Guest". Thus, the output will be:`Hello, Alice!`

---

#### Patterns

1. Write a program that outputs the following pattern:
```
*
* *
* * *
* * * *
* * * * *
```

```python
for i in range(1, 6):
    print('* ' * i)
```

2. Modify the program to accept an integer $n$ as input and print the pattern of height $n$.
```python
n = int(input("Enter the height of the pattern: "))
for i in range(1, n+1):
    print('* ' * i)
```

---

#### Multiple Return Values

1. Write a function named `min_max` that takes a list of numbers as an argument and returns both the minimum and maximum values from the list.
```python
def min_max(nums):
    return min(nums), max(nums)
```

2. How can you unpack the returned values from the `min_max` function into two separate variables?
```python
smallest, largest = min_max([4, 2, 9, 7])
```

---

#### Function Scopes

1. Explain the difference between local and global variables in the context of functions.

Local variables are defined within a function and cannot be accessed outside that function. Global variables are defined outside any function and can be accessed and modified both inside and outside functions.

2. Given the following code, predict the output:
```python
y = 20
def example_function():
    y = 10
    print(y)
example_function()
print(y)
```

```
10
20
```

The global variable `y` is set to 20.
The function `example_function` is defined but not yet executed.
The function `example_function` is called.
    - Inside the function, a local variable `y` (which is separate from the global `y`) is set to 10.
    - The `print(y)` statement inside the function prints the local variable, so it outputs `10`.
After the function execution is complete, the next `print(y)` statement is outside of the function and refers to the global `y`, so it prints `20`.


--- 

#### Challenge 

1. Write a function that takes a string as input and returns the string in reverse order.
```python
def reverse_string(s):
    return s[::-1]
```

Note: recall `sequence[start:stop:step]`
- `start`: The index to start the slice.
	is omitted, so it defaults to the beginning of the sequence.
- `stop`: The index to stop the slice (exclusive).
	is omitted, so it defaults to the end of the sequence.
- `step`: The interval to use when fetching items.
	is `-1`, which means to retrieve items in reverse order.

1. Create a function that accepts a list of numbers and returns a new list containing only the even numbers.
```python
def filter_even(nums):
    return [num for num in nums if num % 2 == 0]
```
