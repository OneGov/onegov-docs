OneGov Cloud Modules
====================

..
    Currently, all sub-modules have to be added manually. It seems like the
    following could fix that: https://github.com/sphinx-doc/sphinx/issues/709

Hierarchy
---------

There are three kinds of OneGov Cloud Modules:

Base modules
    Provide the framework under which OneGov Cloud is run.

Supporting modules
    Provide models/methods/utilities, but *no* HTTP interface (neither HTML
    nor REST).

Applications
    Utilize the base and the supporting modules to actually provide a web
    application. Those may or may not be limited to HTML/REST.

This is how this hierarchy looks like:

.. code-block:: text

                       ┌───────────────┐
                       │               │
                       │ onegov.server │  ◇─┐
                       │               │    │
                       └───────────────┘    │
                               ▲            │ base modules
                               │            │
                       ┌───────────────┐    │
                       │               │    │
                       │  onegov.core  │  ◇─┘
                       │               │
                       └───────────────┘
                               ▲
                               │
                       ┌───────────────┐
                       │               │  ◇─┐
                       │  onegov.town  │    │ an application
                       │               │  ◇─┘
                       └───────────────┘
            ┌──────────────────┼──────────────────┐
            ▼                  ▼                  ▼
    ┌───────────────┐  ┌───────────────┐  ┌───────────────┐
    │               │  │               │  │               │
    │  onegov.page  │  │  onegov.user  │  │  onegov.form  │
    │               │  │               │  │               │
    └───────────────┘  └───────────────┘  └───────────────┘
            ◇                                     ◇
            └─────────────────────────────────────┘
                      supporting modules
           (may depend on onegov.core or each other)

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

.. toctree::
    onegov_core

OneGov Town
-----------

The most visible part of the OneGov municipality websites. Combines
functionailty of other OneGov modules and renders them.

OneGov Town tries to implement features itself when necessary. It's main
concern is rendering JSON/HTML. Therefore it should be considered the UI
layer.

.. toctree::
    onegov_town

OneGov User
-----------

Providers user management without any UI.

.. toctree::
    onegov_user

OneGov Form
-----------

Integrates the form library WTForms with OneGov and provides useful
functionality related to that. May generate html, but won't offer any
UI as such.

.. toctree::
    onegov_form

OneGov Page
-----------

Provides functionality to manage custom pages used by OneGov Town. Does not
provide a UI.

.. toctree::
    onegov_page

OneGov Org
----------

Provides functionality to manage organisations, people and memberships. Does
not provide a UI.

.. toctree::
    onegov_org

OneGov Foundation
-----------------

Provides the Zurb Foundation theme for OneGov in an extendable fashion.

.. toctree::
    onegov_foundation

OneGov Testing
--------------

Provides commonly used testing code for all OneGov modules.

.. toctree::
    onegov_testing

OneGov Election Day
-------------------

Shows Swiss election/voting results in an archive and as they come in during
voting day.

.. toctree::
    onegov_election_day

OneGov Ballot
-------------

Contains a model representing elections/votes in Switzerland.

.. toctree::
    onegov_ballot
