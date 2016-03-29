OneGov Tech Docs
================

OneGov is a Swiss initiative to provide municipalities with affordable and
open-source web-applications to present and manage themeslves through the web.

You've reached the technical documentation of this initiative intended for
administrators, developers and other technical personnel.

If you want to know more about what OneGov Cloud does, please refer to
`https://onegovcloud.ch/ <https://onegovcloud.ch/>`_

OneGov Cloud
------------

OneGov Cloud is a new development whose goal is to provide municipalities
with a lean web presence. It focuses on providing ways to manage and process
transactions (citizen requests). It also offers a way for towns to present
themselves, thought this is not its main focus.

OneGov Cloud is built with `Morepath, the web microframework with superpowers
<http://morepath.readthedocs.org/en/latest/>`_.

OneGov Cloud has strong opinions about the technology it employs. This has the
following consequenes:

 * It only runs on POSIX platforms.
 * It uses PostgreSQL 9.3+ and won't support other databases.
 * It requires Python 3.4+. Python 2.x is *not* supported.
 * It aims to provide concurrency through multiple processes and is not
   necessarily threadsafe.

Language
^^^^^^^^

Though OneGov Cloud supports multiple languages, it only includes German
currently, as this is the language it's going to be deployed in.

Also, all urls are in German for the same reason. We deploy this for German
municipalities and probably won't include another language for many years.

Still, development and docs are in English, because that's what we're most
comfortable in when it comes to development and documentation.

Demo
^^^^

The latest release of OneGov Town, the flagship application of OneGov Cloud,
is available at `<https://govikon.onegovcloud.ch>`_.

Developing OneGov Cloud
^^^^^^^^^^^^^^^^^^^^^^^

Have a look at the development repository for instructions on how to get
OneGov Cloud running:

`<https://github.com/onegov/dev>`_

OneGov Cloud Modules
^^^^^^^^^^^^^^^^^^^^

.. toctree::
   :maxdepth: 2

   onegov_cloud_modules
