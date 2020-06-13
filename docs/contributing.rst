============
Contributing
============

Once you have the source code, the extension can be built via setup.py::

   $ python setup.py build_ext

We recommend testing with ``pytest``::

   $ pytest

A Tox configuration is present to test against multiple Python versions::

   $ tox

Tests use the ``hypothesis`` Python package to perform fuzzing. If you
don't have it, those tests won't run. Since the fuzzing tests take longer
to execute than normal tests, you'll need to opt in to running them by
setting the ``ZSTD_SLOW_TESTS`` environment variable. This is set
automatically when using ``tox``.

The ``cffi`` Python package needs to be installed in order to build the CFFI
bindings. If it isn't present, the CFFI bindings won't be built.

To create a virtualenv with all development dependencies, do something
like the following::

  # Python 2
  $ virtualenv venv

  # Python 3
  $ python3 -m venv venv

  $ source venv/bin/activate
  $ pip install cffi hypothesis nose tox
