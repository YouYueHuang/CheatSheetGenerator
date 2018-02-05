sort tuple
```python
data=[(1, 2), (4, 1), (9, 10), (13, -3)]
# in-memory sort
sorted_by_second_element = sorted(data, key=lambda tup: tup[0])
# not in-memory sort
data.sort(key=lambda x: x[1])
```

filter
```python
number_list = [0.0,0.0,9.8,7.6,12.5,0.0]
not_zero = filter(lambda x: x != 0, number_list)
```

Comparisons to singletons like None should always be done with is or is not, never the equality operators.
```python

class Negator(object):
    def __eq__(self, other):
        return other
thing = Negator()
print (thing == None)    # None
print (thing is None)    # False

class Negator(object):
    def __eq__(self, other):
        return not other

thing = Negator()
print (thing == None)    # True
print (thing is None)    # False
```