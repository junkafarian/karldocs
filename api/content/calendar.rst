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
      
      **Additional methods / attributes:**
      
      .. method:: paint_events(events)
         
         Render ``Bubble`` objects to the ``self.half_hour_slots``
         attribute.
         
      .. attribute:: first_moment
         
         ``datetime`` object representing the beginning of the day.
      
      .. attribute:: last_moment
         
         ``datetime`` object representing the end of the day.
      
      .. attribute:: auto_scroll_class
         
         Return ``'today'`` or ``''`` dependent on whether the view
         represents the current Day.
      
   
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


.. automodule:: karl.content.calendar.presenters.list
   
   .. class:: ListViewPresenter(focus_datetime, now_datetime, url_for)
      
      Inherits from ``karl.content.calendar.presenters.base.BasePresenter``.
      Provides the presentation logic for rendering the Day view.
      
      **Additional methods / attributes:**
      
      .. method:: paint_events(events)
         
         Render ``Bubble`` objects to the ``self.half_hour_slots``
         attribute.
         
      .. method:: paint_paginated_events(events, has_more, per_page, page)
         
         Handles pagination for rendering events.
   
   .. class:: Event(catalog_event, show_url='#', edit_url='#', delete_url='#', start_day_url='#', end_day_url='#')
      
      Presentation helper for rendering events in a list view.
      
      .. attribute:: DEFAULT_LAYER
         
         The name of the default calendar layer

.. automodule:: karl.content.calendar.presenters.month
   
   .. class:: MonthViewPresenter(focus_datetime, now_datetime, url_for)
      
      Inherits from ``karl.content.calendar.presenters.base.BasePresenter``.
      Provides the presentation logic for rendering the Month view.
      
      **Additional methods / attributes:**
      
      .. method:: paint_events(events)
         
         Render ``Bubble`` / other objects to the ``self.half_hour_slots``
         attribute.
      
      .. method:: first_moment
         
         Beginning of the first day of the month view.
      
      .. method:: last_moment
         
         End of the last day of the month view.
      
   .. class:: DayOnMonthView(year, month, day, current_month=True, current_day=False, add_event_url='#', show_day_url='#')
      
      .. attribute:: year
         
         Year of Event.
      
      .. attribute:: month
         
         Month of Event.
      
      .. attribute:: day
         
         Day of Event.
      
      .. attribute:: current_month
         
         Current Month.
      
      .. attribute:: current_day
         
         Current Day.
      
      .. attribute:: add_event_url
         
         URL to Add Event form.
      
      .. attribute:: show_day_url
         
         URL to day view.
      
      .. attribute:: event_slots
         
         A list of 5 slots defaulting to ``[None, None, None, None, None]``.
      
      .. attribute:: events
         
         Returns a list of items from ``self.event_slots`` if they are
         not ``None``
      
      .. attribute:: overflowed_events
         
         Other events if there are more events than the alotted 5
         slots.
      
      .. attribute:: first_moment
         
         Beginning of the day.
      
      .. attribute:: last_moment
         
         End of the day.
      
   .. class:: EventOnMonthView(day, catalog_event, show_url='#', edit_url='#', delete_url='#')
      
      Inherits from ``karl.content.calendar.presenters.base.BaseEvent``. Used
      to render bubbled / other Events in the month view.
      
      .. attribute:: bubbled
         
         ``Bool`` value determining whether to render the event in a
         bubble.
      
      .. attribute:: rounding_class
         
         ``str`` value for the class to render in ... (TODO)
      
      .. attribute:: bubble_title
         
         Title for the event bubble.
      
      .. attribute:: type_class
         
         Returns ``'all_day'`` or ``'at_time'`` based on the
         ``self.bubbled`` attribute.
      

.. automodule:: karl.content.calendar.presenters.week
   
   .. class:: WeekViewPresenter(focus_datetime, now_datetime, url_for)
      
      Inherits from ``karl.content.calendar.presenters.base.BasePresenter``.
      Provides the presentation logic for rendering the Week view.
      
      **Additional methods / attributes:**
      
      .. method:: paint_events(events)
         
         Renders events using
         ``karl.content.calendar.presenters.day.DayPresenter`` objects.
         
      .. attribute:: today_class
         
         Conditionally returns a class value to highlight the day of
         the week if it is identified as today.
      
      .. attribute:: auto_scroll_class
         
         ... (TODO)
      
      .. attribute:: first_moment
         
         ``datetime`` object representing the beginning of the week.
      
      .. attribute:: last_moment
         
         ``datetime`` object representing the end of the week.
      
   .. class:: DayOnWeekView(year, month, day, show_url=None)
      
      .. attribute:: year
         
         Year of Event.
      
      .. attribute:: month
         
         Month of Event.
      
      .. attribute:: day
         
         Day of Event.
      
      .. attribute:: show_url
         
         URL to where the Day view.
      
      .. attribute:: start_datetime
         
         ``datetime`` object representing the beginning of the day.
      
      .. attribute:: end_datetime
         
         ``datetime`` object representing the end of the day.
      
      .. attribute:: all_day_events
         
         ``list`` of all day events.
      
      .. attribute:: half_hour_slots
         
         ``list`` of half hour slots. ... (TODO)
      
      .. attribute:: heading
         
         String representation of the day / date.
      
      .. attribute:: css_day_abbr
         
         3 letter abbreviation of the weekday for use as a css class.
   

.. automodule:: karl.content.calendar.utils
   
   .. autoclass:: MonthSkeleton(year, month)
      
      .. attribute:: year
         
         Skeleton Year.
      
      .. attribute:: month
         
         Skeleton Month.
      
      .. attribute:: day_names
         
         ``list`` of day names in the month.
      
      .. attribute:: day_abbrs
         
         ``list`` of day abbreviations in the month.
      
      .. method:: make_day(year, month, day)
         
         Return ``datetime`` object of the specified day.
