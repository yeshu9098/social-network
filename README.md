# Django project

Add Procfile

    web: gunicorn pybook.wsgi

Install

    pip install gunicorn whitenoise django_heroku

Add this to settings

    import django_heroku

    django_heroku.settings(locals())

Add middleware of whitenoice for static files

    "whitenoise.middleware.WhiteNoiseMiddleware",

In terminal export

    export DJANGO_SETTINGS_MODULE="pybook.settings.prod"

And set the config vars in settings of app in heroku

    DATABASE_URL = database_url
    DJANGO_SETTINGS_MODULE = pybook.settings.prod
    SECRET_KEY = secret_key

Set this in settings
    
    debug = False
    ALLOWED_HOSTS = [
    "*",
    ]

After that you can upload this to heroku by heroku cli

    git init
    git add .
    git commit -m "commit message"

    heroku git:remote -a app_name_on_heroku
    git push heroku master

