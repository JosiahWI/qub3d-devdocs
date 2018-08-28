Qub3d Engine CMake Documentation
################################

This file attempts to show you
how to use Qub3d's CMake build system
without having to read CMakeLists.txt for
reference. The default build process is in
the :guilabel:`##Building` section in
README.md in the engine's repository and
the :guilabel:`Basic Build` section in this
file.

Preliminary Requirements
========================

- GCC to be at least 5.x.

- Clang to be at least 2.0.

- CMake to be at least 3.0.2.

Basic Build
===========

The default way of building the engine is this:

..  code-block:: bash

    $ mkdir build/
    $ cd build/
    $ cmake .. #-DWHATEVER_OPTION=ARGUMENT
    $ make -j$(nproc)

CMake Options
=============

+------------------------+--------------------------+-------------------------+
|         Option         |         Arguments        |       Description       |
+========================+==========================+=========================+
| ``-DCMAKE_BUILD_TYPE`` | ``Debug`` or ``Release`` |       Build types.      |
+------------------------+-------------------+------+-------------------------+
|      ``-D32BIT``       |    ``ON`` or ``OFF``     |  Sets up 32-bit build.  |
+------------------------+--------------------------+-------------------------+
|      ``-D64BIT``       |    ``ON`` or ``OFF``     |  Sets up 64-bit build.  |
+------------------------+--------------------------+-------------------------+

..  note::

    :code:`-D32BIT` and :code:`-D64BIT` cannot be used in the same build.

Default Arguments
-----------------

:code:`-DCMAKE_BUILD_TYPE` : Release

:code:`-D32BIT` : OFF

:code:`-D64BIT` : OFF

Default Compiler Flags
======================

This section is dedicated to compiler flags
on each compiler, option.

Default Build
-------------

The flags for the default build are shown below:

..  code-block:: guess

    -O3 -DNDEBUG -Wall -Wextra -std=c++17 -std=c11

Flags for the debug build:

..  code-block:: guess

    -O0 -g -DNDEBUG -Wall -Wextra -std=c++17 -std=c11

GCC-Specific
------------

If you have the GNU Compiler Collection newer
than 5.x installed, then by default, the :code:`-s` option
is incorporated only in the default build. In the debug build,
the :code:`-fprofile-arcs -ftest-coverage` options are incorporated
in order to `support Gcov <https://gcc.gnu.org/onlinedocs/gcc/Gcov.html>`_.
If you have GCC 7.x and above, then the ``-ggnu-pubnames`` flag is
incorporated to make debugging even easier; the flag creates the files,
``.debug_pubnames`` and ``.debug_pubtypes``, in a format
for conversion to a GDB index format. GDB must be at least version 7
for this option to take effect. Overall, a flag setup with
GCC is this:

* GCC 5.x default:

..  code-block:: guess

    -O3 -DNDEBUG -Wall -Wextra -std=c++17 -std=c11 -s

* GCC 5.x debug:

..  code-block:: guess

    -O0 -g -DNDEBUG -Wall -Wextra -std=c++17 -std=c11 -fprofile-arcs -ftest-coverage

* GCC 7.x+ debug:

..  code-block:: guess

    -O0 -g -DNDEBUG -Wall -Wextra -std=c++17 -std=c11 -fprofile-arcs -ftest-coverage -ggnu-pubnames

Clang-Specific
--------------

If you have Clang installed, no flags will be
incorporated; however, if you *do* have LLVM installed along
with Clang, then the :code:`-stdlib=libc++` flag is incorporated
and you will need to install ``libc++`` if you haven't already. This
only affects C++ files.

Dependencies
============

Here, CMake looks into certain directories for packages
that the Qub3d repositories depend on.

PawLIB
------

CMake looks for PawLIB in ``qub3d-libdeps`` after it has been
built. ``qub3d-libdeps`` must be in the same working directory
as the engine for that to happen.

CPGF
----

CMake looks for CPGF in the :code:`qub3d-libdeps` folder that is
paralell to the Qub3d repositories. That is, after you build it.

SDL2
----

It looks for SDL2 in :code:`qub3d-libdeps` after it has been built.

