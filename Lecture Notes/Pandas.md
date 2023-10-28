

we import Pandas as : `import pandas as pd`

Series: basically one column in an excel notebook

While a series has one column of data, a **data frame** has several. one for each variable. 


```Python
aser = Series([1, 5, -2, 16])
```

Outputs:
```
0    1 
1    5 
2    -2 
3    16 
dtype: int64
```

**Index can be string labels**
```Python
ser = Series([1, 5, -2, 16], index=['a','b','x','d'])
```


#### Accessing Series values

```python
aser[2]
```
Outputs: `-2`


```python
ser
```
Outputs:
```
a     1
b     5
x    -2
d    16
dtype: int64
```
and
```python
ser['x']
```
Outputs:`-2`

to change a value:
```python
ser['a'] = 10
```
Outputs: 
```
a    10 <---
b     5
x    -2
d    16
dtype: int64
```

Can use a list to filter a series:
```python
lst = ['x','a','b']
ser[lst]
```
Outputs:
```
x    -2
a    10
b     5
dtype: int64
```

##### NumPy like array operations work as before, index tags along

```python
import numpy as np

print(ser, '\n') #prints series

res = ser[ser > 0] #prints series where the value > 0
print(res, '\n')

res = ser * 2 # times each value by 2 then prints
print(res, '\n')

res = np.power(ser,2) #square each value
print(res, '\n')

ser = ser ** 2 # same thing as .power()
print(ser, '\n')
```

---

We can also create series by python dictionaries by **casing** the dict. 

```python
udict = {'Rutgers': 55000, 'Princeton': 15000, 'MIT': 20000, 'USC': 40000}
useries = Series(udict)
print(useries)
print(useries.index)
```
Outputs:
```
Rutgers      55000
Princeton    15000
MIT          20000
USC          40000
dtype: int64
Index(['Rutgers', 'Princeton', 'MIT', 'USC'], dtype='object')
```

