.. _content_models_adapters_module:

:mod:`karl.content.models.adapters`
===================================

.. class:: FlexibleTextIndexData(context)
   
   .. attribute:: ATTR_WEIGHT_CLEANER
      
      A list of tuples defining ``(attr, weight, cleaner)``.
      
      **default**::
        
        [('title', 10, None),
        ('description', 1, None),
        ('text', 1, None),
        ]
   
   .. method:: __call__()
      
      TODO: ...
   
.. function:: makeFlexibleTextIndexData(attr_weights)
   
   Factory function for ``FlexibleTextIndexData``. Overwrites 
   ``FlexibleTextIndexData.ATTR_WEIGHT_CLEANER`` with ``attr_weights``.

.. function:: extract_text_from_html(text)
   
   This utility wrapper returns a text representation of the HTML ``text``.

.. data:: TitleAndDescriptionIndexData
   
   ``FlexibleTextIndexData`` object using ``title`` and ``description``
   attributes.

.. data:: TitleAndTextIndexData
   
   ``FlexibleTextIndexData`` object using ``title`` and ``text`` attributes.
   Where ``text`` is returned using the ``extract_text_from_html()`` cleaning
   utility.

.. data:: FileTextIndexData
   
   ``FlexibleTextIndexData`` object using ``title`` and ``blobfile``
   attributes. Attempts to extract file data if there is a 
   ``karl.utilities.converters.interfaces.IConverter`` utility registered for
   the file mimetype.

.. class:: CalendarEventCategoryData(context)
   
   .. method:: __call__()
      
      Attempt to find the Calendar Category value for the object.

