snippy
=======

.. image:: https://img.shields.io/pypi/v/snippy.svg
    :target: https://pypi.python.org/pypi/snippy

``snippy`` is a simple command line utiilty for storing text snippets under simple, memorable key names. It is conceptually similar to `boom`_ by `Zach Holman`_.


Installation
------------

The easiest way to install `snippy`_ is via `pip`_:

.. code-block:: console

    pip install snippy

You can also install it the old-fashioned way, if that's more your speed:

.. code-block:: console

    git clone https://github.com/epochblue/snippy
    cd snippy
    python setup.py install


Usage
-----

To create a new snippet, provide both the key name and a value for the key.

.. code-block:: console

    $> snip new_key new_value
    'new_key' is now 'new_value'.

To retrieve the value for a key once it's been set, simply provide the key name. The value will be automatically copied to the system clipboard.

.. code-block:: console

    $> snip new_key
    'new_key' successfully copied to clipboard.

If you attempt to set a value for an existing key, ``snippy`` will return with an error.

.. code-block:: console

    $> snip new_key new_value
    Error: Key 'new_key' already exists.

If you'd like to update an existing key, use the ``--overwrite`` flag:

.. code-block:: console

    $> snip new_key updated_value --overwrite
    'new_key' is now 'updated_value'.

And if you'd like to delete a key/value pair, use the ``--delete`` flag.

.. code-block:: console

    $> snip new_key --delete
    'new_key' has been removed.

By default, ``snippy`` stores its "database" in a file located at ``$HOME/.snippydb``. If you'd like to save your snippets to a different location, you can use the ``-d`` or ``--database`` flag:

.. code-block:: console

    $> snip --database ./snip.db new_key new_value
    'new_key' is now 'new_value'

If you provide no argument or options to ``snippy``, it will print all the currently-stored records to the screen.

.. code-block:: console

    $> snip
    new_key     new_value
    new_key2    new_value2
    example     example_value

It's not much, but that's all there is to ``snippy``.


License
-------

``snippy`` is MIT licensed. Please see the included ``LICENSE`` file.

Authors
-------

* Bill Israel - `@epochblue`_ - `http://billisrael.info/`_

.. _boom: https://github.com/holman/boom
.. _Zach Holman: https://zachholman.com
.. _snippy: https://github.com/epochblue/snippy
.. _pip: https://pypi.python.org/
.. _@epochblue: https://twitter.com/epochblue
.. _http://billisrael.info/: http://billisrael.info/
