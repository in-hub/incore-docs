
.. _object_SensirionHDLC:


:index:`SensirionHDLC`
----------------------

Description
***********

The SensirionHDLC object implements the Sensirion HDLC (High-Level Data Link Control) protocol to allow easy communication with Sensirion sensors via RS485 and USB cables.

This object was introduced in InCore 2.1.

:**› Inherits**: :ref:`SerialPortBusNode <object_SerialPortBusNode>`
:**› Inherited by**: :ref:`SensirionSFM3300 <object_SensirionSFM3300>`, :ref:`SensirionSPS30 <object_SensirionSPS30>`

Overview
********

Properties
++++++++++

.. hlist::
  :columns: 2

  * :ref:`articleCode <property_SensirionHDLC_articleCode>`
  * :ref:`error <property_SensirionHDLC_error>`
  * :ref:`errorString <property_SensirionHDLC_errorString>`
  * :ref:`firmwareVersion <property_SensirionHDLC_firmwareVersion>`
  * :ref:`hardwareVersion <property_SensirionHDLC_hardwareVersion>`
  * :ref:`productName <property_SensirionHDLC_productName>`
  * :ref:`serialNumber <property_SensirionHDLC_serialNumber>`
  * :ref:`SerialPortBusNode.bus <property_SerialPortBusNode_bus>`
  * :ref:`SerialPortBusNode.portName <property_SerialPortBusNode_portName>`
  * :ref:`SerialPortBusNode.responseTimeout <property_SerialPortBusNode_responseTimeout>`
  * :ref:`SerialPortBusNode.serialPort <property_SerialPortBusNode_serialPort>`
  * :ref:`Object.objectId <property_Object_objectId>`
  * :ref:`Object.parent <property_Object_parent>`

Methods
+++++++

.. hlist::
  :columns: 1

  * :ref:`reset() <method_SensirionHDLC_reset>`
  * :ref:`sendCommand() <method_SensirionHDLC_sendCommand>`
  * :ref:`Object.deserializeProperties() <method_Object_deserializeProperties>`
  * :ref:`Object.fromJson() <method_Object_fromJson>`
  * :ref:`Object.serializeProperties() <method_Object_serializeProperties>`
  * :ref:`Object.toJson() <method_Object_toJson>`

Signals
+++++++

.. hlist::
  :columns: 1

  * :ref:`errorOccurred() <signal_SensirionHDLC_errorOccurred>`
  * :ref:`responseReceived() <signal_SensirionHDLC_responseReceived>`
  * :ref:`Object.completed() <signal_Object_completed>`

Enumerations
++++++++++++

.. hlist::
  :columns: 1

  * :ref:`Error <enum_SensirionHDLC_Error>`



Properties
**********


.. _property_SensirionHDLC_articleCode:

.. _signal_SensirionHDLC_articleCodeChanged:

.. index::
   single: articleCode

articleCode
+++++++++++

This property holds the article code of the connected device.

This property was introduced in InCore 2.5.

:**› Type**: String
:**› Signal**: articleCodeChanged()
:**› Attributes**: Readonly


.. _property_SensirionHDLC_error:

.. _signal_SensirionHDLC_errorChanged:

.. index::
   single: error

error
+++++

This property holds the most recently occurred error or :ref:`SensirionHDLC.NoError <enumitem_SensirionHDLC_NoError>` if no error occurred. If the same error occurs multiple times this property does not change. Use the :ref:`errorOccurred() <signal_SensirionHDLC_errorOccurred>` signal to detect multiple occurrences of the same error.

:**› Type**: :ref:`Error <enum_SensirionHDLC_Error>`
:**› Signal**: errorChanged()
:**› Attributes**: Readonly


.. _property_SensirionHDLC_errorString:

.. _signal_SensirionHDLC_errorStringChanged:

.. index::
   single: errorString

errorString
+++++++++++

This property holds the current human readable error string corresponding to the current value in the :ref:`error <property_SensirionHDLC_error>` property. It may include additional information such as failure reasons or locations.

:**› Type**: String
:**› Signal**: errorStringChanged()
:**› Attributes**: Readonly


.. _property_SensirionHDLC_firmwareVersion:

.. _signal_SensirionHDLC_firmwareVersionChanged:

.. index::
   single: firmwareVersion

firmwareVersion
+++++++++++++++

This property holds the firmware version of the connected device.

This property was introduced in InCore 2.5.

:**› Type**: String
:**› Signal**: firmwareVersionChanged()
:**› Attributes**: Readonly


.. _property_SensirionHDLC_hardwareVersion:

.. _signal_SensirionHDLC_hardwareVersionChanged:

.. index::
   single: hardwareVersion

hardwareVersion
+++++++++++++++

This property holds the hardware version of the connected device.

This property was introduced in InCore 2.5.

:**› Type**: String
:**› Signal**: hardwareVersionChanged()
:**› Attributes**: Readonly


.. _property_SensirionHDLC_productName:

.. _signal_SensirionHDLC_productNameChanged:

.. index::
   single: productName

productName
+++++++++++

This property holds the name of the connected device.

This property was introduced in InCore 2.5.

:**› Type**: String
:**› Signal**: productNameChanged()
:**› Attributes**: Readonly


.. _property_SensirionHDLC_serialNumber:

.. _signal_SensirionHDLC_serialNumberChanged:

.. index::
   single: serialNumber

serialNumber
++++++++++++

This property holds the serial number of the connected device.

This property was introduced in InCore 2.5.

:**› Type**: String
:**› Signal**: serialNumberChanged()
:**› Attributes**: Readonly

Methods
*******


.. _method_SensirionHDLC_reset:

.. index::
   single: reset

reset()
+++++++

This method soft resets the attached sensor. After calling this command, the module is in the same state as after a Power-Reset.



.. _method_SensirionHDLC_sendCommand:

.. index::
   single: sendCommand

sendCommand(UnsignedChar command, ArrayBuffer data)
+++++++++++++++++++++++++++++++++++++++++++++++++++




Signals
*******


.. _signal_SensirionHDLC_errorOccurred:

.. index::
   single: errorOccurred

errorOccurred()
+++++++++++++++

This signal is emitted whenever an error has occurred, regardless of whether the :ref:`error <property_SensirionHDLC_error>` property has changed or not. In contrast to the change notification signal of the :ref:`error <property_SensirionHDLC_error>` property this signal is also emitted several times if a certain error occurs several times in succession.



.. _signal_SensirionHDLC_responseReceived:

.. index::
   single: responseReceived

responseReceived(UnsignedChar command, ArrayBuffer data)
++++++++++++++++++++++++++++++++++++++++++++++++++++++++

This signal is emitted whenever a valid response for a certain command has been received. Both the command being responded to and the response data are supplied in the signal's argument.


Enumerations
************


.. _enum_SensirionHDLC_Error:

.. index::
   single: Error

Error
+++++

This enumeration describes all errors which can occur in SensirionHDLC objects. The most recently occurred error is stored in the :ref:`error <property_SensirionHDLC_error>` property.

.. index::
   single: SensirionHDLC.NoError
.. index::
   single: SensirionHDLC.WrongDataLength
.. index::
   single: SensirionHDLC.UnknownCommand
.. index::
   single: SensirionHDLC.NoAccessRight
.. index::
   single: SensirionHDLC.IllegalCommand
.. index::
   single: SensirionHDLC.SensorBusy
.. index::
   single: SensirionHDLC.NoAckFromSensor
.. index::
   single: SensirionHDLC.I2cCrcError
.. index::
   single: SensirionHDLC.SensorTimeout
.. index::
   single: SensirionHDLC.NoMeasurementStarted
.. index::
   single: SensirionHDLC.InternalFunctionArgumentOutOfRange
.. index::
   single: SensirionHDLC.CommandNotAllowedCurrentState
.. index::
   single: SensirionHDLC.UnknownError
.. index::
   single: SensirionHDLC.InvalidPort
.. index::
   single: SensirionHDLC.ResponseTimeoutError
.. index::
   single: SensirionHDLC.InvalidResponse
.. list-table::
  :widths: auto
  :header-rows: 1

  * - Name
    - Value
    - Description

      .. _enumitem_SensirionHDLC_NoError:
  * - ``SensirionHDLC.NoError``
    - ``0``
    - No error occurred or was detected.

      .. _enumitem_SensirionHDLC_WrongDataLength:
  * - ``SensirionHDLC.WrongDataLength``
    - ``1``
    - Wrong data length for this command.

      .. _enumitem_SensirionHDLC_UnknownCommand:
  * - ``SensirionHDLC.UnknownCommand``
    - ``2``
    - Unknown command.

      .. _enumitem_SensirionHDLC_NoAccessRight:
  * - ``SensirionHDLC.NoAccessRight``
    - ``3``
    - No access right for command.

      .. _enumitem_SensirionHDLC_IllegalCommand:
  * - ``SensirionHDLC.IllegalCommand``
    - ``4``
    - Illegal command parameter or parameter out of allowed range.

      .. _enumitem_SensirionHDLC_SensorBusy:
  * - ``SensirionHDLC.SensorBusy``
    - ``32``
    - Command could not be executed because sensor is busy.

      .. _enumitem_SensirionHDLC_NoAckFromSensor:
  * - ``SensirionHDLC.NoAckFromSensor``
    - ``33``
    - Sensor gives no I2C acknowledge.

      .. _enumitem_SensirionHDLC_I2cCrcError:
  * - ``SensirionHDLC.I2cCrcError``
    - ``34``
    - CRC error while communication with sensor.

      .. _enumitem_SensirionHDLC_SensorTimeout:
  * - ``SensirionHDLC.SensorTimeout``
    - ``35``
    - Timeout of sensor while measurement.

      .. _enumitem_SensirionHDLC_NoMeasurementStarted:
  * - ``SensirionHDLC.NoMeasurementStarted``
    - ``36``
    - No measurement is started.

      .. _enumitem_SensirionHDLC_InternalFunctionArgumentOutOfRange:
  * - ``SensirionHDLC.InternalFunctionArgumentOutOfRange``
    - ``40``
    - Internal function argument out of range.

      .. _enumitem_SensirionHDLC_CommandNotAllowedCurrentState:
  * - ``SensirionHDLC.CommandNotAllowedCurrentState``
    - ``67``
    - Command not allowed in current state.

      .. _enumitem_SensirionHDLC_UnknownError:
  * - ``SensirionHDLC.UnknownError``
    - ``127``
    - Unspecified device error.

      .. _enumitem_SensirionHDLC_InvalidPort:
  * - ``SensirionHDLC.InvalidPort``
    - ``256``
    - Specified serial port does not exist or can't be opened.

      .. _enumitem_SensirionHDLC_ResponseTimeoutError:
  * - ``SensirionHDLC.ResponseTimeoutError``
    - ``257``
    - Did not receive response to request within 5000 ms.

      .. _enumitem_SensirionHDLC_InvalidResponse:
  * - ``SensirionHDLC.InvalidResponse``
    - ``258``
    - Received an invalid response, e.g. invalid CRC or invalid data.

