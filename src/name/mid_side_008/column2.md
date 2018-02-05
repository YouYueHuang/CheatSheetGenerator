py2spark
```python
from pyspark.sql import SparkSession
from pyspark.sql import Row
from pyspark import SparkConf, SparkContext
import time

#Rank of disciplines based on number of visits (regardless the country or the portal)

start_time = time.time()

conf = SparkConf().setMaster("local[*]")
sc = SparkContext(conf = conf)

def loadDisciplines():
    disciplineNames = {}
    with open("/Users/espoelst/Documents/JADS/DataEngineering/StudyPortals/Spark/Discipline_synonym.csv") as f:
        for line in f:
            try:
                fields = line.split(',')
                disciplineNames[float(fields[1].strip('u'))] = fields[0]
            except:
                pass
    return disciplineNames
   
def parseLine(line):
    fields = line.split(',')
    try:
        discipline = int(fields[2].strip('"'))
        country = int(fields[2].strip('"'))
        portals = int(fields[1].strip('"'))
        visited_date = fields[0]
    except:
        pass
    return discipline,country,portals,visited_date  


# The windows thingy Create a SparkSession (the config bit is only for Windows!)

spark = SparkSession \
    .builder \
    .appName("Python Spark SQL basic example") \
    .config("spark.some.config.option", "some-value") \
    .getOrCreate()

nameDict = loadDisciplines()

# Get the raw data
lines = sc.textFile("file:///Users/espoelst/Documents/JADS/DataEngineering/StudyPortals/Spark/date_url_encoded.csv")
# Convert it to a RDD of Row objects
#movies = lines.map(lambda x: Row(Discipline = parseLine(x)))

movies = lines.map(lambda x: Row(discipline = parseLine(x)[0]))
# Convert that to a DataFrame
movieDataset = spark.createDataFrame(movies)
#movieDataset = movieDataset.filter(movieDataset['country'] == 'switzerland')
#movieDataset = movieDataset.filter(movieDataset['portals'] == 'www.phdportal.com')
#movieDataset = movieDataset.filter(movieDataset['visitedDate'] == '2016-12-10')
 
try:
    topDisciplines = movieDataset.groupBy("Discipline").count().orderBy("count", ascending=False).cache()
    topDisciplines.show(100)
except:
    movieDataset.show(10)

top10 = topDisciplines.take(10)

#topDisciplines = hiveContext.sql('""'SELECT discipline,COUNT(discipline) FROM movieDataset WHERE country=switzerland and portals=www.phdportal.com AND visited_date=2016-12-10 GROUP BY discipline'""')
#topDisciplines.show()
#SELECT discipline,COUNT(discipline) FROM date_url_encoded WHERE country=39 and portals=2 AND visited_date=381 GROUP BY discipline

#Print the results
print("\n")
for result in top10:
    #Each row has movieID, count as above.
    try:
        print("%s: %s" % (nameDict[result[0]], result[1]))
    except:
        pass

elapsed_time = time.time() - start_time
print(elapsed_time)
# Stop the session
#spark.stop()

#topDisciplines.to_csv("file:///Users/espoelst/Documents/JADS/DataEngineering/StudyPortals/Spark/Output.csv")
```