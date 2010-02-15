.. _bootstrap_module:

:mod:`karl.bootstrap`
=====================

:mod:`karl.bootstrap.bootstrap`
-------------------------------

.. function:: populate(root[, do_transaction_begin=True])
   
   This function provides a default implementation for populating a
   clean ZODB with default data. This logic can be overridden by 
   providing a ``karl.bootstrap.interfaces.IBootstrapper`` utility.
   
   
.. function:: bootstrap_evolution(root)
   
   Scan for all utilities in the registry providing the
   ``repoze.evolution.IEvolutionManager`` interface and evolve the data stored
   in ``root``

:mod:`karl.bootstrap.data`
--------------------------

.. class:: DefaultInitialData
   
   The default construct for populating an empty application with
   default data. It is designed to be used as a mixin class and
   customised in the controller package (in :ref:`introduction-karlsample`
   this class is configured in ``karlsample.bootstrap.data``)
   
   This class implements the ``karl.bootstrap.interfaces.IInitialData`` interface.
   
   .. attribute:: moderator_principals
      
      Defines the principals to be assigned moderator privileges.
      
      .. note::
         
         tbc. what do these privileges allow
      
      **expected format:** ``[principal_id, ...]``
      
      **default:** ``['group.KarlModerator']``
   
   .. attribute:: member_principals
      
      Defines the principals to be assigned authenticated / Staff privileges.
      
      .. note::
         
         tbc. what do these privileges allow
      
      **expected format:** ``[principal_id, ...]``
      
      **default:** ``['group.KarlStaff']``
   
   .. attribute:: guest_principals
      
      Defines the principals to be assigned guest privileges.
      
      .. note::
         
         tbc. what do these privileges allow
      
      **expected format:** ``[principal_id, ...]``
      
      **default:** ``[]``
   
   .. attribute:: community_tools
      
      Defines the tools (and associated views) to enable for
      ``Community`` objects.
      
      .. note::
         
         Explain lookup process for finding available tools 
         (karl.views.community:L117 / karl.views.community:L198)
      
      **expected format:** ``(tool_id, ...)``
      
      .. note::
         
         where ``tool_id`` is the ``name`` attribute of the ToolFactory
      
      **default:** ``('blog', 'wiki', 'calendar', 'files')``
   
   .. attribute:: intranet_tools
      
      Defines the tools (and associated views) to enable for
      ``Office`` / ``Intranet`` objects.
      
      .. note::
         
         Explain lookup process for finding available tools 
         (karl.views.community:L117 / karl.views.community:L198)
         (uses same logic)
      
      **expected format:** ``(tool_id, ...)``
      
      .. note::
         
         where ``tool_id`` is the ``name`` attribute of the ToolFactory
      
      **default:** ``('forums', 'intranets', 'files')``
   
   .. attribute:: admin_user
      
      Defines the username of the main Admin user.
      
      **expected format:** ``admin_username``
      
      **default:** ``'admin'``
   
   .. attribute:: admin_groups
      
      Defines the groups to be allocated to the admin user.
      
      **expected format:** ``(principal_id, ...)``
      
      **default:** ``('group.KarlStaff', 'group.KarlAdmin')``
   
   .. attribute:: folder_markers
      
      TBD
      
      **expected format:** ``[(folder_id, folder_title, folder_marker, folder_parent), ...]``
      
      **default:** ``[('network-news', 'Network News', 'network_news', 'files'), ('network-events', 'Network Events', 'network_events', 'files')]``
   
   .. attribute:: site_acl
      
      Defines the ACL to be set on the site root object (and therefore
      inherited by default).
      
      **expected format:** ``[ACU, ...]``
      
      **default:** ``[(Allow, repoze.bfg.security.Authenticated, karl.security.policy.GUEST_PERMS), (Allow, 'group.KarlStaff', karl.security.policy.MEMBER_PERMS), (Allow, 'group.KarlModerator', karl.security.policy.MODERATOR_PERMS), (Allow, 'group.KarlAdmin', karl.security.policy.ADMINISTRATOR_PERMS)]``
   
   .. attribute:: profiles_acl
      
      Defines the ACL to be set on the profiles root object (and therefore
      inherited for other profile views).
      
      **expected format:** ``[ACU, ...]``
      
      **default:** ``[(Allow, 'group.KarlUserAdmin', karl.security.policy.ADMINISTRATOR_PERMS)]``
   
   .. attribute:: staff_acl
      
      Defines the ACL to define access rights for "public" resources 
      (and therefore inherited by default).
      
      **expected format:** ``[ACU, ...]``
      
      **default:** ``[(Allow, 'group.KarlAdmin', karl.security.policy.ADMINISTRATOR_PERMS + karl.security.policy.MODERATOR_PERMS), (Allow, 'group.KarlModerator', karl.security.policy.MODERATOR_PERMS), (Allow, 'group.KarlStaff', karl.security.policy.GUEST_PERMS)]``
   
   .. attribute:: users_and_groups
      
      Defines the default users to be added to the system
      
      **expected format:** ``[(login, firstname, lastname, email, (group, ...)), ...]``
      
      **default:** ``[('admin', 'Ad','Min','admin@example.com', ('group.KarlAdmin', 'group.KarlUserAdmin', 'group.KarlStaff'))]``
   
   .. attribute:: office_data
      
      If this attribute is not overridden, it will perform a registry
      lookup for a ``karl.bootstrap.interfaces.IInitialOfficeData`` utility.
      
      **expected format:** ``n/a``
      
      **default:** ``n/a``
   
