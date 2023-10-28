
```python
f = open(path) #returns a file object f. Defaults to read ('r')
f.read() #reads and returns content of the file as a single string
f.readlines() #reads and returns a list of lines from the file
f.close() #this method closes file
```


we can also use `with`


Before `with`
```Python
f = open("example.txt", "r")
content = f.read()
f.close()
```

Using `with`
```Python
with open("example.txt", "r") as f:
    content = f.read()
```

`with` only reading
```Python
with open("example.txt", "r") as f:
    content = f.read()
```

`with` using `'w'` overwrites currently opened file.
```Python
with open("example.txt", "w") as f:
    f.write("Hello, World!")
```

Note:
	if file is not found, one is made. 

read from one file and write to another:
```Python
# Open 'source.txt' in read mode and 'destination.txt' in write mode
with open("source.txt", "r") as source, open("destination.txt", "w") as destination:
    # Read content from source file
    content = source.read()
    
    # Write the content to the destination file
    destination.write(content)
```

