# mongo_tutorials
sudo pip3 install virtualenvwrapper

source virtualenvwrapper.sh

VIRTUALENVWRAPPER_PYTHON=/usr/bin/python3.5

mkvirtualenv django_tutorials

workon django_tutorials

pip3 install django

mkdir djano_projects ( or cd to the projects dir)

django-admin startproject readit

cd readit

tree -- unix 

(if there's no tree installed on mac -- brew install tree)

tree --> manage.py -- wrapper for all the command line utility
         readit
python manage.py migrate -- sync the database (sqllite3)

tree --> now contains sqllite3

python manage.py runserver
Performing system checks...

System check identified no issues (0 silenced).
December 13, 2017 - 01:44:36
Django version 2.0, using settings 'readit.settings'
Starting development server at http://127.0.0.1:8000/  

Opening the above link will show the localhost server

readit folder which is created inside acts like a root.
(django_tutorials) Bhavyas-MacBook-Air-2:readit Saibhavya$ tree
.
├── db.sqlite3
├── manage.py
└── readit
    ├── __init__.py
    ├── __pycache__
    │   ├── __init__.cpython-36.pyc
    │   ├── settings.cpython-36.pyc
    │   └── urls.cpython-36.pyc
    ├── settings.py
    ├── urls.py
    └── wsgi.py
wsgi is used for deployment
settings.py-- contains all the infrastructure/settings (check for the initial database, apps installed)
urls.py -- dynamic traffic director (matches the url to the specified view)
sample - urlpatterns = [
            path('admin/', admin.site.urls),
      ]
Apps in django: A self contained module living inside django. Admin is a default app
     Custom apps - Checkout, Orders, Tracking are different e-commerce project apps

Creating a books app:
django-admin startapp book
.
├── book
│   ├── __init__.py
│   ├── admin.py
│   ├── apps.py
│   ├── migrations
│   │   └── __init__.py
│   ├── models.py
│   ├── tests.py
│   └── views.py
├── db.sqlite3
├── manage.py
└── readit
    ├── __init__.py
    ├── __pycache__
    │   ├── __init__.cpython-36.pyc
    │   ├── settings.cpython-36.pyc
    │   ├── urls.cpython-36.pyc
    │   └── wsgi.cpython-36.pyc
    ├── settings.py
    ├── urls.py
    └── wsgi.py
    
Installing 3rd party apps - pip install <app_name>
   pip install django-debug-toolbar 
   pip freeze #to verify the installation
   (django_tutorials) Bhavyas-MacBook-Air-2:readit Saibhavya$ pip freeze
  click==6.7
  Django==2.0
  django-debug-toolbar==1.9.1
  olefile==0.44
  Pillow==4.3.0
  pyparsing==2.2.0
  pytz==2017.3
  sqlparse==0.2.4
  svgwrite==1.1.11
  Tree==0.2.3
  
  Go to settings.py and add the new installed apps (sequence convention - djano apps,3rd party apps followed by our custom apps)
  Adding debug_toolbar,'books'
  INSTALLED_APPS = [
    'django.contrib.admin',
    'django.contrib.auth',
    'django.contrib.contenttypes',
    'django.contrib.sessions',
    'django.contrib.messages',
    'django.contrib.staticfiles',
    'debug_toolbar', 
    'books'
]


  
