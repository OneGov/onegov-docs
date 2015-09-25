Onegov Tech Docs
================

Onegov is a Swiss initiative to provide municipalities with affordable and
open-source web-applications to present and manage themeslves through the web.

You've reached the technical documentation of this initiative intended for
administrators, developers and other technical personnel.

If you want to know more about what Onegov Cloud does, please refer to
`https://onegovcloud.ch/ <https://onegovcloud.ch/>`_

Projects
--------

Onegov Cloud
~~~~~~~~~~~~

Onegov Cloud is a new development whose goal is to provide municipalities
with a lean web presence. It focuses on providing ways to manage and process
transactions (citizen requests). It also offers a way for towns to present
themselves, thought this is not its main focus.

Onegov Cloud is built with `Morepath, the web microframework with superpowers
<http://morepath.readthedocs.org/en/latest/>`_.

Onegov Cloud has strong opinions about the technology it employs. This has the
following consequenes:

 * It only runs on POSIX platforms.
 * It uses PostgreSQL 9.1+ and won't support other databases.
 * It aims to provide concurrency through multiple processes and is not
   necessarily threadsafe.
 * It uses Chameleon templates by default.

Onegov Cloud supports Python 2.7 and Python 3.4. PyPy support might
be added in the future, if no third-party module prevents us from doing that.

**This project is currently under heavy development and very unfinished.**

Language
^^^^^^^^

Though Onegov Cloud supports multiple languages, it only includes German
currently, as this is the language it's going to be deployed in.

Also, all urls are in German for the same reason. We deploy this for German
municipalities and probably won't include another language for many years.

Still, development and docs are in English, because that's what we're most
comfortable in when it comes to development and documentation.

Developing Onegov Cloud
^^^^^^^^^^^^^^^^^^^^^^^

Have a look at the development repository for instructions on how to get
Onegov Cloud running:

`<https://github.com/Onegov/dev>`_

Onegov Cloud Modules
^^^^^^^^^^^^^^^^^^^^

.. toctree::
   :maxdepth: 2

   onegov_cloud_modules

Running Onegov Cloud
^^^^^^^^^^^^^^^^^^^^

Trying out Onegov Cloud is easy, given that you are on POSIX and have the
following installed:

 * Postgres 9.1+
 * Memcached
 * Python 2.7 or Python 3.4

To provide fulltext search, OneGov Cloud relies on elasticsearch. It is however
optional and if it's not installed, the search simply won't work.

You can install all dependencies like this on OSX (Homebrew)::

    brew install postgresql9 memcached libmemcached
    brew install elasticsearch

And like this on Ubuntu::

    sudo apt-get install postgresql-9.3 memcached libmemcached-dev

For Elasticsearch follow the official instructions on Ubuntu:
https://www.elastic.co/guide/en/elasticsearch/guide/current/_installing_elasticsearch.html

Having done that, create a virtualenv::

    mkdir onegov-cloud
    vitualenv onegov-cloud

Activate it::

    cd onegov-cloud
    source bin/activate

Install Onegov Cloud::

    pip install onegov.town

Get the configuration file::

    curl https://raw.githubusercontent.com/OneGov/dev/master/onegov.yml.example > onegov.yml

Adjust the database string in onegov.yml, with the matching info::

      dsn: postgres://user:password@localhost:5432/database

Add your own identity_secret and csrf_secret in onegov.yml::

      identity_secret: very-secret-key
      csrf_secret: another-very-secret-key

Add your own town::

    bin/onegov-town --dsn postgres://user:password@localhost:5432/database --schema towns-govikon add Govikon

Add your own admin::

    bin/onegov-user --dsn postgres://user:password@localhost:5432/database --schema towns-govikon add admin admin@example.org

Run your onegov town instance::

    bin/onegov-server

Open your site::

    http://localhost:8080/towns/govikon
