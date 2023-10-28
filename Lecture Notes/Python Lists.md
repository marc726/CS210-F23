
##### String Things

`s1.endswith(s2)`: Does s1 end with s2?
`s1.startswith(s2)`: Does s1 start with s2?
`s1.find(s2)`: Find index of s2 in s1
`s.isalpha()`: Does s only use letters?
`s.isdigit()`: Does s only use numbers?
`s1.replace(s2,s3)` Replace occurrences of s2 with s3 in s1. 


#### Lists

List: `[]`
	- delimited with commas
	- do not need to be distinct (can have copies of an element)

use `list(string)` to split a string into a list of characters

use `len(list)` to find length of <u>list</u>

use `in` to determine if an element is in a <u>list</u>. can also use `not in` for opposite effect
	`3 in [1,2,3,4,5]`
	`true`

use `max(list)` to find max (number) element in the list. 
	works for all types but isn't useful

use `min(list)` for minimum element in the list.

can use for loops for list to iterate over every element in the list:

```Python
for i in my_list
	print(i)
```

Slicing a list:

let `my_list = [1,2,3,4,5]`

use `:` to slice a list. 
	left side of the `:` mean to start at that index. if left empty, start at beginning
	right side of the `:` means to end at that index. if left empty, end at last 

`mylist[1:3]` 
	start at `mylist[1]` to `mylist[3]` 

If negative number to the left, `my_list[-3:]` then start from third to last index
	`[3,4,5]` 

If negative number to the right, `my_list[:-2]` then starts from the beginning of the list and goes up to, but does not include, the item 2 positions before the end.

Can also be `list[::]` which represents `[start:slice:step]`
	use `[::1]` to reverse a list
	`[::2]` starts from beginning and gets every two elements (every other)

`.append(number)` to add to the end of the list

use `+` to concatenate lists (of same types).
`my_list + [7,8,9]`

`.extend([7,8,9])` does the same thing. 

Difference? `+` creates a new list, `.extend` grows the list in place

---

`.count(element)` counts occurrences of a given element
`.index(element)` returns first occurrence of element
`.insert(i, x)` insert element `x` at index `i`
`.remove(x)` remove the first occurrence at element `x`
`.pop(i)` remove last element of list at `i` or `.pop()` for last element of list

`sorted(list)` returns a sorted list. Does NOT affect original.
`.sort()` sorts current list in place

`.reverse()` reverses list or `sorted(list, reverse=True)`



Given a list, remove all instances of `'a'` 
```Python
ex_list = list('data analysis')
while 'a' in ex_list:
	ex_list.remove('a')
```



#### List Comprehensions

Python has the ability to build a list dynamically. 

Example: 

`ez_list = [i+1 for i in range (5)]`            (`i` starts at 0. thus the `i+1`)
Output: `[1,2,3,4,5]`

Can also use if statements during comprehension:
odd_list = `[i+1 for i in range (10) if i%2 == 0]`
Output: `[1,3,5,7,9]`

function to produce list of tuples in the form, $(x,x^2)$ where $1\le x\le 10$
```Python
def square_tuples(n=10):
    """ Returns a list of tuples of form (x,x^2) where 1<=x<=n. """
    return [(i,i*i) for i in range (1,n+1)]
```
``` 
Output: [(1, 1), (2, 4), (3, 9), (4, 16), (5, 25), (6, 36), (7, 49), (8, 64), (9, 81), (10, 100)]
```

given two lists of xs and ys produce all $(x,y)$ pairs where $x\ne y$

```Python
def unmatched_pairs(xs, ys):
	return [(x,y) for x in xs for y in ys if (x!=y)]
```

Notes: 
	Can do more than one for loop in the comprehension

Comprehension follow the structure: 
`(values) = [(expression) for (value) in (collection)]`

write a *recursive* function to <u>concatenate</u> two lists
```Python
def concat_lists(list1, list2):
    if not list1:
        return list2
    return [list1[0]] + concat_lists(list1[1:], list2)
```



```Python
[i+1 for i in range (3) for j in range (3)]
```
Imagine this as a nest for loop in java:
```Java
for (int i = 0; i < 3; i++){
	for (int j = 0; j < 3; j++){
		print(i+1);
	}
}
```
Output: `[1, 1, 1, 2, 2, 2, 3, 3, 3]`

