# Django ORM Web Application

## AIM
To develop a Django application to store and retrieve data from a database using Object Relational Mapping(ORM).

## Entity Relationship Diagram

![EN](https://user-images.githubusercontent.com/85949888/232239273-6c993285-8720-46b3-99e3-7b0984acfcae.png)

## DESIGN STEPS

### STEP 1:

clone the repository from github.

### STEP 2:

create an admin interface for django.

### STEP 3:

create an app and edit settings.py

### STEP 4:

make migrations and migrate the changes.

### STEP 5:

create admin user and write python code for admin and models.

### STEP 6:

make all the migrations to 'myapp'.

### STEP 7:

create an student database with 10 fields using runserver command.

## PROGRAM

admin.py
```python

from django.contrib import admin
from .models import Student,StudentAdmin,lab,labAdmin
# Register your models here.
admin.site.register(Student,StudentAdmin)
admin.site.register(lab,labAdmin)
```
models.py
```python

from django.db import models
from django.contrib import admin
# Create your models here.
class Student(models.Model):
    refno=models.CharField(max_length=6,primary_key=True)
    name=models.CharField(max_length=100)
    age=models.IntegerField()
    email=models.EmailField()

class lab(models.Model):
    class Meta():
        permissions=[
            ("view_labs","can view lab details")
        ]
    labname=models.CharField(max_length=100)
    labbudget=models.IntegerField()

class StudentAdmin(admin.ModelAdmin):
    list_display=('refno','name','age','email')

class labAdmin(admin.ModelAdmin):
    list_display=('labname','labbudget')

```

## OUTPUT

![Output](https://user-images.githubusercontent.com/85949888/232239141-c74325b9-b5bb-44bf-8c07-d5555b79d2d0.png)

## RESULT

The program for creating an student database using ORM is executed sucessfully.
