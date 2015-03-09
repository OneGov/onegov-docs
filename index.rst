OneGov Tech Docs
================

OneGov is a Swiss initiative to provide municipalities with affordable and
open-source web-applications to present and manage themeslves through the web.

You've reached the technical documentation of this initiative intended for
administrators, developers and other technical personnel.

If you want to know more about what OneGov does, please refer to
`http://onegov.ch/ <http://onegov.ch/>`_

Projects
--------

OneGov Neo
~~~~~~~~~~

OneGov Neo is a new development whose goal is to provide municipalities
with a lean web presence. It focuses on providing ways to manage and process
transactions (citizen requests). It also offers a way for towns to present
themselves, thought this is not its main focus.

OneGov Neo is built with `Morepath, the web microframework with superpowers
<http://morepath.readthedocs.org/en/latest/>`_.

OneGov Neo has strong opinions about the technology it employs. This has the
following consequenes:

 * It only runs on POSIX platforms.
 * It uses PostgreSQL 9.1+ and won't support other databases.
 * It aims to provide concurrency through multiple processes and is not
   necessarily threadsafe.

OneGov Neo supports Python 2.7, Python 3.3 and Python 3.4. PyPy support might
be added in the future, if no third-party module prevents us from doing that.

**This project is currently under heavy development and very unfinished.**

Developing OneGov Neo
^^^^^^^^^^^^^^^^^^^^^

Have a look at the development repository for instructions on how to get
OneGov Neo running:

`<https://github.com/OneGov/dev>`_

OneGov Neo Modules
^^^^^^^^^^^^^^^^^^

.. toctree::
   :maxdepth: 2

   onegov_neo_modules
