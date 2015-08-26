#########################################
Setting your docs using sphinx-quickstart
#########################################

If your project doesn't already have a ``docs`` directory for Sphinx-based documentation, you'll
need to set it up.

Make sure that you have the lastest version of `Sphinx <http://sphinx-doc.org>`_::

    pip install --upgrade sphinx


*****************
sphinx-quickstart
*****************

Then in the root of your project, issue the command to initialise the documentation::

    sphinx-quickstart

You'll be asked a series of questions. You can accept most of the default values, but some will
need to be set explictly.

Documentation is always in ``docs``::

    > Root path for the documentation [.]: docs

Give the full name of the project, not its Python name (e.g. ``django CMS``, not ``django-cms``)::

    > Project name: Application documentation

The author is ``Divio AG`` if this is a Divio project::

    > Author name(s): Divio AG

Enter the project version numbers::

    > Project version: 0.1
    > Project release [0.1]:

.. todo:: add link to automatic version detection

We want to enable to-do notes::

    > todo: write "todo" entries that can be shown or hidden on build (y/n) [n]: y

Your docs directory now exists in ``docs``, complete with an ``index.rst`` file.
