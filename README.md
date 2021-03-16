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

### Creating Model - listing, realtor

* All fields of the model will be created as variable inside models.py of the app.
* Any app can be imported using `import <app_name>` inside the project
* Reference to the model fields : https://docs.djangoproject.com/en/3.1/ref/models/fields/

### Making Migrations to Database

* Once models are created run `python manage.py makemigrations`, it creates a file inside `migrations` directory of the corresponding app.
* After running `python manage.py migrate`, we can see the **<app_name>_<model_name>** table inside the database.

### Adding Apps to admin area

* Import the models created inside models.py of corresponding app.
* Register the model using `admin.site.register(<model_name>)` inside admins.py of the corresponding app.

### Adding data to models from admin area

* Added two variables MEDIA_ROOT and MEDIA_URL inside settings.py of the project.
* Linked **MEDIA_URL** to **urlpatterns** inside urls.py of the project using static method and attributes of **settings** module which is present inside **django.conf**.

### Modifying Admin Page

* Cretate base_site.html inside `templates/admin/` directory. This over writes the default wrapper of django.
* Add `{% extends 'admin/base.html' %}` as first line inside the new file in order keep all functionalities intact of the admin panel.
* CSS of the admin page is overridden by new file created at `<project_name>/static/css/admin.css`.

### Customizing Admin Display Data

* In order to customize admin display data of a model, create new class inheriting `admin.ModelAdmin`.
* There are various tuples which provides various functionalities, we can customize display data of the paticular model by overridiing this tuples i.e **list_display, list_display_links, list_filter, list_editable, search_fields, list_per_page**