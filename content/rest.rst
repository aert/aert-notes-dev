reST
****

.. module:: reST
   :synopsis: Documentation of reStructuredText and Sphinx
.. moduleauthor:: Christoph Reller <reller@isi.ee.ethz.ch>

.. highlight:: rest

A simple markup language for plain text files.

Structural elements
===================

Sectioning
----------
.. sidebar:: Emacs
   
   ``C-c C-a`` or ``C-=``
      Format the text above as a title or move it down in the decoration
      hierarchy.

   ``C-- C-c C-a``
      Move the title one level up in the hierarchy.

   ``C-c C-h``
      Display the title decoration hierarchy.

Titles are under- (and over-)lined (decorated) by ``=*-^"~`` as below.  The
exact order of the decoration is not important, the one below is the Python
convention. ::

  ####
  Part
  ####

  *******
  Chapter
  *******

  Section
  =======

  Subsection
  ----------

  Subsubsection
  ^^^^^^^^^^^^^

  Paragraph
  """""""""

Normal paragraphs are separated by a blank line.

Transitions
-----------
Any repetition of 4 or more punctuation characters with preceding and trailing
blank line is a transition, and looks like this:

----


Inline markup
=============

========================== ======================
``*emphasize*``            *emphasize*
``**emphasize strongly**`` **emphasize strongly**
````code````               ``code``
```don't know```           `don't know`    
========================== ======================

.. sidebar:: Code for example

   ::

      Asterisk \*, back-quote \`
      and a **mark**\ up.

The following example illustrates special cases:

Asterisk \*, back-quote \`
and a **mark**\ up.

Lists
=====

Bullet list
-----------
.. sidebar:: Code for examples

   ::

      - First item with some lengthy
        text wrapping hopefully
        across several lines.
      - Second item

   ::

      2. We start with point number 2
      #. Automatically numbered item.
      
      a) Point a
      b) Point b
      #) Automatic point c.

- First item with some lengthy
  text wrapping hopefully
  across several lines.
- Second item

Enumerated list
---------------
2. We start with point number 2
#. Automatically numbered item.

a) Point a
b) Point b
#) Automatic point c.

.. note:: Automatic alphabetic numbering works wrongly in Sphinx, but does work
   with plain ``rst2html``.

Definition list
---------------
.. sidebar:: Code for example

   ::

      what
        Definition of "what". We add a few
        words to show the line wrapping.
      how
        Definition of "how".

what
  Definition of "what". We add a few
  words to show the line wrapping.
how
  Definition of "how".

.

Field list
----------
.. sidebar:: Code for examples

   ::

      :Name: Christoph Reller
      :Long: Here we insert more
         text to show the effect of
         many lines (in Pygments). 
      :Remark:
        Start on the next line.

   ::

      -v           An option
      -o file      Same with value
      --delta      A long option
      --delta=len  Same with value

:Name: Christoph Reller
:Long: Here we insert more
   text to show the effect of
   many lines (in Pygments). 
:Remark:
  Start on the next line.

Options list
------------
E.g. for listing command line options.

-v           An option
-o file      Same with value
--delta      A long option
--delta=len  Same with value

Blocks
======

Literal Blocks
--------------
.. sidebar:: Code for example

   ::

      Block one::
      
         **No** interpretation of
         |special| characters.
      
      Another block! ::
      
         In the text body,
            indentation is
         preserved

A block which is not interpreted at all is preceded by a ``::`` and a blank
line. The block must be intended.  If no white space is preceding the
``::`` then it is displayed as ":".

Block one::

   **No** interpretation of
   |special| characters.

Another block! ::

   In the text body,
      indentation is
   preserved

Line blocks
-----------
.. sidebar:: Code for example

   ::

      | Line block
      | New line and we are still on
        the same line
      |   Yet a new line

In a line block every line is preceded with ``|`` and at least one space.

| Line block
| New line and we are still on
  the same line
|   Yet a new line

Block quotes
------------
.. sidebar:: Code for example

   ::

      blah blah blah
      
        blah blah blah blah blah
        blah blah blah blah blah
        blah blah blah blah blah
      
      blah blah blah.

The different indentation levels of paragraphs are preserved.

blah blah blah

  blah blah blah blah blah
  blah blah blah blah blah
  blah blah blah blah blah

blah blah blah.


Tables
======

Simple tables
-------------
.. sidebar:: Code for the examples

   ::

      ==  ==
      aA  bB
      cC  dD
      ==  ==

      =====  ======
      Vokal  Umlaut
      =====  ======
      aA     äÄ
      oO     öÖ
      =====  ======

      =====  =====  ====== 
      Inputs        Output 
      ------------  ------ 
        A      B    A or B 
      =====  =====  ====== 
      False         False 
      ------------  ------
      True   False  True 
      False  True   True 
      True          True
      ============  ======

      ===========  ================
      1. Hallo     | blah blah blah
                     blah blah blah
                     blah 
                   | blah blah
      2. Here      We can wrap the
                   text in source
      32. There    **aha**
      ===========  ================

Tables are preceded and ended with a sequence of "``=``" to indicate the
columns, e.g:

==  ==
aA  bB
cC  dD
==  ==

Headers are indicated by another sequence of "``=``", e.g:

=====  ======
Vokal  Umlaut
=====  ======
aA     äÄ
oO     öÖ
=====  ======

Column spans are followed by a sequence of "``-``" (except for the last header
or last row of the table where we must have "``=``"), e.g:

=====  =====  ====== 
Inputs        Output 
------------  ------ 
  A      B    A or B 
=====  =====  ====== 
False         False 
------------  ------
True   False  True 
False  True   True 
True          True
============  ======

Table cells are treated like a small document on their own up to line breaks,
e.g:

===========  ================
1. Hallo     | blah blah blah
               blah blah blah
               blah 
             | blah blah
2. Here      We can wrap the
             text in source
32. There    **aha**
===========  ================

Grid tables
-----------
.. sidebar:: Code for example

   ::

      +--------+--------+-----------+
      | Header | Header with 2 cols |
      +========+========+===========+
      | A      | Lists: | **C**     |
      +--------+  - aha +-----------+
      | B::    |  - yes | | a block |
      |        |        |   of text |
      |  *hey* |  #. hi | | a break |
      +--------+--------+-----------+

Grid tables have a more difficult syntax but can express more complex tables.

+--------+--------+-----------+
| Header | Header with 2 cols |
+========+========+===========+
| A      | Lists: | **C**     |
+--------+  - aha +-----------+
| B::    |  - yes | | a block |
|        |        |   of text |
|  *hey* |  #. hi | | a break |
+--------+--------+-----------+

Explicit Markup
===============
They all begin with two periods and a white space.

Footnotes
---------
.. sidebar:: Code for example

   ::

      In the text [2]_.
      
      .. [2] In the footnote.
      
      First automatic [#]_.
      Another automatic [#]_.
      
      .. [#] The first automatic.
      .. [#] The other automatic.
      
      A labeled automatic [#one]_.
      Another of these [#two]_.
      
      .. [#one] footnote.
      .. [#two] labeled footnotes.
      
      An autosymbol [*]_.
      More autosymbol [*]_.
      
      .. rubric:: Footnotes
      .. [*] footnote.
      .. [*] footnotes.

``.. [2]`` precedes the definition of the footnote 2.  It is referenced by
``[2]_``. E.g.

In the text [2]_.

.. [2] In the footnote.

First automatic [#]_.
Another automatic [#]_.

.. [#] The first automatic.
.. [#] The other automatic.

A labeled automatic [#one]_.
Another of these [#two]_.

.. [#one] footnote.
.. [#two] labeled footnotes.

An autosymbol [*]_.
More autosymbol [*]_.

.. rubric:: Footnotes
.. [*] footnote.
.. [*] footnotes.

There is no labeled version of these autosymbol footnotes.

Citations
---------
.. sidebar:: Code for example

   ::

      We cite [REL09]_ or REL09_
      or even rel09_.
      
      .. [REL09] Citation

``.. [REL2009]`` is followed by the definition of the citation ``REL2009``.  It
is referenced as ``[REL2009]_`` or ``REL2009_``.  Citation labels can contain
underlines, hyphens and fullstops.  Case is not significant.  In Sphinx,
definition and reference can reside in different files.

We cite [REL09]_ or REL09_
or even rel09_.

.. [REL09] Citation

Hypertext links
---------------

External
~~~~~~~~
There exist two version for doing this.  Either in a citation style or in an
inline style.

.. sidebar:: Code for examples

   ::

      A link_ in citation style.
      
      .. _link: http://www.google.ch
      
      In-line versions are
      `link <http://www.google.ch>`__
      or `<http://www.google.ch>`__
      or (in Sphinx) http://www.google.ch.


**Citation style**:

A link_ in citation style.

.. _link: http://www.google.ch

In printed documents the link will be listed similar as a citation, as opposed
to HTML documents.

**In-line style**:

In-line versions are `link <http://www.google.ch>`__ or
`<http://www.google.ch>`__ or (in Sphinx) http://www.google.ch.

.. note:: The syntax ```link <URI>`_`` produces both a link and a link name as
   if you would have written ``.. _link: URI`` .  This means that you can
   re-reference the same target later in the document as ```link`_``.

   To create an **anonymous** link (a link without specifying a name) use double
   underscores ```link <URI>`__``.  This form is necessary if you want many
   links to have the same name, and it is the preferred form for one-time-used
   links and for links of the form ```<URI>`__``.

.. _internal:

Internal
~~~~~~~~
To define a label for any text location, precede it with::

   .. _‹label›:

plus a blank line.  There are two ways of referencing a label.

**The Sphinx way** (preferred)

To reference ``‹label›`` defined in *any* document of the project use::

   :ref:`‹displayed text› <‹label›>`

If the ``‹label›`` definition is followed by a section title then ``‹displayed
text›`` can be omitted and will be replaced by the title.

E.g. this section is preceded with ``.. _internal:``, so we have:

================================== ==============================
``:ref:`internal```                :ref:`internal`
``:ref:`This section <internal>``` :ref:`This section <internal>`
================================== ==============================

This is the preferred way because it allows linking across files.
E.g. :ref:``subversion repository URL <svnRepoURL>`` links to my document on
subversion.

In Sphinx it is possible to reference a document as follows

================ ===========
``:doc:`reST```  :doc:`rest`
================ ===========

**The reST way**

Given a definition of ``‹label›`` has been made in the document, the following
will be substituted by ``‹label›`` and link to it::

   `‹label›`_

Section titles, footnotes, and citations automatically are link targets.
```Internal`_`` produces `Internal`_.

Directives
==========

Directives are a general-purpose extension mechanism.  The general syntax is
similar to `Explicit Markup`_::

   .. ‹name›:: ‹argument 1›
               ‹argument 2›
      :‹option 1›: ‹value›

      ‹body›

reST directives
---------------

.. _reST-tableOfContents:

Create a **table of contents** containing (sub)titles ranging from level 1 to
level ‹number›::

   .. contents:: `Table of contents`
      :depth: ‹number›

----

**Include an image**::

   .. image:: ‹file name›

----

General **replacements**::

   .. |‹something›| ‹directive›:: here we define what ‹something› is

   here |‹something›| will be replaced by its definition.

Possible ``‹directive›``\ s are ``replace`` or ``image``.

----

**Including** a reST file::

   .. include:: ‹file name›

.. note:: Don't use the same file name extension as your source files.
   Otherwise Sphinx will mistake this file as one of your regular source files.

----

**Raw code** can be written as::

   .. raw:: ‹writer›

      ‹code›

where ``‹writer›`` is ``html`` or ``latex`` (or some other output writer) and
``‹code›`` is the actual code to be inserted.

Sphinx directives
-----------------

Create a **table of contents** across files::

   .. toctree::
      :maxdepth: ‹depth›
      :glob:

      ‹file 1 without file name extension›
      ‹file 2 without file name extension›

A ``glob`` option enables to use wildcards in the filenames, e.g. ``/comp/*``
means all files under the directory ``comp``.

.. note:: Don't try to reference the file which contains the ``toctree``
   directive, otherwise a recursive loop occurs. Use the normal
   `:ref:` reST table of contents <reST-tableOfContents>` directive instead.

.. note:: The depth can be further restricted per file by inserting the
   following `Field list`_ type element in the very first line of the file::

      :tocdepth: ‹depth› 

----

.. index::
   single: reST, index

Entries in the **index** are created automatically from all information units
(like functions, classes or attributes).  Explicit manual entries are made as::

   .. index:: ‹keyword 1›, ‹keyword 2›, ...

   .. index::
      single: ‹keyword›; ‹sub-keyword›

   .. index::
      pair: ‹keyword 1st part›; ‹keyword 2nd part›

The first two versions create single (sub-)entries, while the last version
creates two entries "‹keyword 1st part›; ‹keyword 2nd part›" and "‹keyword 2nd
part›; ‹keyword 1st part›".

----

A **glossary** is created as follows::

   .. glossary::

      ‹reST definition list›

----

Set `Pygment <http://pygments.org>`__ to ‹language› for **code highlighting** in
`Literal Blocks`_ globally for the whole file::

   .. highlight:: ‹language›
      :linenothreshold: ‹number›

The additional ``linenothreshold`` option switches on line numbering for blocks
of size beyond ‹number› lines.

Specify the highlighting for a single literal block::

   .. code-block:: ‹language›
      :linenos:

      ‹body›

The ``linenos`` option switches on line numbering.

----

**Including a file** as a literal block::

   .. literalinclude:: ‹filename›
      :language: ‹language›
      :linenos:

The options ``language`` and ``linenos`` set the highlighting to ``‹language›``
and enables line numbers respectively.

----

Create a **sidebar** with ‹Title› and ‹body› which is treated like a document on
its own::

   .. sidebar:: ‹Title›

      ‹body›

----

Create a boxed **note** with ‹text›::

   .. note:: ‹text›

.. note:: This is a note.

----

Create a boxed **warning** with ‹text›::

   .. warning:: ‹text›

.. warning:: This is a warning.

----

Create a **see also** box::

   .. seealso::

      ‹reST definition list›

.. seealso::

   `Apples <http://en.wikipedia.org/wiki/Apple>`_
      A kind of `fruit <http://en.wikipedia.org/wiki/Fruit>`__.

----

Create a **title not appearing in the table of contents** by::

   .. rubric:: ‹Title›

----

Create a **centered, boldface** text block with::

   .. centered:: ‹text block›

----

There are very powerful directives in ``Sphinx`` for **documenting source code**.

Comments
--------

.. sidebar:: Code for example

   ::

      .. Comment
         Even more comment
      
      Not comment anymore

Everything starting like a directive with two periods and a space but is
followed by normal text is a comment.  Mark the indentation in the example:

.. Comment
   Even more comment

Not comment anymore


`Sphinx <http://sphinx.pocoo.org/>`__
=====================================

Project
-------

To start a Sphinx project use the interactive ``sphinx-quickstart`` command.
This will ask you all the necessary questions.You can choose to build with a
Makefile.

Customization is done in the file ``conf.py`` and the Makefile.

.. Math
.. ----
.. 
.. There is a `mathematical typesetting Sphinx extension
.. <file:///usr/share/doc/python-sphinx/html/ext/math.html?highlight=options#module-sphinx.ext.mathbase>`__
.. called ``sphinx.ext.pngmath`` based on LaTeX.
.. 
.. To enable the extension, the following line has to appear in ``conf.py``:
.. 
.. .. code-block:: python
.. 
..    extensions = ['sphinx.ext.pngmath']
.. 
.. .. note:: The ``sphinx.ext.pngmath`` extension needs ``dvipng``.
.. 
.. You then can type standard LaTeX math expressions, either inline::
.. 
..    :math:`‹LaTeX math expression›`
.. 
.. or in display mode::
.. 
..    .. math::
.. 
..       ‹LaTeX math expressions›
.. 
.. The second version is also available for a one line expression::
.. 
..    .. math:: ‹1 Line LaTeX math expression›
.. 
.. .. sidebar:: Code for example
.. 
..    ::
.. 
..       Pythagoras :math:`a^2+b^2=c^2`
..       
..       .. math:: \sum_{n=0}^N x_n = y
.. 
.. E.g:
.. 
.. Pythagoras :math:`a^2+b^2=c^2`
.. 
.. .. math:: \sum_{n=0}^N x_n = y
.. 
.. Multiline Math
.. ~~~~~~~~~~~~~~
.. 
.. .. sidebar:: Code for example
.. 
..    ::
.. 
..       .. math::
..       
..          a+b = c
..       
..          b = x_n
..       
..          a &= y_n\\
..            &= c-b
.. 
.. **Sphinx Built-in Mechanism**
.. 
.. Several lines of math expressions can be entered by leaving a blank line between
.. them.  In addition there is something like an ``align`` environment syntax if
.. lines are not separated by a blank line.
.. 
.. .. math::
.. 
..    a+b = c
.. 
..    b = x_n
.. 
..    a &= y_n\\
..      &= c-b
.. 
.. .. sidebar:: Code for example
.. 
..    ::
.. 
..       .. math:: \[a = b\]
..          :nowrap:
.. 
..    or equivalently::
.. 
..       .. math::
..          :nowrap:
.. 
..          \[a = b\]
.. 
.. 
.. **Explicit LaTeX with amsmath mechanism**
.. 
.. If the option ``nowrap`` is specified then the full LaTeX code (including the
.. math-environment) has to be given.  We can assume that the ``amsmath`` package
.. is loaded.  This is not limited to math typesetting, any LaTeX construct can be
.. rendered in this way.
.. 
.. .. math:: \[a = b\]
..    :nowrap:
.. 
.. or equivalenty
.. 
.. .. math::
..    :nowrap:
.. 
..    \[a = b\]
.. 
.. 
.. Equation Numbers
.. ~~~~~~~~~~~~~~~~
.. 
.. Equations are labeled with the ``label`` option and referred to using::
.. 
..   :eq:`‹label›`
.. 
.. .. sidebar:: Code for example
.. 
..    ::
.. 
..       .. math:: a^2 + b^2 = c^2
..          :label: pythag
..       
..       See equation :eq:`pythag`.
.. 
.. E.g:
.. 
.. .. math:: a^2 + b^2 = c^2
..    :label: pythag
.. 
.. See equation :eq:`pythag`.
.. 
.. Graphs with `Graphviz <http://graphviz.org/>`__
.. -----------------------------------------------
.. 
.. There is a `graph drawing Sphinx extension
.. <http://sphinx.pocoo.org/ext/graphviz.html>`__ based on `Graphviz
.. <http://graphviz.org/>`__.
.. 
.. To enable the extension we have to add it to the ``extensions`` list in
.. ``conf.py``::
.. 
..   extensions = ['sphinx.est.graphviz']
.. 
.. On Ubuntu Linux the packages ``graphviz`` and ``libgraphviz4`` have to me
.. installed.  There is no need to install ``python-graphviz``.
.. 
.. Examples
.. ~~~~~~~~
.. 
.. .. sidebar:: Undirected graph
.. 
..    ::
.. 
..       .. graph:: foo
..       
..          "bar" -- "baz";
.. 
.. .. .. graph:: foo
.. 
.. ..   "bar" -- "baz";
.. 
.. .. sidebar:: Directed graph
.. 
..    ::
.. 
..       .. digraph:: foo
..       
..          "bar" -> "baz";
.. 
.. .. .. digraph:: foo
.. 
.. ..   "bar" -> "baz";
