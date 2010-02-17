.. _content_models_files_module:

:mod:`karl.content.models.files`
================================

.. automodule:: karl.content.models.files
   
   .. autoclass:: CommunityRootFolder()
      
      The root folder under the ``Files`` tab in a community
   
   .. autoclass:: CommunityFolder()
      
      A Folder in a Community
   
   .. autoclass:: CommunityFile(title, stream, mimetype, filename, creator=u'')
      
      A File in a Community
      
      .. attribute:: title
         
         File Title
      
      .. attribute:: mimetype
         
         File MIMEType
      
      .. attribute:: filename
         
         File Name
      
      .. attribute:: creator
         
         File Creator
      
      .. attribute:: modified_by
         
         User the file was last modified by
      
      .. attribute:: blobfile
         
         The ZODB.Blob object
      
      .. method:: upload(stream)
         
         Store ``stream`` to self.blobfile
   
   .. autoclass:: FilesToolFactory()
      
      .. method:: add(context, request)
         
         Creates a new Files (``'files'``) object in the ``context`` object.
      
      .. method:: remove(context, request)
         
         Removes ``'files'`` from context.
   
   .. data:: files_tool_factory
      
      ``FilesToolFactory`` object.
   

