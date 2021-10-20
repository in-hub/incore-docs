
.. _object_SerialPort:


:index:`SerialPort`
-------------------

Description
***********

The SerialPort object represents a serial port (UART) and allows reading and writing data from it.

:**› Inherits**: :ref:`IoDevice <object_IoDevice>`

Overview
********

Properties
++++++++++

.. hlist::
  :columns: 3

  * :ref:`baudRate <property_SerialPort_baudRate>`
  * :ref:`dataBits <property_SerialPort_dataBits>`
  * :ref:`description <property_SerialPort_description>`
  * :ref:`error <property_SerialPort_error>`
  * :ref:`errorString <property_SerialPort_errorString>`
  * :ref:`manufacturer <property_SerialPort_manufacturer>`
  * :ref:`parity <property_SerialPort_parity>`
  * :ref:`portName <property_SerialPort_portName>`
  * :ref:`productIdentifier <property_SerialPort_productIdentifier>`
  * :ref:`serialNumber <property_SerialPort_serialNumber>`
  * :ref:`stopBits <property_SerialPort_stopBits>`
  * :ref:`usbLocation <property_SerialPort_usbLocation>`
  * :ref:`vendorIdentifier <property_SerialPort_vendorIdentifier>`
  * :ref:`IoDevice.append <property_IoDevice_append>`
  * :ref:`IoDevice.atEnd <property_IoDevice_atEnd>`
  * :ref:`IoDevice.autoOpen <property_IoDevice_autoOpen>`
  * :ref:`IoDevice.bytesAvailable <property_IoDevice_bytesAvailable>`
  * :ref:`IoDevice.canReadLine <property_IoDevice_canReadLine>`
  * :ref:`IoDevice.deviceErrorString <property_IoDevice_deviceErrorString>`
  * :ref:`IoDevice.isOpen <property_IoDevice_isOpen>`
  * :ref:`IoDevice.isWritable <property_IoDevice_isWritable>`
  * :ref:`IoDevice.nameArgument <property_IoDevice_nameArgument>`
  * :ref:`IoDevice.pos <property_IoDevice_pos>`
  * :ref:`IoDevice.readOnly <property_IoDevice_readOnly>`
  * :ref:`IoDevice.size <property_IoDevice_size>`
  * :ref:`IoDevice.truncate <property_IoDevice_truncate>`
  * :ref:`IoDevice.unbuffered <property_IoDevice_unbuffered>`
  * :ref:`Object.objectId <property_Object_objectId>`
  * :ref:`Object.parent <property_Object_parent>`

Methods
+++++++

.. hlist::
  :columns: 2

  * :ref:`builtinRS485PortName() <method_SerialPort_builtinRS485PortName>`
  * :ref:`IoDevice.close() <method_IoDevice_close>`
  * :ref:`IoDevice.flush() <method_IoDevice_flush>`
  * :ref:`IoDevice.open() <method_IoDevice_open>`
  * :ref:`IoDevice.peekAll() <method_IoDevice_peekAll>`
  * :ref:`IoDevice.read() <method_IoDevice_read>`
  * :ref:`IoDevice.readAll() <method_IoDevice_readAll>`
  * :ref:`IoDevice.readLine() <method_IoDevice_readLine>`
  * :ref:`IoDevice.sync() <method_IoDevice_sync>`
  * :ref:`IoDevice.write() <method_IoDevice_write>`
  * :ref:`Object.deserializeProperties() <method_Object_deserializeProperties>`
  * :ref:`Object.fromJson() <method_Object_fromJson>`
  * :ref:`Object.toJson() <method_Object_toJson>`

Signals
+++++++

.. hlist::
  :columns: 1

  * :ref:`errorOccurred() <signal_SerialPort_errorOccurred>`
  * :ref:`IoDevice.lineAvailableForRead() <signal_IoDevice_lineAvailableForRead>`
  * :ref:`IoDevice.readyRead() <signal_IoDevice_readyRead>`
  * :ref:`Object.completed() <signal_Object_completed>`

Enumerations
++++++++++++

.. hlist::
  :columns: 1

  * :ref:`BaudRate <enum_SerialPort_BaudRate>`
  * :ref:`DataBits <enum_SerialPort_DataBits>`
  * :ref:`Error <enum_SerialPort_Error>`
  * :ref:`Parity <enum_SerialPort_Parity>`
  * :ref:`StopBits <enum_SerialPort_StopBits>`



Properties
**********


.. _property_SerialPort_baudRate:

.. _signal_SerialPort_baudRateChanged:

.. index::
   single: baudRate

baudRate
++++++++

This property holds the data baud rate for this port.

:**› Type**: :ref:`BaudRate <enum_SerialPort_BaudRate>`
:**› Signal**: baudRateChanged()
:**› Attributes**: Writable


.. _property_SerialPort_dataBits:

.. _signal_SerialPort_dataBitsChanged:

.. index::
   single: dataBits

dataBits
++++++++

This property holds the data bits in a frame.

:**› Type**: :ref:`DataBits <enum_SerialPort_DataBits>`
:**› Signal**: dataBitsChanged()
:**› Attributes**: Writable


.. _property_SerialPort_description:

.. _signal_SerialPort_descriptionChanged:

.. index::
   single: description

description
+++++++++++

This property holds the description of the serial port, if available.

:**› Type**: String
:**› Signal**: descriptionChanged()
:**› Attributes**: Readonly


.. _property_SerialPort_error:

.. _signal_SerialPort_errorChanged:

.. index::
   single: error

error
+++++

This property holds the most recently occurred error or :ref:`SerialPort.NoError <enumitem_SerialPort_NoError>` if no error occurred. If the same error occurs multiple times this property does not change. Use the :ref:`errorOccurred() <signal_SerialPort_errorOccurred>` signal to detect multiple occurrences of the same error.

:**› Type**: :ref:`Error <enum_SerialPort_Error>`
:**› Signal**: errorChanged()
:**› Attributes**: Readonly


.. _property_SerialPort_errorString:

.. _signal_SerialPort_errorStringChanged:

.. index::
   single: errorString

errorString
+++++++++++

This property holds the current human readable error string corresponding to the current value in the :ref:`error <property_SerialPort_error>` property. It may include additional information such as failure reasons or locations.

:**› Type**: String
:**› Signal**: errorStringChanged()
:**› Attributes**: Readonly


.. _property_SerialPort_manufacturer:

.. _signal_SerialPort_manufacturerChanged:

.. index::
   single: manufacturer

manufacturer
++++++++++++

This property holds the manufacturer string of the serial port, if available.

:**› Type**: String
:**› Signal**: manufacturerChanged()
:**› Attributes**: Readonly


.. _property_SerialPort_parity:

.. _signal_SerialPort_parityChanged:

.. index::
   single: parity

parity
++++++

This property holds the parity checking mode.

:**› Type**: :ref:`Parity <enum_SerialPort_Parity>`
:**› Signal**: parityChanged()
:**› Attributes**: Writable


.. _property_SerialPort_portName:

.. _signal_SerialPort_portNameChanged:

.. index::
   single: portName

portName
++++++++

This property holds the name of the serial port. The prefix "/dev/" from the system location can be omitted.

:**› Type**: String
:**› Signal**: portNameChanged()
:**› Attributes**: Writable


.. _property_SerialPort_productIdentifier:

.. _signal_SerialPort_productIdentifierChanged:

.. index::
   single: productIdentifier

productIdentifier
+++++++++++++++++

This property holds the product identifier of the serial port, if available.

:**› Type**: UnsignedSmallInteger
:**› Signal**: productIdentifierChanged()
:**› Attributes**: Readonly


.. _property_SerialPort_serialNumber:

.. _signal_SerialPort_serialNumberChanged:

.. index::
   single: serialNumber

serialNumber
++++++++++++

This property holds the serial number of the serial port, if available.

:**› Type**: String
:**› Signal**: serialNumberChanged()
:**› Attributes**: Readonly


.. _property_SerialPort_stopBits:

.. _signal_SerialPort_stopBitsChanged:

.. index::
   single: stopBits

stopBits
++++++++

This property holds the number of stop bits in a frame.

:**› Type**: :ref:`StopBits <enum_SerialPort_StopBits>`
:**› Signal**: stopBitsChanged()
:**› Attributes**: Writable


.. _property_SerialPort_usbLocation:

.. _signal_SerialPort_usbLocationChanged:

.. index::
   single: usbLocation

usbLocation
+++++++++++

This property holds the location of the serial port on the USB bus if the serial port is a virtual USB COM port or similar device.

This property was introduced in InCore 2.0.

:**› Type**: String
:**› Signal**: usbLocationChanged()
:**› Attributes**: Readonly


.. _property_SerialPort_vendorIdentifier:

.. _signal_SerialPort_vendorIdentifierChanged:

.. index::
   single: vendorIdentifier

vendorIdentifier
++++++++++++++++

This property holds the vendor identifier of the serial port, if available.

:**› Type**: UnsignedSmallInteger
:**› Signal**: vendorIdentifierChanged()
:**› Attributes**: Readonly

Methods
*******


.. _method_SerialPort_builtinRS485PortName:

.. index::
   single: builtinRS485PortName

builtinRS485PortName()
++++++++++++++++++++++

This method returns the platform-specific name of the builtin RS485 port.

This method was introduced in InCore 2.0.

:**› Returns**: String


Signals
*******


.. _signal_SerialPort_errorOccurred:

.. index::
   single: errorOccurred

errorOccurred()
+++++++++++++++

This signal is emitted whenever an error has occurred, regardless of whether the :ref:`error <property_SerialPort_error>` property has changed or not. In contrast to the change notification signal of the :ref:`error <property_SerialPort_error>` property this signal is also emitted several times if a certain error occurs several times in succession.


Enumerations
************


.. _enum_SerialPort_BaudRate:

.. index::
   single: BaudRate

BaudRate
++++++++

This enumeration describes the unit for symbol rate or modulation rate in symbols per second or pulses per second. It is the number of distinct symbol changes (signaling events) made to the transmission medium per second in a digitally modulated signal

.. index::
   single: SerialPort.Baud1200
.. index::
   single: SerialPort.Baud2400
.. index::
   single: SerialPort.Baud4800
.. index::
   single: SerialPort.Baud9600
.. index::
   single: SerialPort.Baud19200
.. index::
   single: SerialPort.Baud38400
.. index::
   single: SerialPort.Baud57600
.. index::
   single: SerialPort.Baud115200
.. index::
   single: SerialPort.Baud230400
.. index::
   single: SerialPort.Baud250000
.. index::
   single: SerialPort.Baud500000
.. index::
   single: SerialPort.Baud1000000
.. list-table::
  :widths: auto
  :header-rows: 1

  * - Name
    - Value
    - Description

      .. _enumitem_SerialPort_Baud1200:
  * - ``SerialPort.Baud1200``
    - ``1200``
    - 1200 baud.

      .. _enumitem_SerialPort_Baud2400:
  * - ``SerialPort.Baud2400``
    - ``2400``
    - 2400 baud.

      .. _enumitem_SerialPort_Baud4800:
  * - ``SerialPort.Baud4800``
    - ``4800``
    - 4800 baud.

      .. _enumitem_SerialPort_Baud9600:
  * - ``SerialPort.Baud9600``
    - ``9600``
    - 9600 baud.

      .. _enumitem_SerialPort_Baud19200:
  * - ``SerialPort.Baud19200``
    - ``19200``
    - 19200 baud.

      .. _enumitem_SerialPort_Baud38400:
  * - ``SerialPort.Baud38400``
    - ``38400``
    - 38400 baud.

      .. _enumitem_SerialPort_Baud57600:
  * - ``SerialPort.Baud57600``
    - ``57600``
    - 57600 baud.

      .. _enumitem_SerialPort_Baud115200:
  * - ``SerialPort.Baud115200``
    - ``115200``
    - 115200 baud.

      .. _enumitem_SerialPort_Baud230400:
  * - ``SerialPort.Baud230400``
    - ``230400``
    - 230400 baud.

      .. _enumitem_SerialPort_Baud250000:
  * - ``SerialPort.Baud250000``
    - ``250000``
    - 250000 baud.

      .. _enumitem_SerialPort_Baud500000:
  * - ``SerialPort.Baud500000``
    - ``500000``
    - 500000 baud.

      .. _enumitem_SerialPort_Baud1000000:
  * - ``SerialPort.Baud1000000``
    - ``1000000``
    - 1000000 baud.


.. _enum_SerialPort_DataBits:

.. index::
   single: DataBits

DataBits
++++++++

This enumeration describes the number of data bits used.

.. index::
   single: SerialPort.Data5
.. index::
   single: SerialPort.Data6
.. index::
   single: SerialPort.Data7
.. index::
   single: SerialPort.Data8
.. list-table::
  :widths: auto
  :header-rows: 1

  * - Name
    - Value
    - Description

      .. _enumitem_SerialPort_Data5:
  * - ``SerialPort.Data5``
    - ``5``
    - The number of data bits in each character is 5. It is used for Baudot code. It generally only makes sense with older equipment such as teleprinters.

      .. _enumitem_SerialPort_Data6:
  * - ``SerialPort.Data6``
    - ``6``
    - The number of data bits in each character is 6. It is rarely used.

      .. _enumitem_SerialPort_Data7:
  * - ``SerialPort.Data7``
    - ``7``
    - The number of data bits in each character is 7. It is used for true ASCII. It generally only makes sense with older equipment such as teleprinters.

      .. _enumitem_SerialPort_Data8:
  * - ``SerialPort.Data8``
    - ``8``
    - The number of data bits in each character is 8. It is used for most kinds of data, as this size matches the size of a byte. It is almost universally used in newer applications.


.. _enum_SerialPort_Error:

.. index::
   single: Error

Error
+++++

This enumeration describes all errors which can occur in SerialPort objects. The most recently occurred error is stored in the :ref:`error <property_SerialPort_error>` property.

.. index::
   single: SerialPort.NoError
.. index::
   single: SerialPort.DeviceNotFoundError
.. index::
   single: SerialPort.PermissionError
.. index::
   single: SerialPort.OpenError
.. index::
   single: SerialPort.WriteError
.. index::
   single: SerialPort.ReadError
.. index::
   single: SerialPort.ResourceError
.. index::
   single: SerialPort.UnsupportedOperationError
.. index::
   single: SerialPort.UnknownError
.. index::
   single: SerialPort.TimeoutError
.. index::
   single: SerialPort.NotOpenError
.. list-table::
  :widths: auto
  :header-rows: 1

  * - Name
    - Value
    - Description

      .. _enumitem_SerialPort_NoError:
  * - ``SerialPort.NoError``
    - ``0``
    - No error occurred or was detected.

      .. _enumitem_SerialPort_DeviceNotFoundError:
  * - ``SerialPort.DeviceNotFoundError``
    - ``1``
    - An error occurred while attempting to open an non-existing device.

      .. _enumitem_SerialPort_PermissionError:
  * - ``SerialPort.PermissionError``
    - ``2``
    - An error occurred while attempting to open an already opened device by another process or a user not having enough permission and credentials to open.

      .. _enumitem_SerialPort_OpenError:
  * - ``SerialPort.OpenError``
    - ``3``
    - An error occurred while attempting to open an already opened device in this object.

      .. _enumitem_SerialPort_WriteError:
  * - ``SerialPort.WriteError``
    - ``7``
    - An I/O error occurred while writing the data.

      .. _enumitem_SerialPort_ReadError:
  * - ``SerialPort.ReadError``
    - ``8``
    - An I/O error occurred while reading the data.

      .. _enumitem_SerialPort_ResourceError:
  * - ``SerialPort.ResourceError``
    - ``9``
    - An I/O error occurred when a resource becomes unavailable, e.g. when the device is unexpectedly removed from the system.

      .. _enumitem_SerialPort_UnsupportedOperationError:
  * - ``SerialPort.UnsupportedOperationError``
    - ``10``
    - The requested device operation is not supported or prohibited by the running operating system.

      .. _enumitem_SerialPort_UnknownError:
  * - ``SerialPort.UnknownError``
    - ``11``
    - Unknown error: an unknown error occurred.

      .. _enumitem_SerialPort_TimeoutError:
  * - ``SerialPort.TimeoutError``
    - ``12``
    - A timeout error occurred.

      .. _enumitem_SerialPort_NotOpenError:
  * - ``SerialPort.NotOpenError``
    - ``13``
    - This error occurs when an operation is executed that can only be successfully performed if the device is open.


.. _enum_SerialPort_Parity:

.. index::
   single: Parity

Parity
++++++

This enumeration describes the parity scheme used.

.. index::
   single: SerialPort.NoParity
.. index::
   single: SerialPort.EvenParity
.. index::
   single: SerialPort.OddParity
.. index::
   single: SerialPort.SpaceParity
.. index::
   single: SerialPort.MarkParity
.. list-table::
  :widths: auto
  :header-rows: 1

  * - Name
    - Value
    - Description

      .. _enumitem_SerialPort_NoParity:
  * - ``SerialPort.NoParity``
    - ``0``
    - No parity bit it sent. This is the most common parity setting. Error detection is handled by the communication protocol.

      .. _enumitem_SerialPort_EvenParity:
  * - ``SerialPort.EvenParity``
    - ``2``
    - The number of 1 bits in each character, including the parity bit, is always even.

      .. _enumitem_SerialPort_OddParity:
  * - ``SerialPort.OddParity``
    - ``3``
    - The number of 1 bits in each character, including the parity bit, is always odd. It ensures that at least one state transition occurs in each character.

      .. _enumitem_SerialPort_SpaceParity:
  * - ``SerialPort.SpaceParity``
    - ``4``
    - Space parity. The parity bit is sent in the space signal condition. It does not provide error detection information.

      .. _enumitem_SerialPort_MarkParity:
  * - ``SerialPort.MarkParity``
    - ``5``
    - Mark parity. The parity bit is always set to the mark signal condition (logical 1). It does not provide error detection information.


.. _enum_SerialPort_StopBits:

.. index::
   single: StopBits

StopBits
++++++++

This enumeration describes the number of stop bits used.

.. index::
   single: SerialPort.OneStop
.. index::
   single: SerialPort.TwoStop
.. index::
   single: SerialPort.OneAndHalfStop
.. list-table::
  :widths: auto
  :header-rows: 1

  * - Name
    - Value
    - Description

      .. _enumitem_SerialPort_OneStop:
  * - ``SerialPort.OneStop``
    - ``1``
    - 1 stop bit.

      .. _enumitem_SerialPort_TwoStop:
  * - ``SerialPort.TwoStop``
    - ``2``
    - 2 stop bits.

      .. _enumitem_SerialPort_OneAndHalfStop:
  * - ``SerialPort.OneAndHalfStop``
    - ``3``
    - 1.5 stop bits. This is only for the Windows platform.


.. _example_SerialPort:


Example
*******

.. code-block:: qml

    import InCore.Foundation 2.5
    import InCore.IO 2.5
    
    Application {
        SerialPort {
            portName: "ttyUSB0"
            baudRate: SerialPort.Baud9600
            onCompleted: {
                console.log(usbLocation)
                open();
                write("Hello Serial Port!")
            }
            onReadyRead: console.log(readAll())
        }
    }
    