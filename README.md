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


