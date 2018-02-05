 python version: 3.6 - Date: January 2018
 
Launch a browser and link to target site
```python
import webbrowser
new = 5
url =r"https://google.com"
url =r"https://www.youtube.com/watch?v=jU3P7qz3ZrM"
print (webbrowser.open(url, new=new))
```

**Pandas** read csv
```python
import pandas as pd
csvFile = 'path/file_name.csv'
pd.read_csv(csvFile, encoding = "ISO-8859-1")
```

Show html element in Jupyter notebook
```python
from IPython.display import display, HTML
display(HTML('<img src="path/file_name.gif">'))
```