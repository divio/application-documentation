#######################
Documentation structure
#######################

All Divio/Aldryn documentation should share as far as possible a common overall structure, with an
``index.rst`` file at the root of each directory.

A typical project night look like::

	index.rst
	introduction/
		index.rst
		installation.rst
		basic_usage.rst
	reference/
		index.rst
	user/
		index.rst

****
Home
****

(``index.rst``): the root page of the documentation

This should contain a brief description of the application, and links to its GitHub repository
and key related sites (such as django CMS or Aldryn)

************
Introduction
************

``introduction/``: step-by-step, beginning-to-end tutorials to get users up and running

  These tutorials must lead the user all the way to an end-point, in such a way that even if
  they barely understand what is happening, simply by following the steps they will be left
  with a successful, working result.

  The point of the Introduction is **not** to explain, but to lead the user through some simple
  steps.

  The first section in the Introduction should be:

  * **Installation** (``introduction/installation.rst``)

  If appropriate, you should also provide a:

  * **Basic usage** (``introduction/basic_usage.rst``)

  that describes some minimal steps required actually to do something with the software.

  The Introduction is *required*.


*************
How-to guides
*************

``how_to/``: step-by-step guides covering more advanced development

If your documentation has some more free-form guides, that cover key steps in some process but
not all of them, they should go into the how-to section.

The how-to section is optional.


**********
Key topics
**********

``topics/``: discussions and explanations of key parts of the system

The topics section is optional.


*********
Reference
*********

``reference/``: technical reference for APIs, key models and so on

The topics section is optional, but recommended if APIs and models are complex enough to have
several options that need to spelled out.


***********************
Development & community
***********************

``contributing/``

Not usually required; generally, a note in the README and in the main ``index.rst`` will
suffice.


***********************************
Release notes & upgrade information
***********************************

``upgrade/``

Strongly recommended.


***************************
Using <name of application>
***************************

``user/``: guides for *using* rather than setting up or developing for the software

The ``user`` documentation should as nearly as possible be a stand-alone section, so that an
end-user who is not a developer finds it useful.

The ``introduction/basic_usage.rst`` section should have left the system in a state to make
this possible. See for example the `Aldryn Jobs documentation
<http://aldryn-jobs.readthedocs.org>`_, in which the `Using Aldryn Jobs
<http://aldryn-jobs.readthedocs.org/en/latest/user/index.html#using-aldryn-jobs>`_ section
assumes that the Introduction has configured the basics in the admin.
