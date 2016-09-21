# Pyhton Basic References

## Control Loop
```python
for letter in 'Python':     # First Example
   if letter == 'h':
      break
   print(letter) #Pyt
for letter in 'Python':     # First Example
      if letter == 'h':
         continue
      print(letter) #Pyton
for letter in 'Python':     # First Example
    if letter == 'h':
       print('z')
    else:   
       print(letter) #Pytzon

```


## Data Types

    Integer     -256, 15
    Float       -253.23, 1.253e-10
    String      "­Hello", 'Goodbye', """­Multiline­"""
    Boolean     True, False
    List        [ value, ... ]
    Tuple       ( value, ... )
    Dictionary  { key: value, ... }
    Set         { value, value, ... }

Append to list:
```python
my_list=[1,2]
my_list.append(3) # my_list: [1,2,3]
```

Add entry to dict:
```python
my_dict = {'name':'Lola'}
my_dict['age'] = 14 # my_dict: {'age': 14, 'name': 'Lola'}
```

## List file of a directory
```python
import os
os.listdir("/path/to/folder/")
```

## Terminate script execution
    import sys
    sys.exit("Error message")

# References
*   [https://www.cheatography.com/sschaub/cheat-sheets/essential-python/](Cheatography)
