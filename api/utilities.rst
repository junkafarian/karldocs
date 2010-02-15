.. _utilities_module:

:mod:`karl.utilities`
=====================

:mod:`karl.utilities.mailin`
----------------------------

.. class:: MailinRunner(root, maildir_root, options, testing=False)
   
   .. method:: exit(rc)
      
      exit the application
   
   .. method:: print_(message='')
      
      Log ``message`` either using the ``print`` command or an 
      internal log.
   
   .. method:: section(message, sep='-', verbosity=0)
      
      Use self.print_() to log ``message``
   
   .. method:: log(status, message_id, extra='')
      
      Write to self.log_file
   
   .. method:: setup()
      
      Initialise additional requirements (IMailinDispatcher, MaildirStore, PendingQueue utilities)
   
   .. method:: processMessage(message, info, text, attachments)
      
      Proccess ``message`` and forward on to IMailinHandler.handle()
   
   .. method:: bounceMesage(message, info)
      
      Do nothing
   
   .. method:: handleMessage(message_id)
      
      Return 'True' if processed, 'False' if bounced.
      
      .. note::
         
         ...
   
   .. method:: __call__():
      
      Process all messages currently in the self.pending queue.

.. function:: text_scrubber(text, mimetype=None)
   
   TODO
   
