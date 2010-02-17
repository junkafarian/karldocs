.. _content_models_intranets_module:

:mod:`karl.content.models.intranets`
====================================

.. automodule:: karl.content.models.intranets
   
   .. autoclass:: IntranetsFolder()
      
      The root folder containing Intranets
   
   .. autoclass:: IntranetsToolFactory()
      
      .. method:: add(context, request)
         
         Creates a new IntranetsFolder (``'intranets'``) object in the
         ``context`` object.
      
      .. method:: remove(context, request)
         
         Removes ``'intranets'`` from context.
   
   .. data:: intranets_tool_factory
      
      ``IntranetsToolFactory`` object.
   

