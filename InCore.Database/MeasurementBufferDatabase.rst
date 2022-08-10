
.. _object_MeasurementBufferDatabase:


:index:`MeasurementBufferDatabase`
----------------------------------

Description
***********

The MeasurementBufferDatabase object is a helper class to buffer :ref:`Measurement <object_Measurement>` objects in a local database whenever a remote measurement storage client (such as a Cloud of Things client or MQTT measurement writer) is offline or not connected.

This object was introduced in InCore 2.5.

:**› Inherits**: :ref:`DatabaseMeasurementWriter <object_DatabaseMeasurementWriter>`

Overview
********

Properties
++++++++++

.. hlist::
  :columns: 2

  * :ref:`bufferDrainChunkSize <property_MeasurementBufferDatabase_bufferDrainChunkSize>`
  * :ref:`bufferDrainInterval <property_MeasurementBufferDatabase_bufferDrainInterval>`
  * :ref:`bufferSize <property_MeasurementBufferDatabase_bufferSize>`
  * :ref:`buffering <property_MeasurementBufferDatabase_buffering>`
  * :ref:`transmitOrder <property_MeasurementBufferDatabase_transmitOrder>`
  * :ref:`DatabaseMeasurementWriter.database <property_DatabaseMeasurementWriter_database>`
  * :ref:`DatabaseMeasurementWriter.databaseTable <property_DatabaseMeasurementWriter_databaseTable>`
  * :ref:`DatabaseMeasurementWriter.measurements <property_DatabaseMeasurementWriter_measurements>`
  * :ref:`Object.objectId <property_Object_objectId>`
  * :ref:`Object.parent <property_Object_parent>`

Methods
+++++++

.. hlist::
  :columns: 1

  * :ref:`DatabaseMeasurementWriter.clear() <method_DatabaseMeasurementWriter_clear>`
  * :ref:`DatabaseMeasurementWriter.datasetCount() <method_DatabaseMeasurementWriter_datasetCount>`
  * :ref:`DatabaseMeasurementWriter.store() <method_DatabaseMeasurementWriter_store>`
  * :ref:`Object.deserializeProperties() <method_Object_deserializeProperties>`
  * :ref:`Object.fromJson() <method_Object_fromJson>`
  * :ref:`Object.serializeProperties() <method_Object_serializeProperties>`
  * :ref:`Object.toJson() <method_Object_toJson>`

Signals
+++++++

.. hlist::
  :columns: 1

  * :ref:`DatabaseMeasurementWriter.measurementsDataChanged() <signal_DatabaseMeasurementWriter_measurementsDataChanged>`
  * :ref:`Object.completed() <signal_Object_completed>`

Enumerations
++++++++++++

.. hlist::
  :columns: 1

  * :ref:`TransmitOrder <enum_MeasurementBufferDatabase_TransmitOrder>`



Properties
**********


.. _property_MeasurementBufferDatabase_bufferDrainChunkSize:

.. _signal_MeasurementBufferDatabase_bufferDrainChunkSizeChanged:

.. index::
   single: bufferDrainChunkSize

bufferDrainChunkSize
++++++++++++++++++++

This property holds how many buffered measurements are sent at once whenever the remote resource is online again. The lowest allowed value is ``1``.

:**› Type**: SignedInteger
:**› Default**: ``1``
:**› Signal**: bufferDrainChunkSizeChanged()
:**› Attributes**: Writable


.. _property_MeasurementBufferDatabase_bufferDrainInterval:

.. _signal_MeasurementBufferDatabase_bufferDrainIntervalChanged:

.. index::
   single: bufferDrainInterval

bufferDrainInterval
+++++++++++++++++++

This property holds the send interval in which buffered measurements are sent whenever the remote resource is online again. The lowest allowed value is ``100``.

:**› Type**: SignedInteger
:**› Default**: ``2000``
:**› Signal**: bufferDrainIntervalChanged()
:**› Attributes**: Writable


.. _property_MeasurementBufferDatabase_bufferSize:

.. _signal_MeasurementBufferDatabase_bufferSizeChanged:

.. index::
   single: bufferSize

bufferSize
++++++++++

This property holds the number of :ref:`Measurement <object_Measurement>` objects which can be buffered at most. If this limit is reached, the oldest measurement will be removed. Setting to ``0`` disables buffering.

:**› Type**: SignedInteger
:**› Default**: ``100000``
:**› Signal**: bufferSizeChanged()
:**› Attributes**: Writable


.. _property_MeasurementBufferDatabase_buffering:

.. _signal_MeasurementBufferDatabase_bufferingChanged:

.. index::
   single: buffering

buffering
+++++++++

This property holds whether measurements should be buffered in the local database whenever the remote resource is offline or not connected. Once the remote resource is online again, buffered measurements are sent at a writer-specific interval.

:**› Type**: Boolean
:**› Default**: ``true``
:**› Signal**: bufferingChanged()
:**› Attributes**: Writable


.. _property_MeasurementBufferDatabase_transmitOrder:

.. _signal_MeasurementBufferDatabase_transmitOrderChanged:

.. index::
   single: transmitOrder

transmitOrder
+++++++++++++

This property holds the order in which the :ref:`Measurement <object_Measurement>` objects are sent whenever a connection is restored.

:**› Type**: :ref:`MeasurementBufferDatabase.TransmitOrder <enum_MeasurementBufferDatabase_TransmitOrder>`
:**› Default**: :ref:`MeasurementBufferDatabase.Descending <enumitem_MeasurementBufferDatabase_Descending>`
:**› Signal**: transmitOrderChanged()
:**› Attributes**: Writable

Enumerations
************


.. _enum_MeasurementBufferDatabase_TransmitOrder:

.. index::
   single: TransmitOrder

TransmitOrder
+++++++++++++

This enumeration describes the order in which buffered :ref:`Measurement <object_Measurement>` objects are sent whenever a connection is restored.

.. index::
   single: MeasurementBufferDatabase.Ascending
.. index::
   single: MeasurementBufferDatabase.Descending
.. list-table::
  :widths: auto
  :header-rows: 1

  * - Name
    - Value
    - Description

      .. _enumitem_MeasurementBufferDatabase_Ascending:
  * - ``MeasurementBufferDatabase.Ascending``
    - ``0``
    - Send measurements in ascending order - oldest first.

      .. _enumitem_MeasurementBufferDatabase_Descending:
  * - ``MeasurementBufferDatabase.Descending``
    - ``1``
    - Send measurements in descending order - latest first.

