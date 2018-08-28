Development Environment
#######################

This section describes the environment needed for
an efficient workflow in order to develop for the
Qub³d project.

Supported operating systems
===========================

- Windows 7/8/8.1/10

- macOS

- Any Linux distribution

- FreeBSD

Development Tools
-----------------

IDE (Integrated Development Environment): Any multilingual
IDE that floats your boat is recommended.

Supported compilers: GCC 5.x+, and LLVM Clang 2.0+.

- `OpenGL <https://opengl.org>`_

- `PawLIB <https://mousepawmedia.com/pawlib>`_

- `CMake <https://cmake.org/>`_

- `Sphinx <https://sphinx-doc.org>`_

OpenGL is a rendering API that the Rendering API
repository requires to even function.

PawLIB is the library that Qub³d requires in order to
work. It has the Goldilocks testing suite
required by the Qub³d Engine Group.

CMake is the cross-platform compiling software that
most of the Qub³d Engine Group's repositories require.

Sphinx is the software used to make documentation
cleaner. It is required by the Qub³d Engine Group if
you're working on documentation or want to read the
documentation locally in a specified file format.

Installation of CMake
^^^^^^^^^^^^^^^^^^^^^

For Windows, download the CMake tarball and extract it.
Once done, just run the `.exe`.

For macOS, TO BE FILLED IN LATER

For Linux distributions with the Apt package manager, simply type:

..  code-block:: bash

    $ sudo apt-get install cmake

And it will do the magic for you. For Gentoo and its derivatives, type:

..  code-block:: bash

    $ sudo emerge -av dev-util/cmake

For Linux distributions with the DNF package manager, type:

..  code-block:: bash

    $ sudo dnf install cmake

If you have a Linux installation without a package manager like
(B)LFS, you can compile from source and install it. `The tarball
for CMake is here <https://cmake.org/download>`_.

For FreeBSD, type:

..  code-block:: bash

    % sudo pkg install cmake

Installing Sphinx
^^^^^^^^^^^^^^^^^

The Qub³d documentation is written in Sphinx and
uses the ReST file format.

For Windows, you need to install Python if it isn't on
your system already, as most people don't have it installed
by default. So in order to do that, you need to `install it <http://docs.python-guide.org/en/latest/starting/install3/win>`_.
Once you have `pip` installed, press the Windows key and type
:code:`cmd`. When the Command Prompt is running, type:

..  code-block:: bash

	C:\> pip install -U sphinx

On macOS, you need to `install Homebrew <https://brew.sh>`_.
Once you have done that, launch iTerm and type:

..  code-block:: bash

	$ brew install sphinx-doc

To install Sphinx on Linux, as simple as it is, all you need
to do on a Debian(-based) distribution is to access the shell
and type:

..  code-block:: bash

    $ sudo apt-get install python-sphinx

On RHEL/CentOS distributions:

..  code-block:: bash

  	$ sudo yum install python-sphinx

On Fedora:

..  code-block:: bash

	  $ sudo dnf install python-sphinx

On Gentoo(-based) systems:

..  code-block:: bash

	  $ sudo emerge -av dev-python/sphinx

Once you have Sphinx installed, you can simply go
to the root of the Qub³d documentation and type
:code:`make html` to build for HTML, :code:`make latexpdf`
for PDF files, etc. If you want a different file format,
just type :code:`make` for it to list the file formats it
currently has.

Arcanist and Git
================

`Arcanist <https://secure.phabricator.com/book/phabricator/article/arcanist/>`_

`Git <https://git-scm.com/docs>`_

Check out one of our repositories via Diffusion on Phabricator.
(You'll want to set up either a VCS Password or SSH Public
Key on your Phabricator Settings.)

Working on the Qub³d engine with Git/Arcanist:

On UNIX-like platforms, type from the command line after installing git:

..  code-block:: bash

    $ git clone https://github.com/qub3d/qub3dengine
    $ cd qub3dengine/

On your local copy of the repository, create a new branch via
git checkout -b thenewbranchname

Make your changes, and then send them up:

..  code-block:: bash

    $ git add .
    $ git commit -m "<Insert Commit Summary>"
    $ arc diff

Your code will appear as a new Revision on Differential.
It will need to be reviewed and approved by a Trusted member.
If they request changes, do the following after making changes:

..  code-block:: bash

    $ git add .
    $ git commit -m "<Insert Problem Address>"
    $ arc diff

Then, the current diff will get updated to address the change
requests.

Git commit messages must be:

- Descriptive. (No "Update file.cpp" or "Fix a problem.") You must tell
  the maintainers *why* you're making this commit in the first place.

- Concise. The hard limit of characters to be on the subject line is 50.

- Capitalized. All subjects must be capitalized. i.e. "Fix all Bugs with Goldilocks implemented"

- Free of spelling errors.

- In present tense. No "-ed" suffixes.

- Professional. No slang words, no incorporating personal opinions, and
  no grammatical errors. Professional acronyms such as "AFAIK" are allowed.

- Free of useless punctuation. No periods at the end of the subject line,
  for space is precious if you're trying to keep below 50 characters.

- Easy to understand. Type the commit messages as if you were talking to
  average person who knows nothing about your intentions.

Here are some good examples:

..  code-block:: bash

    $ git commit -m "Remove unused function intFoo() and add specific parameters \
                     to intFooBar(), named foo with the type int in order for it to \
                     print out a number assigned to that variable."
    
    $ git commit -m "Turn 3 into 3 superscript for all Qub3d names because staff \
                     agreed to using it that way."
                     
Git commit bodies are also useful if you're launching a significant/complex diff.
The commit bodies' rules are the same as the commit messages but with two
more mandatory rules:

- Limit the amount of characters to 72.

- Tell the maintainer how your patch works in an efficiently descriptive manner.

Global Development Environment (Editors)
========================================

If your editor of choice is Emacs, your ``.emacs`` file
may need to contain this:

..  code-block:: guess

    (setq make-backup-files nil)
    (global-undo-tree-mode)

Since our coding style requires that you use tab instead of spaces,
you'll need to do ``C-q <TAB>`` to do that.

If it's Vim, then the ``.vimrc`` may need to look like this:

..  code-block:: guess

    syntax on
    set nocompatible
    filetype plugin indent on
    set noswapfile
    set hidden
    set nobackup
    set nowb
    set autoindent
    set smartindent
    set smarttab
    set tabstop=4
    set linebreak
    set expandtab

For nano, then ``.nanorc`` should look like this:

..  code-block:: guess

    set linenumbers
    # Disable `set nowrap`

Workflow For The Qub³d Engine
=============================

You'll need a folder to stack the `engine <https://phab.qub3d.tk/diffusion/qub3d-engine>`_
and the `library dependencies <https://phab.qub3d.tk/diffusion/qub3d-libdeps>`_.

``qub3d-libdeps`` will need to be paralell to the engine's repository. On first-time
setup, you just need to run these commands:

..  code-block:: bash

    $ mkdir qub3d
    $ cd qub3d
    $ git clone https://phab.qub3d.tk/source/qub3d-libdeps.git
    $ git clone https://phab.qub3d.tk/source/qub3d-engine.git
    $ cd qub3d-libdeps
    $ make all
    $ cd ../qub3d-engine
    # Do whatever you're planning to do with the engine...
    $ mkdir build && cd build # At the root of the engine repository after configuring default.config...
    $ cmake ..
    $ make -j$(nproc)
    # If build passed successfully...
    $ cd ..
    $ git add .
    $ git commit -m "<Summary of what you did>"
    $ arc diff

Workflow For The Client
=======================

You'll need a similar setup as the engine except that
the repository is ``client``.

First-time setup commands (after setting up the engine):

..  code-block:: bash

    # Assuming you already have cloned the engine and library dependencies...
    $ cd qub3d
    $ git clone https://phab.qub3d.tk/source/client.git
    $ cd sandblox-client
    # Do what you planned to do with the client...
    $ mkdir build && cd build # At the root of repository after making configurations to default.config...
    $ cmake ..
    $ make -j$(nproc)
    # If it built properly...
    $ ../bin/client # Check for any runtime failures...
    # If runtime passed...
    $ cd ..
    $ git add .
    $ git commit -m "<Summary of what you did>"
    $ arc diff
