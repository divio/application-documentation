######
Markup
######

********
Sections
********

Use two carriage returns before a new section. Headings should be marked up as follows::

    ##########
    Page title
    ##########

    *******
    heading
    *******

    sub-heading
    ===========

    sub-sub-heading
    ---------------

    sub-sub-sub-heading
    ^^^^^^^^^^^^^^^^^^^

    sub-sub-sub-sub-heading
    """""""""""""""""""""""


*************
Inline markup
*************

* use backticks - `````` - for:
    * literals::

        The ``cms.models.pagemodel`` contains several important methods.

    * filenames::

        Before you start, edit ``settings.py``.

    * names of fields and other specific items in the Admin interface::

        Edit the ``Redirect`` field.

* use emphasis - ``*Home*`` - around:
    * the names of available options in or parts of the Admin::

        To hide and show the *Toolbar*, use the...

    * the names of important modes or states::

        ... in order to switch to *Edit mode*.

    * values in or of fields::

        Enter *Home* in the field.

* use strong emphasis - ``**`` - around:
    * buttons that perform an action::

        Hit **Save as draft**.


Rules for using technical words
===============================

There should be one consistent way of rendering any technical word, depending on its context.
Please follow these rules:

* in general use, simply use the word as if it were any ordinary word, with no capitalisation or
  highlighting: "Your placeholder can now be used."
* at the start of sentences or titles, capitalise in the usual way: "Placeholder management guide"
* when introducing the term for the the first time, or for the first time in a document, you may
  highlight it to draw attention to it: "**Placeholders** are special model fields".
* when the word refers specifically to an object in the code, highlight it as a literal:
  "``Placeholder`` methods can be overwritten as required" - when appropriate, link the term to
  further reference documentation as well as simply highlighting it.


References
==========

Create (``.. _testing:``) and use (``:ref:`testing```) internal cross-references liberally.

Use absolute links to other documentation pages - ``:doc:`/how_to/toolbar``` -
rather than relative links - ``:doc:`/../toolbar```. This makes it easier to
run search-and-replaces when items are moved in the structure.