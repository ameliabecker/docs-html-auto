.. _today:

***************
Today's To Do's
***************

Gitlab
======
* Gitlab lab account
* Gitlab sync with rtd lab vm

    - on rtd server setup with "git"
    - get "git" to use the lab gitlab account
    - test pushes and pulls
      
Gitlab notes
------------
double check account on narm-gitlab (amelia.becker@10.11.12.15)
gen public key for rtd-v2
add public key to gitlab profile
clone into ``checkouts`` folder (using ssh): ``git clone git@10.11.12.15:readthedocs/readthedocstest.git``

changed readme and pushed the changes--in "readthedocstest" folder

* ``git checkout master`` gets latest version/checks if its up to date
* ``git status`` status of changes
* ``git add .`` adds all changes to commit or ``git add <FILE OR FOLDER``
* ``git commit -m "<COMMENT MESSAGE HERE>"``
* ``git push origin master`` to send the changed code


Django Server
=============
* see `Managing the server`_
* add projects
* ask Andrew--next week?
  
  * `Reinstall django on VM`_  ``pip install Django==2.1.7`` 1.11.18
  * Try a `django project`_ (on my computer)
  * Try the RTD (django) server from my computer

.. _Managing the server: vm2.html
.. _Reinstall django on VM: https://docs.djangoproject.com/en/2.1/intro/install/
.. _django project: https://docs.djangoproject.com/en/2.1/intro/tutorial01/

Django "mysite" proj notes
--------------------------
* /mysite/settings.py: 

    - debug settings
    - root url config
    - password validations
* apps in folder with manage.py (then many projects can call the same app)
* when using databases:

    - initially uses SQLite, maybe use a "more scalable database" like PostgreSQL
    - if so, look at `DATABASES doc`_
    - view by using "sqlite3" and ".schema"
* in /settings.py: By default, INSTALLED_APPS contains the following apps, all of which come with Django:

    - django.contrib.admin – The admin site. You’ll use it shortly.
    - django.contrib.auth – An authentication system.
    - django.contrib.contenttypes – A framework for content types.
    - django.contrib.sessions – A session framework.
    - django.contrib.messages – A messaging framework.
    - django.contrib.staticfiles – A framework for managing static files.
* making model changes

    - Change your models (in models.py).
    - Run python manage.py makemigrations to create migrations for those changes
    - Run python manage.py migrate to apply those changes to the database.
* admin.py changes the settings on the admin site (eg admin.py. admin.site.register(Question) adds stuff)
*  ``python manage.py shell`` using the shell
*  ``python manage.py runserver`` running the server
*  Creating tests:

    -  a separate TestClass for each model or view
    -  class QuestionDetailViewTests(TestCase):
   		def test_future_question(self):
    	self.assertEqual(response.status_code, 404)

*  	`testing in Django`_ 
*  	`testing tools`_ 
*  	Django source files ['/usr/local/lib/python3.7/site-packages/django']



.. _testing tools: http://https://docs.djangoproject.com/en/1.11/topics/testing/tools/#django.test.Client

.. _testing in Django: http://https://docs.djangoproject.com/en/1.11/topics/testing/


.. _DATABASES doc: https://docs.djangoproject.com/en/1.11/ref/settings/#std:setting-DATABASES

Lab "readthedocs" instance customization
========================================

Use the local instance to test mods
-----------------------------------
* how does django work?
* Why do we need the "server" setup like this? auth for any viewers?
* 