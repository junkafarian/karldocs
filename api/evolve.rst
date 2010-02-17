.. _evolve_module:

:mod:`karl.evolve`
==================

Persistent storage evolutions

.. automodule:: karl.evolve.zodb
   
   ZODB evolutions
   
   .. data:: VERSION
      
      The version to evolve the database to. The ``repoze.evolution`` machinery
      will iterate through the evolution scripts from ``1`` to ``VERSION``
   
   .. data:: NAME
      
      Name of the project.
   

