```python
# Matching Everything with Dot-Star
nameRegex = re.compile(r'First Name: (.*) Last Name: (.*)')
mo = nameRegex.search('First Name: Al Last Name: Sweigart')
print mo.group(1)
print mo.group(2)

nongreedyRegex = re.compile(r'<.*?>')
mo = nongreedyRegex.search('<To serve man> for dinner.>')
print mo.group()

greedyRegex = re.compile(r'<.*>')
mo = greedyRegex.search('<To serve man> for dinner.>')
print mo.group()

# Matching Newlines with the Dot Character. The dot-star will match everything except a newline.
noNewlineRegex = re.compile('.*')
print noNewlineRegex.search('Serve the public trust.\nProtect the innocent.\nUphold the law.').group()

newlineRegex = re.compile('.*', re.DOTALL)
print newlineRegex.search('Serve the public trust.\nProtect the innocent.\nUphold the law.').group()

#==============================================================================
# {n,m}? or *? or +? performs a nongreedy match of the preceding group.
# 
# ^spam means the string must begin with spam.
# 
# spam$ means the string must end with spam.
# 
# The . matches any character, except newline characters.
# 
# \d, \w, and \s match a digit, word, or space character, respectively.
# 
# \D, \W, and \S match anything except a digit, word, or space character, respectively.
# 
# [abc] matches any character between the brackets (such as a, b, or c).
# 
# [^abc] matches any character that isn’t between the brackets.
#==============================================================================
```