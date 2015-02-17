OneGov Neo Modules
==================

..
    Currently, all sub-modules have to be added manually. It seems like the
    following could fix that: https://github.com/sphinx-doc/sphinx/issues/709

Onegov Server
-------------

`https://github.com/OneGov/onegov.server.git <https://github.com/OneGov/onegov.server.git>`_

Serves the OneGov web-applications. Meant to be the runner and configurator
of all applications. Not meant to run publicly. Like all python
web-applications this one should be proxied behind Nginx or Apache2.

.. toctree::
    onegov_server