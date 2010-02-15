.. _content_adapters_module:

:mod:`karl.content.adapters`
============================

:mod:`karl.content.adapters.mailin`
-----------------------------------

.. class BlogEntryMailinHandler(context)
   
   Handles mailin requests for commenting on Blog entries.
   
   .. note::
      
      Also see :ref:`adapters_interfaces` for more details the functionality
      this adapter provides.
      
   .. method:: handle(message, info, text, attachemnts)
      
      Creates a new comment on a blog post based on the information in the email
      message.


.. class BlogMailinHandler(context)
   
   Handles mailin requests for creating new Blog entries.
   
   .. method:: handle(message, info, text, attachments)
      
      Creates a new blog post based on the information in the email message.
   
