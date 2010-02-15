.. _content_calendar_module:

:mod:`karl.content.calendar`
============================

:mod:`karl.content.calendar.navigation`
---------------------------------------

.. automodule:: karl.content.calendar.navigation
   
   .. autoclass:: Navigation(calendar_presenter)
   

.. automodule:: karl.content.calendar.presenters.base
   
   .. autoclass:: BasePresenter(focus_datetime, now_datetime, url_for)
      
   
   .. class:: BaseEvent(day, catalog_event, show_url='#', edit_url='#', delete_url='#')
      
      Mixin class for Calendar events
      
      .. attribute:: title
         
         Event Title
      
      .. attribute:: location
         
         Event Location
      
      .. attribute:: description
         
         Event Description
      
      .. attribute:: color
         
         Event Colour
      
      .. attribute:: layer
         
         Event Layer
      
      .. attribute:: show_url
         
         URL to display the event
      
      .. attribute:: edit_url
         
         URL to edit the event
      
      .. attribute:: delete_url
         
         URL to delete the event
      
      .. attribute:: first_moment
         
         Event start datetime
      
      .. attribute:: last_moment
         
         Event end datetime
      
      .. attribute:: time_in_words
         
         Returns 'all-day' or 'starttime - endtime' for display.

.. automodule:: karl.content.calendar.presenters.day
   
   .. class:: DayViewPresenter(focus_datetime, now_datetime, url_for)
      
      Inherits from ``karl.content.calendar.presenters.base.BasePresenter``.
      Provides the presentation logic for rendering the Day view.
   
   .. class:: TimeSlot(shaded_row=False, is_half_hour=False, start_datetime=0, add_event_url='#')
      
      Presentation helper for storing information on a timeslot in a day view.
      
      .. attribute:: shaded_row
         
         ...
      
      .. attrubte:: is_half_hour
         
         ``Bool`` value describing the duration of the slot.
      
      .. attribute:: start_datetime
         
         ``datetime`` object for the TimeSlot start time
      
      .. attribute:: add_event_url
         
         A URL pointing to the Add Event form.
      
      .. attribute:: bubbles
         
         ``list`` of ``Bubble`` objects.
      
      .. attribute:: bubble
         
         Returns first element of ``self.bubbles`` or ``None``
      
   .. class:: Bubble(event=None)
      
      Presentation helper for displaying an event "Bubble"
      
      .. attribute:: event
         
         The event object that this bubble represents.
      
      .. attribute:: length
         
         Integer describing how many half-hour slots this event takes up.
      
      .. attribute:: length_px
         
         Returns the height the bubble should be in 'px' based on ``self.length``
   
   .. class:: EventOnDayView(day, catalog_event, show_url='#', edit_url='#', delete_url='#')
      
      .. attribute:: time_of_first_moment
         
         Returns a string representation of ``self.first_moment``

