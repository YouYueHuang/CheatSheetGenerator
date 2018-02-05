# time

* make the thread sleep
```python
import time 
time.sleep(5)
```

* time format data parsing and comparison

```python
from datetime import date
import datetime
def time_comparator(early_year,early_month,early_date,early_hour,early_min
                    ,now_year,now_month,now_date,now_hour,now_min):
    previous_time = datetime.datetime(early_year,early_month,early_date,early_hour,early_min)
    present_time = datetime.datetime(now_year,now_month,now_date,now_hour,now_min)
    return previous_time == present_time
    
mytime = i[12].split("/")
yearandtime = mytime[2].split(" ")
Time = yearandtime[1].split(":")
if early_year < 100:
    early_year = 2000 + early_year

year = int(result[0],10)
month = int(result[1],10)
date = int(result[2],10)
hour = int(result[3],10)
minute = int(result[4],10)

Daayttt = {"0":"Sunday","6":"Saturday","1":"Monday","2":"Tuesday","3":"Wednesday","4":"Thursday","5":"Friday"}
d0 = date(2008, 12, 28)
d1 = date(2008, 12, 29)
delta = (d1 - d0)
print type(delta)
print delta//7.0

time1 = datetime.datetime(2007, 12, 6, 16, 29, 43)
time2 = datetime.datetime(2007, 12, 6, 15, 29, 43)
a = 0
if time1 > time2:
    a= time1-time2
else:
    a= time2-time1
print a.seconds


year,month,date,hour,minu,second = int(year),int(month,10),int(date,10),int(hour,10),int(minu,10),int(round(float(second)))
_time = "{} {} {} {} {} {}".format(year,month,date,hour,minu,second)
```