# django-dev-to-deployment
Learning Django from Udemy Course [Demo Website of BT real estate]

### Apps

Run `python manage.py startapp <app_name>` command where the app needs to be created.

**Make sure to add <app_name> to INSTALLED_APPS list in settings.py of the project**

* For each app created, a separate urls.py file have to be created for navigating in the app.
* Path of every urls.py file in an app should be added to the urls.py of the project.

### Templates

* Path to the templates directory need to be specified in **TEMPLATES** list in settings.py of the project.
* Above points helps in accessing the templates anywhere inside the app

### Static Files

* In order to preload all static files run `python manage.py collectstatic` command
* The above command copies all static files from all static directory of apps in to the `static` dir of the project.
* Created a path with `STATIC_ROOT` string variable and `STATICFILES_DIRS` list in settings.py of the project.

### Bootstrap files

* Add components of webpage in `base.html` by linking it to the files  `templates/partials` dir
* ` {% load static %}` to load all static files in current html
* `{% include 'partials/_topbar.html'%}` to load the contents of `_topbar.html` in current file.

### Linking NavBar to html pages

* `{% url 'index' %}` index in url name specified in urls.py inside pages app.
* `{% if '/' == request.path %}` this template tag checks whether current path is the root path, in order to implement dynamic behaviours inside a webpage. request.path is a string path.

### Linking Database to Project

* `psycopg2` pip package is used to connect to postgress database from python.
* New items added in DATABASES dict in settings.py of the project i.e NAME, USER, PASSWORD, HOST and changed the engine name from sqlite3 to postgresql.

### Creating Model - listing

* All fields of the model will be created as variable insidel models.py of the app.
* Any app can be imported using `import <app_name>` inside the project
* Reference to the model fields : https://docs.djangoproject.com/en/3.1/ref/models/fields/