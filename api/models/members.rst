.. _models_members_module:

:mod:`karl.models.members`
==========================

.. automodule:: karl.models.members
   
   .. autoclass:: Invitation(email, message)
      
      Persistent storage for an invitation to an unregistered user.
      
      .. attribute:: email
         
         Email address to send invitation to.
      
      .. attribute:: message
         
         Message to send to ``self.email``.
      
   .. autoclass:: Members()
      
      Folder for storing member information.
