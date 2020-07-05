![alt_text](https://d2h0cx97tjks2p.cloudfront.net/blogs/wp-content/uploads/sites/2/2019/03/Django-Architecture-Diagram.jpg)

![alt text](https://mpng.pngfly.com/20181212/shf/kisspng-django-middleware-blog-csdn-user-5c11bc1b88b499.40510264154466613956.jpg)


Django REST Framework Tutorial – CRUD
Django REST Framework Tutorial – Login and Authentiction
Django REST Framework Tutorial – Custom Fields
Django REST Framework Tutorial – Pagination
Django REST Framework Tutorial – Filters and Filtering
Django REST Framework Tutorial – Functional Endpoints and API Nesting
Django REST Framework Tutorial – Selective Fields and Related Objects
http://dokelung-blog.logdown.com/archives


https://sunscrapers.com/blog/ultimate-tutorial-django-rest-framework-part-1/

JWT Authentication in Django
https://code.tutsplus.com/tutorials/how-to-authenticate-with-jwt-in-django--cms-30460

Python Django JWT — djangorestframework-jwt Example
https://www.techiediaries.com/django-rest-framework-jwt-tutorial/

Permissions
https://www.django-rest-framework.org/api-guide/permissions/#isauthenticated

Using the Django authentication system
https://docs.djangoproject.com/en/2.2/topics/auth/default/#permission-caching


Django筆記
http://dokelung-blog.logdown.com/posts/220833-django-notes-7-forms
https://wsvincent.com/django-rest-framework-authentication-tutorial/
https://data-flair.training/blogs/django-crud-example/

REST framework JWT Auth
https://jpadilla.github.io/django-rest-framework-jwt/

Q & A:
https://stackoverflow.com/questions/9081123/is-django-for-the-frontend-or-backend

Neither.

Django is a framework, not a language. Python is the language in which Django is written.

Django is a collection of Python libs allowing you to quickly and efficiently create a quality Web application, and is suitable for both frontend and backend.

However, Django is pretty famous for its "Django admin", an auto generated backend that allows you to manage your website in a blink for a lot of simple use cases without having to code much.

More precisely, for the front end, Django helps you with data selection, formatting, and display. It features URL management, a templating language, authentication mechanisms, cache hooks, and various navigation tools such as paginators.

For the backend, Django comes with an ORM that lets you manipulate your data source with ease, forms (an HTML independent implementation) to process user input and validate data and signals, and an implementation of the observer pattern. Plus a tons of use-case specific nifty little tools.

For the rest of the backend work Django doesn't help with, you just use regular Python. Business logic is a pretty broad term.

You probably want to know as well that Django comes with the concept of apps, a self contained pluggable Django library that solves a problem. The Django community is huge, and so there are numerous apps that do specific business logic that vanilla Django doesn't.

