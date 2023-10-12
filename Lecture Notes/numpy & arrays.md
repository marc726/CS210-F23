

**NumPy**, short for Numerical Python, is a foundational package for numerical computations in Python. It provides support for large multidimensional arrays and matrices, along with a collection of mathematical functions to operate on these arrays.


NumPy's main object is the <u>homogeneous multidimensional array.</u> It is a table of elements (usually numbers), all of the same type, indexed by a tuple of non-negative integers.

Import: 
```python
import numpy #as np
```

**Attributes of arrays**:

- `array.ndim`: the number of axes (dimensions) of the array.
- `array.shape`: the dimensions of the array. For a matrix with n rows and m columns, shape will be `(n, m)`.
- `array.size`: the total number of elements in the array.
- `array.dtype`: the type of the elements in the array.
- `array.itemsize`: the size in bytes of each element of the array.

---
#### Creating Arrays

```python
import numpy as np
a = np.array([[1, 2, 3], [4, 5, 6]])
print(a.shape)  # (2, 3)
```

- From a regular Python list or tuple using `array()` function.
- Using functions like `zeros()`, `ones()`, `empty()`, `arange()`, `linspace()`, etc.

---
#### Array Functions

1. `numpy.zeros(shape, dtype=float, order='C')` 
- Returns a new array of given shape and type, filled with zeros.

**Parameters**:
	- `shape`: Tuple indicating the shape of the desired array.
	- `dtype`: Desired data type of array. Default is `float64`.
	- `order`: Whether to store multi-dimensional data in row-major (C-style) or column-major (Fortran-style) order in memory.

**Example**: 
```python
np.zeros((2, 3))
```
Outputs: 
```
[[0. 0. 0.]
 [0. 0. 0.]]
```



2. `numpy.ones(shape, dtype=None, order='C')`
- Returns a new array of given shape and type, filled with ones.
- Parameters and usage are similar to `zeros()`.
Example:
```python
np.ones((2, 2))
```



3. `numpy.empty(shape, dtype=float, order='C')`
- Returns a new array of given shape and type, without initializing entries (i.e., filled with random values unless you fill it up). It's slightly faster than `zeros()` or `ones()` if you're planning to populate the array later.
- Parameters are similar to `zeros()`.
**Example**:
```python
np.empty((3, 2))
```


4. `numpy.arange([start, ]stop, [step, ]dtype=None)`

- Returns evenly spaced values within a given interval. Similar to Python's `range()` but returns an array.
- **Parameters**:
	- `start`: Start of the interval.
	- `stop`: End of the interval.
	- `step`: Spacing between values. Default is 1.
	- `dtype`: Desired data type of the output array.
**Example**:
```python
np.arange(10)
```
Outputs:
`array([0, 1, 2, 3, 4, 5, 6, 7, 8, 9])`



5. **`numpy.linspace(start, stop, num=50, endpoint=True, retstep=False, dtype=None, axis=0)`**

- Returns evenly spaced numbers over a specified interval.
- **Parameters**:
	- `start`: Start of the interval.
	- `stop`: End of the interval.
	- `num`: Number of evenly spaced samples to be generated. Default is 50.
	- `endpoint`: If True, `stop` is the last value in the range.
	- `retstep`: If True, return the step size between values.
**Example:**
```python
np.linspace(0, 1, 5)
```
Output: 
```
[0.   0.25 0.5  0.75 1.  ]
```



6. `numpy.eye(N, M=None, k=0, dtype=<class 'float'>, order='C')`

- Returns a 2-D array with ones on the diagonal and zeros elsewhere.
- **Parameters**:
    - `N`: Number of rows.
    - `M`: Number of columns. If `None`, defaults to `N`.
    - `k`: Index of the diagonal. Default is the main diagonal.
**Example**:
```python
np.eye(3)
```

See #advancednpeye

7. `numpy.full(shape, fill_value, dtype=None, order='C')`
- Returns a new array of given shape and type, filled with `fill_value`.
- **Parameters**:
    - `shape`: Tuple indicating the shape of the desired array.
    - `fill_value`: Scalar value to fill the new array.
**Example**:
```python
np.full((2, 3), 7)
```

---
#### Array Operations

Arithmetic operators on arrays apply #elementwise. A new array is created and filled with the result.
```python
a = np.array([10, 20, 30, 40])
b = np.array([1, 2, 3, 4])
c = a - b  # array([ 9, 18, 27, 36])
```

#elementwise : 

Given two arrays:

$$\text{A} = \begin{bmatrix}
a & b \\
c & d \\
\end{bmatrix}$$
and

$$\text{B} = \begin{bmatrix}
e & f \\
g & h \\
\end{bmatrix}$$

The elementwise sum of these two arrays, $\text{A} + \text{B}$, is: 

$$\begin{bmatrix}
a+e & b+f \\
c+g & d+h \\
\end{bmatrix}$$

---
#### Universal Functions (`ufunc`)

NumPy provides familiar mathematical functions such as sin, cos, and exp. These are #elementwise operations.

```python
B = np.arange(3)
y = np.exp(B)  # array([ 1.        ,  2.71828183,  7.3890561 ])
```

---
#### Indexing, Slicing and Iterating

One-dimensional arrays can be indexed, sliced, and iterated over, much like lists and other Python sequences.

```python
a = np.arange(10)**2
print(a[2])  # 4
print(a[2:5])  # array([ 4,  9, 16])
```

---
#### **Shape Manipulation**

##### Changing the shape of an array 

An array has a shape given by the number of elements along each axis, which can be modified using various commands like `ravel()`, `reshape()`, `T`, etc.

**`reshape()`**:
- This method allows the array to be restructured into a different shape while preserving its data.
- The new shape must have the same total number of elements as the original array.
**Example**:
```python
arr = np.arange(12)
arr_reshaped = arr.reshape(3, 4)
```
This takes a 1D array with 12 elements and reshapes it into a 3x4 matrix.


**`ravel()`**:
- This method returns a flattened 1D array. Essentially, it "flattens" a multidimensional array.
- The returned array will have the same type and order of elements.
**Example**:
```python
arr = np.array([[1, 2, 3], [4, 5, 6]])
arr_flattened = arr.ravel()
```
This will produce a 1D array: `[1, 2, 3, 4, 5, 6]`.


**`T` (Transpose Attribute)**:
- This attribute provides the transpose of an array. It's especially useful for matrices.
- Transposing a 2D array (matrix) swaps rows with columns.
**Example**:
```python
arr = np.array([[1, 2], [3, 4], [5, 6]])
arr_transposed = arr.T
```


**`resize()`**:
- This method returns a new array with the specified shape.
- Unlike `reshape()`, if the new shape requires more elements than the original, the array is "filled in" using repeated copies of the original array.
**Example**:
```python
arr = np.array([1, 2, 3])
arr_resized = arr.resize(5)
```
This will produce an array: `[1, 2, 3, 1, 2]`.


**`squeeze()`**:
- This method removes single-dimensional entries from the shape of an array.
**Example**:
```python
arr = np.array([[[1], [2], [3]]])
arr_squeezed = arr.squeeze()
```
This will produce an array: `[1, 2, 3]`.


**`flatten()`**:
- This method is similar to `ravel()`, but it returns a new copy of the array in memory (while `ravel()` returns a view unless forced otherwise).


**Note:** When reshaping or otherwise modifying the shape of arrays, it's important to ensure that the total number of elements is consistent (unless using methods like `resize()` which handle this explicitly). Otherwise, you'll get an error due to incompatible shapes.

##### Stacking together different arrays

Several arrays can be stacked together along different axes, e.g., `vstack`, `hstack`.

---
#### Linear Algebra

Linear algebra operations like dot products, vector norms, determinants, eigenvalues can be handled effortlessly with NumPy.

```python
A = np.array([[1, 1], [0, 1]])
B = np.array([[2, 0], [3, 4]])
print(np.dot(A, B))  # matrix product
```

---


Note: #advancednpeye


Observe: 
```python
np.eye(5, dtype='int64')*4+np.ones((5,5), dtype='int64')
```

Lets break this down: 

Output:
```
array([[5, 1, 1, 1, 1], 
	   [1, 5, 1, 1, 1], 
	   [1, 1, 5, 1, 1], 
	   [1, 1, 1, 5, 1], 
	   [1, 1, 1, 1, 5]])
```


##### Left Side

**`np.eye(5, dtype='int64')`**:
- This creates a 5x5 identity matrix with integer data type `int64`. An identity matrix is a square matrix in which all the elements of the main diagonal are ones and all other elements are zeros.
Result: 
```
[[1 0 0 0 0]
 [0 1 0 0 0]
 [0 0 1 0 0]
 [0 0 0 1 0]
 [0 0 0 0 1]]
```


**`*4`**:
- This multiplies every element in the matrix by 4.
Result:
```
[[4 0 0 0 0]
 [0 4 0 0 0]
 [0 0 4 0 0]
 [0 0 0 4 0]
 [0 0 0 0 4]]
```

##### Right Side

**`np.ones((5,5), dtype='int64')`**:
- This creates a 5x5 matrix filled with ones of data type `int64`.
Result:
```
[[1 1 1 1 1]
 [1 1 1 1 1]
 [1 1 1 1 1]
 [1 1 1 1 1]
 [1 1 1 1 1]]
```

**`+`**:
- This adds the two matrices element-wise. Thus the end result:
```
[[5 1 1 1 1]
 [1 5 1 1 1]
 [1 1 5 1 1]
 [1 1 1 5 1]
 [1 1 1 1 5]]
```

