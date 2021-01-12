
.. _object_ErrorCollector:


:index:`ErrorCollector`
-----------------------

Description
***********

The ErrorCollector object collects errors from a list of objects and triggers an internal event populated with the data of the most recently occurred error. The object has to be a children of an :ref:`EventLog <object_EventLog>` object so that the internal event is sent to the configured :ref:`EventLog.outputs <property_EventLog_outputs>`.

:**› Inherits**: :ref:`EventLogItem <object_EventLogItem>`

Overview
********

Properties
++++++++++

.. hlist::
  :columns: 1

  * :ref:`currentEvent <property_ErrorCollector_currentEvent>`
  * :ref:`objects <property_ErrorCollector_objects>`
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

  * :ref:`Object.completed() <signal_Object_completed>`



Properties
**********


.. _property_ErrorCollector_currentEvent:

.. _signal_ErrorCollector_currentEventChanged:

.. index::
   single: currentEvent

currentEvent
++++++++++++

This property holds an :ref:`Event <object_Event>` object which represents the most recently occurred error. While most properties are set and updated internally, the :ref:`Event.severity <property_Event_severity>` property can be changed to a custom value. This way the filtering and processing of error events in :ref:`EventOutput <object_EventOutput>` objects can be customized. Per default the severity of this event is set to :ref:`Event.Error <enumitem_Event_Error>`.

:**› Type**: :ref:`Event <object_Event>`
:**› Signal**: currentEventChanged()
:**› Attributes**: Readonly


.. _property_ErrorCollector_objects:

.. _signal_ErrorCollector_objectsChanged:

.. index::
   single: objects

objects
+++++++

This property holds a list of objects to monitor for errors. The monitored objects need to have at least one of the properties ``error`` or ``errorString`` and should have an ``errorOccurred()`` signal. See the example for information on how to add such properties and signals in custom objects.

:**› Type**: List
:**› Signal**: objectsChanged()
:**› Attributes**: Writable


.. _example_ErrorCollector:


Example
*******

.. code-block:: qml

    import InCore.Foundation 2.0
    
    Application {
    
        File {
            // file without storage will raise an error when opened
            id: file
            fileName: "test.txt"
        }
    
        Sms {
            // SMS without transport will raise an error when sent
            id: sms
        }
    
        // polling on property which does not support polling will an raise error
        Polling on name {
            id: polling
            interval: 1000
        }
    
        // create custom object with errorString property
        Object {
            id: customObject
            property string errorString;
    
            function doSomething() {
                errorString = "Something bad happened";
            }
        }
    
        // create custom object with errorOccurred signal - the event description will be empty due to the
        // missing errorString property
        Object {
            id: customObjectWithSignal
            signal errorOccurred();
    
            function doSomething() {
                errorOccurred()
            }
        }
    
        EventLog {
            // print events to console
            outputs: [ EventJournal { } ]
    
            // collect errors from objects defined above
            ErrorCollector {
                objects: [ file, sms, polling, customObject, customObjectWithSignal ]
            }
        }
    
        onCompleted: {
            // trigger errors
            file.open();
            sms.send();
            customObject.doSomething()
            customObjectWithSignal.doSomething()
        }
    }
    