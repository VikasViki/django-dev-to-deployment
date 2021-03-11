# django-dev-to-deployment
Learning Django from Udemy Course [Demo Website of BT real estate]

### Apps

Run the  below command where the app needs to be created
`python manage.py startapp <app_name>`

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