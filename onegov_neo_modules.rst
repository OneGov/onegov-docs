OneGov Neo Modules
==================

..
    Currently, all sub-modules have to be added manually. It seems like the
    following could fix that: https://github.com/sphinx-doc/sphinx/issues/709

OneGov Server
-------------

`https://github.com/OneGov/onegov.server.git <https://github.com/OneGov/onegov.server.git>`_

Serves the OneGov web-applications. Meant to be the runner and configurator
of all applications. Not meant to run publicly. Like all python
web-applications this one should be proxied behind Nginx or Apache2.

OneGov server does not depend on any other OneGov module.

.. toctree::
    onegov_server

OneGov Core
-----------

Contains functionality shared between all the other OneGov modules, with the
exception of OneGov Server, which may not depend on the core.

OneGov Town
-----------

The most visible part of the OneGov municipality websites. Combines
functionailty of other OneGov modules and renders them.

OneGov Town tries to implement features itself when necessary. It's main
concern is rendering JSON/HTML. Therefore it should be considered the UI
layer.

OneGov User
-----------

Providers user management without any UI.

OneGov Forms
------------

Integrates the form library WTForms with OneGov and provides useful
functionality related to that. May generate html, but won't offer any
UI as such.

OneGov Pages
------------

Provides functionality to manage custom pages used by OneGov Town. Does not
provide a UI, but may render HTML.

Uses Markdown internally.
