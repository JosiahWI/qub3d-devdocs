Checklist For Submitting Code
#############################

(1) Accomplish the feature(s) it was designed to accomplish.

(2) Have merged all changes from `master` into itself, and all conflicts resolved. (`$ git pull origin master`)

(3) Have binaries and unnecessary cruft untracked and removed. (Keep an eye on `.gitignore`!)

(4) Compile and run properly.

(5) Be free of compiler errors and warnings (must compile with `-Wall -Wextra`).

(6) Be Valgrind pure (no memory leaks detected).

(7) Comply with Coding Standards/Style.

(8) Be free of linter errors. (`$ arc lint --lintall`)

(9) Be fully CSI commented.

(10) Have an up-to-date build script (generally CMake) if relevant.

(11) Contain relevant LIT tests on Goldilocks.

(12) Have a Test Plan, generally containing a list of Goldilocks tests the reviewer should run.

(13) Be reviewed, built, tested, and approved by at least one Trusted review (Staff or Contributor).

(14) Have up-to-date Sphinx documentation, which compiles with no warnings.

(15) Have all reviewer comments processed and marked "Done".

(16) For bug fixes, please show a way of demonstrating that the diff actually fixes something.

(17) If the contributor doesn't run the Goldilocks test suite on the diff, then the maintainer will.

(18) If the diff fixes a bug reported in Maniphest, a brief reference to that bug must be included in the Summary.

(19) Have tests run by Jenkins CI pass properly.


If you are unfamiliar with CSI, `then please read the documentation
for it by MousePaw Media <https://standards.mousepawmedia.com/csi.html>`_.

You must also abide by the C++ and Lua coding standards/style provided by the Qub³d
Engine Group. For more information on our Coding Standards/Style, see the
`C++ Coding Standards <../standards/cpp-standards.html>`_ and the `Lua Coding Standards <../standards/lua-standards.html>`_.

Before launching any significant diff, please double check to see
if there is an issue with a :guilabel:`Help Wanted` tag that describes your
intention, has been approved, and was not assigned to anyone else. However,
if there is no such issue, `create a new one in Maniphest <https://phab.qub3d.tk/maniphest>`_.
If there is an issue that wasn't assigned to anyone, simply leave a
comment behind stating that you wish to work on it, and a Trusted Member
will assign it to you, or you can scroll to the bottom of the issue
page and click on :menuselection:`Actions... --> Assign/Claim` to show others
that you are officially working on the issue. If you're submitting a
minor bug fix, documentation change, and/or other miniscule changes, there
is no need to create an issue, just launch the diff.

If there aren't any bugs in Maniphest to fix, then find a new bug
by running tests with the repositories, or maybe you can casually use them
and spot bugs that way. There's always never a shortage of bugs to fix
in any project.

If you get the :code:`No paths are lintable.` error after typing :code:`arc lint --lintall`,
don't worry about it, for you can ignore it.

If Jenkins fails to pass the test properly, please find out why.
The Qub³d Engine Group will not let failed tests pass through the gates to
landing for any reason.

