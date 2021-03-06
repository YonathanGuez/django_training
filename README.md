# Django Training
Training Django 

## Install all package : 

### If you use virtual environment :
* Install virtual environement : 
```
pip install virtualenv
```
* Create a virtual environment for a project : 
```
virtualenv venv
```
* Begin to use env :
> Windows: 
```
env\Scripts\activate
```
> Linux:
```
source /env/bin/activate
```
* For stop : 
```
deactivate
```

### Install all packages:
```
pip install -r requirements.txt
```

### If we want to add new packages:
```
pip freeze > requirements.txt
```
### Remarque :
We put the CI for run tests :
[.github/workflows/pythonapp.yml](https://github.com/YonathanGuez/django_training/blob/master/.github/workflows/pythonapp.yml)
for the beging that will test only test_pytest.py

## Begin With Django:
### 1) Create files manager : 
```
django-admin startproject <mysite>
```
That will build folder mysite with folders and files :
```
mysite/
    manage.py
    mysite/
        __init__.py
        settings.py
        urls.py
        asgi.py
        wsgi.py
```
### 2) Check my Server :
I need to enter in my folder : 
``` cd test_site```

and run my server :
```
py manage.py runserver
```
you can check now your page : http://127.0.0.1:8000/

### 2-bis) Give the IP available:
All available public IPs:
Listen on all available public IPs use: (0 is a shortcut for 0.0.0.0. )
```
py manage.py runserver 0:8000
```

### 3) Creation application and Work with rooting in Django:
* we need to be at the same level of manage.py before to run this:
```
python manage.py startapp polls
```
that will create :
```
polls/
    __init__.py
    admin.py
    apps.py
    migrations/
        __init__.py
    models.py
    tests.py
    views.py
```
* We will add a file urls.py :
```
from django.urls import path
from . import views
urlpatterns = [
    path('', views.index, name='index'),
]
```
and put something in views.py : 
```
from django.http import HttpResponse
def index(request):
    return HttpResponse("Hello, world. You're at the polls index.")
```
that will read our function index when we enter in /polls/

* For rooting our new app
And in test_site/urls.py  we will import include and this line: 
```
path('polls/', include('polls.urls')), 
```
relaunch our server
Now we can check the URL: http://localhost:8000/polls/

### 4) Database configuration:
```
python manage.py migrate
```
we will set in the database: 
'django.contrib.admin',
'django.contrib.auth',
'django.contrib.contenttypes',
'django.contrib.sessions',
'django.contrib.messages',
'django.contrib.staticfiles',

1) We want to create database now : We will build a model into polls/models.py 
2) For activate model in  settings.py we need to add a line into INSTALLED_APPS: 'polls.apps.PollsConfig'
3) Indicate model change : python manage.py makemigrations polls
3 bis) Indicate what kind of model : python manage.py sqlmigrate polls 0001
4) add the new migration : python manage.py migrate

### 5) Create Superadmin 
```
python manage.py createsuperuser
```
Now we can manage some data in the administation

### 6) Template :
we need to build a folder into polls and by convention add an other folder with the same 
name as our app (in this example polls )
i this folders we will put all template html we need 
we will manage thoses templates with urls.py and views.py

![template and view](https://github.com/YonathanGuez/django_training/blob/site/img/relationtemplate.png?raw=true)

### 7) Create Test :
Test must be a file in polls the name of the file must begin by test or tests by convention 
In this system it s will find automaticly  all tests if the name begin by test
for launch tests in pools: 
```
python manage.py test polls
```

### 8) Static files : css , img ...
we need to build a directory static in polls like templates
static is in link with  STATICFILES_FINDERS  into Django
AppDirectoriesFinder search « static » into each app of INSTALLED_APPS
Into static we need also polls
#### css:
```
polls/static/polls/style.css
```
load static styles.csspython manage.py runserver
```
{% load static %}
<link rel="stylesheet" type="text/css" href="{% static 'polls/style.css' %}">
```
#### images:
```
polls/static/polls/images/background.png
```