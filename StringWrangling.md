# String split

  email= a@b.c
  org = email.split('@')[1] # org = 'b.c'
  
# Use of Regex

## find all element
  content = 'I have 10 fingers and 2 eyes'
  re.findall('[0-9]+',content)] # returns ['10', '2']
  