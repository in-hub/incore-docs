
.. _object_I2cBus:


:index:`I2cBus`
---------------

Description
***********

The I2cBus object represents an I2C bus with attached :ref:`I2cDevice <object_I2cDevice>` objects. This abstract base object provides common properties and methods only. Use a dedicated I2C bus implementation such as :ref:`SystemI2cBus <object_SystemI2cBus>` and :ref:`FtdiI2cBus <object_FtdiI2cBus>`.

:**› Inherits**: :ref:`Object <object_Object>`
:**› Inherited by**: :ref:`FtdiI2cBus <object_FtdiI2cBus>`, :ref:`SystemI2cBus <object_SystemI2cBus>`

Overview
********

Properties
++++++++++

.. hlist::
  :columns: 1

  * :ref:`devices <property_I2cBus_devices>`
  * :ref:`speed <property_I2cBus_speed>`
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

  * :ref:`devicesDataChanged() <signal_I2cBus_devicesDataChanged>`
  * :ref:`Object.completed() <signal_Object_completed>`



Properties
**********


.. _property_I2cBus_devices:

.. _signal_I2cBus_devicesChanged:

.. index::
   single: devices

devices
+++++++

This property holds a list of I2C devices to use on this bus.

:**› Type**: :ref:`List <object_List>`\<:ref:`I2cDevice <object_I2cDevice>`>
:**› Signal**: devicesChanged()
:**› Attributes**: Readonly


.. _property_I2cBus_speed:

.. _signal_I2cBus_speedChanged:

.. index::
   single: speed

speed
+++++

This property holds the bus speed in *Hz*.

:**› Type**: UnsignedInteger
:**› Default**: ``100000``
:**› Signal**: speedChanged()
:**› Attributes**: Writable

Signals
*******


.. _signal_I2cBus_devicesDataChanged:

.. index::
   single: devicesDataChanged

devicesDataChanged(SignedInteger index)
+++++++++++++++++++++++++++++++++++++++

This signal is emitted whenever the :ref:`List.dataChanged() <signal_List_dataChanged>` signal is emitted, i.e. the item at ``index`` in the :ref:`devices <property_I2cBus_devices>` list itself emitted the dataChanged() signal.

