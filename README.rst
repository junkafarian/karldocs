KARL Project Documentation
==========================

`Sphinx <http://sphinx.pocoo.org/>`_ documentation for `KARL Project <http://karlproject.org/>`_. 

Installation Steps
------------------

#. Create a Sphinx documentation directory (if your project does not already have one) using ``sphinx-quickstart``
#. ``$ git clone git://github.com/junkafarian/karldocs.git PATH_TO_DOCS/karl``
#. Add the relevant files to your root ``toctree`` directive::
   
   KARL Project
   ------------
   
   The following pages are aimed to help get started building on KARL Project's existing functionalities.
   
   .. toctree::
      :maxdepth: 2
      
      karl/introduction
      karl/features
      karl/entry_points
      karl/customisation
   
   KARL Project API
   ----------------
   
   .. toctree::
      :maxdepth: 3
      
      karl/api

 