
.. _object_I2cEeprom:


:index:`I2cEeprom`
------------------

Description
***********

The I2cEeprom object implements a driver for I2C-based EEPROMs, usually referred to as AT24 or similar. The data in the EEPROM can be mapped into the :ref:`data <property_I2cEeprom_data>` property

This object was introduced in InCore 2.0.

:**› Inherits**: :ref:`I2cDevice <object_I2cDevice>`

Overview
********

Properties
++++++++++

.. hlist::
  :columns: 1

  * :ref:`data <property_I2cEeprom_data>`
  * :ref:`dataAddress <property_I2cEeprom_dataAddress>`
  * :ref:`dataSize <property_I2cEeprom_dataSize>`
  * :ref:`I2cDevice.address <property_I2cDevice_address>`
  * :ref:`Object.objectId <property_Object_objectId>`
  * :ref:`Object.parent <property_Object_parent>`

Methods
+++++++

.. hlist::
  :columns: 1

  * :ref:`read() <method_I2cEeprom_read>`
  * :ref:`I2cDevice.read() <method_I2cDevice_read>`
  * :ref:`I2cDevice.write() <method_I2cDevice_write>`
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


.. _property_I2cEeprom_data:

.. _signal_I2cEeprom_dataChanged:

.. index::
   single: data

data
++++

This property holds a mapped data buffer containing the EEPROM data starting from :ref:`dataAddress <property_I2cEeprom_dataAddress>`. It's cached and only read again whenever :ref:`dataAddress <property_I2cEeprom_dataAddress>` or :ref:`dataSize <property_I2cEeprom_dataSize>` are changed.

:**› Type**: :ref:`ByteArray <object_ByteArray>`
:**› Signal**: dataChanged()
:**› Attributes**: Readonly


.. _property_I2cEeprom_dataAddress:

.. _signal_I2cEeprom_dataAddressChanged:

.. index::
   single: dataAddress

dataAddress
+++++++++++

This property holds the address where to start reading :ref:`data <property_I2cEeprom_data>` from the EEPROM.

:**› Type**: UnsignedInteger
:**› Default**: ``0``
:**› Signal**: dataAddressChanged()
:**› Attributes**: Writable


.. _property_I2cEeprom_dataSize:

.. _signal_I2cEeprom_dataSizeChanged:

.. index::
   single: dataSize

dataSize
++++++++

This property holds the number of bytes to read from the EEPROM into the :ref:`data <property_I2cEeprom_data>` property.

:**› Type**: UnsignedInteger
:**› Default**: ``0``
:**› Signal**: dataSizeChanged()
:**› Attributes**: Writable

Methods
*******


.. _method_I2cEeprom_read:

.. index::
   single: read

read(UnsignedInteger startAddress, UnsignedInteger bytes)
+++++++++++++++++++++++++++++++++++++++++++++++++++++++++

This method reads – starting from a given address – the specified number of bytes from the EEPROM.

:**› Returns**: ArrayBuffer



.. _example_I2cEeprom:


Example
*******

.. code-block:: qml

    import InCore.Foundation 2.0
    import InCore.IO 2.0
    
    Application {
        FtdiI2cBus {
            I2cEeprom {
                id: eeprom
                address: 0x50
                dataAddress: 0x0
                dataSize: 16
            }
        }
    
        onCompleted: console.log(eeprom.data.hex)
    }
    