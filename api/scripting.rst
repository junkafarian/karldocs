.. _scripting_module:

:mod:`karl.scripting`
=====================

.. automodule:: karl.scripting
   
   .. autofunction:: get_default_config()
      
   .. autofunction:: open_root(config, name='karl')
      
   .. autofunction:: run_daemon(name, func, interval=300)
      
      Repeatedly runs `func`, sleeping for `interval` between runs. `name` is
      used for logging purposes.
   

