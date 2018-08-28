Contributors' Guide
###################

This file is dedicated to people who want to
contribute to the project but don't know what
Qub3d Engine Group's guidelines are.

This guide is not a tutorial on how to get the
basics with Qub3d. The Getting Started Guide and
the numerous Qub3d support channels exist for that.
Instead, this guide is a tutorial on how to take
advantage of Qub3d's internals and using it for the
purpose of contributing to the project.

Getting Started
===============

This section displays the guidelines for making a development
environment for the Qub3d project.

Create an account on Qub³d Engine Group's `Phabricator <https://phab.qub3d.tk>`_
using your GitHub account. If you don't have a GitHub
account, go ahead and create one. It's free, only takes
a couple minutes, and gives you access to the majority
of the open source development world! After you're done
creating one, on the main page, click on your profile
picture somewhere at the top right and click on :guilabel:`Settings`
and customize/configure to your heart's content.

Go to your Phabricator profile's home page by clicking on your
profile picture at the top right region, click on :guilabel:`Manage`. On the
right, you will see :guilabel:`Edit Profile`. Click on it and fill in the blanks
to your heart's content.

..  note::

    Before submitting contributions, the Qub3d Engine Group will need
    verification that you have signed the `Terms of Development <https://phab.qub3d.tk/L2>`_,
    otherwise they cannot accept your diff.

Contributor Requirements
========================

The following are the requirements to meet before contributing
to the project.

Code
----

To contribute to the engine/launcher, you must have fair
knowledge of at least *one* of the following languages:

C++, Lua, and YAML.

As they are the languages used in the Qub3d code repositories.

Documentation
-------------

If you're just contributing to documentation, you should have the
following characteristics:

- Professional Working Proficiency (ILR Level 3) or better with English

- Knowledge of ReST and its syntax

- Knowledge of Markdown (Only applicable if you're writing Markdown in the
  documentation)

..  note::

    Having fair knowledge of English is mandatory if
    working on documentation.

Beginning Development
=====================

Like any complex project, enhancing the Qub3d
project requires a clear description and purpose of
the problem you're trying to solve. This section will
guide you through on how to plan for developing for the
Qub3d project. In some cases such as an immediate documentation
fix or a typo fix in the code, you don't need to plan for it.

Isolating The Problem
---------------------

If you *do* come across a bug, please make sure it's expected
behavior by looking at the source code to see which file the
problem may be related to, or ask the developers at Freenode IRC or
the Discord server. If it's not expected behavior, then the bug
is confirmed and you may submit it to `Maniphest <https://phab.qub3d.tk/maniphest>`_
as a bug report. It is strongly advised that you claim the task
as the developers already have enough on their plates. By doing so,
scroll down to the bottom of your bug report page and click on
:menuselection:`Actions... --> Assign/Claim` to claim the task.
If, for any rational reason, you can't claim the task, then leave
it open so someone else can do that for you.

Rules
=====

Below are the rules you must abide by when contributing
to the project.

Rules For Submitting Code
-------------------------

There are preliminary checks you must do on your branch before launching.
All the criteria is in `the checklist <../other/checklist.html>`_.

Rules For Submitting Documentation
----------------------------------

See the `Documentation Howto <documentation.html>`_
about this. Also, don't change the scope of the
project via docs. In other words, don't be misleading;
that is strictly prohibited in the project.

Miscellaneous
=============

If you don't feel like hacking and/or documenting the Qub3d
repositories, there's still plenty of other ways for you to help!
You can answer questions on the Discord Server and/or
`Ponder on Phabricator <https://phab.qub3d.tk/ponder>`_, find bugs, promote
Qub³d, contribute to the Qub³d official website, leave behind ideas in the
`Ideas Board <https://phab.qub3d.tk/w/ideas>`_, help review a
diff, provide penetration test results for the qub3d.tk server,
and/or give end-user feedback. The list of ways you can
contribute to the project is inexhaustible.

Post-Launch
===========

You have launched your first diff, congratulations!

If your diff is a work in progress, then please scroll down to the bottom of
your diff page and click :menuselection:`Actions... --> Plan Changes`
to let everyone know that you're not ready for review; that is, unless
you allow it by letting them know via comment or summary.

Now What?
---------

You wait for the diff to get reviewed. Once it is reviewed, you wait
for approval from the maintainers.

When you are certain that you're finished with your diff,
please comment on it, saying: "Done."

The Review Process
------------------

The number one rule for waiting on the reviewers is to be
patient, of course. Every reviewer requires patience and courteousness
from you. If your diff is taking a long time to review, this ensures
quality as the reviewers are actually taking more time to test, look
more closely at the diff, etc. They may request changes and you must
address them unless they're wrong (but that's very rare). Please don't
push the reviewers because you're just making it frustrating for them
and no one likes you in the end.

The process of reviewing a diff is necessary for display to show you
how to do so or to help you understand what the reviewers are doing and why.

It is always wise to have more than one reviewer to inspect your diff, and we
already have `Herald <https://phab.qub3d.tk/herald/query/active>`_ configured to make
that happen.

Once your diff is launched, it shows up in `Diffusion <https://phab.qub3d.tk/diffusion>`_
and sends everyone a :guilabel:`Needs Review` message. That will catch the attention
of the reviewers that Herald automatically put in your diff. As the diff can't automatically
show up at their faces, it will need to take a while for it to get noticed once it's launched.
The reviewer then looks over the diff to see if it checks off all of the items in the *Rules For
Submitting Code* checklist. If not, then (s)he will request changes for that. The reviewer will
also put the diff into action and testing it thoroughly. We trust that the diff submitter did the same.
We also trust that the diff submitter takes the effort to make a good and useful diff because
many of the reviewers have day jobs and usually won't have enough time to look closely at the submitted
diff.

If a change was requested regarding design (the checklist), then please redesign the diff as publicly
as possible as this will save a lot of time in the future.

For documentation diffs, Austin (SonosFuer) and Jay (NewbProgrammer101) are the people you hold
accountable to. Two rules: read and apply the `Documentation Howto <documentation.html>`_, and
don't change the scope of the project. If you break at least one of these rules, you
have inflicted frustration on the reviewers because they have to waste time by telling
you what to do when you could've just followed two extremely basic rules. The reviewers will
comply these two rules while reviewing your documentation change.

There is only one person who has direct access to the repositories, and that
is NewbProgrammer101, and he is who you go to ask to land the diff if you aren't
a :guilabel:`Trusted Member` yet. Only Trusted Members can perform :code:`arc land` once
their diff gets accepted. One of the biggest mistakes a Trusted Member makes is
landing the diff without it being accepted by all reviewers listed by the diff,
this inevitably causes annoyance among everyone if it's actually broken/crappy.

Troubleshooting
---------------

This is where you troubleshoot problems regarding pretty much
anything related to contributing to the Qub³d Engine Group. For problems specific
to Git and/or Arcanist that is not covered in this section, please visit
the `#devop` channel on the Qub³d Engine Group's Discord server.

(Problem 1)
^^^^^^^^^^^

You have launched a diff but it's being prevented by an HTTP
error 403. Fear not! `There's a solution here <https://phab.qub3d.tk/Q1>`_.

Conclusion
==========

While this may seem like a lot to abide by, it is beneficial for both
you and the Qub3d project. It also gets easier the more you contribute.
