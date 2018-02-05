```python
# Case-Insensitive Matching
robocop = re.compile(r'robocop', re.IGNORECASE)
print robocop.search('Robocop is part man, part machine, all cop.').group()

#Substituting Strings with the sub() Method
# you can type \1, \2, \3, and so on, to mean “Enter the text of group 1, 2, 3, and so on, in the substitution.”
namesRegex = re.compile(r'Agent \w+')
print namesRegex.sub('CENSORED', 'Agent Alice gave the secret documents to Agent Bob.')

agentNamesRegex = re.compile(r'Agent (\w)(\w)\w*')
print agentNamesRegex.sub(r'\2****', 'Agent Alice told Agent Carol that Agent Eve knew Agent Bob was a double agent.')

#Managing Complex Regexes
#You can mitigate this by telling the re.compile() function to ignore whitespace and comments inside the regular expression string. 
#This “verbose mode” can be enabled by passing the variable re.VERBOSE as the second argument to re.compile()

#Note how the previous example uses the triple-quote syntax (
#''') to create a multiline string so that you can spread the regular expression definition over many lines, 
#making it much more legible.
phoneRegex = re.compile(r'((\d{3}|\(\d{3}\))?(\s|-|\.)?\d{3}(\s|-|\.)\d{4}(\s*(ext|x|ext.)\s*\d{2,5})?)')

phoneRegex = re.compile(r'''(
    (\d{3}|\(\d{3}\))?            # area code
    (\s|-|\.)?                    # separator
    \d{3}                         # first 3 digits
    (\s|-|\.)                     # separator
    \d{4}                         # last 4 digits
    (\s*(ext|x|ext.)\s*\d{2,5})?  # extension
    )''', re.VERBOSE)
print phoneRegex.search("(342).980-2129 x 349").group()

# Combining re.IGNORECASE, re.DOTALL, and re.VERBOSE
# use re.VERBOSE to write comments in your regular expression 
# use re.IGNORECASE to ignore capitalization
# combining the re.IGNORECASE, re.DOTALL, and re.VERBOSE variables using the pipe character (|), 
# which in this context is known as the bitwise or operator.
someRegexValue = re.compile('foo', re.IGNORECASE | re.DOTALL | re.VERBOSE)
```