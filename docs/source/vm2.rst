.. _vm2:

***********************
Lab VM Notes Post Clone
***********************

Setting up Django First Time
============================

ssh amelia.becker@10.11.12.14

:: 

    sudo yum install -y django



.. warning:: this may be sketch

.. note:: pip for user is from python3, pip root is python2.7. use pip ...... --user

Setup Django:
:: 

    $ python ./manage.py migrate
    $ python ./manage.py createsuperuser

.. note:: using the tag "python" runs python 3.6

Make a "superuser" account

.. _Managing the server:
Managing the Server
===================

#. navigate to /checkouts/readthedocs.org
#. Manage the server:
	::

 	   python ./manage.py runserver 0.0.0.0:8000

local settings
==============
[amelia.becker@rtd-v2 readthedocs.org]$ vim readthedocs/settings/local_settings.py

PRODUCTION_DOMAINPRODUCTION_DOMAIN = '10.11.12.14:8000'
SLUMBER_API_HOST = 'http://10.11.12.14:8000'

ALLOW_ADMIN = True
DEBUG = True

https://codefarm.me/2016/05/12/how-to-install-read-the-docs-on-centos/

added: "on_delete=models.DO_NOTHING," for Django 2

