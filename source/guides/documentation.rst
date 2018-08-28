Documentation Howto
###################

This file is targeted at people who want
to document the project but don't know what
guidelines to follow.

The development environment for writing Sphinx docs is covered
in the Development Environment file.

The Qub3d documentation is written in Sphinx and
uses the ReST file format.

..  _environment::

    Installing Sphinx
    =================

:ref:`guides/environment`

Writing a New File
==================

If creating a new documentation file, it must
include the following:

Introduction: Description about what the file is dedicated to.

Description: Long description about the subject;
it must be very clear, readable and free of
grammatical and spelling errors.

When you successfully create an ReST file, you need to put this file
in the Table of Contents section of :code:`source/index.rst` and put
the file in its respective category. When inserting a file in the index.rst
file, do not insert a file extension at the end of the filename.
Another rule when putting the file in the Table of
Contents section of the index.rst file, is that it must have
the path to the file to be only one line long. An example
is shown below as to what it should look like in the index.rst
file.

..  code-block:: rst

    guides/gettingstarted
    guides/documentation

Note that the :code:`source/` directory isn't seen here. That is because,
to Sphinx, everything inside the source/ directory is considered;
whereas, Sphinx is blind to everything else outside the source/
directory other than make-related files such as Makefile. The order
of files in the Table of Contents are sorted by importance. The top, being
the most important and bottom being the least important.

Format Standards
================

The guidelines for formatting documentation is as follows:

- Keep the markup simple and try not to make the most out of it.

- Maintain the format as shown below in Qub3d documentation.

ReST Format
-----------

If writing documentation in a ".rst" file,
you need to apply the following format:

**Title:**

..  code-block:: rst

    Title/Section
    #############

Capitalize the major words of the title/section
and the pounds "#" should always be the amount
of characters the title has. The title
must appear only once in the file, and it must
appear at the very top.

**Sub-sections:**

..  code-block:: rst

    Subsection
    ==========

    Sub-subsection
    --------------

    Sub-sub-subsection
    ^^^^^^^^^^^^^^^^^^

Description: The description's amount of columns can
be unlimited; however, one line *must* never consist
of two lines (If you have text wrapping enabled, you
can easily notice this situation).

Spacing: Titles/subsections/sub-subsections must be separated
from each other by one line.

Links: Links should only be shown as hyperlinks, *never* as
raw links. As an example, https://qub3d.org needs to be given
the name, "Qub3d." Instead of just leaving the link as it is,
do the following:

..  code-block:: rst

    `Qub3d <https://qub3d.org>`_

This shows "Qub3d" as a hyperlink for qub3d.org.

..  note::

    Links **must** have :code:`https://` instead of :code:`http://`. The only
    exception is that if the URL doesn't support ``HTTPS``.

Tables
^^^^^^

Use grid tables instead of list tables. Here's an example:

..  code-block:: rst

    +----------+----------+----------+
    | Column 1 | Column 2 | Column 3 |
    +----------+----------+----------+
    | `Foo()`  | `Bar()`  | fooBar() |
    +----------+----------+----------+

Rendered in HTML as this:

+----------+----------+----------+
| Column 1 | Column 2 | Column 3 |
+----------+----------+----------+
| `Foo()`  | `Bar()`  | fooBar() |
+----------+----------+----------+

For more information on ReST grid tables, `see the
documentation by Sphinx regarding them <http://www.sphinx-doc.org/en/master/usage/restructuredtext/basics.html#tables>`_.

Markdown Format
---------------

It is rare to write Markdown files other than the README
and the LICENSE. However, there can be a time where a Markdown file
gets written. If that's the case, then the following format
is required in order to write a .md file for the Qub3d project:

**Title:**

..  code-block:: guess

    # Title

Where the first letter is capitalized and there is only one
pound "#" before the title.

**Subsection:**

..  code-block:: guess

    ## Subsection About Stuff

Where the subsection always comes after the Title, and all major
words are capitalized. Subsections also must be consistent with
two pounds "##" before the subsection title.

**Further sub-* sections:**

Just add another pound "#" to the section's title. An example is
demonstrated below.

..  code-block:: guess

    ### Sub-subsection

Where there's an extra pound "#" in the title. And so forth.

Description: The amount of columns are limited to 60. If you're
starting a new subject within the same section, you must have a
space between the two subjects. When doing bullet/list points,
you must insert a plain text description between the title and
the list/bullet points.

Links: Never insert raw links. Instead, give these links a name.
For example, the file shouldn't display https://qub3d.org by itself.
Instead it should be given the name, "Qub3d." The incorrect method
is demonstrated in the following:

..  code-block:: guess

    https://qub3d.org

What should've been done is:

..  code-block:: guess

    [Qub3d](https://qub3d.org)

This displays "Qub3d" as a hyperlink to https://qub3d.org.

..  note::

    Links **must** have :code:`https://` instead of :code:`http://`. The only
    exception is that if the URL doesn't support ``HTTPS``.

Miscellaneous
=============

The Qub3d development documentation is already hosted on
`Read The Docs <https://qub3d.readthedocs.io>`_.
However, you can always read and compile it into different
file formats locally.

Language
--------

To be consistent, the documentation must be written in American
English. Abbreviations are all-uppercase such as HTTP instead of
Hyper Text Transfer Protocol.

Localization
------------

The documentation is written with the UTF-8 localization format.
Please use unicode for documentation when possible.

For more information about the ReST primer, `check
it out <http://www.sphinx-doc.org/en/stable/rest.html>`_.

..  note::

    This file is *not* a tutorial on ReST and Markdown, rather,
    it is a tutorial on how the Qub3d documentation should look
    like/be written.
