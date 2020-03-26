```bash
pip install django djangorestframework

django-admin startproject django_react .

django-admin startapp react_demos

```

```python
INSTALLED_APPS = [
    'django.contrib.admin',
    'django.contrib.auth',
    'django.contrib.contenttypes',
    'django.contrib.sessions',
    'django.contrib.messages',
    'django.contrib.staticfiles',
    'react_demos.apps.ReactDemosConfig', # activate the new app
]

# models.py
from django.db import models

class Lead(models.Model):
    name = models.CharField(max_length=100)
    email = models.EmailField()
    message = models.CharField(max_length=300)
    created_at = models.DateTimeField(auto_now_add=True)

```

```bash
python manage.py makemigrations react_demos
python manage.py migrate

```
unit test
```bash
pip install coverage

coverage run --source='.' manage.py test

```