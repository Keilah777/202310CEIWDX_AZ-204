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

# Added github link:
https://github.com/primecarecorp/202310CEIWDX_AZ-204

# Those who want to get ahead: (this Friday or next Monday)
Install Docker Desktop: https://docs.docker.com/desktop/install/windows-install/
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

