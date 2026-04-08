# **Django**

## **Django Architecture (MVT Pattern)**

Django follows the Model–View–Template (MVT) design pattern, which helps in organizing the application into separate layers.

### Model (Data Layer)

The model represents the structure of the database. Each model corresponds to a table in the database and is responsible for handling data operations such as creating, retrieving, updating, and deleting records.

Example:

```python
from django.db import models

class Product(models.Model):
    name = models.CharField(max_length=100)
    price = models.FloatField()
```

---

### View (Business Logic Layer)

The view handles incoming requests and returns responses. It interacts with models to process data and sends the result back to the user.

Example:

```python
from django.http import HttpResponse

def home(request):
    return HttpResponse("Welcome!")
```

---

### Template (Presentation Layer)

Templates define how data is displayed to the user. They use Django Template Language (DTL) to dynamically render content.

Example:

```html
<h1>Hello {{ name }}</h1>
```

---

## **Django Project vs App**

A project represents the entire web application, while an app is a module that handles a specific feature or functionality.

For example, in an e-commerce application:

* Project: ecommerce
* Apps: users, products, orders

---

## **Django Project Structure**

```
myproject/
│
├── manage.py
├── myproject/
│   ├── __init__.py
│   ├── settings.py
│   ├── urls.py
│   ├── asgi.py
│   └── wsgi.py
│
└── myapp/
    ├── models.py
    ├── views.py
    ├── admin.py
    ├── apps.py
    ├── migrations/
```

### Important Files

* manage.py
  
  Used to execute project-related commands such as running the server and applying migrations.

* settings.py

  Contains all project configurations including database setup, installed apps, middleware, and static files.

* urls.py

  Defines URL patterns and maps them to corresponding views.

* models.py

  Defines the database schema using Python classes.

* views.py

  Contains the logic to handle requests and return responses.

* admin.py

  Used to register models for the admin interface.

* migrations/

  Stores changes made to the database schema over time.

---

## **Installation and Setup**

Install Django:

```bash
pip install django
```

Create a project:

```bash
django-admin startproject myproject
cd myproject
```

Run the development server:

```bash
python manage.py runserver
```

Create an app:

```bash
python manage.py startapp myapp
```

Register the app in settings.py:

```python
INSTALLED_APPS = [
    'myapp',
]
```

---

## **URL Routing**

URL routing connects incoming requests to appropriate views.

Example:

```python
from django.urls import path
from . import views

urlpatterns = [
    path('', views.home, name='home'),
]
```

Dynamic URL example:

```python
path('user/<int:id>/', views.profile)
```

---

## **Views**

Views process requests and return responses.

Function-based view:

```python
def home(request):
    return HttpResponse("Hello")
```

Rendering a template:

```python
from django.shortcuts import render

def home(request):
    return render(request, 'home.html', {'name': 'Subhash'})
```

Class-based view:

```python
from django.views import View

class HomeView(View):
    def get(self, request):
        return HttpResponse("Class View")
```

---

## **Models and ORM**

Django uses an Object Relational Mapping (ORM) system to interact with the database using Python instead of SQL.

Example model:

```python
class Student(models.Model):
    name = models.CharField(max_length=100)
    age = models.IntegerField()
```

Apply database changes:

```bash
python manage.py makemigrations
python manage.py migrate
```

CRUD operations:

```python
Student.objects.create(name="John", age=20)

students = Student.objects.all()

student = Student.objects.get(id=1)
student.age = 25
student.save()

student.delete()
```

---

## **Templates and Django Template Language**

Variables:

```html
{{ name }}
```

Loop:

```html
{% for s in students %}
  <p>{{ s.name }}</p>
{% endfor %}
```

Condition:

```html
{% if age > 18 %}
  Adult
{% else %}
  Minor
{% endif %}
```

---

## **Static Files**

Static files include CSS, JavaScript, and images used in the frontend.

Configuration:

```python
STATIC_URL = '/static/'
```

---

## **Forms in Django**

Basic form handling:

```python
def form_view(request):
    if request.method == "POST":
        name = request.POST.get('name')
```

Using Django forms:

```python
from django import forms

class StudentForm(forms.Form):
    name = forms.CharField(max_length=100)
```

---

## **Admin Panel**

Create a superuser:

```bash
python manage.py createsuperuser
```

Register models:

```python
from django.contrib import admin
from .models import Student

admin.site.register(Student)
```

The admin panel allows managing data without writing additional code.

---

## **Request–Response Lifecycle**

* A user sends a request through a browser.
* Django processes the request and matches it with a URL pattern.
* The corresponding view is executed.
* The view interacts with models if required.
* Data is passed to a template.
* The template renders the output.
* The response is sent back to the user.

---

## **Advantages of Django**

* Django enables fast development with built-in features.
* It provides a secure environment with protections against common attacks.
* It supports scalability and clean architecture.
* It includes a powerful admin interface.

---
