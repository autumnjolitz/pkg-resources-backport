========================
pkg-resources backport
========================

For when your runtime dependencies absolutely require ``pkg-resources`` but you're unable to downgrade to setuptools 80.10.x.

.. code:: console

    (cpython312) autumn@JudgmentOfCarrion{arm64}:~/software# python -m pip install -U setuptools
    Requirement already satisfied: setuptools in /Users/autumn/.virtualenvs/cpython312/lib/python3.12/site-packages (80.9.0)
    ... /snip
    Successfully installed setuptools-82.0.0
    (cpython312) autumn@JudgmentOfCarrion{arm64}:~/software# python
    Python 3.12.12 (main, Oct  9 2025, 11:07:00) [Clang 17.0.0 (clang-1700.4.4.1)] on darwin
    Type "help", "copyright", "credits" or "license" for more information.
    >>> import pkg_resources
    Traceback (most recent call last):
      File "<stdin>", line 1, in <module>
    ModuleNotFoundError: No module named 'pkg_resources'
    >>> ^D
    (cpython312) autumn@JudgmentOfCarrion{arm64}:~/software# cd pkg-resources-backport
    (cpython312) autumn@JudgmentOfCarrion{arm64}:~/software/pkg-resources-backport# python -m pip install -e .
    Obtaining file:///Users/autumn/software/pkg-resources-backport
    ... /snip
    Successfully built pkg-resources-backport
    Installing collected packages: pkg-resources-backport
    Successfully installed pkg-resources-backport-1.0.0
    (cpython312) autumn@JudgmentOfCarrion{arm64}:~/software/pkg-resources-backport# cd ..
    (cpython312) autumn@JudgmentOfCarrion{arm64}:~/software# python
    Python 3.12.12 (main, Oct  9 2025, 11:07:00) [Clang 17.0.0 (clang-1700.4.4.1)] on darwin
    Type "help", "copyright", "credits" or "license" for more information.
    >>> import pkg_resources
    >>> ^D
    (cpython312) autumn@JudgmentOfCarrion{arm64}:~/software#
