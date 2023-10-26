
tuple, is similar to a list, however immutable.

Example: `(2,1,3)` denoted by `()` instead of `[]`


#### Strings

list functions can be used on strings like so: 

```Python
my_str = "Data Science"
list(my_str)
```

` ''.join(list)` Join a list of characters into string 

Example:

```Python
my_words = ["Data", "Science", "is", "cool"]
" / ".join(my_words)
```
Output: `'Data / Science / is / cool'`

`.split()` to break up words into a list. 

`"Data Science is cool".split()` outputs `['Data', 'Science', 'is', 'cool']`

