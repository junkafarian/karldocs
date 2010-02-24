.. _models_profile_module:

:mod:`karl.models.profile`
==========================

.. automodule:: karl.models.profile
   
   .. autoclass:: Profile(firstname='', lastname='', email='', phone='', extension='', department='', position='', organization='', location='', country='', website='', languages='', office='', room_no='', biography='', data=None, home_path=None)
      
      User Profile
      
      .. attribute:: firstname
      
      .. attribute:: lastname
      
      .. attribute:: email
      
      .. attribute:: phone
      
      .. attribute:: extension
      
      .. attribute:: department
      
      .. attribute:: position
      
      .. attribute:: organization
      
      .. attribute:: location
      
      .. attribute:: country
      
      .. attribute:: website
      
      .. attribute:: languages
      
      .. attribute:: office
      
      .. attribute:: room_no
      
      .. attribute:: biography
      
      .. attribute:: home_path
      
      .. attribute:: categories
         
         ``PersistentMapping`` of user categories
      
      .. attribute:: password_reset_key
         
         TODO: ...
      
      .. attribute:: password_reset_time
         
         Time the password reset was requested
      
      .. attribute:: creator
      
      .. attribute:: title
         
         "Firstname Lastname"
      
      .. method:: get_photo()
         
         Returns the ImageFile object of the profile picture if one has been
         uploaded.
      
      .. method:: get_alerts_preference(community_name)
         
         Returns the user preference on when to be alerted regarding
         ``community_name``
      
      .. method:: set_alerts_preference(community_name, preference)
         
         Sets the user preference on when to be alerted regarding
         ``community_name``
      
   .. autoclass:: CaseInsensitiveOOBTree()
      
      Converts all lookups to lowercase to provide case insensitivity
   
   .. autoclass:: ProfilesFolder(data=None)
      
      Stores profile information
      
      .. attribute:: email_to_name
         
         ``CaseInensitiveOOBTree`` object for mapping usernames to email
         addresses.
      
      .. method:: getProfileByEmail(email)
         
         Returns the profile with the matching ``email``.
   
   .. autofunction:: profile_textindexdata(profile)
      
   


