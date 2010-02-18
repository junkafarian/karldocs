.. _models_image_module:

:mod:`karl.models.image`
========================

.. automodule:: karl.models.image
   
   .. data:: extensions
      
      Dictionary of mimetype >> extension mappings
   
   .. data:: ie_types
      
      Dictionary of Internet Explorer specific mimetypes to standardised
      mimetypes.
   
   .. data:: mimetypes
      
      List of mimetypes taken from the keys of ``extensions`` and ``ie_types``
   
   .. function:: upload_stream(stream, file)
      
      Writes ``stream`` out to the ``file`` file-type object. Returns data
      length.
   
   .. autoclass:: ImageFile(stream, mimetype)
      
      Storage for an uploaded image file.
      
      .. attribute:: mimetype
         
         Image mimetype.
      
      .. attribute:: blobfile
         
         ``ZODB.blob.Blob()`` object for storing the image file data.
      
      .. method:: upload(stream)
         
         Writes ``stream`` to ``self.blobfile``
      
      .. attribute:: extension
         
         Returns the corresponding extension for ``self.mimetype``
      
      .. attribute:: stream
         
         Returns ``self.blobfile`` opened for reading
      

