
.. _object_EventGroup:


:index:`EventGroup`
-------------------

Description
***********

The EventGroup object is a container which groups :ref:`Event <object_Event>` objects for example in a :ref:`EventLog <object_EventLog>`. It can be used to assign a severity or a :ref:`EventCategory <object_EventCategory>` to :ref:`events <property_EventGroup_events>`.

:**› Inherits**: :ref:`EventLogItem <object_EventLogItem>`

Overview
********

Properties
++++++++++

.. hlist::
  :columns: 1

  * :ref:`category <property_EventGroup_category>`
  * :ref:`events <property_EventGroup_events>`
  * :ref:`severity <property_EventGroup_severity>`
  * :ref:`Object.objectId <property_Object_objectId>`
  * :ref:`Object.parent <property_Object_parent>`

Methods
+++++++

.. hlist::
  :columns: 1

  * :ref:`Object.fromJson() <method_Object_fromJson>`
  * :ref:`Object.toJson() <method_Object_toJson>`

Signals
+++++++

.. hlist::
  :columns: 1

  * :ref:`eventsDataChanged() <signal_EventGroup_eventsDataChanged>`
  * :ref:`Object.completed() <signal_Object_completed>`



Properties
**********


.. _property_EventGroup_category:

.. _signal_EventGroup_categoryChanged:

.. index::
   single: category

category
++++++++

This property holds the :ref:`EventCategory <object_EventCategory>` of the group. If the elements in :ref:`events <property_EventGroup_events>` have no category assigned this one is used.

:**› Type**: :ref:`EventCategory <object_EventCategory>`
:**› Signal**: categoryChanged()
:**› Attributes**: Writable, Optional


.. _property_EventGroup_events:

.. _signal_EventGroup_eventsChanged:

.. index::
   single: events

events
++++++

This property holds a list of :ref:`Event <object_Event>` objects.

:**› Type**: :ref:`List <object_List>`\<:ref:`Event <object_Event>`>
:**› Signal**: eventsChanged()
:**› Attributes**: Readonly


.. _property_EventGroup_severity:

.. _signal_EventGroup_severityChanged:

.. index::
   single: severity

severity
++++++++

This property holds the severity of the group. If the elements in :ref:`events <property_EventGroup_events>` have no severity assigned this one is used.

:**› Type**: :ref:`Event.Severity <enum_Event_Severity>`
:**› Default**: :ref:`Event.NoSeverity <enumitem_Event_NoSeverity>`
:**› Signal**: severityChanged()
:**› Attributes**: Writable, Optional

Signals
*******


.. _signal_EventGroup_eventsDataChanged:

.. index::
   single: eventsDataChanged

eventsDataChanged(SignedInteger index)
++++++++++++++++++++++++++++++++++++++

This signal is emitted whenever the :ref:`List.dataChanged() <signal_List_dataChanged>` signal is emitted, i.e. the item at ``index`` in the :ref:`events <property_EventGroup_events>` list itself emitted the dataChanged() signal.


Example
*******
See :ref:`EventLog example <example_EventLog>` on how to use EventGroup.
