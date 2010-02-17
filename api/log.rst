.. _log_module:

:mod:`karl.log`
===============

.. automodule:: karl.log
   
   .. data:: LOG_NAME
      
      Name of the default logger.
   
   .. function:: get_logger()
      
      Returns system logger.
   
   .. function:: configure_log(**config)
      
      Configures default KARL logging.
   
   .. function:: set_subsystem(subsystem)
      
      Sets ``subsystem`` as the subsystem for the logger ``ErrorMonitorHandler``
   
   .. autoclass:: KarlSysLogHandler(app_name, address)
      
      .. method:: format(record)
         
         Formats ``record`` ready for writing to the logs
   
   .. autoclass:: ErrorMonitorHandler(path)
      
      .. method:: set_subsystem(subsystem)
         
         Sets the path for ``self.file`` based on ``subsystem``
      
      .. method:: emit(record)
         
         Writes a formatted version of ``record`` to the system log if the
         subsystem is configured. Otherwise, do nothing.
   
   .. autoclass:: NullHandler
      
      Copied verbatim from Python logging documentation
   

