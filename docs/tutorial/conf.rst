#############################
Configuring the documentation
#############################


Before building your documentation, you need to make some minor manual changes to the ``conf.py``
file that is automatically created by ``sphinx-quickstart``.


*****
Theme
*****

At the top of ``conf.py`` ensure that ``sys`` is imported as well as ``os``.

Find the section::

    # -- Options for HTML output ----------------------------------------------
    html_theme = 'alabaster'

*Alabaster* is a plain and perfectly functional theme, but both on the `Read the Docs
<readthedocs.org>`_ website and when building locally, you will want your documentation to use the
``sphinx_rtd_theme``.

In place of the line setting the ``html_theme``, add::

    # on_rtd is whether we are on readthedocs.org
    on_rtd = os.environ.get('READTHEDOCS', None) == 'True'

    if not on_rtd:  # only import and set the theme if we're building docs locally
        try:
            import sphinx_rtd_theme
            html_theme = 'sphinx_rtd_theme'
            html_theme_path = [sphinx_rtd_theme.get_html_theme_path()]
        except:
            html_theme = 'default'

When building locally, this will use the ``sphinx_rtd_theme`` if it's available, and if not will
use the default theme. It will always use ``sphinx_rtd_theme`` on the Read the Docs.

``sphinx_rtd_theme`` *should* be available, so add it to your application's requirements.


.. _version_detection:

***************************
Automatic version detection
***************************

When we first used ``sphinx-quickstart``, we provided version numbers. It's more convenient to
extract these automatically from the software itself.

You'll find lines in ``conf.py`` that set the ``version`` and ``release``.  Replace these with::

	try:
	    application_name  # substitute the actual application name here
	except ImportError:
	    version = release = "undefined"
	else:
	    version = application_name.__version__   # substitute the actual application name here
	    # The full version, including alpha/beta/rc tags.
	    release = application_name.__version__   # substitute the actual application name here

This tries to import the application, and extract the version information (obviously, this requires
your application to provide this information in the first place).

If it can't import the application, it'll just use a value ``undefined``, which is fine for
local building.
