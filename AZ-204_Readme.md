- Git Installed? V
- VS Code Installed?
- Python Version V
- pip Version V

- Python Virtual Environment Check. What was used in PCEP Course? (conda, virutalenv, pyenv, pipenv, venv) 
https://docs.python.org/3/tutorial/venv.html
pip3 install pipenv
pipenv install django==4.1
pipenv shell
exit

===
# Markdown:
- Tutorial: https://www.markdowntutorial.com/
- Markdown Cheatsheet: https://www.markdownguide.org/cheat-sheet/
- Github Markdown Reference: https://docs.github.com/en/get-started/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax

===
# Django Tutorials
https://docs.djangoproject.com/en/4.1/intro/tutorial01/

===
# Install PIP:
mac: python -m ensurepip --upgrade
win: py -m ensurepip --upgrade

# Install Django
pip install django
---
Check Django Version:
python
import django
django.VERSION
exit()
---
python -c "import django; print(django.get_version())"
---
# Start django project
pipenv install django==2.1
pipenv shell
django-admin startproject test_project .
python manage.py runserver

---
Flask vs Django:  https://wsvincent.com/flask-vs-django/
---

# Tree command:
brew install tree
---

# Django Apps:
- A djago project can contain multiple apps
- project level vs app level

```python
python manage.py startapp pages
```

manually add apps to settings of project

# Views URLConfs
Django Request/Response Cycle: URL -> View -> Model (typically) -> Template

# Add an About page to our website

## Templates
Teamples, Views, and URLs make up a webpage

URL: control initial route, entry point into a page such as /about
View: contains the logic or what to display from the model/database
Template: has HTML with variables

## Django Class-based-Views
function vs class based views

# Django Official Pages:
- Django WebApp: https://docs.djangoproject.com/en/4.2/ref/
- Django API: https://www.django-rest-framework.org

# Day 1 Django Homework:
- Homework: read page 431-433 of Python Cookbook 3rd Edition
- Homework: read first chapter of django book

Kill port: sudo lsof -t -i tcp:8000 | xargs kill -9

# Added github link:
https://github.com/primecarecorp/202310CEIWDX_AZ-204

# Those who want to get ahead: (this Friday or next Monday)
Install Docker Desktop: 
- Windows: https://docs.docker.com/desktop/install/windows-install/
- Mac: https://docs.docker.com/desktop/install/mac-install/
  
Tutorials: https://www.docker.com/play-with-docker/

# Day 2:
Add more pages/routes to our website
Add Templates
Add Tests

## Add About Page:
1) Added templates/about.html and added html code in it
2) Add Class for About Page in pages/views.py (App Level)
3) Add path to pages/urls.py

## Extend Templates: use base template to extend to all other templates
1) Create templates/base.html
2) Add repeating HTML in base.html
3) Use/Extend base.html to other Templates (about.html and home.html)

## Add Tests:
python manage.py test
(optional) Further reading PyTest Articles/Tutorials
https://docs.djangoproject.com/en/4.2/topics/testing/overview/


## Create a new App that can Post information to Database
cd ..
mkdir 3django
cd 3django
django-admin startproject mb_project .
python manage.py startapp posts
python manage.py migrate
python manage.py runserver

## Create a Database Model:
https://docs.djangoproject.com/en/4.2/ref/models/fields/

- Download  DBeaver to view the sqllite Database: https://dbeaver.io/download/
- Or use DB Shell to query the database
Goto the folder where the database is and then:
sqlite3  db.sqlite3
Then depending on what you want:
.tables
or .schema
Instead of invoking sqlite3 directly you could do:
python manage.py dbshell 
python manage.py inspectdb
please see https://docs.djangoproject.com/en/3.0/ref/django-admin/#django-admin-inspectdb for additional info.

Here is a query:
python3 manage.py dbshell
.tables

Here is another Query: Find the name of the table you are looking for, then run the following commands:
.header on
.mode column
pragma table_info('table you are looking for');
Do not forget the semicolon in the last instruction.

But please do yourself a favour and get a GUI database client. Life is much easier when you have one.

### Activating a Model:
1) Create a Migration File "makemigrations" command but does not execute the SQL commands
python manage.py makemigrations posts
2) Build Database with "migrate" command does execute the instructions in the migration file
python manage.py migrate posts

## Django Admin
- To use Django Admin we need to create a "superuser"

Type:
1) Username
2) Email
3) Password

python manage.py createsuperuser
python manage.py runserver
http://127.0.0.1:8000/admin/

- Display posts app in Admin requires explicit mention in posts/admin.py
- Add a Post
- Handle Post Object as a String in posts/models.py
- Display Database Content on our homepage: Views, Templates, URLConfs

posts/views.py > Add ListView and Models
mkdir templates
touch templates/home.html

- Let Django know where to look for Templates folder: mb_project/settings.py
"DIRS": [os.path.join(BASE_DIR, 'templates')], # Added new
Make sure to import "os" in the header

- object_list
In templates/home.html we use the Django Templating Language > for loop to list all the objects within object_list
object_list: the name of the variable that ListView returns to us

- Django Best Practice: rename object_list to a more specific name
Provide an explicit name to "object_list" using "context-object-name": make it easier to know what is contained in the template

- Link main project with app urls
setup URLConfs mb_project/urls.py to include posts

- Create an app level urls.py:
touch posts/urls.py

python manage.py runserver

# Day 3:
- Challenge Labs
- Attendance
- Git Introduction - based on our conversation yesterday
- Database Viewer/Browser/Explorer: DBeaver, SQL Bench, SQL Server Management Studio, Azure Data Studio, 
- If anyone still stuck on their machine to run any of my code then let me know here.

- Django Continuation of Post App:
    - Add Tests in this App (with Database)

-  Django Blog App:


### Git Introduction

To follow along with AJ's Django folder do the following:

1 time steps:
1) Create a directory: AJ_GithubRepo
2) cd AJ_GithubRepo
3) git init
4) git clone https://github.com/primecarecorp/202310CEIWDX_AZ-204.git
5) git remote add origin https://github.com/primecarecorp/202310CEIWDX_AZ-204.git

Everytime AJ uploads code in his GitHub Repo: 202310CEIWDX_AZ-204, run following commands from folder AJ_GithubRepo:
- git fetch origin
- git merge origin/main

make sure to not make any changes to AJ_GithubRepo Folder, use this folder only to pull code from AJ's repo.
Do Django development in a seperate folder, and you don't need to push your code to GitHub.

Reference: https://docs.github.com/en/get-started/using-git/getting-changes-from-a-remote-repository

---