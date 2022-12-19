# How to use mixins, Viewsets & Routers to create a Todo API in Django Rest Framework

# Introduction

Following this link: [https://emmakodes.com/build-a-todo-api-backend-using-generic-class-based-views-in-django-rest-framework](https://emmakodes.com/build-a-todo-api-backend-using-generic-class-based-views-in-django-rest-framework) we implemented a Todo API using Generic class-based views in Django Rest Framework.

In this article, we will see how to use mixins, Viewsets & Routers to create the same Todo API.

Note: This article is a follow-up from [https://emmakodes.com/build-a-todo-api-backend-using-generic-class-based-views-in-django-rest-framework](https://emmakodes.com/build-a-todo-api-backend-using-generic-class-based-views-in-django-rest-framework)

# Using mixins

To use mixins:

*   Replace the code in the [views.py](http://views.py) file of the todo app directory with the following code:
    

```python
from .models import Todo
from .serializers import TodoSerializer
from rest_framework import mixins
from rest_framework import generics

class TodoList(mixins.ListModelMixin,
                  mixins.CreateModelMixin,
                  generics.GenericAPIView):
    queryset = Todo.objects.all()
    serializer_class = TodoSerializer

    def get(self, request, *args, **kwargs):
        return self.list(request, *args, **kwargs)

    def post(self, request, *args, **kwargs):
        return self.create(request, *args, **kwargs)
    
    
class TodoDetail(mixins.RetrieveModelMixin,
                    mixins.UpdateModelMixin,
                    mixins.DestroyModelMixin,
                    generics.GenericAPIView):
    queryset = Todo.objects.all()
    serializer_class = TodoSerializer

    def get(self, request, *args, **kwargs):
        return self.retrieve(request, *args, **kwargs)

    def put(self, request, *args, **kwargs):
        return self.update(request, *args, **kwargs)

    def delete(self, request, *args, **kwargs):
        return self.destroy(request, *args, **kwargs)
```

We're building our view using GenericAPIView(which helps to provide the core functionality), and adding in ListModelMixin and CreateModelMixin to TodoList class to help process the listing and creation of new Todo objects.

We also added RetrieveModelMixin, UpdateModelMixin, and DestroyModelMixin to TodoDetail class to provide retrieve, update and destroy actions respectively for a single Todo object.

You can start your development server and see that your API is working as before.

# Using Viewsets & Routers

REST framework includes an abstraction for dealing with ViewSets, that allows the developer to concentrate on modeling the state and interactions of the API, and leave the URL construction to be handled automatically, based on common conventions.

*   Replace the code in the [views.py](http://views.py) file of the todo app directory with the following code:
    

```python
from rest_framework import viewsets
from .models import Todo
from .serializers import TodoSerializer

class TodoViewSet(viewsets.ModelViewSet):
    """
    This viewset automatically provides `list`, `create`, `retrieve`,
    `update` and `destroy` actions.

    """
    queryset = Todo.objects.all()
    serializer_class = TodoSerializer
```

This time we've used the ModelViewSet class in order to get the complete set of default read and write operations. We're still setting the query set and serializer\_class attributes exactly as we did when we were using regular views, but we no longer need to provide the same information to two separate classes.

*   Replace the code in the [urls.py](http://urls.py) file of the todo app directory with the following code:
    

```python
from django.urls import path, include
from rest_framework.routers import DefaultRouter
from . import views

# Create a router and register our viewsets with it.
router = DefaultRouter()
router.register(r'todos', views.TodoViewSet,basename="todo")

# The API URLs are now determined automatically by the router.
urlpatterns = [
    path('', include(router.urls)),
]
```

Because we're using ViewSet classes rather than View classes, we actually don't need to design the URL conf ourselves. The conventions for wiring up resources into views and URLs can be handled automatically, using a Router class. All we need to do is register the appropriate view sets with a router, and let it do the rest.

Start your development server and go to the following address on your web address to see the API in action: [http://127.0.0.1:8000/api/todos/](http://127.0.0.1:8000/api/todos/) [http://127.0.0.1:8000/api/todos/1/](http://127.0.0.1:8000/api/todos/1/)

Using viewsets can be a really useful abstraction. It helps ensure that URL conventions will be consistent across your API, minimizes the amount of code you need to write, and allows you to concentrate on the interactions and representations your API provides rather than the specifics of the URL conf.

# Conclusion

The end. Thanks for reading.

Check out how to build the same Todo API backend using Generic class-based views in Django Rest Framework: [https://emmakodes.com/build-a-todo-api-backend-using-generic-class-based-views-in-django-rest-framework](https://emmakodes.com/build-a-todo-api-backend-using-generic-class-based-views-in-django-rest-framework)