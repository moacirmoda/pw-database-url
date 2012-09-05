pw-database-url
~~~~~~~~~~~~~~~

This simple Python utility allows you to utilize the
`12factor <http://www.12factor.net/backing-services>`_ inspired
``DATABASE_URL`` environment variable to configure your Peewee ORM application.

All credit goes to Kenneth Reitz for this one, as it's a direct
port of his dj-database-url utility for Django apps.


Usage
-----

Configure your database from ``DATABASE_URL``::

    DATABASE = pw_database_url.config()

Parse an arbitrary Database URL::

    DATABASE = pw_database_url.parse('postgres://...')

Supported databases
-------------------

Support currently exists for PostgreSQL, MySQL and SQLite.

SQLite connects to file based databases. The same URL format is used, omitting
the hostname, and using the "file" portion as the filename of the database.
This has the effect of four slashes being present for an absolute file path:
``sqlite:////full/path/to/your/database/file.sqlite``.

Installation
------------

Installation is simple too::

    $ pip install git+git://github.com/neilalbrock/pw-database-url.git