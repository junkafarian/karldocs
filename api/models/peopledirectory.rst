.. _models_peopledirectory_module:

:mod:`karl.models.peopledirectory`
===================================

.. automodule:: karl.models.peopledirectory
   
   .. function:: get_lastname_firstletter(obj, default)
      
      Return the first letter of ``obj``s ``lastname`` attribute or default.
   
   .. autoclass:: ProfileCategoryGetter(catid)
      
   
   .. function:: get_department(obj, default)
      
      Return the department of ``obj`` or default
   
   .. function:: email(obj, default)
      
      Return the email of ``obj`` or default
   
   .. function:: get_location(obj, default)
      
      Return the location of ``obj`` or default
   
   .. function:: get_organization(obj, default)
      
      Return the organization of ``obj`` or default
   
   .. function:: get_phone(obj, default)
      
      Return the phone of ``obj`` or default
   
   .. function:: get_position(obj, default)
      
      Return the position of ``obj`` or default
   
   .. function:: get_groups(obj, default)
      
      Return the groups of the user matching ``obj.__name__`` or default
   
   .. function:: is_staff(obj, default)
      
      Returns a boolean value representing if the user is a member of the
      ``group.KarlStaff`` group.
   
   .. autoclass:: PeopleDirectory()
      
      .. attribute:: categories
         
         Dictionary of categories in the format ``{id: PeopleCategory, ...}``
      
      .. attribute:: catalog
         
         ``karl.models.catalog.CachingCatalog()`` instance
      
      .. attribute:: order
         
         Tuple defining the order of the columns. TODO: ...
      
      .. method:: set_order(order)
         
         Resets ``self.order`` to ``order``
      
      .. method:: update_indexes()
         
         Adds default indexes to catalog if not present and determines whether
         the catalog requires reindexing.
      
   .. autoclass:: PeopleCategory(title)
      
      TODO: ...
      
      .. attribute:: title
         
         Category title
   
   .. autoclass:: PeopleCategoryItem(title, description=u'')
      
      TODO: ...
   
   .. autoclass:: PeopleSection(title, tab_title=None)
      
      TODO: ...
      
      .. attribute:: columns
         
         A sequence of ``PeopleSectionColumn``s
      
      .. method:: set_columns(columns)
         
         Reset ``self.columns`` to ``columns``
      
   
   .. autoclass:: PeopleReportGroup(title)
      
      TODO: ...
      
      .. attribute:: reports
         
         A sequence of ``PeopleReport``s and ``PeopleReportGroup``s
      
      .. method:: set_reports(reports)
         
         Reset ``self.reports`` to ``reports``
      
   
   .. autoclass:: PeopleSectionColumn()
      
      A report group with an empty title
   
   .. autoclass:: PeopleReport(title, link_title=None, css_class='')
      
      TODO: ...
   
   .. autoclass:: PeopleDirectorySchemaChanged(peopledir)
      
      TODO: ...
   
   .. function:: reindex_peopledirectory(peopledir)
      
      Reindex the ``Profiles`` stored in the ``peopledir`` catalog (and index
      any new ones).

