.. _models_feedstorage_module:

:mod:`karl.models.feedstorage`
==============================

.. automodule:: karl.models.feedstorage
   
   .. autoclass:: FeedsContainer()
      
      A ``Folder`` for storing ``Feed`` objects
   
   .. autoclass:: Feed(title)
      
      A persistent storage object for syndication feeds. 
      
      .. attribute:: title
         
         Feed title
      
      .. attribute:: subtitle
         
         Feed subtitle
      
      .. attribute:: link
         
         Feed link
      
      .. attribute:: entries
         
         ``PersistentList`` storing ``FeedEntry`` objects.
      
      .. attribute:: etag
         
         TODO: ...
      
      .. attribute:: feed_modified
         
         date the feed was last modified
      
      .. attribute:: old_uri
         
         TODO: ...
      
      .. attribute:: new_uri
         
         TODO: ...
      
   .. autoclass:: FeedEntry(parser_entry)
      
      Stores information on an item in a syndication feed.
      
      .. method:: update(parser_entry)
         
         Store information taken from ``parser_entry`` and store against
         ``self``
      

