
.. _object_Event:


:index:`Event`
--------------

Description
***********

The Event object represents a system or runtime event which is sent to certain :ref:`EventOutput <object_EventOutput>` objects whenever it is triggered.

:**› Inherits**: :ref:`DataObject <object_DataObject>`

Overview
********

Properties
++++++++++

.. hlist::
  :columns: 2

  * :ref:`category <property_Event_category>`
  * :ref:`errorCode <property_Event_errorCode>`
  * :ref:`severity <property_Event_severity>`
  * :ref:`DataObject.data <property_DataObject_data>`
  * :ref:`DataObject.dataType <property_DataObject_dataType>`
  * :ref:`DataObject.description <property_DataObject_description>`
  * :ref:`DataObject.name <property_DataObject_name>`
  * :ref:`DataObject.timestamp <property_DataObject_timestamp>`
  * :ref:`DataObject.uuid <property_DataObject_uuid>`
  * :ref:`DataObject.view <property_DataObject_view>`
  * :ref:`Object.objectId <property_Object_objectId>`
  * :ref:`Object.parent <property_Object_parent>`

Methods
+++++++

.. hlist::
  :columns: 1

  * :ref:`trigger() <method_Event_trigger>`
  * :ref:`DataObject.touch() <method_DataObject_touch>`
  * :ref:`Object.deserializeProperties() <method_Object_deserializeProperties>`
  * :ref:`Object.fromJson() <method_Object_fromJson>`
  * :ref:`Object.toJson() <method_Object_toJson>`

Signals
+++++++

.. hlist::
  :columns: 1

  * :ref:`Object.completed() <signal_Object_completed>`

Enumerations
++++++++++++

.. hlist::
  :columns: 1

  * :ref:`Severity <enum_Event_Severity>`
  * :ref:`DataObject.DataType <enum_DataObject_DataType>`



Properties
**********


.. _property_Event_category:

.. _signal_Event_categoryChanged:

.. index::
   single: category

category
++++++++

This property is optional and can be set to group events. This property can be used for filtering within :ref:`EventOutput <object_EventOutput>`. If no category is set and the event is child of an :ref:`EventGroup <object_EventGroup>` the category of the group is used.

:**› Type**: :ref:`EventCategory <object_EventCategory>`
:**› Signal**: categoryChanged()
:**› Attributes**: Writable, Optional


.. _property_Event_errorCode:

.. _signal_Event_errorCodeChanged:

.. index::
   single: errorCode

errorCode
+++++++++

This property holds a user-defined, system- or application-specific error code and can be used for data modelling purposes. Its value is not evaluated by any InCore object.

:**› Type**: SignedInteger
:**› Default**: ``0``
:**› Signal**: errorCodeChanged()
:**› Attributes**: Writable, Optional


.. _property_Event_severity:

.. _signal_Event_severityChanged:

.. index::
   single: severity

severity
++++++++

This property holds the severity of this event. If the event is child of an :ref:`EventGroup <object_EventGroup>` and the :ref:`severity <property_Event_severity>` property of the event equals :ref:`Event.NoSeverity <enumitem_Event_NoSeverity>` the severity of the event group is used instead.

:**› Type**: :ref:`Severity <enum_Event_Severity>`
:**› Default**: :ref:`Event.NoSeverity <enumitem_Event_NoSeverity>`
:**› Signal**: severityChanged()
:**› Attributes**: Writable, Optional

Methods
*******


.. _method_Event_trigger:

.. index::
   single: trigger

trigger()
+++++++++

This method triggers the event. If the event belongs to an :ref:`EventLog <object_EventLog>` with one or multiple attached :ref:`EventOutput <object_EventOutput>` objects it will be forwarded to these outputs. Depending on the configured filters it either will be discarded or handled by the respective output.


Enumerations
************


.. _enum_Event_Severity:

.. index::
   single: Severity

Severity
++++++++

This enumeration describes all possible types of data which can be represented by the :ref:`DataObject.data <property_DataObject_data>` property.

.. index::
   single: Event.NoSeverity
.. index::
   single: Event.Debug
.. index::
   single: Event.Information
.. index::
   single: Event.Warning
.. index::
   single: Event.Error
.. index::
   single: Event.Fatal
.. list-table::
  :widths: auto
  :header-rows: 1

  * - Name
    - Value
    - Description

      .. _enumitem_Event_NoSeverity:
  * - ``Event.NoSeverity``
    - ``0``
    - The event has no dedicated severity and will match any severity filters.

      .. _enumitem_Event_Debug:
  * - ``Event.Debug``
    - ``1``
    - The event is only relevant for debugging the application.

      .. _enumitem_Event_Information:
  * - ``Event.Information``
    - ``2``
    - Events of this severity are used for informational purposes, e.g. information on the current operating status.

      .. _enumitem_Event_Warning:
  * - ``Event.Warning``
    - ``3``
    - Events of this severity signal deviations from the normal operating state.

      .. _enumitem_Event_Error:
  * - ``Event.Error``
    - ``4``
    - An error occurred and usually requires actions to be taken.

      .. _enumitem_Event_Fatal:
  * - ``Event.Fatal``
    - ``5``
    - A fatal error occurred which usually leads to a system failure.


.. _example_Event:


Example
*******

.. code-block:: qml

    import InCore.Foundation 2.0
    
    Application {
    
        Timer {
            interval: 5000
            onTriggered: timerEvent.trigger()
        }
    
        EventLog {
            //define categories to group events - its id can be handled in the outputs
    
            EventCategory {
                id: deviceCategory
            }
    
            //each Event in the group will get the groups category and severity, besides it overrides them
            EventGroup {
                category: deviceCategory
                severity: Event.Error
                Event {
                    id: omniscientEvent
                    errorCode: 42
                    name: "omniscient event"
                    description: "the answer to life, the universe and everything"
                    severity: Event.Information
                }
                Event {
                    id: timerEvent
                    name: "Timer event"
                    description: "the timer timed out"
                }
            }
    
            //each event will be delivered to all outputs, but only handled if the filtering based on category or severity matches
            outputs: [ journal ]
        }
    
        //this outputs date, time, name and description of the event to the journal if the category matches
        EventJournal {
            id: journal
        }
    }
    