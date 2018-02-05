```python
# Greedy and Nongreedy Matching
# Greedy means that in ambiguous situations they will match the longest string possible. 
# The non-greedy matches the shortest string possible has the closing curly bracket followed by a question mark.
# the question mark can have two meanings: (1)declaring a nongreedy match or (2)flagging an optional group.
greedyHaRegex = re.compile(r'(Ha){3,5}')
mo1 = greedyHaRegex.search('HaHaHaHaHa')
print mo1.group()

nongreedyHaRegex = re.compile(r'(Ha){3,5}?')
mo2 = nongreedyHaRegex.search('HaHaHaHaHa')
print mo2.group()

xmasRegex = re.compile(r'\d+\s\w+')
print xmasRegex.findall('12 drummers, 11 pipers, 10 lords, 9 ladies, 8 maids, 7swans, 6 geese, 5 rings, 4 birds, 3 hens, 2 doves, 1 partridge')

# Making Your Own Character Classes
vowelRegex = re.compile(r'[aeiouAEIOU47.]')
print vowelRegex.findall('Robocop eats baby food. BABY FOOD.1234567890.')

# negative character class
consonantRegex = re.compile(r'[^aeiouAEIOU ]')
print consonantRegex.findall('Robocop eats baby food. BABY FOOD.')

beginsWithHello = re.compile(r'^Hello')
print beginsWithHello.search('Hello world!').group()
print beginsWithHello.search('He said hello.') == None

# The Caret and Dollar Sign Characters
endsWithNumber = re.compile(r'\d$')
print endsWithNumber.search('Your number is 78942').endpos
print endsWithNumber.search('Your number is forty two.') == None

wholeStringIsNum = re.compile(r'^\d+$')
print wholeStringIsNum.search('1234567890').endpos
print '1234567890'[wholeStringIsNum.search('1234567890').endpos:]
print wholeStringIsNum.search('12345xyz67890') == None
print wholeStringIsNum.search('12 34567890') == None

#　The Wildcard Character
atRegex = re.compile(r'.at')
print atRegex.findall('The cat in the hat sat on the flat mat.')
```