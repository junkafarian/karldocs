.. _models_site_module:

:mod:`karl.models.site`
==========================

.. automodule:: karl.models.site
   
   .. autoclass:: UserEvent(site, id, login, groups, old_groups=None)
      
      Base implementation for User events.
   
   .. autoclass:: UserAddedEvent(site, id, login, groups, old_groups=None)
      
      Fired when a User is added to the system.
   
   .. autoclass:: UserRemovedEvent(site, id, login, groups, old_groups=None)
      
      Fired when a User is removed from the system.
   
   .. autoclass:: UserAddedGroupEvent(site, id, login, groups, old_groups=None)
      
      Fired when a user adds a group.
   
   .. autoclass:: UserRemovedGroupEvent(site, id, login, groups, old_groups=None)
      
      Fired when a user removes one of their groups.
   
   .. autoclass:: KARLUsers(site)
      
      Extends the standard :mod:`repoze.who` ZODB plugin implementation to
      provide event notifications.
   
   .. function:: get_acl(object, default)
      
      Returns ``object``s ACL if it has one, otherwise returns ``default``.
      (Used for indexing)
   
   .. function:: get_title(object, default)
      
      Returns ``object``s title if it has one, otherwise returns ``default``.
      (Used for indexing)
   
   .. function:: get_name(object, default)
      
      Returns ``object``s ``__name__`` attribute if it has one, otherwise
      returns ``default``. (Used for indexing)
   
   .. function:: get_title_firstletter(object, default)
      
      Tries to return the first letter of ``object``s title, otherwise returns
      ``default``. (Used for indexing)
   
   .. function:: get_interfaces(object, default)
      
      Returns ``object``s derived and immediate interfaces. (Used for indexing)
   
   .. function:: get_path(object, default)
      
      Returns ``object``s model path. (Used for indexing)
   
   .. function:: get_textrepr(object, default)
      
      Return the result of ``object``s ``ITextIndexData`` adapter, if it has
      one, otherwise return ``object``s title and description. (Used for
      indexing)
   
   .. function:: get_creation_date(object, default)
      
      Returns the date ``object`` was created. (Used for indexing)
   
   .. function:: get_modified_date(object, default)
      
      Returns the date ``object`` was last modified. (Used for indexing)
   
   .. function:: get_start_date(object, default)
      
      Returns the start date of the ``object`` (events only). (Used for indexing)
   
   .. function:: get_end_date(object, default)
      
      Returns the end date of the ``object`` (events only). (Used for indexing)
   
   .. function:: get_publication_date(object, default)
      
      Returns the date ``object`` was published. (Used for indexing)
   
   .. function:: get_mimetype(object, default)
      
      Returns the mimetype of ``object``. (Used for indexing)
   
   .. function:: get_creator(object, default)
      
      Returns the ``object``s creator. (Used for indexing)
   
   .. function:: get_email(object, default)
      
      Returns the email attribute of ``object``. (Used for indexing)
   
   .. function:: get_allowed_to_view(object, default)
      
      Returns the principals allowed to view ``object``. (Used for indexing)
   
   .. function:: get_lastfirst(object, default)
      
      Returns ``lastname, firstname`` if ``object`` is a user profile. (Used for
      indexing)
   
   .. function:: get_member_name(object, default)
      
      Returns ``firstname lastname`` if ``object`` is a user profile. (Used for
      indexing)
   
   .. function:: get_virtual(object, default)
      
      Returns the Virtual Data for ``object``. (Used for indexing)
   
   .. autoclass:: Site()
      
      The root object of a KARL application.
      
      On initialization the ``Site`` object configures the following child
      containers:
      
      ``profiles``: A ``karl.models.profile.ProfilesFolder`` used to store user
      profiles.
      
      ``communities``: A ``karl.models.community.CommunitiesFolder`` to store
      community objects.
      
      ``people``: A ``karl.models.peopledirectory.PeopleDirectory`` to store
      user profiles for reports / admin purposes. TODO: confirm?
      
      .. attribute:: catalog
         
         ``CachingCatalog`` object used to index site-wide information.
      
      .. attribute:: users
         
         KARL users.
      
      .. attribute:: tags
         
         Site-wide tagging engine.
      
      .. attribute:: sessions
         
         Side-wide session data
      
      .. attribute:: filestore
         
         TODO: ...
      
      .. method:: update_indexes()
         
         Resets indexes in ``self.catalog``
   
   

