.. _entry-points:

KARL Entry Points - Initialisation
==================================

By design KARL allows you to control the underlaying system functionality by
defining a controller package in the ``[DEFAULT]`` section of the ``karl.ini``
`PasteDeploy <http://pythonpaste.org/deploy/>`_ file.

The application is then run using the following stack:
    
#. PasteDeploy (karl.ini)
#. karl.application.make_app

   #. Initialises KARL infrastructure including :ref:`feature-persistence` and
      ``Logging``
   #. Returns a ``repoze.bfg.router.make_app`` instance using the controller
      package loaded from the ``package`` parameter defined in ``karl.ini``

#. Loads the ``configure.zcml`` file located in the controller package
#. This controls which KARL packages are included.


Application Bootstrapping
-------------------------

When the :ref:`feature-persistence` layer is initialised, if there is no data
structure found in the ZODB instance KARL will bootstrap default data by looking
up utilities implementing marker interfaces.

``karl.bootstrap.interfaces.IBootstrapper``
        If a utility is registered with this interface, it is used to control
        populating the database. If the desired application structure differs
        significantly to the KARL defaults, you will likely want to implement
        this utility. Unless this utility is registered / found, KARL will
        default to initialise the database using
        ``karl.bootstrap.bootstrap.populate``.

``karl.bootstrap.interfaces.IInitialData``
        By default KARL uses this to populate a number of example users and the
        groups they belong to.

``karl.bootstrap.interfaces.IInitialOfficeData``
        Configures :ref:`feature-offices` and their corresponding ``Intranet``
        views / functionality.


KARL Entry Points - Application Development
===========================================

Event Subscribers
-----------------

KARL utilises the ``zope.component`` event framework to notify the system of
common actions and to allow developers to perform additional processing when
these actions take place.

Most commonly it will be useful to hook into the ``repoze.folder`` events as
they are used to notify when an object is being added or removed from the system
(specifically their parent folder).

For instance, if an attribute on a user's profile needed to be augmented when
the profile was created, the following code could be used:

.. code-block:: python
   
   >>> def comment_out_foo(obj, event):
   ...     obj.text = obj.text.replace(' foo ', ' *** ')

This can then be hooked up to the event using the following ZCML:

.. code-block:: xml
   
   <subscriber
       for="karl.models.interfaces.Profile
            repoze.folder.interfaces.IObjectAddedEvent"
       handler=".subscribers.comment_out_foo" />




