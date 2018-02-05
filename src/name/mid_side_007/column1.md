# SQL connection

Py2MySQL
```python

# Store URL
# MySQL 5.0.3 use TEXT or VARCHAR(2083)

import MySQLdb
try:
    # Open database connection
    db = MySQLdb.connect(host = "localhost"
                        , user = "root"
                        , passwd = "root"
                        , db = "studyportals" 
                        , charset = 'utf8')
    # prepare a cursor object using cursor() method
    cursor = db.cursor()
    
    # execute SQL query using execute() method.
    cursor.execute("SELECT VERSION()")
    
    for song in songs:
        cur.execute("INSERT INTO song (title) VALUES (%s)", song)
        print "Auto Increment ID: %s" % cur.lastrowid
    
    # Fetch a single row using fetchone() method.
    data = cursor.fetchone()    
    print "Database version : %s " % data

except MySQLdb.Error as e:
    print "Error %d: %s" % (e.args[0], e.args[1])
finally:
    # disconnect from server
    db.close()    
```