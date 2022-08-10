
.. _object_DatabaseMeasurementWriter:


:index:`DatabaseMeasurementWriter`
----------------------------------

Description
***********

The DatabaseMeasurementWriter object encapsulates a :ref:`LocalDatabase <object_LocalDatabase>` to store :ref:`Measurement <object_Measurement>` objects, mainly used for implementing :ref:`MeasurementBufferDatabase <object_MeasurementBufferDatabase>`.

This object was introduced in InCore 2.5.

:**› Inherits**: :ref:`Object <object_Object>`
:**› Inherited by**: :ref:`MeasurementBufferDatabase <object_MeasurementBufferDatabase>`

Overview
********

Properties
++++++++++

.. hlist::
  :columns: 1

  * :ref:`database <property_DatabaseMeasurementWriter_database>`
  * :ref:`databaseTable <property_DatabaseMeasurementWriter_databaseTable>`
  * :ref:`measurements <property_DatabaseMeasurementWriter_measurements>`
  * :ref:`Object.objectId <property_Object_objectId>`
  * :ref:`Object.parent <property_Object_parent>`

Methods
+++++++

.. hlist::
  :columns: 1

  * :ref:`clear() <method_DatabaseMeasurementWriter_clear>`
  * :ref:`datasetCount() <method_DatabaseMeasurementWriter_datasetCount>`
  * :ref:`store() <method_DatabaseMeasurementWriter_store>`
  * :ref:`Object.deserializeProperties() <method_Object_deserializeProperties>`
  * :ref:`Object.fromJson() <method_Object_fromJson>`
  * :ref:`Object.serializeProperties() <method_Object_serializeProperties>`
  * :ref:`Object.toJson() <method_Object_toJson>`

Signals
+++++++

.. hlist::
  :columns: 1

  * :ref:`measurementsDataChanged() <signal_DatabaseMeasurementWriter_measurementsDataChanged>`
  * :ref:`Object.completed() <signal_Object_completed>`



Properties
**********


.. _property_DatabaseMeasurementWriter_database:

.. _signal_DatabaseMeasurementWriter_databaseChanged:

.. index::
   single: database

database
++++++++

This property holds a reference to the internal :ref:`LocalDatabase <object_LocalDatabase>` instance used for storing the measurements.

This property was introduced in InCore 2.6.

:**› Type**: :ref:`LocalDatabase <object_LocalDatabase>`
:**› Signal**: databaseChanged()
:**› Attributes**: Readonly


.. _property_DatabaseMeasurementWriter_databaseTable:

.. _signal_DatabaseMeasurementWriter_databaseTableChanged:

.. index::
   single: databaseTable

databaseTable
+++++++++++++

This property holds a reference to the internal :ref:`DatabaseTable <object_DatabaseTable>` used for storing the measurements.

This property was introduced in InCore 2.6.

:**› Type**: :ref:`DatabaseTable <object_DatabaseTable>`
:**› Signal**: databaseTableChanged()
:**› Attributes**: Readonly


.. _property_DatabaseMeasurementWriter_measurements:

.. _signal_DatabaseMeasurementWriter_measurementsChanged:

.. index::
   single: measurements

measurements
++++++++++++

This property holds a list of :ref:`Measurement <object_Measurement>` objects which to store in the database when calling :ref:`store() <method_DatabaseMeasurementWriter_store>`.

This property was introduced in InCore 2.6.

:**› Type**: :ref:`List <object_List>`\<:ref:`DataObject <object_DataObject>`>
:**› Signal**: measurementsChanged()
:**› Attributes**: Readonly

Methods
*******


.. _method_DatabaseMeasurementWriter_clear:

.. index::
   single: clear

clear()
+++++++

This method removes all stored :ref:`Measurement <object_Measurement>` objects from the database.



.. _method_DatabaseMeasurementWriter_datasetCount:

.. index::
   single: datasetCount

datasetCount()
++++++++++++++

This method returns the number of currently stored :ref:`Measurement <object_Measurement>` objects.

:**› Returns**: SignedInteger



.. _method_DatabaseMeasurementWriter_store:

.. index::
   single: store

store(Boolean dirtyOnly)
++++++++++++++++++++++++




Signals
*******


.. _signal_DatabaseMeasurementWriter_measurementsDataChanged:

.. index::
   single: measurementsDataChanged

measurementsDataChanged(SignedInteger index)
++++++++++++++++++++++++++++++++++++++++++++

This signal is emitted whenever the :ref:`List.dataChanged() <signal_List_dataChanged>` signal is emitted, i.e. the item at ``index`` in the :ref:`measurements <property_DatabaseMeasurementWriter_measurements>` list itself emitted the dataChanged() signal.


