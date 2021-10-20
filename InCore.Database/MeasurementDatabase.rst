
.. _object_MeasurementDatabase:


:index:`MeasurementDatabase`
----------------------------

Description
***********

The MeasurementDatabase object encapsulates a :ref:`LocalDatabase <object_LocalDatabase>` to store :ref:`Measurement <object_Measurement>` objects, mainly used for implementing :ref:`MeasurementBufferDatabase <object_MeasurementBufferDatabase>`.

This object was introduced in InCore 2.5.

:**› Inherits**: :ref:`Object <object_Object>`
:**› Inherited by**: :ref:`MeasurementBufferDatabase <object_MeasurementBufferDatabase>`

Overview
********

Properties
++++++++++

.. hlist::
  :columns: 1

  * :ref:`storage <property_MeasurementDatabase_storage>`
  * :ref:`Object.objectId <property_Object_objectId>`
  * :ref:`Object.parent <property_Object_parent>`

Methods
+++++++

.. hlist::
  :columns: 1

  * :ref:`clear() <method_MeasurementDatabase_clear>`
  * :ref:`datasetCount() <method_MeasurementDatabase_datasetCount>`
  * :ref:`Object.deserializeProperties() <method_Object_deserializeProperties>`
  * :ref:`Object.fromJson() <method_Object_fromJson>`
  * :ref:`Object.toJson() <method_Object_toJson>`

Signals
+++++++

.. hlist::
  :columns: 1

  * :ref:`Object.completed() <signal_Object_completed>`



Properties
**********


.. _property_MeasurementDatabase_storage:

.. _signal_MeasurementDatabase_storageChanged:

.. index::
   single: storage

storage
+++++++

This property holds the storage which the database is saved to. If left blank, an internal :ref:`LocalStorage <object_LocalStorage>` object is used.

:**› Type**: :ref:`Storage <object_Storage>`
:**› Signal**: storageChanged()
:**› Attributes**: Writable, Optional

Methods
*******


.. _method_MeasurementDatabase_clear:

.. index::
   single: clear

clear()
+++++++

This method removes all stored :ref:`Measurement <object_Measurement>` objects from the database.



.. _method_MeasurementDatabase_datasetCount:

.. index::
   single: datasetCount

datasetCount()
++++++++++++++

This method returns the number of currently stored :ref:`Measurement <object_Measurement>` objects.

:**› Returns**: SignedInteger

