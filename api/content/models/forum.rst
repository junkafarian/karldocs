.. _content_models_forum_module:

:mod:`karl.content.models.forum`
================================

.. automodule:: karl.content.models.forum
   
   .. autoclass:: ForumsFolder()
      
      The root folder under the ``Forums`` tab in a community
   
   .. autoclass:: Forum()
      
      A Forum in a Community
   
   .. autoclass:: ForumTopic(title='', text='', creator=None)
      
      A Topic in a Forum. Contains ``CommentsFolder`` and ``AttachmentsFolder``
      objects.
      
      .. attribute:: title
         
         ForumTopic Title
      
      .. attribute:: text
         
         Descriptive text
      
      .. attribute:: creator
         
         File Creator
      
      .. attribute:: modified_by
         
         User the file was last modified by
      
   
   .. autoclass:: ForumsToolFactory()
      
      .. method:: add(context, request)
         
         Creates a new ForumsFolder (``'forums'``) object in the ``context``
         object.
      
      .. method:: remove(context, request)
         
         Removes ``'forums'`` from context.
   
   .. data:: forums_tool_factory
      
      ``ForumsToolFactory`` object.
   

