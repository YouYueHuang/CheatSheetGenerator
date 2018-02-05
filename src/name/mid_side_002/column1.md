# os, sys

Import module
```python
import sys
import os
```

Update module search path (temporary)
```python
sys.path.append('module path')
```

Remove the last path
```python
sys.path.pop(-1)
```

Set path
```python
os.path.join('usr', 'bin', 'spam')
```

Get and change current working directory
```python
os.getcwd()
os.chdir('target dir')
```

Get a string of a relative path from the rsc path to dst path.
```python
os.path.relpath(dst, src) 
```

Get dir and base name
```python
os.path.basename(path)
os.path.dirname(path)
```

Finding File Sizes and Folder Contents
```python
os.path.getsize('file path')
os.listdir('dir path')
```

Get system info
```python
os.name
sys.platform
```