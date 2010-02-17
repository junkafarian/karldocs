.. _adapters_module:

:mod:`karl.adapters`
====================

.. automodule:: karl.models.adapters
   
   .. autoclass:: CatalogSearch(context, request=None)
      
      .. method:: __call__(**kw)
         
         Query the catalog using the parameters provided in ``kw``.
      
   
   .. autoclass:: PeopleDirectoryCatalogSearch(context, request=None)
      
   
   .. autoclass:: GridEntryInfo(context, request)
      
      .. attribute:: title
         
         The ``context`` title.
      
      .. attribute:: url
         
         If ``context`` is a ``Comment``, form url appropriately. Otherwise,
         return the model_url.
      
      .. attribute:: type
         
         Return content type of ``self.context``
      
      .. attribute:: modified
         
         Return date ``self.context`` was last modified in the form
         ``DD/MM/YYYY``
      
      .. attribute:: created
         
         Return date ``self.context`` was created in the form ``DD/MM/YYYY``
      
      .. attribute:: creator_title
         
         Attempt to find the profile title of the user that created
         ``self.context``
      
      .. attribute:: creator_url
         
         Attempt to find the url to the profile of the user that created
         ``self.context``
      
      .. attribute:: modified_by_profile
         
         Return the profile of the user that last modified ``self.context``
      
      .. attribute:: modified_by_url
         
         Return the url to the profile of the user that last modified
         ``self.context``
      
   
   .. autoclass:: TagQuery(context, request)
      
      TODO: ...
      
      .. atribute:: docid
         
         The docid of ``self.context`` stored in the Catalog DocumentMap.
      
      .. attribute:: usertags
         
         Tags that ``self.username`` has tagged ``self.context`` with.
      
      .. autoattribute:: tagswithcounts
         
      .. attribute:: tagusers
         
         A string representation of ``self.usertags``
      
      .. method:: tags_with_prefix(prefix)
         
         Return a list of tags matching ``prefix``
      
   
   .. autoclass:: CommunityInfo(context, request)
      
      Provides additional information around ``Community`` objects.
      
      .. attribute:: context
         
         ``Community`` object.
      
      .. attribute:: request
         
         ``Request`` object.
      
      .. attribute:: name
         
         ``__name__`` attribute of ``self.context``
      
      .. attribute:: title
         
         ``title`` attribute of ``self.context``
      
      .. attribute:: description
         
         ``title`` attribute of ``self.context``
      
      .. attribute:: tags
         
         Tags for ``self.context``
      
      .. attribute:: number_of_members
         
         Number of members belonging to the community
      
      .. attribute:: url
         
         Absolute url to ``self.context``.
      
      .. attribute:: last_activity_date
         
         String representation of the date the object was last modified
      
      .. attribute:: tabs
         
         Tab views presented by the object.
      
      .. autoattribute:: community_tags
      
      .. attribute:: moderator
         
         Return ``True`` if current user is a moderator for the community.
      
      


