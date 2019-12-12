Travel
=======

A django version of TDWAY project.

Contains

- gallery
- repotrs
- user account
- blog
- forum (?)
- admin
- backup -> amazon
- login via django/social-auth
and more

Database notes
--------------

1. Create model from existing database:
> python manage.py inspectdb > models.py
> python manage.py migrate

2. Install social auth:
> python manage.py syncdb
> python manage.py migrate



Djnago pakage notes
-------------------

Django 1.9 can't be used to the issue with caches in django_imagekit_library.


Data


Installation
------------

1. create virtual environment and use it
Better to use PyCharm IDE so it can be reused for other projects OR use a command
$ virtualenv <ve folder name>
to use virtual environment
$ source <ve>/bin/activate


2.0
Before pip install -r requirements.txt on windows:

pip install rcssmin --install-option="--without-c-extensions"
pip install rjsmin --install-option="--without-c-extensions"

2. install psycopg2
http://initd.org/psycopg/docs/install.html
after installation copy it to <ve>/site-packages/
windows: todo
mac: todo: by some miracle it managed to work, describe next time

3. install Pillow
https://pypi.python.org/pypi/Pillow/3.2.0
todo: describe windows installation
linux or mac: 
$ pip install Pillow

4. install python dependencies
$ pip install -r "requirements/local.txt"

5. make sure you use proper config files here: 
config/settings/__init__.py
settings_production.py should not be loaded for local environment

6. specify in your config file STATIC_ROOT and LOCALE_PATHS


Run after update
----------------

1. install bower dependencies
$ python manage.py bower_install

2. update DB
$ python manage.py migrate

3. run
$ python manage.py runserver
It should be made as running configuration for IDE for better experience,
Working directory must point to root of project e.g. /Users/Max/Projects/tdway_django