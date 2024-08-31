Installation
============

Installing `django-sage-timezone` is like below:

Using `pip` with `virtualenv`
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

1. **Create a Virtual Environment**:

   .. code-block:: bash

      python -m venv .venv

2. **Activate the Virtual Environment**:

   - On Windows:

     .. code-block:: bash

        .venv\Scripts\activate

   - On macOS/Linux:

     .. code-block:: bash

        source .venv/bin/activate

3. **Install `django-sage-timezone`**:

   .. code-block:: bash

      pip install django-sage-timezone

Using `poetry`
~~~~~~~~~~~~~~

1. **Initialize Poetry** (if not already initialized):

   .. code-block:: bash

      poetry init

2. **Install `django-sage-timezone`**:

   .. code-block:: bash

      poetry add django-sage-timezone

3. **Apply Migrations**:

   After installation, make sure to run the following commands to create necessary database tables:

   .. code-block:: bash

      python manage.py makemigrations
      python manage.py migrate

Django Settings Configuration
-----------------------------

Installed Apps
~~~~~~~~~~~~~~

To use `django-sage-timezone`, add it to your `INSTALLED_APPS` in the Django settings:

.. code-block:: python

    INSTALLED_APPS = [
        ...
        "sage_timezone",
        "django.contrib.admin"
    ]
    MIDDLEWARE = [
      ...
      'django.contrib.sessions.middleware.SessionMiddleware',
      'sage_timezone.middleware.timezone.TimezoneMiddleware',
      ...
    ]

.. warning::

   The `sage_timezone` app must be placed after the
   `django.contrib.admin` in your `INSTALLED_APPS` setting.


.. warning::

   The `sage_timezone.middleware.timezone.TimezoneMiddleware` must be placed after the
   `django.contrib.sessions.middleware.SessionMiddleware` in your `MIDDLEWARE` setting.
   This order is crucial to ensure that the session data is available when the timezone is set.

**Note**: You can set a custom session name in your Django settings using the `TIME_ZONE_SESSION_NAME` setting. For example:

.. code-block:: python

   TIME_ZONE_SESSION_NAME = 'your_custom_session_name'
