py2postgresql
```python
from datetime import date
import datetime
import psycopg2
import csv
import numpy as np

try:
    #conn = psycopg2.connect("dbname=mydb user=postgres")
    #cur = conn.cursor()
    
    # CREATE table
    # cur.execute("CREATE TABLE horseMarket (id serial PRIMARY KEY, num integer, data varchar);")
    
    # ALTER table
    # ALTER TABLE {table_name}
    # (1) ADD {column_name} {data_type}
    # (2) DROP COLUMN {column_name}
    
    #cur.execute("INSERT INTO city (num, data) VALUES (%s, %s)",(100, "abc'def"))
    
    # cur.execute("SELECT * FROM city;")
    # #b = cur.fetchone()
    # b = cur.fetchmany(3)
    # print b
    # c = cur.fetchall()
    # print c

    # cur.execute(
    #     """INSERT INTO some_table (an_int, a_date, another_date, a_string)
    #     VALUES (%(int)s, %(date)s, %(date)s, %(str)s);""",
    #     {'int': 10, 'str': "O'Reilly", 'date': datetime.date(2005, 11, 18)})

    cur.execute("INSERT INTO foo VALUES (%s)", ("bar",))
    conn.commit()

except psycopg2.ProgrammingError as err:
    print err
    print "haha"
    
finally:
    cur.close()
    conn.close()
```