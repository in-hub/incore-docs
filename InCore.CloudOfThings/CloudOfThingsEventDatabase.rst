
.. _object_CloudOfThingsEventDatabase:


:index:`CloudOfThingsEventDatabase`
-----------------------------------

Description
***********

The CloudOfThingsEventDatabase object is used in :ref:`CloudOfThingsEventWriter <object_CloudOfThingsEventWriter>` to buffer :ref:`Event <object_Event>` objects if the :ref:`CloudOfThingsClient <object_CloudOfThingsClient>` is not connected. It is designed to work with Cloud of Things only and has additional properties to limit memory usage.

:**› Inherits**: :ref:`Object <object_Object>`

Overview
********

Properties
++++++++++

.. hlist::
  :columns: 1

  * :ref:`bufferSize <property_CloudOfThingsEventDatabase_bufferSize>`
  * :ref:`error <property_CloudOfThingsEventDatabase_error>`
  * :ref:`errorString <property_CloudOfThingsEventDatabase_errorString>`
  * :ref:`storage <property_CloudOfThingsEventDatabase_storage>`
  * :ref:`Object.objectId <property_Object_objectId>`
  * :ref:`Object.parent <property_Object_parent>`

Methods
+++++++

.. hlist::
  :columns: 1

  * :ref:`clear() <method_CloudOfThingsEventDatabase_clear>`
  * :ref:`datasetCount() <method_CloudOfThingsEventDatabase_datasetCount>`
  * :ref:`Object.deserializeProperties() <method_Object_deserializeProperties>`
  * :ref:`Object.fromJson() <method_Object_fromJson>`
  * :ref:`Object.serializeProperties() <method_Object_serializeProperties>`
  * :ref:`Object.toJson() <method_Object_toJson>`

Signals
+++++++

.. hlist::
  :columns: 1

  * :ref:`errorOccurred() <signal_CloudOfThingsEventDatabase_errorOccurred>`
  * :ref:`Object.completed() <signal_Object_completed>`

Enumerations
++++++++++++

.. hlist::
  :columns: 1

  * :ref:`Error <enum_CloudOfThingsEventDatabase_Error>`



Properties
**********


.. _property_CloudOfThingsEventDatabase_bufferSize:

.. _signal_CloudOfThingsEventDatabase_bufferSizeChanged:

.. index::
   single: bufferSize

bufferSize
++++++++++

This property holds how many :ref:`Event <object_Event>` objects can be stored. If this limit is reached the oldest events will be removed. Set to ``0`` will disable buffering.

:**› Type**: SignedInteger
:**› Default**: ``100000``
:**› Signal**: bufferSizeChanged()
:**› Attributes**: Writable


.. _property_CloudOfThingsEventDatabase_error:

.. _signal_CloudOfThingsEventDatabase_errorChanged:

.. index::
   single: error

error
+++++

This property holds the most recently occurred error or :ref:`CloudOfThingsEventDatabase.NoError <enumitem_CloudOfThingsEventDatabase_NoError>` if no error occurred. If the same error occurs multiple times this property does not change. Use the :ref:`errorOccurred() <signal_CloudOfThingsEventDatabase_errorOccurred>` signal to detect multiple occurrences of the same error.

:**› Type**: :ref:`Error <enum_CloudOfThingsEventDatabase_Error>`
:**› Signal**: errorChanged()
:**› Attributes**: Readonly


.. _property_CloudOfThingsEventDatabase_errorString:

.. _signal_CloudOfThingsEventDatabase_errorStringChanged:

.. index::
   single: errorString

errorString
+++++++++++

This property holds the current human readable error string corresponding to the current value in the :ref:`error <property_CloudOfThingsEventDatabase_error>` property. It may include additional information such as failure reasons or locations.

:**› Type**: String
:**› Signal**: errorStringChanged()
:**› Attributes**: Readonly


.. _property_CloudOfThingsEventDatabase_storage:

.. _signal_CloudOfThingsEventDatabase_storageChanged:

.. index::
   single: storage

storage
+++++++

This property holds the :ref:`Storage <object_Storage>` where the database is stored.

:**› Type**: :ref:`Storage <object_Storage>`
:**› Signal**: storageChanged()
:**› Attributes**: Writable, Optional

Methods
*******


.. _method_CloudOfThingsEventDatabase_clear:

.. index::
   single: clear

clear()
+++++++

This method removes all stored :ref:`Event <object_Event>` objects.



.. _method_CloudOfThingsEventDatabase_datasetCount:

.. index::
   single: datasetCount

datasetCount()
++++++++++++++

This method is a getter of the number of currently stored :ref:`Event <object_Event>` objects.

:**› Returns**: SignedInteger


Signals
*******


.. _signal_CloudOfThingsEventDatabase_errorOccurred:

.. index::
   single: errorOccurred

errorOccurred()
+++++++++++++++

This signal is emitted whenever an error has occurred, regardless of whether the :ref:`error <property_CloudOfThingsEventDatabase_error>` property has changed or not. In contrast to the change notification signal of the :ref:`error <property_CloudOfThingsEventDatabase_error>` property this signal is also emitted several times if a certain error occurs several times in succession.


Enumerations
************


.. _enum_CloudOfThingsEventDatabase_Error:

.. index::
   single: Error

Error
+++++

This enumeration describes all errors which can occur in CloudOfThingsEventDatabase objects. The most recently occurred error is stored in the :ref:`error <property_CloudOfThingsEventDatabase_error>` property.

.. index::
   single: CloudOfThingsEventDatabase.NoError
.. index::
   single: CloudOfThingsEventDatabase.InvalidParentError
.. index::
   single: CloudOfThingsEventDatabase.InvalidIdError
.. list-table::
  :widths: auto
  :header-rows: 1

  * - Name
    - Value
    - Description

      .. _enumitem_CloudOfThingsEventDatabase_NoError:
  * - ``CloudOfThingsEventDatabase.NoError``
    - ``0``
    - No error occurred or was detected.

      .. _enumitem_CloudOfThingsEventDatabase_InvalidParentError:
  * - ``CloudOfThingsEventDatabase.InvalidParentError``
    - ``1``
    - Parent not set, or parent is no CloudOfThingsEventWriter.

      .. _enumitem_CloudOfThingsEventDatabase_InvalidIdError:
  * - ``CloudOfThingsEventDatabase.InvalidIdError``
    - ``2``
    - CloudOfThingsEventWriter has empty or invalid object id.

Example
*******
See :ref:`CloudOfThingsEventWriter example <example_CloudOfThingsEventWriter>` on how to use CloudOfThingsEventDatabase.
