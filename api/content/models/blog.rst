.. _content_models_blog_module:

:mod:`karl.content.models.blog`
===============================

.. automodule:: karl.content.models.blog
   
   .. autoclass:: Blog()
      
      Stores Blog entries
   
   .. autoclass:: BlogEntry(title, text, description, creator)
      
      Contains a ``karl.content.models.commenting.CommentsFolder`` named 
      ``'comments'`` and an karl.content.models.attachments.AttachmentsFolder``
      named ``'attachments'``
   
   .. autoclass:: BlogToolFactory()
      
      .. method:: add(context, request)
         
         Creates a new Blog (``'blog'``) in the ``context`` object.
      
      .. method:: remove(context, request)
         
         Removes ``'blog'`` from context.
   
   .. data:: blog_tool_factory
      
      ``BlogToolFactory`` object

