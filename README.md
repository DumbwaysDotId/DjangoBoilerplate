# Zahir X API - Django

## Requirements
- Python3
- Git
- MySQL

## Installation (DEV)
- create database named "zahir_x_django" on MySQL
- cd to deserved folder
- Clone the project:
```
$ git clone https://bitbucket.org/zahironline/zahir_x_django.git
```
- Change dir to cloned project:
```
$ cd zahir_x_django
```
- Create Virtualenv (make sure you already install pip3 install python-virtualenv)
then run this command to create virtualenv
```
virtualenv venv
```
- Change source to venv that you created
```
source venv/bin/activate
```
- Make sure you are already install mysqlclient on your engine
```
Mac OSx: brew install mysql
Ubuntu: sudo apt-get install libmysqlclient-dev
Ubuntu alternative if failed: sudo apt-get install python-mysqldb
```
- Install requirements.txt to install all required dependencies
```
pip3 install -r requirements.txt
```
- Migrate all table:
```
$ python3 manage.py migrate
```
- Create Super User (admin):
```
$ python3 manage.py createsuperuser
```
- Generate fixtures
```
python3 manage.py loaddata languages
python3 manage.py loaddata countries
python3 manage.py loaddata currencies
```
- Generate static files, mainly for admin page
```
python manage.py collectstatic
```
- Run the server:
```
$ python3 manage.py runserver
```
- Multiple settings files
```
Since the majority of the content of each of these files is the same,
we put all of the repeated code in a base.py
we use a settings file for......
- local environment - local.py
- heroku environment - heroku.py, to override Heroku configuration variable you can run this command:
    heroku config:set DJANGO_SETTINGS_MODULE=app.settings.heroku
```

Congratz!! Now check on browser http://localhost:8000, to view the API Lists doc that you can play around!

## If you found error on migrations, do these

find . -path "*/migrations/*.py" -not -name "__init__.py" -delete
find . -path "*/migrations/*.pyc"  -delete
