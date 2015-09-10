###############
Spelling checks
###############

We want to be able to have automated spelling checking for the documentation, that can developers
can use to help when writing it, and also that runs on Travis, so that we can see at a glance
whether a pull request contain documentation changes is free of spelling errors.


====================
Sphinx configuration
====================

Add the following to the end of the ``docs/conf.py`` file::

    # -- Options for spelling checks ----------------------------------------------

    # Spelling check needs an additional module that is not installed by default.
    # Add it only if spelling check is requested so docs can be generated without it.
    if 'spelling' in sys.argv:
        extensions.append("sphinxcontrib.spelling")

    # Spelling language.
    spelling_lang = 'en_GB'

    # Location of word list.
    spelling_word_list_filename = 'spelling_wordlist'

    spelling_ignore_pypi_package_names = True


========================
Add ``Makefile`` command
========================

In the ``Makefile``, add::

    @echo "  spelling  to check for typos in documentation"

to the ``help`` section, and::

    spelling:
    	$(SPHINXBUILD) -b spelling $(ALLSPHINXOPTS) _build/spelling
    	@echo
    	@echo "Check finished. Wrong words can be found in " \
    		"_build/spelling/output.txt."

to the end of the same file (check of course that similar lines have not already been added).

=====================================
Installation of spelling dependencies
=====================================

Add::

    sphinx
    sphinxcontrib-spelling
    pyenchant

to the project's ``test_requirements.txt`` file (or whichever file is responsible for installing
dependencies required for testing).

Install them::

    pip install -r test_requirements.txt  # or whatever the file is called

You will need to install ``enchant`` too, if it's not already installed. The easy way to check is
to run ``make spelling`` from the ``docs`` directory. If it runs successfully, you don't need to do
anything, but if not you will have to install ``enchant`` for your system. For example, on OS X::

    brew install enchant

or Debian Linux::

    apt-get install enchant


====================
Set up the word-list
====================

Numerous words that you are likely to need to use are known to be flagged as errors against various
default dictionaries, including Travis's. To avoid having to identify and add all these for each
project, copy the `spelling_wordlist
<https://github.com/divio/application-documentation-starter-files/tree/master/starter-docs/spelling_wordlist>`_ file from the `documentation starter files
<https://github.com/divio/application-documentation-starter-files>`_ to the ``docs`` directory.

Run the spelling checks
=======================

Now you should be able to run ``make spelling`` from the ``docs`` directory. With luck, it will
exit without errors (``build succeeded.``), but if not, it will create a file ``output.txt``
listing the words it doesn't recognise, and where they occur.

Words that are not in the built-in dictionary can be added to ``docs/spelling_wordlist``. **If**
you are certain that a word is incorrectly flagged as misspelt, add it to the ``spelling_wordlist``
document, in alphabetical order. **Please do not add new words unless you are sure they should be
in there.**

If you find technical terms are being flagged, please check that you have capitalised them
correctly - ``javascript`` and ``css`` are **incorrect** spellings for example. Commands and
special names (of classes, modules, etc) in double backticks - `````` - will not caught by the
spelling checker.


================================
Set up spelling checks on Travis
================================

Just like your local environment, Travis will also need to have ``enchant`` installed. Add::

    addons:
      apt:
        packages:
        - enchant

to your project's ``travis.yml`` file.


=================================================================
Add the documentation build and spelling checks to the test suite
=================================================================

.. todo:: Add a documentation test class to the test suite. See https://github.com/evildmp/django-cms/blob/316328a38941e408c2af279cbcd7260fc2ab2746/cms/tests/test_docs.py for django CMS's example.
