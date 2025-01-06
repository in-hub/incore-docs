
.. _object_SystemSpiBus:


:index:`SystemSpiBus`
---------------------

Description
***********

The SystemSpiBus object is an :ref:`SpiBus <object_SpiBus>` implementation providing access to devices on an SPI bus on the local system.

This object was introduced in InCore 2.8.

:**› Inherits**: :ref:`SpiBus <object_SpiBus>`

Overview
********

Properties
++++++++++

.. hlist::
  :columns: 2

  * :ref:`error <property_SystemSpiBus_error>`
  * :ref:`errorString <property_SystemSpiBus_errorString>`
  * :ref:`index <property_SystemSpiBus_index>`
  * :ref:`SpiBus.bitsPerWord <property_SpiBus_bitsPerWord>`
  * :ref:`SpiBus.devices <property_SpiBus_devices>`
  * :ref:`SpiBus.mode <property_SpiBus_mode>`
  * :ref:`SpiBus.speed <property_SpiBus_speed>`
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

  * :ref:`errorOccurred() <signal_SystemSpiBus_errorOccurred>`
  * :ref:`SpiBus.devicesDataChanged() <signal_SpiBus_devicesDataChanged>`
  * :ref:`Object.completed() <signal_Object_completed>`

Enumerations
++++++++++++

.. hlist::
  :columns: 1

  * :ref:`Error <enum_SystemSpiBus_Error>`
  * :ref:`SpiBus.Mode <enum_SpiBus_Mode>`



Properties
**********


.. _property_SystemSpiBus_error:

.. _signal_SystemSpiBus_errorChanged:

.. index::
   single: error

error
+++++

This property holds the most recently occurred error or :ref:`SystemSpiBus.NoError <enumitem_SystemSpiBus_NoError>` if no error occurred. If the same error occurs multiple times this property does not change. Use the :ref:`errorOccurred() <signal_SystemSpiBus_errorOccurred>` signal to detect multiple occurrences of the same error.

:**› Type**: :ref:`Error <enum_SystemSpiBus_Error>`
:**› Signal**: errorChanged()
:**› Attributes**: Readonly


.. _property_SystemSpiBus_errorString:

.. _signal_SystemSpiBus_errorStringChanged:

.. index::
   single: errorString

errorString
+++++++++++

This property holds the current human readable error string corresponding to the current value in the :ref:`error <property_SystemSpiBus_error>` property. It may include additional information such as failure reasons or locations.

:**› Type**: String
:**› Signal**: errorStringChanged()
:**› Attributes**: Readonly


.. _property_SystemSpiBus_index:

.. _signal_SystemSpiBus_indexChanged:

.. index::
   single: index

index
+++++

This property holds the SPI bus number.

:**› Type**: UnsignedInteger
:**› Default**: ``4294967295``
:**› Signal**: indexChanged()
:**› Attributes**: Writable

Signals
*******


.. _signal_SystemSpiBus_errorOccurred:

.. index::
   single: errorOccurred

errorOccurred()
+++++++++++++++

This signal is emitted whenever an error has occurred, regardless of whether the :ref:`error <property_SystemSpiBus_error>` property has changed or not. In contrast to the change notification signal of the :ref:`error <property_SystemSpiBus_error>` property this signal is also emitted several times if a certain error occurs several times in succession.


Enumerations
************


.. _enum_SystemSpiBus_Error:

.. index::
   single: Error

Error
+++++

This enumeration describes all errors which can occur in SystemSpiBus objects. The most recently occurred error is stored in the :ref:`error <property_SystemSpiBus_error>` property.

.. index::
   single: SystemSpiBus.NoError
.. index::
   single: SystemSpiBus.DeviceOpenError
.. index::
   single: SystemSpiBus.TransferError
.. list-table::
  :widths: auto
  :header-rows: 1

  * - Name
    - Value
    - Description

      .. _enumitem_SystemSpiBus_NoError:
  * - ``SystemSpiBus.NoError``
    - ``0``
    - No error occurred or was detected.

      .. _enumitem_SystemSpiBus_DeviceOpenError:
  * - ``SystemSpiBus.DeviceOpenError``
    - ``1``
    - Device could not be opened.

      .. _enumitem_SystemSpiBus_TransferError:
  * - ``SystemSpiBus.TransferError``
    - ``2``
    - Failed to transfered the specified number of bytes from/to configured address.

