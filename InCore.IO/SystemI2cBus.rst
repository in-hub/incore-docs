
.. _object_SystemI2cBus:


:index:`SystemI2cBus`
---------------------

Description
***********

The SystemI2cBus object is an :ref:`I2cBus <object_I2cBus>` implementation providing access to devices on an I2C bus on the local system.

This object was introduced in InCore 2.5.

:**› Inherits**: :ref:`I2cBus <object_I2cBus>`

Overview
********

Properties
++++++++++

.. hlist::
  :columns: 1

  * :ref:`error <property_SystemI2cBus_error>`
  * :ref:`errorString <property_SystemI2cBus_errorString>`
  * :ref:`index <property_SystemI2cBus_index>`
  * :ref:`I2cBus.devices <property_I2cBus_devices>`
  * :ref:`I2cBus.speed <property_I2cBus_speed>`
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

  * :ref:`errorOccurred() <signal_SystemI2cBus_errorOccurred>`
  * :ref:`I2cBus.devicesDataChanged() <signal_I2cBus_devicesDataChanged>`
  * :ref:`Object.completed() <signal_Object_completed>`

Enumerations
++++++++++++

.. hlist::
  :columns: 1

  * :ref:`Error <enum_SystemI2cBus_Error>`



Properties
**********


.. _property_SystemI2cBus_error:

.. _signal_SystemI2cBus_errorChanged:

.. index::
   single: error

error
+++++

This property holds the most recently occurred error or :ref:`SystemI2cBus.NoError <enumitem_SystemI2cBus_NoError>` if no error occurred. If the same error occurs multiple times this property does not change. Use the :ref:`errorOccurred() <signal_SystemI2cBus_errorOccurred>` signal to detect multiple occurrences of the same error.

:**› Type**: :ref:`Error <enum_SystemI2cBus_Error>`
:**› Signal**: errorChanged()
:**› Attributes**: Readonly


.. _property_SystemI2cBus_errorString:

.. _signal_SystemI2cBus_errorStringChanged:

.. index::
   single: errorString

errorString
+++++++++++

This property holds the current human readable error string corresponding to the current value in the :ref:`error <property_SystemI2cBus_error>` property. It may include additional information such as failure reasons or locations.

:**› Type**: String
:**› Signal**: errorStringChanged()
:**› Attributes**: Readonly


.. _property_SystemI2cBus_index:

.. _signal_SystemI2cBus_indexChanged:

.. index::
   single: index

index
+++++

This property holds the I2C bus number.

:**› Type**: UnsignedInteger
:**› Default**: ``0``
:**› Signal**: indexChanged()
:**› Attributes**: Writable

Signals
*******


.. _signal_SystemI2cBus_errorOccurred:

.. index::
   single: errorOccurred

errorOccurred()
+++++++++++++++

This signal is emitted whenever an error has occurred, regardless of whether the :ref:`error <property_SystemI2cBus_error>` property has changed or not. In contrast to the change notification signal of the :ref:`error <property_SystemI2cBus_error>` property this signal is also emitted several times if a certain error occurs several times in succession.


Enumerations
************


.. _enum_SystemI2cBus_Error:

.. index::
   single: Error

Error
+++++

This enumeration describes all errors which can occur in SystemI2cBus objects. The most recently occurred error is stored in the :ref:`error <property_SystemI2cBus_error>` property.

.. index::
   single: SystemI2cBus.NoError
.. index::
   single: SystemI2cBus.DeviceOpenError
.. index::
   single: SystemI2cBus.ReadError
.. index::
   single: SystemI2cBus.WriteError
.. list-table::
  :widths: auto
  :header-rows: 1

  * - Name
    - Value
    - Description

      .. _enumitem_SystemI2cBus_NoError:
  * - ``SystemI2cBus.NoError``
    - ``0``
    - No error occurred or was detected.

      .. _enumitem_SystemI2cBus_DeviceOpenError:
  * - ``SystemI2cBus.DeviceOpenError``
    - ``1``
    - Device could not be opened.

      .. _enumitem_SystemI2cBus_ReadError:
  * - ``SystemI2cBus.ReadError``
    - ``2``
    - Failed to read the specified number of bytes from configured address.

      .. _enumitem_SystemI2cBus_WriteError:
  * - ``SystemI2cBus.WriteError``
    - ``3``
    - Failed to write the specified number of bytes to configured address.

