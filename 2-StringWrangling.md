# String split

    email= a@b.c
    org = email.split('@')[1] # org = 'b.c'
  
# Use of Regex

## find all element

    content = 'I have 10 fingers and 2 eyes'
    re.findall('[0-9]+',content)] # returns ['10', '2']
  
# References 
* Python 2 : https://docs.python.org/2/library/string.html
* Python 3: https://docs.python.org/3.5/library/string.html