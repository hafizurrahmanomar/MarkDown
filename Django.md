# Hafizur Rahman Omar

<div align="center">

![Hafizur Rahman Omar](https://avatars.githubusercontent.com/u/80614973?s=400&u=0fd97c4869d564d66141159f44c31ebc2891db63&v=4)

</div>

---

<details>

<summary>Hafizur Rahman Omar info Read more...</summary>

# I'm a Professional Web and App Developer and Digital Marketer

</details>

---

![MarkDown](https://shorturl.at/ikoBQ)

# Python and Django-admin in common commands for web development

---

**Django. Some of the most commonly used commands are–**

- python manage.py startapp
- python manage.py makemigrations
- python manage.py migrate
- python manage.py runserver

**Step 1: Initialize a project by following command**

**Creating a virtual environment**

---

```python
python -m venv env

# env activate

# for windows

env/Scripts/activate

# linux/Mac 

 source env/bin/activate

# pip install inside the env

pip install Django

```

**Step 2: Create SuperUser for Django Admin Panel**

---

```python

# This command python manage.py list show

# cd hafiz

 python manage.py createsuperuser

 # User Name(Hafizurrahmanomar)
 # password:
 # email:example@gmail.com

 # Local Host Link

 localhost:8000/

 or

 http://127.0.0.1:8000/

  # Local Host administration link

  https://localhost:8000/admin/



```



**hafiz(hafiz=projectName)/setting.py**

**Step 3: Add your app to the settings.py**

```python



from pathlib import Path

# Custom import

import os

# Build paths inside the project like this: BASE_DIR / 'subdir'.
BASE_DIR = Path(__file__).resolve().parent.parent

# Custom templates directory create by Hafizur Rahman Omar

TEMPLATES_DIR = os.path.join(BASE_DIR,'templates')

STATIC_DIR = os.path.join(BASE_DIR,'static')



# Application definition

INSTALLED_APPS = [
    'django.contrib.admin',
    'django.contrib.auth',
    'django.contrib.contenttypes',
    'django.contrib.sessions',
    'django.contrib.messages',
    'django.contrib.staticfiles',

    # Custom app
      'blog',
]


TEMPLATES = [
    {
        'BACKEND': 'django.template.backends.django.DjangoTemplates',

        'DIRS': [TEMPLATES_DIR],

        or

        'DIRS': [BASE_DIR / 'templates'],
         

        'APP_DIRS': True,
        
    },
]



# Static files (CSS, JavaScript, Images)
# https://docs.djangoproject.com/en/4.2/howto/static-files/

STATIC_URL = 'static/'

# custom add by Hafizur Rahman

    STATICFILES_DIRS = [


        STATIC_DIR,

    ]








```

**Step 4: Create Models named Article and Comment in the blog app**

---

##### Model Article :

- Fields :
  - **_title:_** Stores the title of an article
  - **_body:_** Content of that article
  - **_created_on:_** Date and Time on which that article was created

##### Model Comment :

- Fields :
  - **_article:_** Article on which comment is created
  - **_text:_** Actual comment
  - **_created_on:_** Date and Time on which that article was created

```python

from django.db import models


class Article(models.Model):
	title = models.CharField(max_length=200)
	body = models.TextField()
	created_on = models.DateTimeField(auto_now_add=True)


class Comment(models.Model):
	article = models.ForeignKey(Article, on_delete=models.CASCADE)
	text = models.CharField(max_length=200)
	created_on = models.DateTimeField(auto_now_add=True)



```

**Step 5: Register your model in blog/admin.py so that it shows up in the admin panel.**

---

```python

from django.contrib import admin
from .models import Article, Comment

admin.site.register(Article)
admin.site.register(Comment)


```


**Step 6: Now, To migrate all your changes and start the server, run the following commands in your terminal**


```python
python manage.py makemigrations
python manage.py migrate
python manage.py runserver

# Create a superuser account to log in to the admin panel

python manage.py createsuperuser

# Visit the admin panel link at 

http://127.0.0.1:8000/admin/

```



**display the current Django version**

```
django-admin version

```

**Runs a development server with data from the given fixture(s).**

```
django-admin testserver

```

**create new migrations to the database based on the changes detected in the models**

```
django-admin makemigrations

```

**synchronize the database state with your current state project models and migrations**

```
django-admin migrate

```

**Shows all available migrations for the current project.**

```
django-admin showmigrations

```

**display usage information and a list of the commands provided by each application**

```
django-admin help

```

**Returns a list of the SQL statements required to return all tables in the database to the state they were in just after they were installe**

```
django-admin sqlflush

```

**Prints the SQL statements for the named migration.**

```
django-admin sqlmigrate

```

**Prints the SQL statements for resetting sequences for the given app name(s).**

```
django-admin sqlsequencereset

```

**Squashes an existing set of migrations (from first until specified) into a single new one.**

```
django-admin squashmigrations

```

**Deletes stale content types (from deleted models) in your database.**

```
django-admin remove_stale_contenttypes

```

**start the development webserver at 127.0.0.1 with the port <port> default 8000**

```
django-admin runserver <port>

```

**Sends a test email to the email addresses specified as arguments.**

```
django-admin sendtestemail

```

**Runs a Python interactive interpreter.**

```
django-admin shell

```

**Checks the entire Django project for potential problems**

```
django-admin check

```

**Allows changing a user’s password**

```
django-admin changepassword <username>

```

**Can be run as a cron job or directly to clean out expired sessions.**

```
django-admin clearsessions

```

**Helps to collect all the static files in the one mentioned directory**

```
django-admin collectstatic

```

**Creates a superuser account**

```
django-admin createsuperuser

```

**Compiles .po files to .mo files for use with builtin gettext support**

```
django-admin compilemessages

```

**Creates the tables needed to use the SQL cache backend.**

```
django-admin createcachetable

```

**Runs the command-line client for a specified database, or the default database if none is provided.**

```
django-admin dbshell

```

**Displays differences between the current settings.py and Django's default settings.**

```
django-admin diffsettings
```

**Output the contents of the database as a fixture of the given format (using each model's default manager unless --all is specified).**

```
django-admin dumpdata

```

**Removes ALL DATA from the database, including data added during migrations. Does not achieve a "fresh install" state.**

```
django-admin flush

```

**Introspects the database tables in the given database and outputs a Django model module.**

```
django-admin inspectdb

```

**Installs the named fixture(s) in the database.**

```
django-admin loaddata

```

**Runs over the entire source tree of the current directory and pulls out all strings marked for translation.**

```
django-admin makemessages

```
