
denoted by `{}`

A *dictionary*, or `dict`, maps *keys* to *values*. 

Note that keys are unique. They can be any *hashable* type, including strings.  

```Python
state_abbreviations = {"NJ": "New Jersey",
                       "CT": "Connecticut",
                       "NY": "New York",
                       "PA": "Pennsylvania"}
```
```Python
for key, val in state_abbreviations.items():

    print(f"The abbreviation for '{val}' is '{key}'.")
```

to iterate thru dict you must use `for i in test_dict.items()`; it is essential to have `.items()`


