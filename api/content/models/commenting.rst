.. _content_models_commenting_module:

:mod:`karl.content.models.commenting`
=====================================

.. automodule:: karl.content.models.commenting
   
   .. autoclass:: CommentsFolder()
      
      Initialted within a parent object in order to hold Comment objects
   
   .. autoclass:: Comment(title, text, description, creator)
      
      .. attribute:: title
         
         Comment Title
      
      .. attribute:: text
         
         Comment text
      
      .. attribute:: description
         
         Comment Description
      
      .. attribute:: creator
         
         Comment Creator (username)
      
      .. attribute:: attachments
         
         Stores information on any attachments uploaded with the comment.
      
      .. attribute:: modified_by
         
         The user that modified the comment (defaults to ``self.creator``)
      

