.. _adapters_module:

:mod:`karl.adapters`
=====================

.. toctree::
   :maxdepth: 2
   
   adapters_interfaces

:mod:`karl.adapters.mailin`
---------------------------

.. automodule:: karl.adapters.mailin

   .. class:: MailinDispatcher(context)
      
      Implementation of an adapter to process generic repoze.mailin requests.
      
      .. note::
         
         Also see :ref:`utilities_module` for more details on how this adapter
         is initialised / controlled by the application.
      
      .. note::
         
         Also see :ref:`adapters_interfaces` for more details the functionality
         this adapter provides.
      
   

:mod:`karl.adapters.url`
------------------------

.. automodule:: karl.adapters.url
   
   .. autoclass:: OfflineContextURL(model,request)
   
   .. autoclass:: OfflineRequest()
   
