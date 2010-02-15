.. _consts_module:

:mod:`karl.consts`
==================

.. data:: countries
   
   A ``list`` of countries as tuples of ``(COUNTRY_CODE, COUNTRY_NAME)``. eg::
     
     ('GB', 'United Kingdom')
   
   This list has 2 custom attributes:
   
   .. attribute:: as_dict
      
      returns a ``dict`` of ``{COUNTRY_CODE: COUNTRY_NAME, ...}``
   
   .. attribute:: as_rdict
      
      returns a ``dict`` of ``{COUNTRY_NAME: COUNTRY_CODE, ...}``


