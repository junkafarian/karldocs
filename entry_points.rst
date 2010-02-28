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

