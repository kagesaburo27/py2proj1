# py2proj1
# ToDo list using Django Web Framework

### Installation
```bash
python -m venv venvset1
venvset1\Scripts\activate
pip install django
pip install psycopg2
```

django-admin startproject mysite
python manage.py runserver
### Usage
django-todo comes with its own `todo/base.html`, which extends your master `base.html`. All content lives inside of:

`{% block content %}{% endblock %}`

If you use some other name for your main content area, you'll need to override and alter the provided templates.

All views are login-required. Therefore, you must have a working user authentication system.

Add to your settings:

```
INSTALLED_APPS = (
    ...
    'todo',
)
```

Migrate in database tables:

`python manage.py migrate todo`

Add to your URL conf:

`path('todo/', include('todo.urls', namespace="todo")),`

Add links to your site's navigation system:

```
<a href="{% url 'todo:lists' %}">Todo Lists</a>
<a href="{% url 'todo:mine' %}">My Tasks</a>
```

django-todo makes use of the Django `messages` system. Make sure you have something like [this](https://docs.djangoproject.com/en/2.1/ref/contrib/messages/#displaying-messages) (link) in your `base.html`.

Log in and access `/todos`!
