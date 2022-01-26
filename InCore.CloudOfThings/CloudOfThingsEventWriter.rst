
.. _object_CloudOfThingsEventWriter:


:index:`CloudOfThingsEventWriter`
---------------------------------

Description
***********

The CloudOfThingsEventWriter object sends :ref:`Event <object_Event>` objects to the Cloud of Things or stores them, if the connection is temporary lost.

:**› Inherits**: :ref:`EventOutput <object_EventOutput>`

Overview
********

Properties
++++++++++

.. hlist::
  :columns: 2

  * :ref:`alarmCategories <property_CloudOfThingsEventWriter_alarmCategories>`
  * :ref:`buffering <property_CloudOfThingsEventWriter_buffering>`
  * :ref:`client <property_CloudOfThingsEventWriter_client>`
  * :ref:`error <property_CloudOfThingsEventWriter_error>`
  * :ref:`errorString <property_CloudOfThingsEventWriter_errorString>`
  * :ref:`eventDatabase <property_CloudOfThingsEventWriter_eventDatabase>`
  * :ref:`sendStoredDataCount <property_CloudOfThingsEventWriter_sendStoredDataCount>`
  * :ref:`sendStoredDataInterval <property_CloudOfThingsEventWriter_sendStoredDataInterval>`
  * :ref:`EventOutput.filterCategories <property_EventOutput_filterCategories>`
  * :ref:`EventOutput.filterExactSeverity <property_EventOutput_filterExactSeverity>`
  * :ref:`EventOutput.filterMinimumSeverity <property_EventOutput_filterMinimumSeverity>`
  * :ref:`Object.objectId <property_Object_objectId>`
  * :ref:`Object.parent <property_Object_parent>`

Methods
+++++++

.. hlist::
  :columns: 1

  * :ref:`Object.deserializeProperties() <method_Object_deserializeProperties>`
  * :ref:`Object.fromJson() <method_Object_fromJson>`
  * :ref:`Object.serializeProperties() <method_Object_serializeProperties>`
  * :ref:`Object.toJson() <method_Object_toJson>`

Signals
+++++++

.. hlist::
  :columns: 1

  * :ref:`alarmCategoriesDataChanged() <signal_CloudOfThingsEventWriter_alarmCategoriesDataChanged>`
  * :ref:`errorOccurred() <signal_CloudOfThingsEventWriter_errorOccurred>`
  * :ref:`EventOutput.filterCategoriesDataChanged() <signal_EventOutput_filterCategoriesDataChanged>`
  * :ref:`Object.completed() <signal_Object_completed>`

Enumerations
++++++++++++

.. hlist::
  :columns: 1

  * :ref:`AlarmSeverity <enum_CloudOfThingsEventWriter_AlarmSeverity>`
  * :ref:`Error <enum_CloudOfThingsEventWriter_Error>`



Properties
**********


.. _property_CloudOfThingsEventWriter_alarmCategories:

.. _signal_CloudOfThingsEventWriter_alarmCategoriesChanged:

.. index::
   single: alarmCategories

alarmCategories
+++++++++++++++

This property holds a list of :ref:`EventCategory <object_EventCategory>` objects, which assigned :ref:`Event <object_Event>` objects are treated as alarms. Other events pushed to this output are treated as Cloud of Things events and the severity is ignored.

:**› Type**: :ref:`List <object_List>`\<:ref:`EventCategory <object_EventCategory>`>
:**› Signal**: alarmCategoriesChanged()
:**› Attributes**: Readonly


.. _property_CloudOfThingsEventWriter_buffering:

.. _signal_CloudOfThingsEventWriter_bufferingChanged:

.. index::
   single: buffering

buffering
+++++++++

This property holds whether :ref:`Event <object_Event>` objects should be stored when :ref:`CloudOfThingsClient <object_CloudOfThingsClient>` is not connected. If the connection is restored buffered measurements will be sent with an interval of :ref:`sendStoredDataInterval <property_CloudOfThingsEventWriter_sendStoredDataInterval>` ms.

:**› Type**: Boolean
:**› Default**: ``true``
:**› Signal**: bufferingChanged()
:**› Attributes**: Writable


.. _property_CloudOfThingsEventWriter_client:

.. _signal_CloudOfThingsEventWriter_clientChanged:

.. index::
   single: client

client
++++++

This property holds the Cloud of Things client. This property can be left blank if :ref:`CloudOfThingsClient <object_CloudOfThingsClient>` is a parent.

:**› Type**: :ref:`CloudOfThingsClient <object_CloudOfThingsClient>`
:**› Signal**: clientChanged()
:**› Attributes**: Writable


.. _property_CloudOfThingsEventWriter_error:

.. _signal_CloudOfThingsEventWriter_errorChanged:

.. index::
   single: error

error
+++++

This property holds the most recently occurred error or :ref:`CloudOfThingsEventWriter.NoError <enumitem_CloudOfThingsEventWriter_NoError>` if no error occurred. If the same error occurs multiple times this property does not change. Use the :ref:`errorOccurred() <signal_CloudOfThingsEventWriter_errorOccurred>` signal to detect multiple occurrences of the same error.

:**› Type**: :ref:`Error <enum_CloudOfThingsEventWriter_Error>`
:**› Signal**: errorChanged()
:**› Attributes**: Readonly


.. _property_CloudOfThingsEventWriter_errorString:

.. _signal_CloudOfThingsEventWriter_errorStringChanged:

.. index::
   single: errorString

errorString
+++++++++++

This property holds the current human readable error string corresponding to the current value in the :ref:`error <property_CloudOfThingsEventWriter_error>` property. It may include additional information such as failure reasons or locations.

:**› Type**: String
:**› Signal**: errorStringChanged()
:**› Attributes**: Readonly


.. _property_CloudOfThingsEventWriter_eventDatabase:

.. _signal_CloudOfThingsEventWriter_eventDatabaseChanged:

.. index::
   single: eventDatabase

eventDatabase
+++++++++++++

This property holds the event database which buffers the events if no connection is available.

:**› Type**: :ref:`CloudOfThingsEventDatabase <object_CloudOfThingsEventDatabase>`
:**› Signal**: eventDatabaseChanged()
:**› Attributes**: Readonly


.. _property_CloudOfThingsEventWriter_sendStoredDataCount:

.. _signal_CloudOfThingsEventWriter_sendStoredDataCountChanged:

.. index::
   single: sendStoredDataCount

sendStoredDataCount
+++++++++++++++++++

This property holds how many stored events from :ref:`eventDatabase <property_CloudOfThingsEventWriter_eventDatabase>` are sent at once after the connection is restored. The lowest possible value is ``1``.

:**› Type**: SignedInteger
:**› Default**: ``1``
:**› Signal**: sendStoredDataCountChanged()
:**› Attributes**: Writable


.. _property_CloudOfThingsEventWriter_sendStoredDataInterval:

.. _signal_CloudOfThingsEventWriter_sendStoredDataIntervalChanged:

.. index::
   single: sendStoredDataInterval

sendStoredDataInterval
++++++++++++++++++++++

This property holds holds the send interval in milliseconds in which stored elements from :ref:`eventDatabase <property_CloudOfThingsEventWriter_eventDatabase>` are sent after the connection is restored. The minimum value is ``100``.

:**› Type**: SignedInteger
:**› Default**: ``2000``
:**› Signal**: sendStoredDataIntervalChanged()
:**› Attributes**: Writable

Signals
*******


.. _signal_CloudOfThingsEventWriter_alarmCategoriesDataChanged:

.. index::
   single: alarmCategoriesDataChanged

alarmCategoriesDataChanged(SignedInteger index)
+++++++++++++++++++++++++++++++++++++++++++++++

This signal is emitted whenever the :ref:`List.dataChanged() <signal_List_dataChanged>` signal is emitted, i.e. the item at ``index`` in the :ref:`alarmCategories <property_CloudOfThingsEventWriter_alarmCategories>` list itself emitted the dataChanged() signal.



.. _signal_CloudOfThingsEventWriter_errorOccurred:

.. index::
   single: errorOccurred

errorOccurred()
+++++++++++++++

This signal is emitted whenever an error has occurred, regardless of whether the :ref:`error <property_CloudOfThingsEventWriter_error>` property has changed or not. In contrast to the change notification signal of the :ref:`error <property_CloudOfThingsEventWriter_error>` property this signal is also emitted several times if a certain error occurs several times in succession.


Enumerations
************


.. _enum_CloudOfThingsEventWriter_AlarmSeverity:

.. index::
   single: AlarmSeverity

AlarmSeverity
+++++++++++++

This enumeration describes the serverity of an alarm in Cloud of Things. A fixed mapping from :ref:`Event <object_Event>` serverity is performed, if the events category is in :ref:`alarmCategories <property_CloudOfThingsEventWriter_alarmCategories>`.

.. index::
   single: CloudOfThingsEventWriter.Warning
.. index::
   single: CloudOfThingsEventWriter.Minor
.. index::
   single: CloudOfThingsEventWriter.Major
.. index::
   single: CloudOfThingsEventWriter.Critical
.. list-table::
  :widths: auto
  :header-rows: 1

  * - Name
    - Value
    - Description

      .. _enumitem_CloudOfThingsEventWriter_Warning:
  * - ``CloudOfThingsEventWriter.Warning``
    - ``0``
    - Lowest severity - default if not set otherwise.

      .. _enumitem_CloudOfThingsEventWriter_Minor:
  * - ``CloudOfThingsEventWriter.Minor``
    - ``1``
    - Minor severity is used when the events severity is Warning.

      .. _enumitem_CloudOfThingsEventWriter_Major:
  * - ``CloudOfThingsEventWriter.Major``
    - ``2``
    - Major severity is used when the events severity is Error.

      .. _enumitem_CloudOfThingsEventWriter_Critical:
  * - ``CloudOfThingsEventWriter.Critical``
    - ``3``
    - Critical severity is used when the events severity is Fatal.


.. _enum_CloudOfThingsEventWriter_Error:

.. index::
   single: Error

Error
+++++

This enumeration describes all errors which can occur in CloudOfThingsEventWriter objects. The most recently occurred error is stored in the :ref:`error <property_CloudOfThingsEventWriter_error>` property.

.. index::
   single: CloudOfThingsEventWriter.NoError
.. index::
   single: CloudOfThingsEventWriter.InvalidClient
.. index::
   single: CloudOfThingsEventWriter.InvalidIdError
.. list-table::
  :widths: auto
  :header-rows: 1

  * - Name
    - Value
    - Description

      .. _enumitem_CloudOfThingsEventWriter_NoError:
  * - ``CloudOfThingsEventWriter.NoError``
    - ``0``
    - No error occurred or was detected.

      .. _enumitem_CloudOfThingsEventWriter_InvalidClient:
  * - ``CloudOfThingsEventWriter.InvalidClient``
    - ``1``
    - No CloudOfThingsClient set or found.

      .. _enumitem_CloudOfThingsEventWriter_InvalidIdError:
  * - ``CloudOfThingsEventWriter.InvalidIdError``
    - ``2``
    - Empty or invalid object id.


.. _example_CloudOfThingsEventWriter:


Example
*******

.. code-block:: qml

    
    import InCore.Foundation 2.5
    import InCore.CloudOfThings 2.5
    
    Application {
    
        EventLog {
            outputs: [ eventWriter ]
            EventCategory { id: measurementValueCategory }
            EventGroup {
                Event {
                    id: temperatureEvent
                    description: "temperature above 70°C"
                }
                Event {
                    id: deviceStartedEvent
                    description: "device started"
                }
                Event {
                    id: measurementValueEvent
                    description: "measurement above threshold"
                    category: measurementValueCategory
                    severity: Event.Error
                }
            }
        }
    
        //trigger events here
    
        CloudOfThingsClient {
            id: client
            tenant: "mustercloud"
            transport.tenantForMQTT: "nb-iot"
    
            registrator {
                isRegistered: true
                password: "y0urAwes@meP4ssword"
            }
    
            CloudOfThingsEventWriter {
                id: eventWriter
                //events with a category in alarmCategories are sent as alarm, all other as event
                alarmCategories: [ measurementValueCategory ]
    
                eventDatabase {
                    bufferSize: 500
                }
            }
        }
    }
    