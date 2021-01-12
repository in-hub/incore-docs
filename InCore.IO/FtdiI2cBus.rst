
.. _object_FtdiI2cBus:


:index:`FtdiI2cBus`
-------------------

Description
***********

The FtdiI2cBus object is an :ref:`I2cBus <object_I2cBus>` implementation to communicate with an FT232H-based IC2 bus via USB. In addition to reading and writing to the I2C bus it allows controlling the GPIO lines of the FT232H chip.

:**› Inherits**: :ref:`I2cBus <object_I2cBus>`

Overview
********

Properties
++++++++++

.. hlist::
  :columns: 2

  * :ref:`channel <property_FtdiI2cBus_channel>`
  * :ref:`error <property_FtdiI2cBus_error>`
  * :ref:`errorString <property_FtdiI2cBus_errorString>`
  * :ref:`gpioPinStates <property_FtdiI2cBus_gpioPinStates>`
  * :ref:`latency <property_FtdiI2cBus_latency>`
  * :ref:`useFastOperations <property_FtdiI2cBus_useFastOperations>`
  * :ref:`I2cBus.devices <property_I2cBus_devices>`
  * :ref:`I2cBus.speed <property_I2cBus_speed>`
  * :ref:`Object.objectId <property_Object_objectId>`
  * :ref:`Object.parent <property_Object_parent>`

Methods
+++++++

.. hlist::
  :columns: 1

  * :ref:`pollGpioPinStates() <method_FtdiI2cBus_pollGpioPinStates>`
  * :ref:`readGpioPin() <method_FtdiI2cBus_readGpioPin>`
  * :ref:`writeGpioPin() <method_FtdiI2cBus_writeGpioPin>`
  * :ref:`Object.fromJson() <method_Object_fromJson>`
  * :ref:`Object.toJson() <method_Object_toJson>`

Signals
+++++++

.. hlist::
  :columns: 1

  * :ref:`errorOccurred() <signal_FtdiI2cBus_errorOccurred>`
  * :ref:`I2cBus.devicesDataChanged() <signal_I2cBus_devicesDataChanged>`
  * :ref:`Object.completed() <signal_Object_completed>`

Enumerations
++++++++++++

.. hlist::
  :columns: 1

  * :ref:`Error <enum_FtdiI2cBus_Error>`



Properties
**********


.. _property_FtdiI2cBus_channel:

.. _signal_FtdiI2cBus_channelChanged:

.. index::
   single: channel

channel
+++++++

This property holds the I2C channel to operate on. Usually only one device with one channel is connected so the default value can be used.

:**› Type**: UnsignedInteger
:**› Default**: ``0``
:**› Signal**: channelChanged()
:**› Attributes**: Writable


.. _property_FtdiI2cBus_error:

.. _signal_FtdiI2cBus_errorChanged:

.. index::
   single: error

error
+++++

This property holds the most recently occurred error or :ref:`FtdiI2cBus.NoError <enumitem_FtdiI2cBus_NoError>` if no error occurred. If the same error occurs multiple times this property does not change. Use the :ref:`errorOccurred() <signal_FtdiI2cBus_errorOccurred>` signal to detect multiple occurrences of the same error.

:**› Type**: :ref:`Error <enum_FtdiI2cBus_Error>`
:**› Signal**: errorChanged()
:**› Attributes**: Readonly


.. _property_FtdiI2cBus_errorString:

.. _signal_FtdiI2cBus_errorStringChanged:

.. index::
   single: errorString

errorString
+++++++++++

This property holds the current human readable error string corresponding to the current value in the :ref:`error <property_FtdiI2cBus_error>` property. It may include additional information such as failure reasons or locations.

:**› Type**: String
:**› Signal**: errorStringChanged()
:**› Attributes**: Readonly


.. _property_FtdiI2cBus_gpioPinStates:

.. _signal_FtdiI2cBus_gpioPinStatesChanged:

.. index::
   single: gpioPinStates

gpioPinStates
+++++++++++++

This property holds the states of the 12 GPIOs pins while each pin is represented by one bit.

:**› Type**: UnsignedInteger
:**› Signal**: gpioPinStatesChanged()
:**› Attributes**: Readonly, Requires :ref:`Polling <object_Polling>`


.. _property_FtdiI2cBus_latency:

.. _signal_FtdiI2cBus_latencyChanged:

.. index::
   single: latency

latency
+++++++

This property holds the value for the FTDI latency timer in the range of [1..255]. The latency timer inside the FTDI device is used to flush small transmit buffers. Without this timer the host would not receive any data until the transmit buffer of the device is full (64 bytes). This allows the device to be better optimized for protocols requiring faster response times from short data packets.

:**› Type**: UnsignedInteger
:**› Default**: ``16``
:**› Signal**: latencyChanged()
:**› Attributes**: Writable


.. _property_FtdiI2cBus_useFastOperations:

.. _signal_FtdiI2cBus_useFastOperationsChanged:

.. index::
   single: useFastOperations

useFastOperations
+++++++++++++++++

This property holds whether to use MPSSE fast read/write operations. Disable if you encounter communication problems.

:**› Type**: Boolean
:**› Default**: ``true``
:**› Signal**: useFastOperationsChanged()
:**› Attributes**: Writable

Methods
*******


.. _method_FtdiI2cBus_pollGpioPinStates:

.. index::
   single: pollGpioPinStates

pollGpioPinStates()
+++++++++++++++++++

This method polls the :ref:`gpioPinStates <property_FtdiI2cBus_gpioPinStates>` property. It is called automatically when using a :ref:`Polling <object_Polling>` property modifier on this property and usually does not have to be called manually.



.. _method_FtdiI2cBus_readGpioPin:

.. index::
   single: readGpioPin

readGpioPin(SignedInteger pin)
++++++++++++++++++++++++++++++

This method reads the specified GPIO pin. This method is provided for convenience only. Consider a declarative approach by polling and evaluating the :ref:`gpioPinStates <property_FtdiI2cBus_gpioPinStates>` property.

:**› Returns**: Boolean



.. _method_FtdiI2cBus_writeGpioPin:

.. index::
   single: writeGpioPin

writeGpioPin(SignedInteger pin, Boolean state)
++++++++++++++++++++++++++++++++++++++++++++++

This method sets the specified GPIO pin to the specified state.

:**› Returns**: Boolean


Signals
*******


.. _signal_FtdiI2cBus_errorOccurred:

.. index::
   single: errorOccurred

errorOccurred()
+++++++++++++++

This signal is emitted whenever an error has occurred, regardless of whether the :ref:`error <property_FtdiI2cBus_error>` property has changed or not. In contrast to the change notification signal of the :ref:`error <property_FtdiI2cBus_error>` property this signal is also emitted several times if a certain error occurs several times in succession.


Enumerations
************


.. _enum_FtdiI2cBus_Error:

.. index::
   single: Error

Error
+++++

This enumeration describes all errors which can occur in FtdiI2cBus objects. The most recently occurred error is stored in the :ref:`error <property_FtdiI2cBus_error>` property.

.. index::
   single: FtdiI2cBus.NoError
.. index::
   single: FtdiI2cBus.DeviceOpenError
.. index::
   single: FtdiI2cBus.ReadError
.. index::
   single: FtdiI2cBus.WriteError
.. index::
   single: FtdiI2cBus.GpioReadError
.. index::
   single: FtdiI2cBus.GpioWriteError
.. list-table::
  :widths: auto
  :header-rows: 1

  * - Name
    - Value
    - Description

      .. _enumitem_FtdiI2cBus_NoError:
  * - ``FtdiI2cBus.NoError``
    - ``0``
    - No error occurred or was detected.

      .. _enumitem_FtdiI2cBus_DeviceOpenError:
  * - ``FtdiI2cBus.DeviceOpenError``
    - ``1``
    - Device could not be opened.

      .. _enumitem_FtdiI2cBus_ReadError:
  * - ``FtdiI2cBus.ReadError``
    - ``2``
    - Failed to read the specified number of bytes from configured address.

      .. _enumitem_FtdiI2cBus_WriteError:
  * - ``FtdiI2cBus.WriteError``
    - ``3``
    - Failed to write the specified number of bytes to configured address.

      .. _enumitem_FtdiI2cBus_GpioReadError:
  * - ``FtdiI2cBus.GpioReadError``
    - ``4``
    - Failed to read GPIO states.

      .. _enumitem_FtdiI2cBus_GpioWriteError:
  * - ``FtdiI2cBus.GpioWriteError``
    - ``5``
    - Failed to write GPIO states.


.. _example_FtdiI2cBus:


Example
*******

.. code-block:: qml

    import InCore.Foundation 2.0
    import InCore.IO 2.0
    
    Application {
        FtdiI2cBus {
            onCompleted: {
                // switch on LED attached to GPIO 13
                writeGpios(8192, 1)
                // read lower 8 GPIO channels
                console.log(readGpios() & 0xff)
            }
        }
    }
    