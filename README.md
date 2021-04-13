# How to install Django app TODO list:

1. *cd* to your environments folder and activate your environment:

    - **Mac/Linux**: `source djangoPy3Env/bin/activate`                      

    - **Windows (command prompt)**: `call djangoPy3Env\Scripts\activate`    

    - **Windows (git bash)**: `source djangoPy3Env/Scripts/activate`      

2. Navigate to the folder where you want to create your project

3. Create a project folder `mkdir <Project Name>`

4. Create your project using 
`django-admin startproject <Project Name>`

5. *cd* into your project: `cd <Project Name>`

6. Test your project by typing next command in your terminal: `python manage.py runserver`

7. Create you app by typing next command in your terminal: `python manage.py startapp <Your APP Name>`

8. Open settings.py inside of your project folder and add `<Your APP Name>` as a **first element to the INSTALLED_APPS list**

9. Open urls.py inside of your project folder 
    - add **include** to the end of `from django.urls import path`, it should look something like this `from django.urls import path, include`
    - add this line `path('', include('<Your APP Name>.urls')),` as a **first element to the urlpatterns list**

10. Create urls.py inside of your app and add this code snippet: 
```
from django.urls import path     
from . import views
urlpatterns = [
    path('', views.index),	   
]
```

11. Open views.py inside your app and add this code snippet: 
```
from django.shortcuts import render, HttpResponse
def index(request):
    return HttpResponse("this is the equivalent of @app.route('/')!")
```

12. run your app using next command in your terminal: `python manage.py runserver`

13. Dont forget to have fun while you are coding!!!
