Django jQuery Plus
==================

Requirements
------------

`django-appconf`

`Django <https://www.djangoproject.com/>`_ 1.3 or later

Installation
------------

::

    $ pip install django-jquery-plus


Setup
-----

Just add ``'django.contrib.staticfiles'`` and ``'jquery'`` to INSTALLED_APPS in
your settings.py::

    INSTALLED_APPS = (
        # ...

        'django.contrib.staticfiles',
        'jquery',

        # ...
    )

Refer to Django `static files <https://docs.djangoproject.com/en/dev/howto/static-files/>`_
documentation to configure and deploy static files.


Usage
-----

You can refer to jquery in your template with::
	{% load jquery %}
	{% jquery_js %}
	{% jquery_js 1.7.2 %}

Admin template customization::

    {% extends "admin/base_site.html" %}

    {% block extrahead %}
		{% load jquery %}
		{% jquery_js %}
		{% jquery_js 1.7.2 %}
    {% endblock %}


Custom widget::
	NOT IMPLEMENTED YET

	ABSTRACT:
    class MyWidget(forms.TextInput):
        class Media:
            js = ('js/jquery.js',)

        def render(self, name, value, attrs=None):
            html = super(MyWidget, self).render(name, value, attrs=attrs)
            # ...
            return html
