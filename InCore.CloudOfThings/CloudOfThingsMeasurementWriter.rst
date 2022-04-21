
.. _object_CloudOfThingsMeasurementWriter:


:index:`CloudOfThingsMeasurementWriter`
---------------------------------------

Description
***********

The CloudOfThingsMeasurementWriter object exports :ref:`Measurement <object_Measurement>` objects to the Cloud of Things. Measurements grouped in a :ref:`MeasurementGroup <object_MeasurementGroup>` are displayed in one diagram.

:**› Inherits**: :ref:`DataObjectWriter <object_DataObjectWriter>`

Overview
********

Properties
++++++++++

.. hlist::
  :columns: 2

  * :ref:`bufferDatabase <property_CloudOfThingsMeasurementWriter_bufferDatabase>`
  * :ref:`client <property_CloudOfThingsMeasurementWriter_client>`
  * :ref:`error <property_CloudOfThingsMeasurementWriter_error>`
  * :ref:`errorString <property_CloudOfThingsMeasurementWriter_errorString>`
  * :ref:`DataObjectWriter.datasetCount <property_DataObjectWriter_datasetCount>`
  * :ref:`DataObjectWriter.objects <property_DataObjectWriter_objects>`
  * :ref:`DataObjectWriter.running <property_DataObjectWriter_running>`
  * :ref:`DataObjectWriter.submitChangedObjectsOnly <property_DataObjectWriter_submitChangedObjectsOnly>`
  * :ref:`DataObjectWriter.submitInterval <property_DataObjectWriter_submitInterval>`
  * :ref:`DataObjectWriter.submitMode <property_DataObjectWriter_submitMode>`
  * :ref:`Object.objectId <property_Object_objectId>`
  * :ref:`Object.parent <property_Object_parent>`

Methods
+++++++

.. hlist::
  :columns: 2

  * :ref:`DataObjectWriter.close() <method_DataObjectWriter_close>`
  * :ref:`DataObjectWriter.open() <method_DataObjectWriter_open>`
  * :ref:`DataObjectWriter.submit() <method_DataObjectWriter_submit>`
  * :ref:`DataObjectWriter.sync() <method_DataObjectWriter_sync>`
  * :ref:`DataObjectWriter.truncate() <method_DataObjectWriter_truncate>`
  * :ref:`Object.deserializeProperties() <method_Object_deserializeProperties>`
  * :ref:`Object.fromJson() <method_Object_fromJson>`
  * :ref:`Object.serializeProperties() <method_Object_serializeProperties>`
  * :ref:`Object.toJson() <method_Object_toJson>`

Signals
+++++++

.. hlist::
  :columns: 1

  * :ref:`errorOccurred() <signal_CloudOfThingsMeasurementWriter_errorOccurred>`
  * :ref:`DataObjectWriter.objectsDataChanged() <signal_DataObjectWriter_objectsDataChanged>`
  * :ref:`DataObjectWriter.submitted() <signal_DataObjectWriter_submitted>`
  * :ref:`DataObjectWriter.truncated() <signal_DataObjectWriter_truncated>`
  * :ref:`Object.completed() <signal_Object_completed>`

Enumerations
++++++++++++

.. hlist::
  :columns: 1

  * :ref:`Error <enum_CloudOfThingsMeasurementWriter_Error>`
  * :ref:`DataObjectWriter.SubmitMode <enum_DataObjectWriter_SubmitMode>`



Properties
**********


.. _property_CloudOfThingsMeasurementWriter_bufferDatabase:

.. _signal_CloudOfThingsMeasurementWriter_bufferDatabaseChanged:

.. index::
   single: bufferDatabase

bufferDatabase
++++++++++++++

This property holds the database to which the measurements are written temporarily when :ref:`MeasurementBufferDatabase.buffering <property_MeasurementBufferDatabase_buffering>` is set to ``true`` and the Cloud of Things client is offline or not connected.

This property was introduced in InCore 2.5.

:**› Type**: :ref:`MeasurementBufferDatabase <object_MeasurementBufferDatabase>`
:**› Signal**: bufferDatabaseChanged()
:**› Attributes**: Readonly


.. _property_CloudOfThingsMeasurementWriter_client:

.. _signal_CloudOfThingsMeasurementWriter_clientChanged:

.. index::
   single: client

client
++++++

This property holds the Cloud of Things client. This property can be left blank if the parent object is a :ref:`CloudOfThingsClient <object_CloudOfThingsClient>`.

:**› Type**: :ref:`CloudOfThingsClient <object_CloudOfThingsClient>`
:**› Signal**: clientChanged()
:**› Attributes**: Writable


.. _property_CloudOfThingsMeasurementWriter_error:

.. _signal_CloudOfThingsMeasurementWriter_errorChanged:

.. index::
   single: error

error
+++++

This property holds the most recently occurred error or :ref:`CloudOfThingsMeasurementWriter.NoError <enumitem_CloudOfThingsMeasurementWriter_NoError>` if no error occurred. If the same error occurs multiple times this property does not change. Use the :ref:`errorOccurred() <signal_CloudOfThingsMeasurementWriter_errorOccurred>` signal to detect multiple occurrences of the same error.

:**› Type**: :ref:`Error <enum_CloudOfThingsMeasurementWriter_Error>`
:**› Signal**: errorChanged()
:**› Attributes**: Readonly


.. _property_CloudOfThingsMeasurementWriter_errorString:

.. _signal_CloudOfThingsMeasurementWriter_errorStringChanged:

.. index::
   single: errorString

errorString
+++++++++++

This property holds the current human readable error string corresponding to the current value in the :ref:`error <property_CloudOfThingsMeasurementWriter_error>` property. It may include additional information such as failure reasons or locations.

:**› Type**: String
:**› Signal**: errorStringChanged()
:**› Attributes**: Readonly

Signals
*******


.. _signal_CloudOfThingsMeasurementWriter_errorOccurred:

.. index::
   single: errorOccurred

errorOccurred()
+++++++++++++++

This signal is emitted whenever an error has occurred, regardless of whether the :ref:`error <property_CloudOfThingsMeasurementWriter_error>` property has changed or not. In contrast to the change notification signal of the :ref:`error <property_CloudOfThingsMeasurementWriter_error>` property this signal is also emitted several times if a certain error occurs several times in succession.


Enumerations
************


.. _enum_CloudOfThingsMeasurementWriter_Error:

.. index::
   single: Error

Error
+++++

This enumeration describes all errors which can occur in CloudOfThingsMeasurementWriter objects. The most recently occurred error is stored in the :ref:`error <property_CloudOfThingsMeasurementWriter_error>` property.

.. index::
   single: CloudOfThingsMeasurementWriter.NoError
.. index::
   single: CloudOfThingsMeasurementWriter.InvalidClient
.. index::
   single: CloudOfThingsMeasurementWriter.InvalidIdError
.. index::
   single: CloudOfThingsMeasurementWriter.InvalidGroupName
.. index::
   single: CloudOfThingsMeasurementWriter.InvalidMeasurementName
.. index::
   single: CloudOfThingsMeasurementWriter.InvalidUnit
.. list-table::
  :widths: auto
  :header-rows: 1

  * - Name
    - Value
    - Description

      .. _enumitem_CloudOfThingsMeasurementWriter_NoError:
  * - ``CloudOfThingsMeasurementWriter.NoError``
    - ``0``
    - No error occurred or was detected.

      .. _enumitem_CloudOfThingsMeasurementWriter_InvalidClient:
  * - ``CloudOfThingsMeasurementWriter.InvalidClient``
    - ``1``
    - No CloudOfThingsClient set or found.

      .. _enumitem_CloudOfThingsMeasurementWriter_InvalidIdError:
  * - ``CloudOfThingsMeasurementWriter.InvalidIdError``
    - ``2``
    - Empty or invalid object id.

      .. _enumitem_CloudOfThingsMeasurementWriter_InvalidGroupName:
  * - ``CloudOfThingsMeasurementWriter.InvalidGroupName``
    - ``3``
    - Invalid name set for measurement group, '.', ',' and '$' not allowed.

      .. _enumitem_CloudOfThingsMeasurementWriter_InvalidMeasurementName:
  * - ``CloudOfThingsMeasurementWriter.InvalidMeasurementName``
    - ``4``
    - No or invalid name set for measurement, '.', ',' and '$' not allowed.

      .. _enumitem_CloudOfThingsMeasurementWriter_InvalidUnit:
  * - ``CloudOfThingsMeasurementWriter.InvalidUnit``
    - ``5``
    - Invalid unit, no comma allowed.


.. _example_CloudOfThingsMeasurementWriter:


Example
*******

.. code-block:: qml

    import InCore.Foundation 2.5
    import InCore.CloudOfThings 2.5
    import InCore.Database 2.5
    
    Application {
    
        CloudOfThingsClient {
            id: client
            tenant: "mustercloud"
            transport {
                tenantForMQTT: "nb-iot"
    
                cleanSessionMQTT: false
                keepAlive: 2000
                //set high interval values to reduce traffic
                requestOperationsIntervalMQTT: 10 * 60 * 1000
    
                //log important state changes
                onConnected: console.log( "Cloud of Things client connected" )
                onErrorChanged: console.log( "oh... error occurred", errorString )
            }
    
            registrator {
                isRegistered: true
                password: "y0urAwes@meP4ssword"
            }
    
            CloudOfThingsMeasurementWriter {
                id: measurementWriter
    
                //buffer data if connection is lost
                bufferDatabase    {
                    bufferSize: 5000
                    transmitOrder: MeasurementBufferDatabase.Descending
                }
    
                submitMode: CloudOfThingsMeasurementWriter.SubmitPeriodically
                submitInterval: 5000
    
                onErrorChanged: console.log( "writer error", errorString )
    
                Measurement { id: sensor1; name: "sensor1"; data: 1 }
                Measurement { id: sensor2; name: "sensor2"; data: 2 }
                Measurement { id: temp; name: "Temperature"; data: 0.0; unit: "°C" }
                //unlike other databases here no DateTime object needed
                //every measurement is send with timestamp automatically
            }
        }
    }
    
    