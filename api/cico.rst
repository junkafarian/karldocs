.. _cico_module:

:mod:`karl.cico`
================

.. toctree::
   :maxdepth: 2
   
   cico_interfaces

:mod:`karl.cico.people`
-----------------------

.. automodule:: karl.cico.people

   .. class:: UserProfileImporter(element)
      
      Import User profile information taken from items matching an XML schema
      (self.SCHEMA) located within the parent ``element``
      
      This utility provides the ``karl.cico.interfaces.IContentIn`` interface
      and so provides ``.create()`` and ``.update()`` methods.
      
      .. method:: create(profiles)
         
         Adds the parent ``element`` to the application ``Users`` storage
         object. Then iterate over any child elements presenting the correct
         schema and add them as well.
      
      .. method:: update(profile)
         
         Remove the old reference to ``profile`` from the Users container and
         add a new instance of the Profile (whilst maintaining the groups / 
         memberships that the user previously belonged to.)
   
   
   .. class:: PeopleCategoryImporter(element)
      
      Import User categories taken from items matching an XML schema
      (self.SCHEMA) located within the parent ``element``
      
      This utility provides the ``karl.cico.interfaces.IContentIn`` interface
      and so provides ``.create()`` and ``.update()`` methods.
      
      .. method:: create(profiles)
         
         ...
      
      .. method:: update(profile)
         
         ...
      
