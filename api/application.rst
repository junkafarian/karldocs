.. _application_module:

:mod:`karl.application`
=======================

.. function:: appmaker(root)
   
   If ``root`` is an empty persistent storage instance, invoke the ``karl.bootstrap.interfaces.Ibootstrapper`` utility to populate the application.

.. function:: make_app(global_config, **kw)
   
   Paste ``app_factory``, performs initial application setup before loading controller package configuration.

.. function:: find_users(root)
   
   Used by repoze.who ZODB plugin to find users 

