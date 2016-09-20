# Python: String and Regular Expressions

## String manipulation
### String split
```python
email= a@b.c
org = email.split('@')[1] # org = 'b.c'
```

## Regular Expressions
```python
import re
re.search('me', "It's all about me!")
```

### find all element
```python
content = 'I have 10 fingers and 2 eyes'
re.findall('[0-9]+',content)] # returns ['10', '2']
```

## References
*   Python 2 : [https://docs.python.org/2/library/string.html](Python 2 Doc)
*   Python 3: [https://docs.python.org/3.5/library/string.html](Python 3 Doc)
