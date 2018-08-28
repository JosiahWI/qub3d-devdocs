C++ Coding Standards
####################

This document outlines the current coding standards
that should be followed when writing C++ code
for the Qub3d project.

The aims of these conventions are to:

- Ensure code readability, allowing developers to understand new code quickly and easily
- Ensure code is cross compiler compatible
- Make the code easier to maintain (roughly 80% of the lifetime of a codebase goes to maintenance)

Commenting
==========

For any comment that takes up a single line use :code:`//` 
where the :code:`//` and comment is separated by a single space.
For example:

..  code-block:: c++

    // This is a single line comment
    int doSomething();

For multiline comments use :code:`/* */` where the :code:`/*` and :code:`*/` are on their
own separate lines and the comment text is indented - where each line starts with a :code:`*`. A correct example would be:

.. code-block:: c++

    /*
     *   This is a multiline comment
     *   As in a comment with multiple lines.
     *   Etc...
     */

Care should be taken to ensure that all comments are descriptive and as a rule of thumb should
say *why* code is there and not *just* what it does.

Naming
======

Files
-----

C++ Source files should use the :code:`.cpp` file extension and Header files should use the :code:`.hpp` file.

File names should follow camel case naming, where the first world begins with a lowercase letter and following words being with a capital. An example of which is as follows:

.. code-block:: c++

    qub3dHeaderFile.hpp
    qub3dSourceFile.cpp

Functions
---------

Functions and methods names should also use camel case (lowercase first letter and subsequent words start with a capital). This is an acceptable function name:

.. code-block:: c++

    int functionName();

and these are not:

.. code-block:: c++

    void FunctionName();
    void function_name();
    void Function_Name();
    etc...

Function names should be descriptive and describe the purpose of the function. For instance, a function to calculate player health should look like this
:code:`calculatePlayerRemainingHealth()` rather than a generic :code:`calculate`.

Variables
---------

In a similar manner, functions names should use camel case and the name should describe what the variable is for. For example:

..  code-block:: c++

    int playerHealth = 430;

and **not**:

..  code-block:: c++

    std::string random_variable_name;
    int AnotherVariable;

Do **not** use any form of Hungarian notation when naming variables (e.g. encoding information a variable and its type in its name - such as :code:`int iHealth;` 
or :code:`std::string* spName`)

The only valid prefixes for variable names are

+--------+-------------------------------------+
| ``g_`` | For global variables.               |
+--------+-------------------------------------+
| ``m_`` | For private class member variables. |
+--------+-------------------------------------+

Namespaces
----------

Namespaces should also use camel case - where the first letter is lowercase and any subsequent words start with a capital. For example:

..  code-block:: c++

    namespace qub3dEngine
    {
    } // namespace qub3dEngine

and **not**

..  code-block:: c++

    namespace Qub3dEngine
    {}

    namespace qub3d_engine
    {}

The second brace in a namespace declaration should also have a comment on the same line that signifies which namespace it belongs to - in the format
:code:`} // namespace <name-of-the-namespace>`. An example is given above in the first example.

Constants and Macros
---------------------

Constants should follow the convention of being all upperspace characters, where each word is broken via an underscore. For example:

..  code-block:: c++

    const int TOTAL_PLAYER_HEALTH = 1000;

and **not**

..  code-block:: c++

    const int playerHealth = 0001;

Macros should also follow this convention. For example:

..  code-block:: c++

    #define STRINGIFY(str) #str
    #define SOME_CONSTANT (666)

Classes
-------
Classes should be named using Pascal Case - where the first letter is _capitalised_ and the first letter of each subsequent word is also capitalised.
For instance:

..  code-block:: c++

    class ClassNamesUsePascalCase 
    {
    public:
        void whereasFunctionsUseCamelCase();
    };

and **not**

..  code-block:: c++

    class DO_NOT_USE_THIS {};

    class or_this {};

    class orEvenThis {};

Formatting
==========

Braces
------

All braces should be on their own lines with the brace aligned with the start of the statement (e.g not indented). For example:

..  code-block:: c++

    if (someBoolean)
    {
    }

    void functionName()
    {
    }

    namespace qub3d
    {
    } // namespace qub3d

and **not**

..  code-block:: c++

    int getHealth(){
    }

or

..  code-block:: c++

    if (condition)
        {
        }

Pointers
--------

Pointer operators should always be aligned next to the type and not the variable name. For example:

..  code-block:: c++

    char* someString;

and **not**

..  code-block:: c++

    char * someString;
    char *someString;

Indentation
-----------

Tabs should be used for indentation and **not** spaces. Tabs can be configured to whatever size the developer wants in 
their own editor - making them more flexible than spaces.

Class access modifiers should not be indented - for example like this:

..  code-block:: c++

    class Dave 
    {
    public:
        Dave();

    protected:
        virtual void virtualFunction();

    private:
        int m_memberVariable;
    };

and **not** this

..  code-block:: c++

    class Dave 
    {
        public:
            Dave();

        protected:
            virtual void virtualFunction();

        private:
            int m_memberVariable;
    };


There should also always be a space between a condition keyword and the start of the expression. For example:

..  code-block:: c++

    if (condition) { ... }

    while (condition) { .. }

and **not**

..  code-block:: c++

    if(condition){}

    for(int x=0; x<10;x++){}


C++ Constructs
==============

Namespaces
----------

- Do not use :code:`using namespace std;` at global scope
- Use of the :code:`using namespace`  is acceptable for other namespaces, however, developers should use their
  discretion - it should only be used where it does not pollute the global scope *too* much
- :code:`using namespace` is acceptable within a function body.

Dependencies
------------

- Always use :code:`#pragma once` at the start of header files to prevent against multiple includes. Do not use :code:`#ifndef` guards instead.
- Try to minimise coupling in general.
- Use forward declarations instead of including a header, if possible.

Modern C++ Features
-------------------

In order to be the most cross compiler compatible as possible stick to using :code:`C++11` - many compilers do not support more modern features.

Here are some examples of C++11 features that are supported, and encouraged.

- Using range based for loops - for example :code:`for(auto& x : list)` - is encouraged to be used wherever possible as 
  it keeps code easier to maintain and understand, compared to directly writing iterator based loops directly.
- Use the :code:`auto` keyword when it simplifies declarations and makes code easier to understand - for example when dealing with iterators, lambdas or in template code where the type
  of an expression cannot be easily discerned.
- Lambdas are encouraged when it makes the code simpler - however, they should be kept short.

Miscellaneous
=============

This is the collection of style and standards to follow that do not fit in any major categories.

- Use :code:`nullptr` instead of :code:`NULL` dealing with null pointers.
- Initialise default values for member variables in the class member initialisation list (and not in the class declaration)

..  code-block:: c++

    struct Dave
    {
        Dave():
            m_variable1(123),
            m_variable2("Hello World") 
        {}

        int m_variable1;
        std::string m_variable2;
    }

- :code:`const` should some before the type and not after - e.g :code:`const int CONSTANT = 123;` and *not* :code:`int const CONSTANT = 123`.
- Never submit anything that includes commented out code - unless it describes some part of the code.
- Line length - try to keep lines under 80 characters. You may have more than 80 characters on one line, but no more than 120.


Includes
--------

Use :code:`#include <>` for library headers (e.g any third party headers). Use :code:`#include ""` for any headers belonging to that codebase.

Third party header includes should also come before any internal includes in a file. Such as:

..  code-block:: c++

    #include <thread>
    #include <iostream>

    #include "gameEngine.hpp"

When including C standard header files from C++ use the C++ version - for example :code:`#include <cstdio>` and *not* :code:`#include <stdio.h>`

Conditions
----------

Conditions should always read left to right. For example

..  code-block:: c++

    if (result != GLEW_OK) { ... }

and **not**

..  code-block:: c++

    if (GLEW_OK != result) { ... }
