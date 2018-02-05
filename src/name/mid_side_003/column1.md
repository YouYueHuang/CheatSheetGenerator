# String processing 

Stuff chars to the string 
```python
'string'.rjust(10, '*')
'string'.ljust(10, '-')
'string'.center(10, '=')
```

Search word with pattern
```python
'Hello world!'.startswith('Hello')
'Hello world!'.endswith('world!')
```

Remove chars
```python
'string'.strip('ampS')
'string'.lstrip('ampS')
'string'.rstrip('Smpa')
```

Check if the string consists of only letters and is not blank.
`'string'.isalpha()`


Check if the string consists only of letters and numbers and is not blank.
```python
'string'.isalnum() 
```

Check if the string consists only of numeric characters and is not blank.
```python
'string'.isdigit() 
```

Check if the string consists only of spaces, tabs, and new-lines and is not blank.
```python
'\t\n '.isspace() 
> True
```