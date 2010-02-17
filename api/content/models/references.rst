.. _content_models_references_module:

:mod:`karl.content.models.references`
=====================================

.. automodule:: karl.content.models.references
   
   .. autoclass:: Ordering()
      
      .. method:: sync(entries)
         
         Add any items that are in the folder but not in the ordering to the
         end. Any items that are in the ordering but not in the folder, remove.
      
      .. method:: moveUp(name)
         
         Move the item with __name__ == name up a position.  If at
         the beginning, move to last position.
      
      .. method:: moveDown(name)
         
         Move the item with __name__ == name down a position.  If at
         the beginning, move to the first position.
      
      .. method:: add(name)
         
         When a new item is added to a folder, put it at the end.
      
      .. method:: remove(name)
         
         When an existing item is removed from folder, remove from
         ordering.  Sure would be nice to use events to do this for
         us.
      
      .. method:: items()
         
         Returns objects stored in the ``Ordering``
      
      .. method:: previous_name(current_name)
         
         Given a position in the list, get the previous name, or None if
         at the beginning of the list
      
      .. method:: next_name(current_name)
         
         Given a position in the list, get the next name, or None if
         at the end of the list
   
   .. autoclass:: ReferenceSection(title, description, creator)
      
      A reference section
      
      .. attribute:: title
         
         Section Title
      
      .. attribute:: description
         
         Section Description
      
      .. attribute:: creator
         
         Username of creator
      
      .. attribute:: modified_by
         
         Username of last user to modify the object
      
      .. attribute:: ordering
         
         ``Ordering`` object
      
   .. autoclass:: ReferenceManual(title, description, creator)
      
      A reference manual
      
      .. attribute:: title
         
         Section Title
      
      .. attribute:: description
         
         Section Description
      
      .. attribute:: creator
         
         Username of creator
      
      .. attribute:: modified_by
         
         Username of last user to modify the object
      
      .. attribute:: ordering
         
         ``Ordering`` object
      

