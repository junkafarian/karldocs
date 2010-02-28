KARL Customisation
==================

.. _customising-overriding-zcml:

Overriding ZCML Configuration
-----------------------------

When the application ZCML is loaded at startup, it is validated to ensure there
are no conflicting directives.

The following ZCML is used to configure the default view for the ``Site``
object. This will be used when visiting the root of the site ("/").

.. code-block:: xml
   
    <view
      for="karl.models.interfaces.ISite"
      view=".site.site_view"
      permission="view"
    />

If this declaration was duplicated (perhaps in another file):

.. code-block:: xml
   
    <view
      for="karl.models.interfaces.ISite"
      view="karl.views.site.site_view"
      permission="view"
    />

You would recieve an describing that the two declarations are conflicting.

In order to allow the :term:`policy package` to override this view the system
must be instructed to use one set of declarations rather than another. This can
be done using the ``<includeOverrides>`` directive. 

By default the following declaration is included in the ``policy package``::
    
    <include package=".views" />

In order to override existing declarations in KARL, this can be changed to::

    <includeOverrides package=".views" file="overrides.zcml" />
    <include package=".views" />


.. _customising-overriding-content:

Overriding content created using ``repoze.lemonade.content.create_content``
---------------------------------------------------------------------------

.. note::
   
   This method requires :ref:`customising-overriding-zcml`, use the same
   ``<includeOverrides>`` directive to point to an ``overrides.zcml`` file
   configuring the content you wish to override the KARL defaults.

``repoze.lemonade`` creates content by looking up a content factory associated
with a particular interface. For example the default ZCML configuration for
creating a new ``Profile`` object looks like this:

.. code-block:: xml
   
   <lemonade:content
      factory=".profile.Profile"
      type=".interfaces.IProfile"
      />

This is then invoked using the following python code from within the
application:

.. code-block:: python
   
   >>> from repoze.lemonade import create_content
   >>> from karl.models.interfaces import IProfile
   >>> profile = create_content(IProfile, *args)

In order to customise the ``Profile`` base class, it will have to be redefined /
extended from the existing definition.

.. code-block:: python
   
   >>> from karl.models.profile import Profile as KARLProfile
   >>> class Profile(KARLProfile):
   ...     new_attr = u'Some new attribute'

However, this new declaration will ignored when profiles are created using the
standard KARL machinery. Therefore the new class will need to be registered to
override the default KARL one. This can be done simply by using the following
ZCML:

.. code-block:: xml
   
   <lemonade:content
      factory="yourpackage.models.profile.Profile"
      type="karl.models.interfaces.IProfile"
      />


