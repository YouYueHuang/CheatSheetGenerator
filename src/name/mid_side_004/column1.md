```python
batRegex = re.compile(r'Bat(man|mobile|copter|bat)')
mo = batRegex.search('Batmobile lost a wheel')
print mo.group()
print mo.group(1)

# Optional Matching with the Question Mark
# Matching Zero or More with the Star
# Matching One or More with the Plus
batRegex = re.compile(r'Bat(wo)*man')  # ? + * 
mo1 = batRegex.search('The Adventures of Batman')
print mo1.group()

mo2 = batRegex.search('The Adventures of Batwowoman')
if mo2 is None:
    print mo2
else:
    print mo2.group()
    
#Matching Specific Repetitions with Curly Brackets
haRegex = re.compile(r'(Ha){3}')
mo1 = haRegex.search('HaHaHa')
print mo1.group()
mo2 = haRegex.search('Ha')
print mo2 == None
```