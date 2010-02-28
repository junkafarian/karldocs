KARL Customisation
==================

.. _customising-overriding-content:

Overriding content created using ``repoze.lemonade.content.create_content``
---------------------------------------------------------------------------

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


