
.. _object_I2cDevice:


:index:`I2cDevice`
------------------

Description
***********

The I2cDevice object represents a generic I2C device operating on a parent :ref:`I2cBus <object_I2cBus>` object. Data can be written to an I2C slave at address :ref:`address <property_I2cDevice_address>` using :ref:`write() <method_I2cDevice_write>` and read from a I2C slave using :ref:`read() <method_I2cDevice_read>`.

:**› Inherits**: :ref:`Object <object_Object>`
:**› Inherited by**: :ref:`I2cEeprom <object_I2cEeprom>`, :ref:`Ltc2483Adc <object_Ltc2483Adc>`, :ref:`Sht3x <object_Sht3x>`

Overview
********

Properties
++++++++++

.. hlist::
  :columns: 1

  * :ref:`address <property_I2cDevice_address>`
  * :ref:`Object.objectId <property_Object_objectId>`
  * :ref:`Object.parent <property_Object_parent>`

Methods
+++++++

.. hlist::
  :columns: 1

  * :ref:`read() <method_I2cDevice_read>`
  * :ref:`write() <method_I2cDevice_write>`
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


.. _property_I2cDevice_address:

.. _signal_I2cDevice_addressChanged:

.. index::
   single: address

address
+++++++

This property holds the bus address of the I2C device.

:**› Type**: UnsignedInteger
:**› Default**: ``0``
:**› Signal**: addressChanged()
:**› Attributes**: Writable

Methods
*******


.. _method_I2cDevice_read:

.. index::
   single: read

read(UnsignedInteger bytes)
+++++++++++++++++++++++++++

This method reads the specified number of bytes from the I2C slave. Returns an empty buffer if the slave did not respond or an error occurred.

:**› Returns**: ArrayBuffer



.. _method_I2cDevice_write:

.. index::
   single: write

write(ArrayBuffer data)
+++++++++++++++++++++++

This method writes the specified bytes to the I2C slave. Returns ``false`` if the slave did not respond (acknowledge) or an error occurred.

:**› Returns**: Boolean



.. _example_I2cDevice:


Example
*******

.. code-block:: qml

    import InCore.Foundation 2.5
    import InCore.IO 2.5
    
    Application {
        FtdiI2cBus {
            I2cDevice {
                id: eeprom
                address: 0x50
            }
        }
    
        ByteArray {
            id: eepromCommandBuffer
            data: [ 0x80 ]
        }
    
        ByteArray {
            id: eepromReadBuffer
        }
    
        onCompleted: {
            eeprom.write(eepromCommandBuffer.arrayBuffer)
            eepromReadBuffer.arrayBuffer = eeprom.read(16)
            console.log(eepromReadBuffer.hex)
        }
    }
    