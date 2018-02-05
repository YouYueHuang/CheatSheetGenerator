 Heroku - Date: January 2018
 
# Deploy python web framework on Heroku

Pipenv installed 
```python
pip install pipenv
```

Set up Postgres on Windows
[postgreSQL](https://www.enterprisedb.com/downloads/postgres-postgresql-downloads#windows)

Remember to update your PATH environment variable to add the `bin` directory of your Postgres installation. The directory will be similar to this: `C:\Program Files\PostgreSQL\<VERSION>\bin`. If you forget to update your PATH, commands like `heroku pg:psql` won’t work.

postgresql-10.1

db port is 5433

apache server port is 8081

Display the contents of an environment variable in Windows
`echo %PATH%`

Write evironmental variables to a text file.
`set > filename.txt`

check postgresql version
```sh
psql --version
```
