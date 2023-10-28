
import statement: 

`import numpy as np`

Create a `numpy` array from a list. 

```Python
mylist = [3, 7, 10, 4, 2, 8]
arr = np.array(mylist)
```

Use `*` to multiply all the elements by some factor. 
Similarly, you can use `+`, `-`, `/`, `//`, and `%`. 

```Python
2 * arr
```


NOTE: With Python lists, the `*` will simply repeat the same elements. 
```Python
2 * mylist
```
Outputs: `[3, 7, 10, 4, 2, 8, 3, 7, 10, 4, 2, 8]`


```Python
arr % 2
```
Output: `array([1, 1, 0, 0, 0, 0])`

`numpy` will convert every element to the same type without throwing error. They need to be single type:
```Python
np.array([1, 2, 3, False])
```
Outputs: `array([1, 2, 3, 0])`

```Python
np.array([False, 1, 2, 3, "5"])
```
Outputs: `array(['False', '1', '2', '3', '5'], dtype='<U21')` (string)


`np.arrays` must be same length:
```Python
arr = np.array([[1, 2, 3], [4, 5, 6, 7]])
```
Will error out


`np.zeros(5)` creates an array of zeros of column length 5: `array([0., 0., 0., 0., 0.])`

`np.ones(3)` same thing but with ones

`np.eye(5, dtype='int64')` diagonal of length 5 of 1s going diagonal. rest is 0s. Need to specify type for second arg. 
```
array([[1, 0, 0, 0, 0], 
	   [0, 1, 0, 0, 0], 
	   [0, 0, 1, 0, 0], 
	   [0, 0, 0, 1, 0], 
	   [0, 0, 0, 0, 1]])
```

Also accepts tuples of lengths

`np.zeros((2, 3, 4))` (2 arrays, of 3 rows, 4 columns)

Outputs: 
```
array([[[0., 0., 0., 0.], 
	    [0., 0., 0., 0.], 
	    [0., 0., 0., 0.]], 
	    
	    [[0., 0., 0., 0.], 
	    [0., 0., 0., 0.], 
	    [0., 0., 0., 0.]]])
```