

**Command-line parameters**

```python
import sys
print(sys.argv)
print(sys.argv[1])
```

---

#### Functions

Example:
```python
def g():
    x = 10
def f():
    x = 5
g()
print(x)
```



Write a program to output this pattern:
```
* * * * *
* * * *
* * *
* *
*
```
Ans: 
```python
def print_pattern(n):
    for i in range(n, 0, -1): #start n, until 0, increment -1 each loop
        print('* ' * i)

n = 5
print_pattern(n)
```



Functions can return multiple values:
```python
def h(x):
    return 2*x, x*x
y, z = h(3)
```

This defines a function named `h` that takes a single argument `x`. The function returns two values: `2*x` and `x*x`. When multiple values are returned from a function in this manner, they are packed into a tuple.

`y, z = h(3)`

Here, the function `h` is called with the argument `3`.

- Inside the function, `2*x` evaluates to `2*3` which is `6`.
- `x*x` evaluates to `3*3` which is `9`.

So, the function returns the tuple `(6, 9)`.

**Multiple Assignment**: When the returned tuple `(6, 9)` is assigned to `y, z`, it's essentially a form of tuple unpacking. The first value in the tuple (which is `6`) gets assigned to `y`, and the second value in the tuple (which is `9`) gets assigned to `z`.

As a result:

- `y` will have the value `6`.
- `z` will have the value `9`.

In summary, the function `h` returns two values packed into a tuple. When calling the function and assigning its return values to `y` and `z`, the tuple is unpacked, and its values are assigned to the respective variables.


**Questions**

What does this print?
```python
def f():
    x = 20
f()
print(x)
```

Ans: Error. 

1. Inside the function `f()`, a local variable `x` is defined and assigned the value `20`.
2. After the function `f()` is called, the local variable `x` goes out of scope, which means it is no longer accessible outside of the function.
3. When you try to `print(x)` outside of the function, Python will raise a `NameError` because `x` is not defined in the global scope.

What does this print?
```python
x = 10
def f():
    x = 20
f()
print(x)
```

The global variable `x` retains its original value of `10` because the function `f()` only modifies a local variable with the same name, not the global one.

```python
x = 10
def f():
    global x
    x = 20
f()
print(x)
```

The global variable `x` is modified to `20` by the function `f()` because of the use of the `global` keyword.

**Default arguments**:
```Python
def f(n = 5):
    return 2*n
x = f(4)
y = f()
```
When `f()` is called without any arguments, the default value of `n` (which is `5`) is used. The function returns `2*5` which is `10`. Thus, `y` will have the value `10`.

**Keyword arguments**:
```python
def f(x, y):
    return x + y
x = f(4)
y = f()
```
The call `f()` will also raise an error because the function expects two arguments, but none are provided.

**Lambda functions**:
```python
def double1(x):
    return 2*x
double2 = lambda x: 2*x
```

- The function `double1` is a regular function that takes an argument `x` and returns its double.

- `double2` is a lambda function that achieves the same result. Lambda functions are a way to define small, anonymous functions in a concise manner. In this case, `double2` is equivalent to `double1` in functionality. Given an input `x`, both `double1` and `double2` will return `2*x`.


---
#### Strings

- String functions:
    - `s1.endswith(s2)` Does s1 end with s2?
    - `s1.startswith(s2)` Does s1 start with s2?
    - `s1.find(s2)` Find index of s2 in s1
    - `s.isalpha()` Does s use only letters?
    - `s.isdigit()` Does s use only numbers?
    - `s1.replace(s2, s3)` Replace occurrences of s2 with s3 in s1
    - `s.strip()` Remove whitespace at the beginning/end of s

What does this program print?
```python
s1 = "hello"
s2 = "hello"
print(s1 == s2)
```
Output = `True`



**Slicing:**

To get individual characters or substrings:
```python
s = "hello"
c = s[0]
s2 = s[1:]
```

In Python, the colon `:` inside square brackets when accessing elements of a sequence (like a string, list, or tuple) is used for slicing. Slicing allows you to extract a portion of the sequence.

The syntax for slicing is:
`sequence[start:stop:step]`
In the expression `s2 = s[1:]`:

- `start` is `1`, so the slice begins from the second element of `s` (since indexing starts from 0).
- `stop` is omitted, so the slice goes until the end of `s`.
- `step` is omitted, so it defaults to 1, meaning every element in the specified range is included.

For example, if `s = "hello"`, then `s[1:]` would return `"ello"`.

---
#### Exceptions:

```python
try:
    dangerousCode()
except:
    handleError()
```

#### **Random numbers**

```python
import random
n = random.randint(3, 5)
x = random.random()
```

#### Recursion 

```python
def f(n):
    if n == 0:
        print(n)
    else:
        print(n)
        f(n-1)
```
