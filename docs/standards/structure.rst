#########
Structure
#########

All Divio/Aldryn documentation should share as far as possible a common overall structure, with an
``index.rst`` file at the root of each directory.

A typical project might contain::

    docs/
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

``index.rst``: the root page of the documentation

This should contain a brief description of the application, and links to its GitHub repository
and key related sites (such as django CMS or Aldryn).

It will typically share some of the same content as the README.


************
Introduction
************

``introduction/``: step-by-step, beginning-to-end tutorials to get users up and running

These tutorials must lead the user all the way to an end-point, in such a way that even if
they barely understand what is happening, simply by following the steps they will be left
with a successful, working result.

The point of the Introduction is **not** to explain, but to lead the user through some simple
steps.


Installation
============

``introduction/installation.rst``

The Installation section needs to be reasonably comprehensive.

Example: `Aldryn Jobs installation
<https://aldryn-jobs.readthedocs.io/en/latest/introduction/installation.html>`_.

The Installation section is *required*.


Basic usage
===========

``introduction/basic_usage.rst``

This section describes some minimal steps required actually to do something with the software, the
steps you'd expect the site administrator to do to set it up within the Django admin, but **not**
the ordinary content editor.

Example: `Aldryn Jobs basic usage
<https://aldryn-jobs.readthedocs.io/en/latest/introduction/basic_usage.html>`_.

Unless these steps are unnecessary, or are completely obvious, this section is *required*.


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

Example: `Aldryn Jobs reference
<https://aldryn-jobs.readthedocs.io/en/latest/reference/index.html>`_.

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

.. note::

   The ``introduction/basic_usage.rst`` section should have left the system in a state to make this
   possible. See for example the `Aldryn Jobs documentation <https://aldryn-jobs.readthedocs.io>`_,
   in which the `Using Aldryn Jobs
   <https://aldryn-jobs.readthedocs.io/en/latest/user/index.html#using-aldryn-jobs>`_ section
   assumes that the Introduction has configured the basics in the admin.

The user-facing documentation needs to be written for a *user*, not simply for a developer or
technical expert who happens to be using it. It should describe the *interface* the user will see,
the *actions* they can take, and the *effects* that will follow.

It should not describe what happens behind the scenes, and it should not rely on technical terms in
its explanations (explanations in general belong in the *Key topics* section).

As far as possible, the ``user`` documentation needs to take the user through simple steps of
operation so that they can see how to achieve basic things with it.

