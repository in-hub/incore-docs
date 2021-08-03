
.. _object_EventLog:


:index:`EventLog`
-----------------

Description
***********

The EventLog object is used to couple :ref:`EventOutputs <object_EventOutput>` with :ref:`EventLogItems <object_EventLogItem>` for example a :ref:`EventGroup <object_EventGroup>`. Each event is delivered to all outputs. Internally this object is used to redirect :ref:`Event.trigger() <method_Event_trigger>` calls to the outputs.

:**› Inherits**: :ref:`Object <object_Object>`

Overview
********

Properties
++++++++++

.. hlist::
  :columns: 1

  * :ref:`items <property_EventLog_items>`
  * :ref:`outputs <property_EventLog_outputs>`
  * :ref:`Object.objectId <property_Object_objectId>`
  * :ref:`Object.parent <property_Object_parent>`

Methods
+++++++

.. hlist::
  :columns: 1

  * :ref:`Object.deserializeProperties() <method_Object_deserializeProperties>`
  * :ref:`Object.fromJson() <method_Object_fromJson>`
  * :ref:`Object.toJson() <method_Object_toJson>`

Signals
+++++++

.. hlist::
  :columns: 1

  * :ref:`itemsDataChanged() <signal_EventLog_itemsDataChanged>`
  * :ref:`outputsDataChanged() <signal_EventLog_outputsDataChanged>`
  * :ref:`Object.completed() <signal_Object_completed>`



Properties
**********


.. _property_EventLog_items:

.. _signal_EventLog_itemsChanged:

.. index::
   single: items

items
+++++

This property holds a list of :ref:`EventLogItem <object_EventLogItem>` objects. Each event will be delivered to all outputs.

:**› Type**: :ref:`List <object_List>`\<:ref:`EventLogItem <object_EventLogItem>`>
:**› Signal**: itemsChanged()
:**› Attributes**: Readonly


.. _property_EventLog_outputs:

.. _signal_EventLog_outputsChanged:

.. index::
   single: outputs

outputs
+++++++

This property holds a list of outputs.

:**› Type**: :ref:`List <object_List>`\<:ref:`EventOutput <object_EventOutput>`>
:**› Signal**: outputsChanged()
:**› Attributes**: Readonly

Signals
*******


.. _signal_EventLog_itemsDataChanged:

.. index::
   single: itemsDataChanged

itemsDataChanged(SignedInteger index)
+++++++++++++++++++++++++++++++++++++

This signal is emitted whenever the :ref:`List.dataChanged() <signal_List_dataChanged>` signal is emitted, i.e. the item at ``index`` in the :ref:`items <property_EventLog_items>` list itself emitted the dataChanged() signal.



.. _signal_EventLog_outputsDataChanged:

.. index::
   single: outputsDataChanged

outputsDataChanged(SignedInteger index)
+++++++++++++++++++++++++++++++++++++++

This signal is emitted whenever the :ref:`List.dataChanged() <signal_List_dataChanged>` signal is emitted, i.e. the item at ``index`` in the :ref:`outputs <property_EventLog_outputs>` list itself emitted the dataChanged() signal.



.. _example_EventLog:


Example
*******

.. code-block:: qml

    import InCore.Foundation 2.0
    import InCore.Database 2.0
    
    Application {
    
        Timer {
            interval: 5000
            onTriggered: timerEvent.trigger()
        }
    
        EventLog {
            // define categories to group events - its id can be handled in the outputs
            EventCategory {
                id: customCategory
            }
            EventCategory {
                id: deviceCategory
            }
    
            // each Event in the group will inherit the groups category and severity except for it overrides them
            EventGroup {
                category: customCategory
                severity: Event.Warning
                Event {
                    id: omniscientEvent
                    errorCode: 42
                    name: "omniscient event"
                    description: "the answer to life, the universe and everything"
                }
                Event {
                    id: timerEvent
                    name: "Timer event"
                    description: "the timer timed out"
                }
            }
    
            EventGroup {
                severity: Event.Information
                Event {
                    id: deviceStartedEvent
                    name: "device started"
                    description: "the device was started"
                    category: deviceCategory
                }
            }
    
            // each event will be delivered to all outputs, but only handled if the filtering based on category or severity matches
            outputs: [ journal, writer ]
        }
    
        // this outputs date, time, name and description of the event to the journal if the category matches
        EventJournal {
            id: journal
            filterCategories: [ deviceCategory ]
        }
    
        // write everything with minimum severity level 'information' to the database
        DatabaseEventWriter {
            id: writer
            filterMinimumSeverity: Error.Information
        }
    
        onCompleted: deviceStartedEvent.trigger()
    }
    