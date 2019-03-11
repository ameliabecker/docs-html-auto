.. _rtdinstall:
***************************************
Understanding the Read The Docs Install
***************************************

`on RTD.org <https://docs.readthedocs.io/en/stable/custom_installs/customization.html>`_

Customization (Project)
=======================



eg:
add to ``conf.py`` in the project

adds the Secunetics logo

.. code-block:: python

	# Adds Secunetics Logo to the theme
	# in project "build/_static" folder

	html_logo = 'secunetics_logo.png'


Customization (site wide)
=========================

New Local Settings
------------------

find the ``readthedocs/settings`` directory and add file ``local_settings.py``
in ``amelia.becker/checkouts/readthedocs.org/readthedocs/settings``
``touch local_settings.py``

Adding your own title to pages
------------------------------

This requires 2 parts of setup. First, you need to add a custom ``TEMPLATE_DIRS`` setting that points at your template overrides. Then, in those template overrides you have to insert your logo where the normal RTD logo goes.

.. note:: This works for any setting you wish to change.

Example ``local_settings.py``::

    import os

    # Directory that the project lives in, aka ../..
    SITE_ROOT = '/'.join(os.path.dirname(__file__).split('/')[0:-2])

    TEMPLATE_DIRS = (
        "%s/var/custom_templates/" % SITE_ROOT, # Your custom template directory, before the RTD one to override it.
        '%s/readthedocs/templates/' % SITE_ROOT, # Default RTD template dir
    )

Example ``base.html`` in your template overrides::

    {% extends "/home/docs/checkouts/readthedocs.org/readthedocs/templates/base.html" %}
    {% load i18n %}

    {% block branding %}{% trans "My sweet site" %} {% endblock %}

Files
=====
/readthedocs.org

	/media: added secuneticslogo.jpg


Django
======

Django with AA?
---------------