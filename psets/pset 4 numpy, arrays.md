

#### Array Creation 

1. Given a `list` of integers, convert it into a <u>numpy</u> array.

Input:
```python
mylist = [5, 12, 6, 9, 11]
```
Output: 
```python
array([ 5, 12,  6,  9, 11])
```


2. Will the following compile? Why or why not?
```python
arr = np.array([[1, 2, 3], [4, 5, 6, 7]])
```


3. Write a function that creates a numpy array <u>filled with zeros</u> of the specified shape.

Input:
```python
shape = (3, 4)
```
Output: 
```python
array([[0., 0., 0., 0.],
       [0., 0., 0., 0.],
       [0., 0., 0., 0.]])
```

4. Write a function that creates a numpy array <u>filled with ones</u> of the specified shape.

Input:
```python
shape = (2, 3)
```
Output: 
```python
array([[1., 1., 1.],
       [1., 1., 1.]])
```


5. Write a function that creates an identity matrix of the specified size using numpy's `np.eye()` function.

Input:
```python
n = 3
```
Output: 
```python
array([[1., 0., 0.],
       [0., 1., 0.],
       [0., 0., 1.]])
```


6. Write a function that creates a numpy array of evenly spaced values using the `np.arange()` function.
Input:
```python
start = 5
stop = 20
step = 3
```
Output:
```python
array([5, 8, 11, 14, 17])
```



---

#### Array Operations

1. Given a numpy array, perform the specified arithmetic operation on all the elements of the array.

Input:
```python
arr = np.array([3, 7, 10, 4, 8])
```
Output: 
```python
array([ 6, 14, 20,  8, 16])
```



2. What will be the output of the code below?
```python
import numpy as np

arr = np.array([True, 4, 5, False])
print(arr)
```

A) `[True, 4, 5, False]`
B) `[1, 4, 5, 0]`
C) `[True, True, True, False]`
D) `Type Error`

---

#### Array Attributes

1. Write a function that determines the **number of dimensions** of a given numpy array.

**Input**: 
```python
arr = np.array([[1, 2, 3], [4, 5, 6]])
```
Output: 
```
2
```



2. Write a function that returns the **shape** of a given numpy array.

**Input**: 
```python
arr = np.array([[1, 2, 3], [4, 5, 6]])
```
Output: 
```
(2, 3)
```



