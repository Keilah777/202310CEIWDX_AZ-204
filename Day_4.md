# Day 4

- https://www.w3schools.com/git/git_staging_environment.asp?remote=github 
- RDP Lab Environment: confirmed
- SQL Experience
- Database Viewer/Browser/Explorer: DBeaver, SQL Bench, SQL Server Management Studio, Azure Data Studio, Oracle SQL Developer 
- If anyone still stuck on their machine to run any of my code then let me know here.

- Django Continuation of Post App:
    - Add Tests in this App (with Database)

-  Django Blog App:

### Interacting with sqllite DB
Goto the folder where the database is and then

sqlite3  db.sqlite3
Then:
.tables
or do:
.schema

Instead of invoking sqlite3 directly you could do

python manage.py dbshell 

and then type the sqlite commands.

python3 manage.py dbshell
.tables
Find the name of the table you are looking for, then run the following commands:

.header on
.mode column
pragma table_info('table you are looking for');
Do not forget the semicolon in the last instruction.

If you are working with a legacy database you can generate Django models for that using the
 python manage.py inspectdb

https://docs.djangoproject.com/en/3.0/ref/django-admin/#django-admin-inspectdb for additional info.

Get a GUI database client. Life is much easier when you have one.

--- 