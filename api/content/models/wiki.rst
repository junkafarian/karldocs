.. _content_models_wiki_module:

:mod:`karl.content.models.wiki`
=====================================

.. automodule:: karl.content.models.wiki
   
   .. autoclass:: Wiki(creator)
      
      A wiki with a default ``WikiPage`` for 'front_page'
   
   .. autoclass:: WikiPage(title, text, descriptiom, creator)
      
      A page in a ``Wiki``
      
      .. attribute:: title
         
         Page title
      
      .. attribute:: text
         
         Page body text
      
      .. attribute:: description
         
         Page descriptive text
      
      .. attribute:: creator
         
         User that created the page
      
      .. attribute:: modified_by
         
         User that last modified the object
      
      .. method:: change_title(title)
         
         Update references in sibling ``WikiPage`` objects before updating
         ``self.title``
      
      .. method:: cook(request)
         
         TODO: ...
      
      .. automethod:: fix_links()
         
      
   .. autoclass:: WikiToolFactory()
      
      .. method:: add(context, request)
         
         Creates a new Wiki (``'wiki'``) object in the
         ``context`` object.
      
      .. method:: remove(context, request)
         
         Removes ``'wiki'`` from context.
   
   .. data:: wiki_tool_factory
      
      ``WikiToolFactory`` object.
   

