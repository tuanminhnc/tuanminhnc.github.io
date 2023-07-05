# Github page - My page using Django Framework


### Local setup

Install project dependencies:
````bash
 pip install -r requirements.tx
````

### Run localy
```bash
python manage.py runserver

or

./manage.py runserver
```

### Deloy on Vervel

We allow "*.vercel.app" subdomains in ALLOWED_HOSTS, in addition to 127.0.0.1:
```bash
# vercel_app/settings.py
ALLOWED_HOSTS = ['127.0.0.1', '.vercel.app']
```

The wsgi module must use a public variable named app to expose the WSGI application:
```bash
# vercel_app/wsgi.py
app = get_wsgi_application()
```

The corresponding WSGI_APPLICATION setting is configured to use the app variable from the vercel_app.wsgi module:
```bash
# vercel_app/settings.py
WSGI_APPLICATION = 'vercel_app.wsgi.app'
```
