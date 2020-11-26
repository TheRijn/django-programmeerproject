# Programmeerproject: Session 1

```
django-admin startproject books app
```


## Adding an App


```shell
python3 manage.py startapp ratings
```

`settings.py`

```python
INSTALLED_APPS = [
    'ratings.apps.RatingsConfig',
   	 ...
]
```

`urls.py`

```python
from django.contrib import admin
from django.urls import path, include

urlpatterns = [
    path('/', include('ratings.urls')),
    path('admin/', admin.site.urls),
]
```
<div style="page-break-after: always;"></div>

## Custom User Model

`models.py`

```python
from django.contrib.auth.models import AbstractUser
from django.db import models

class User(AbstractUser):
    pass
```

`settings.py`

```python
AUTH_USER_MODEL = 'ratings.User'
```

`admin.py`

```python
from django.contrib.auth.admin import UserAdmin

admin.site.register(User, UserAdmin)
```
