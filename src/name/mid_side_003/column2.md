# Regular expression

```python

#==============================================================================
# \d
# Any numeric digit from 0 to 9.
# 
# \D
# Any character that is not a numeric digit from 0 to 9.
# 
# \w
# Any letter, numeric digit, or the underscore character. (Think of this as matching “word” characters.)
# 
# \W
# Any character that is not a letter, numeric digit, or the underscore character.
# 
# \s
# Any space, tab, or newline character. (Think of this as matching “space” characters.)
# 
# \S
# Any character that is not a space, tab, or newline.
#==============================================================================
import re

phoneNumRegex = re.compile(r'\d\d\d-\d\d\d-\d\d\d\d')
mo = phoneNumRegex.search('My number is 415-555-4242. And my friends is 999-444-2422')
print('Phone number found: ' + mo.group())
fa =phoneNumRegex.findall('Cell: 415-555-9999 Work: 212-555-0000') # has no groups
print fa

phoneNumRegex = re.compile(r'(\d\d\d)-(\d\d\d)-(\d\d\d\d)')
mo = phoneNumRegex.search('My number is 415-555-4242.')
print mo.group(1)
print mo.group(2)
print mo.group(0)
print mo.groups()
phoneNumRegex = re.compile(r'(\d\d\d)-(\d\d\d)-(\d\d\d\d)') # has groups
print phoneNumRegex.findall('Cell: 415-555-9999 Work: 212-555-0000')


phoneNumRegex = re.compile(r'(\(\d\d\d\)) (\d\d\d-\d\d\d\d)')
mo = phoneNumRegex.search('My phone number is (415) 555-4242.')
print mo.groups()

# Matching Multiple Groups with the Pipe
heroRegex = re.compile (r'Batman|Tina Fey')
mo1 = heroRegex.search('Batman and Tina Fey.',7,200)
print mo1.group()
mo2 = heroRegex.search('Tina Fey and Batman.')
print mo2.group()
```