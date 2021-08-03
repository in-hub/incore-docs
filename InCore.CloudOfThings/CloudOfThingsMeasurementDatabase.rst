
.. _object_CloudOfThingsMeasurementDatabase:


:index:`CloudOfThingsMeasurementDatabase`
-----------------------------------------

Description
***********

The CloudOfThingsMeasurementDatabase object encapsulates a :ref:`LocalDatabase <object_LocalDatabase>` which stores :ref:`Measurement <object_Measurement>` objects if the :ref:`CloudOfThingsClient <object_CloudOfThingsClient>` is not connected. It is designed to work with Cloud of Things only and has additional properties to limit memory usage.

:**› Inherits**: :ref:`Object <object_Object>`

Overview
********

Properties
++++++++++

.. hlist::
  :columns: 1

  * :ref:`bufferSize <property_CloudOfThingsMeasurementDatabase_bufferSize>`
  * :ref:`error <property_CloudOfThingsMeasurementDatabase_error>`
  * :ref:`errorString <property_CloudOfThingsMeasurementDatabase_errorString>`
  * :ref:`storage <property_CloudOfThingsMeasurementDatabase_storage>`
  * :ref:`transmitOrder <property_CloudOfThingsMeasurementDatabase_transmitOrder>`
  * :ref:`Object.objectId <property_Object_objectId>`
  * :ref:`Object.parent <property_Object_parent>`

Methods
+++++++

.. hlist::
  :columns: 1

  * :ref:`clear() <method_CloudOfThingsMeasurementDatabase_clear>`
  * :ref:`datasetCount() <method_CloudOfThingsMeasurementDatabase_datasetCount>`
  * :ref:`Object.deserializeProperties() <method_Object_deserializeProperties>`
  * :ref:`Object.fromJson() <method_Object_fromJson>`
  * :ref:`Object.toJson() <method_Object_toJson>`

Signals
+++++++

.. hlist::
  :columns: 1

  * :ref:`errorOccurred() <signal_CloudOfThingsMeasurementDatabase_errorOccurred>`
  * :ref:`Object.completed() <signal_Object_completed>`

Enumerations
++++++++++++

.. hlist::
  :columns: 1

  * :ref:`Error <enum_CloudOfThingsMeasurementDatabase_Error>`
  * :ref:`TransmitOrder <enum_CloudOfThingsMeasurementDatabase_TransmitOrder>`



Properties
**********


.. _property_CloudOfThingsMeasurementDatabase_bufferSize:

.. _signal_CloudOfThingsMeasurementDatabase_bufferSizeChanged:

.. index::
   single: bufferSize

bufferSize
++++++++++

This property holds the number of :ref:`Measurement <object_Measurement>` objects which can be stored at most. If this limit is reached the oldest measurement will be removed. Setting to ``0`` will disable buffering.

:**› Type**: SignedInteger
:**› Default**: ``100000``
:**› Signal**: bufferSizeChanged()
:**› Attributes**: Writable


.. _property_CloudOfThingsMeasurementDatabase_error:

.. _signal_CloudOfThingsMeasurementDatabase_errorChanged:

.. index::
   single: error

error
+++++

This property holds the most recently occurred error or :ref:`CloudOfThingsMeasurementDatabase.NoError <enumitem_CloudOfThingsMeasurementDatabase_NoError>` if no error occurred. If the same error occurs multiple times this property does not change. Use the :ref:`errorOccurred() <signal_CloudOfThingsMeasurementDatabase_errorOccurred>` signal to detect multiple occurrences of the same error.

:**› Type**: :ref:`Error <enum_CloudOfThingsMeasurementDatabase_Error>`
:**› Signal**: errorChanged()
:**› Attributes**: Readonly


.. _property_CloudOfThingsMeasurementDatabase_errorString:

.. _signal_CloudOfThingsMeasurementDatabase_errorStringChanged:

.. index::
   single: errorString

errorString
+++++++++++

This property holds the current human readable error string corresponding to the current value in the :ref:`error <property_CloudOfThingsMeasurementDatabase_error>` property. It may include additional information such as failure reasons or locations.

:**› Type**: String
:**› Signal**: errorStringChanged()
:**› Attributes**: Readonly


.. _property_CloudOfThingsMeasurementDatabase_storage:

.. _signal_CloudOfThingsMeasurementDatabase_storageChanged:

.. index::
   single: storage

storage
+++++++

This property holds the storage where the database is saved. If left blank a :ref:`LocalStorage <object_LocalStorage>` object is used.

:**› Type**: :ref:`Storage <object_Storage>`
:**› Signal**: storageChanged()
:**› Attributes**: Writable, Optional


.. _property_CloudOfThingsMeasurementDatabase_transmitOrder:

.. _signal_CloudOfThingsMeasurementDatabase_transmitOrderChanged:

.. index::
   single: transmitOrder

transmitOrder
+++++++++++++

This property holds the order in which the :ref:`Measurement <object_Measurement>` objects are sent, when a connection is restored.

:**› Type**: :ref:`CloudOfThingsMeasurementDatabase.TransmitOrder <enum_CloudOfThingsMeasurementDatabase_TransmitOrder>`
:**› Default**: :ref:`CloudOfThingsMeasurementDatabase.Descending <enumitem_CloudOfThingsMeasurementDatabase_Descending>`
:**› Signal**: transmitOrderChanged()
:**› Attributes**: Writable

Methods
*******


.. _method_CloudOfThingsMeasurementDatabase_clear:

.. index::
   single: clear

clear()
+++++++

This method removes all stored :ref:`Measurement <object_Measurement>` objects from the database.



.. _method_CloudOfThingsMeasurementDatabase_datasetCount:

.. index::
   single: datasetCount

datasetCount()
++++++++++++++

This method returns the number of currently stored :ref:`Measurement <object_Measurement>` objects. This will be less or equal :ref:`bufferSize <property_CloudOfThingsMeasurementDatabase_bufferSize>`.

:**› Returns**: SignedInteger


Signals
*******


.. _signal_CloudOfThingsMeasurementDatabase_errorOccurred:

.. index::
   single: errorOccurred

errorOccurred()
+++++++++++++++

This signal is emitted whenever an error has occurred, regardless of whether the :ref:`error <property_CloudOfThingsMeasurementDatabase_error>` property has changed or not. In contrast to the change notification signal of the :ref:`error <property_CloudOfThingsMeasurementDatabase_error>` property this signal is also emitted several times if a certain error occurs several times in succession.


Enumerations
************


.. _enum_CloudOfThingsMeasurementDatabase_Error:

.. index::
   single: Error

Error
+++++

This enumeration describes all errors which can occur in CloudOfThingsMeasurementDatabase objects. The most recently occurred error is stored in the :ref:`error <property_CloudOfThingsMeasurementDatabase_error>` property.

.. index::
   single: CloudOfThingsMeasurementDatabase.NoError
.. index::
   single: CloudOfThingsMeasurementDatabase.InvalidParentError
.. index::
   single: CloudOfThingsMeasurementDatabase.InvalidIdError
.. list-table::
  :widths: auto
  :header-rows: 1

  * - Name
    - Value
    - Description

      .. _enumitem_CloudOfThingsMeasurementDatabase_NoError:
  * - ``CloudOfThingsMeasurementDatabase.NoError``
    - ``0``
    - No error occurred or was detected.

      .. _enumitem_CloudOfThingsMeasurementDatabase_InvalidParentError:
  * - ``CloudOfThingsMeasurementDatabase.InvalidParentError``
    - ``1``
    - Parent not set, or parent is no CloudOfThingsMeasurementWriter.

      .. _enumitem_CloudOfThingsMeasurementDatabase_InvalidIdError:
  * - ``CloudOfThingsMeasurementDatabase.InvalidIdError``
    - ``2``
    - CloudOfThingsMeasurementWriter has empty or invalid object id.


.. _enum_CloudOfThingsMeasurementDatabase_TransmitOrder:

.. index::
   single: TransmitOrder

TransmitOrder
+++++++++++++

This enumeration describes the mode in which order buffered :ref:`Measurement <object_Measurement>` objects will be sent when a connection is restored.

.. index::
   single: CloudOfThingsMeasurementDatabase.Ascending
.. index::
   single: CloudOfThingsMeasurementDatabase.Descending
.. list-table::
  :widths: auto
  :header-rows: 1

  * - Name
    - Value
    - Description

      .. _enumitem_CloudOfThingsMeasurementDatabase_Ascending:
  * - ``CloudOfThingsMeasurementDatabase.Ascending``
    - ``0``
    - Send data objects in ascending order - oldest first.

      .. _enumitem_CloudOfThingsMeasurementDatabase_Descending:
  * - ``CloudOfThingsMeasurementDatabase.Descending``
    - ``1``
    - Send data objects in descending order - latest first.

Example
*******
See :ref:`CloudOfThingsMeasurementWriter example <example_CloudOfThingsMeasurementWriter>` on how to use CloudOfThingsMeasurementDatabase.
