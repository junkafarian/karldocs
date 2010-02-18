.. _models_catalog_module:

:mod:`karl.models.catalog`
==========================

.. automodule:: karl.models.catalog
   
   .. autoclass:: CachingCatalog()
      
      Provides a caching layer on top of catalog searches
      
      .. method:: clear()
         
         Invalidates cache
      
      .. method:: index_doc(*arg, **kw)
         
         Invalidates cache
      
      .. method:: unindex_doc(*arg, **kw)
         
         Invalidates cache
      
      .. method:: reindex_doc(*arg, **kw)
         
         Invalidates cache
      
      .. method:: __setitem__(*arg, **kw)
         
         Invalidates cache
      
      .. method:: search(*arg, **kw)
         
         Inserts the query into the cache and returns the correct response.
      
      .. method:: invalidate()
         
         Invalidates cache in this process and informs other processes to
         invalidate theirs.
      
   .. autoclass:: CatalogQueryEvent(catalog, query, duration, result)
      
      Notification that a catalog was queried
   
   .. function:: reindex_catalog(context, path_re=None, commit_interval=200, dry_run=False, output=None, transaction=transaction, indexes=None)
      
      Reindexes the catalog for the Site ``context`` is contained in.


