.. _models_community_module:

:mod:`karl.models.community`
============================

.. automodule:: karl.models.community
   
   .. autoclass:: Community(title, description, text=u'', creator=u'')
      
      Community implementation. Configures and stores a
      ``karl.models.members.Members()`` instance by default.
      
      .. attribute:: default_tool
         
         Specifies which tool (tab) to focus on by default when users land on
         the community
      
      .. attribute:: content_modified
         
         Stores the date community content was last modified. This is set by the
         event subscribers for created and modified events.
      
      .. attribute:: title
         
         The community title
      
      .. attribute:: description
         
         A description of the community.
      
      .. attribute:: text
         
         Community text
      
      .. attribute:: creator
         
         User that created this community
      
      .. attribute:: members_group_name
         
         Identifier string for searching members belonging to this community.
      
      .. attribute:: moderators_group_name
         
         Identifier string for searching moderators of this community.
      
      .. attribute:: number_of_members
         
         Number of members that belong to this community.
      
      .. attribute:: member_names
         
         A ``set`` of usernames belonging to this community.
      
      .. attribute:: moderator_names
         
         A ``set`` of usernames moderating this community.
      
   .. autoclass:: CommunitiesFolder()
      
      A ``Folder`` for storing ``Community`` objects.

