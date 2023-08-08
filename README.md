# Django-Project-Guide


# NOTE: It is a good practice to create  a projects in a virtual environment.
      * Some most used commands
      * pip install virtualenv
      * pip virtualenv environment_name 
      * cd myenv (to use it)
      * Scripts/activate


1. django-admin startproject  project1         ----------> for starting project.
2. python manage.py runserver    ----------------------> to start server.
   
3. python manage.py startapp app1 ----------------------> to start/create new  app.


4. when we request for a page it first comes to the urls of urls of project then it will pass to the urls of apps.

    * syntax:
      * for project--------path('', include('app.urls'))
      * for app------- path('pagename', views.function_name , name="...")

6. HttpResponse is use to render texts 
7. render is used to render templates. ex: render(request , 'template name')


8. for setting static files directories   

    STATICFILES_DIRS = [
         os.path.join(BASE_DIR, 'static')
      ]

    same to do with template find template section and add path 


9. for rendering variable in html page  use {{a}}
   syntax:
    #context is a set of variables to be passed in page
     context={
           'a':45
      }

    render(request , 'home.html' , context)



10. python manage.py makemigrations ------------>which is responsible for creating new migrations based on the changes you have made to your models.
11. python manage.py migrate --------------->which is responsible for applying and unapplying migrations.
12. python manage.py createsuperuser   --------------> for making super user of project.  ----------------> a person who can modifed data of admin page.

13. We can inherit one template into another template in Django. by creating block. 

14. https://source.unsplash.com/random/1600x600/?river&1    unsplash api

15. To send the data to the backend we need to create a model in a models.py moudle 
       * there we need to create a class named (whatever our purpose is)
       * then register that class in admin.py module using (admin.site.register(classname))
       * then go to apps.py module and copy name of class and paste that name in settings.py module in installed app sections as "appname.apps.classname"
       * then make migrations using "python manage.py makemigrations"
       *  then run "python manage.py migrate "
       * now create instance of object of model class and pass data to that object.
       *  Note : {% csrf_token %} must be used in html page before sending data to the backend.
