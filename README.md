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
