

#### String Manipulation

1. Given the string `t = "Have a great day!"`, determine whether the string has only alphabetic characters.
   
   
2. Which of the following will remove the spaces in the string `u = "Remove the spaces!"`?
    - (a) `u.replace(" ", "")`
    - (b) `u.strip(" ")`
    - (c) `"".join(u.split())`
    - (d) `u.replace("", " ")`

---
#### Variable and Function Interactions

1. Consider the following code snippet:
```python
x = 4
def add_val(val=3):
    return x + val
y = add_val(5)
x==4 and y==9
```
Will the last line evaluate to True or False?

---
#### Boolean Logic

1. - If `a = True` and `b = False`, what will be the value of `a or not b and a`?

---

#### Global vs Local Variables

What will be the output of the following code:
```python
y = 5
def modify():
    global y
    y += 3
modify()
print(y)
```

---

#### String Reversal

Which of the following will correctly reverse the string `v = "hello"`?

- (a) `v[::-1]`
- (b) `"".join(list(v).reverse())`
- (c) `reversed(v)`
- (d) `"".join(reversed(v))`

---

#### Loop and Calculation

With the code below, determine the final value of `z`:
```python
z = 2
n = z
for i in range(n):
    z += i
```

---

#### String Replacement

Given the string `w = "Where is the place?"`, which of the following lines of Python code produces the output `"place is the Where?"`?

- (a) `w.split()[-2] + " " + " ".join(w.split()[:-2])`
- (b) `" ".join(reversed(w.split()))`
- (c) `w[-6:-1] + w[5:-6]`
- (d) `w[-5:] + w[:-5]`