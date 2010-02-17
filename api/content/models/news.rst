.. _content_models_news_module:

:mod:`karl.content.models.news`
===============================

.. automodule:: karl.content.models.news
   
   .. autoclass:: NewsItem(title, text, creator, publication, caption=None, data=None)
      
      A news item.
      
      .. attribute:: title
         
         NewsItem title
      
      .. attribute:: text
         
         NewsItem description text
      
      .. attribute:: creator
         
         NewsItem creator username
      
      .. attribute:: modified_by
         
         The last user to modify the object
      
      .. attribute:: publication_date
         
         Date the news item was published.
      
      .. attribute:: caption
         
         NewsItem caption
      
      .. method:: get_photo
         
         Check whether the item contains a photo.

