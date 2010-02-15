KARL Features
=============

The `KARL documentation <http://dev.karlproject.org/>`_ includes a helpful starting point by defining, and providing some explanation for, the architecture decisions made around the `feature set <http://dev.karlproject.org/archguide/byfeature.html>`_. 

This page attempts to define the features listed more practically for those who wish to extend or adapt the functionality.

.. _feature-people:

People
------

KARL ships with inbuilt User management capabilities. The system is designed to be restricted to authorised access only.

KARL provides user management more suitable to day-to-day actions as part of managing :ref:`feature-communities`

**Related Files:**

``karl/models/members.py``: Defines the marker class for a ``Members`` `Folder <http://docs.repoze.org/folder/>`_

``karl/models/profile.py``: The implementation of a user's profile. It defines user metadata such as ``name``, ``email``, ``organization`` and other user / office specific information.

``karl/models/peopledirectory.py``: Provides a number of utilities and clases for storing groups of member profiles.
   
.. _feature-tagging:

Tagging
-------

Tagging plays a very important part in KARL. A large effort is made to allow tags on all content objects. In return for providing the system with a large number of relevant tags on various content objects, there is a selection of well known tagging functionality such as; ``Tag Clouds``, ``Related Tags``, ``Related Items`` (content).

There is a `Tags` sidebar widget on most content views.

**Related Files:**

``karl/tagging/__init__.py``: Provides an extensive implementation for a site-wide ``ITaggingEngine`` and `ITaggingStatistics`.

``karl/tagging/index.py``: Provides a searching/query interface in front of the tagging engine and site catalog.

.. _feature-search:

Search
------

**Related Files:**

``karl/views/search.py``: Provides view logic related to basic / advanced textual searching.


.. _feature-communities:

Communities
-----------

Communities maintain a list of ``Members`` (users currently interacting with the community). 

The KARL implementation of a Community is minimal, only providing some attributes to summarise details of the Community ``Members``

**Related Files:**

``karl/models/community.py``: Provides the basis for a Community Folder


.. _feature-membership:

Membership
----------

**Related Files:**

``karl/models/members.py``: Defines the marker class for a ``Members`` `Folder <http://docs.repoze.org/folder/>`_


.. _feature-alerts:

Alerts
------

.. _feature-files:

Files
-----

Files can be uploaded through various interactions with a Community. There is a listings view which displays all files that have been uploaded to the community.

**Related Files:**

``karl/content/models/files.py``: Defines CommunityFile objects


.. _feature-wiki:

Wiki
----

KARL provides a basic wiki implementation for use in :ref:`feature-communities` to brainstorm and document relevent information.

**Related Files:**

``karl/content/models/wiki.py``: Defines a Wiki Folder designed to contain WikiPage objects.

.. _feature-blog:

Blog
----

KARL provides a very basic blog implementation for use in :ref:`feature-communities` to broadcast relevent information.

Blog entries can be commented on and have attachments uploaded to them.

**Related Files:**

``karl/content/models/blog.py``: Defines a Blog Folder designed to contain BlogEntry objects.

.. _feature-calendar:

Calendar
--------

There is a more definitive implementation of Calendar functionality aimed at :ref:`feature-communities` to allow ``Members`` to document events / timescales / important dates.

**Related Files:**

``karl/content/models/calendar.py``: Defines the structure for implementing a Community Calendar.

.. _feature-offices:

Offices
-------

Offices are allocated an ``Intranet`` functionality which allows for custom pages, Forums, Office metadata, etc.

**Related Files:**

``karl/content/models/intranets.py``: 

``karl/bootstrap/bootstrap.py``: Where the Intranet functionality is initialised based on the office data provided an InitialData.

.. _feature-syndication:

Syndication
-----------

Dynamic content in KARL is syndicated through standardised RSS feeds and email notifications.

.. _feature-forums:

Forums
------

KARL provides basic Forum functionality

**Related Files:**

``karl/content/models/forum.py``: Defines basic forum functionality.

.. _feature-reference-manuals:

Reference Manuals
-----------------

KARL provides this functionality as part of the Office implementation.

**Related Files:**

``karl/content/models/references.py``: Defines basic forum functionality.

``karl/bootstrap/bootstrap.py``: Where the Reference Manual functionality is initialised based on the office data provided an InitialData as part of the Intranet creation.


Other Features
==============

.. _feature-persistence:

Persistence
-----------

KARL uses the ZODB to store all persistant application data