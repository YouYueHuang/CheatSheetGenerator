Read file
```python
with open("path/file_name", 'r')
	for index, record in enumerate(f, 0):
		# process the data
```

Read and write csv
```python
import csv
def ReadCSVFile(read_file_name):
    CrimeFile = open(read_file_name+".csv", 'r')
    CrimeList = list(csv.reader(CrimeFile,delimiter=',',quotechar='"'))
    CrimeFile.close()
    return CrimeList

def WriteCSVFile():
    file11 = open("C:\\Users\\yhuang\\Desktop\\Reduced_coldspot.csv","a")
    w = csv.writer(file11, delimiter=',', lineterminator='\n')
    w.writerows([data])
    file11.close()
```

read and write JSON
```python
import json

# json to text
with open('path/file_name.json', 'w') as f:
     json.dump(pythonValue, f)

# text to json
with open('path/file_name.json', 'r') as f:
     data = json.load(f)
     # data processing
```