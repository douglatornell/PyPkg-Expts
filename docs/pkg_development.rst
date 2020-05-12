.. Copyright 2020, Doug Latornell
..
.. Licensed under the Apache License, Version 2.0 (the "License");
.. you may not use this file except in compliance with the License.
.. You may obtain a copy of the License at
..
..    https://www.apache.org/licenses/LICENSE-2.0
..
.. Unless required by applicable law or agreed to in writing, software
.. distributed under the License is distributed on an "AS IS" BASIS,
.. WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
.. See the License for the specific language governing permissions and
.. limitations under the License.


.. _PyPkg-ExptsPackagedDevelopment:

**********************************************************
:kbd:`pypkg_expts` Package Development
**********************************************************


.. image:: https://img.shields.io/badge/license-Apache%202-cb2533.svg
    :target: https://www.apache.org/licenses/LICENSE-2.0
    :alt: Licensed under the Apache License, Version 2.0
.. image:: https://img.shields.io/badge/python-3.6+-blue.svg
    :target: https://docs.python.org/3.8/
    :alt: Python Version
.. image:: https://img.shields.io/badge/version%20control-git-blue.svg?logo=github
    :target: https://github.com/douglatornell/PyPkg-Expts/
    :alt: Git on GitHub
.. image:: https://img.shields.io/badge/code%20style-black-000000.svg
    :target: https://black.readthedocs.io/en/stable/
    :alt: The uncompromising Python code formatter
.. image:: https://readthedocs.org/projects/pypkg-expts/badge/?version=latest
    :target: https://pypkg-expts.readthedocs.io/en/latest/
    :alt: Documentation Status
.. image:: https://img.shields.io/github/issues/douglatornell/PyPkg-Expts?logo=github
    :target: https://github.com/douglatornell/PyPkg-Expts/issues
    :alt: Issue Tracker

The PyPkg-Expts package (:kbd:`pypkg_expts`) is Python packaging configuration experiments re: pip, setup.py, setup.cfg, pyproject.toml, etc.


.. _PyPkg-ExptsPythonVersions:

Python Versions
===============

.. image:: https://img.shields.io/badge/python-3.6+-blue.svg
    :target: https://docs.python.org/3.8/
    :alt: Python Version

The :kbd:`pypkg_expts` package is developed and tested using `Python`_ 3.8 or later.
The package uses some Python language features that are not available in versions prior to 3.6,
in particular:

* `formatted string literals`_
  (aka *f-strings*)
* the `file system path protocol`_

.. _Python: https://www.python.org/
.. _formatted string literals: https://docs.python.org/3/reference/lexical_analysis.html#f-strings
.. _file system path protocol: https://docs.python.org/3/whatsnew/3.6.html#whatsnew36-pep519


.. _PyPkg-ExptsGettingTheCode:

Getting the Code
================

.. image:: https://img.shields.io/badge/version%20control-git-blue.svg?logo=github
    :target: https://github.com/douglatornell/PyPkg-Expts/
    :alt: Git on GitHub

Clone the code and documentation `repository`_ from GitHub with:

.. _repository: https://github.com/douglatornell/PyPkg-Expts/

.. code-block:: bash

    $ git clone git@github.com/douglatornell/PyPkg-Expts.git PyPkg-Expts

or

.. code-block:: bash

    $ git clone https://github.com/douglatornell/PyPkg-Expts.git PyPkg-Expts

if you don't have `ssh key authentication`_ set up on GitHub,
or copy the link from the :guilabel:`Clone or download` button on the `repository`_ page).

.. _ssh key authentication: https://help.github.com/en/github/authenticating-to-github/connecting-to-github-with-ssh


.. _PyPkg-ExptsDevelopmentEnvironment:

Development Environment
=======================

Setting up an isolated development environment using `Conda`_ is recommended.
Assuming that you have the `Anaconda Python Distribution`_ or `Miniconda3`_ installed,
you can create and activate an environment called :kbd:`pypkg-expts` that will have all of the Python packages necessary for development,
testing,
and building the documentation with the commands below.

.. _Conda: https://conda.io/en/latest/
.. _Anaconda Python Distribution: https://www.anaconda.com/distribution/
.. _Miniconda3: https://docs.conda.io/en/latest/miniconda.html

.. code-block:: bash

    $ cd PyPkg-Expts
    $ conda env create -f envs/environment-dev.yaml
    $ source activate pypkg-expts
    (pypkg-expts)$ pip install --editable .

The :kbd:`--editable` option in the :command:`pip install` command above installs the package from the cloned repo via symlinks so that the installed package will be automatically updated as the repo evolves.

To deactivate the environment use:

.. code-block:: bash

    (pypkg-expts)$ source deactivate


.. _PyPkg-ExptsCodingStyle:

Coding Style
============

.. image:: https://img.shields.io/badge/code%20style-black-000000.svg
    :target: https://black.readthedocs.io/en/stable/
    :alt: The uncompromising Python code formatter

The :kbd:`PyPkg-Expts` package uses the `black`_ code formatting tool to maintain a coding style that is very close to `PEP 8`_.

.. _black: https://black.readthedocs.io/en/stable/
.. _PEP 8: https://www.python.org/dev/peps/pep-0008/

:command:`black` is installed as part of the :ref:`PyPkg-ExptsDevelopmentEnvironment` setup.

To run :command:`black` on the entire code-base use:

.. code-block:: bash

    $ cd PyPkg-Expts
    $ conda activate pypkg_expts
    (pypkg-expts)$ black ./

in the repository root directory.
The output looks something like::

  **add example black output**


.. _PyPkg-ExptsBuildingTheDocumentation:

Building the Documentation
==========================

.. image:: https://readthedocs.org/projects/pypkg-expts/badge/?version=latest
    :target: https://pypkg-expts.readthedocs.io/en/latest/
    :alt: Documentation Status

The documentation for the :kbd:`PyPkg-Expts` package is written in `reStructuredText`_ and converted to HTML using `Sphinx`_.
Creating a :ref:`PyPkg-ExptsDevelopmentEnvironment` as described above includes the installation of Sphinx.
Building the documentation is driven by the :file:`docs/Makefile`.
With your :kbd:`salishsea-nowcast` development environment activated,
use:

.. _reStructuredText: http://www.sphinx-doc.org/en/master/usage/restructuredtext/basics.html
.. _Sphinx: http://www.sphinx-doc.org/en/master/

.. code-block:: bash

    (pypkg-expts)$ (cd docs && make clean html)

to do a clean build of the documentation.
The output looks something like::

  **add example Sphinx output**

The HTML rendering of the docs ends up in :file:`docs/_build/html/`.
You can open the :file:`index.html` file in that directory tree in your browser to preview the results of the build.

If you have write access to the `repository`_ on GitHub,
whenever you push changes to GitHub the documentation is automatically re-built and rendered at https://pypkg-expts.readthedocs.io/en/latest/.


.. _PyPkg-ExptsLinkCheckingTheDocumentation:

Link Checking the Documentation
-------------------------------

Sphinx also provides a link checker utility which can be run to find broken or redirected links in the docs.
With your :kbd:`pypkg-expts)` environment activated,
use:

.. code-block:: bash

    (pypkg-expts))$ cd PyPkg-Expts)/docs/
    (pypkg-expts)) docs$ make linkcheck

The output looks something like::

  **add example linkcheck output**

Look for any errors in the above output or in _build/linkcheck/output.txt


.. _PyPkg-ExptsRunningTheUnitTests:

Running the Unit Tests
======================

The test suite for the :kbd:`PyPkg-Expts` package is in :file:`PyPkg-Expts/tests/`.
The `pytest`_ tool is used for test parametrization and as the test runner for the suite.

.. _pytest: https://docs.pytest.org/en/latest/

With your :kbd:`pypkg-expts` development environment activated,
use:

.. code-block:: bash

    (pypkg-expts)$ cd PyPkg-Expts/
    (pypkg-expts)$ py.test

to run the test suite.
The output looks something like::

  **add example pytest output**

You can monitor what lines of code the test suite exercises using the `coverage.py`_ tool with the command:

.. _coverage.py: https://coverage.readthedocs.io/en/latest/

.. code-block:: bash

    (pypkg-expts)$ cd PyPkg-Expts/
    (pypkg-expts)$ coverage run -m py.test

and generate a test coverage report with:

.. code-block:: bash

    (pypkg-expts)$ coverage report

to produce a plain text report,
or

.. code-block:: bash

    (pypkg-expts)$ coverage html

to produce an HTML report that you can view in your browser by opening :file:`PyPkg-Expts/htmlcov/index.html`.


.. _PyPkg-ExptsVersionControlRepository:

Version Control Repository
==========================

.. image:: https://img.shields.io/badge/version%20control-git-blue.svg?logo=github
    :target: https://github.com/douglatornell/PyPkg-Expts/
    :alt: Git on GitHub

The :kbd:`PyPkg-Expts` package code and documentation source files are available as a `Git`_ repository at https://github.com/douglatornell/PyPkg-Expts/.

.. _Git: https://git-scm.com/


.. _PyPkg-ExptsIssueTracker:

Issue Tracker
=============

.. image:: https://img.shields.io/github/issues/douglatornell/PyPkg-Expts?logo=github
    :target: https://github.com/douglatornell/PyPkg-Expts/issues
    :alt: Issue Tracker

Development tasks,
bug reports,
and enhancement ideas are recorded and managed in the issue tracker at https://github.com/douglatornell/PyPkg-Expts/issues.


License
=======

.. image:: https://img.shields.io/badge/license-Apache%202-cb2533.svg
    :target: https://www.apache.org/licenses/LICENSE-2.0
    :alt: Licensed under the Apache License, Version 2.0

The code and documentation of the Python Packaging Experiments project
are copyright 2020 by Doug Latornell.

They are licensed under the Apache License, Version 2.0.
https://www.apache.org/licenses/LICENSE-2.0
Please see the LICENSE file for details of the license.
