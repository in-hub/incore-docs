
.. _object_ModbusDevice:


:index:`ModbusDevice`
---------------------

Description
***********

The ModbusDevice object is the base class for Modbus client or server implementations. It provides basic communication mechanisms and properties and manages communication-related errors.

This object was introduced in InCore 2.0.

:**› Inherits**: :ref:`Object <object_Object>`
:**› Inherited by**: :ref:`ModbusClient <object_ModbusClient>`, :ref:`ModbusRtuMaster <object_ModbusRtuMaster>`, :ref:`ModbusServer <object_ModbusServer>`

Overview
********

Properties
++++++++++

.. hlist::
  :columns: 1

  * :ref:`autoConnect <property_ModbusDevice_autoConnect>`
  * :ref:`error <property_ModbusDevice_error>`
  * :ref:`errorString <property_ModbusDevice_errorString>`
  * :ref:`state <property_ModbusDevice_state>`
  * :ref:`Object.objectId <property_Object_objectId>`
  * :ref:`Object.parent <property_Object_parent>`

Methods
+++++++

.. hlist::
  :columns: 1

  * :ref:`connectDevice() <method_ModbusDevice_connectDevice>`
  * :ref:`disconnectDevice() <method_ModbusDevice_disconnectDevice>`
  * :ref:`Object.deserializeProperties() <method_Object_deserializeProperties>`
  * :ref:`Object.fromJson() <method_Object_fromJson>`
  * :ref:`Object.serializeProperties() <method_Object_serializeProperties>`
  * :ref:`Object.toJson() <method_Object_toJson>`

Signals
+++++++

.. hlist::
  :columns: 1

  * :ref:`connected() <signal_ModbusDevice_connected>`
  * :ref:`disconnected() <signal_ModbusDevice_disconnected>`
  * :ref:`errorOccurred() <signal_ModbusDevice_errorOccurred>`
  * :ref:`Object.completed() <signal_Object_completed>`

Enumerations
++++++++++++

.. hlist::
  :columns: 1

  * :ref:`Error <enum_ModbusDevice_Error>`
  * :ref:`State <enum_ModbusDevice_State>`



Properties
**********


.. _property_ModbusDevice_autoConnect:

.. _signal_ModbusDevice_autoConnectChanged:

.. index::
   single: autoConnect

autoConnect
+++++++++++

This property holds whether the device should automatically reconnect if the connection is lost or closed.

:**› Type**: Boolean
:**› Default**: ``true``
:**› Signal**: autoConnectChanged()
:**› Attributes**: Writable


.. _property_ModbusDevice_error:

.. _signal_ModbusDevice_errorChanged:

.. index::
   single: error

error
+++++

This property holds the most recently occurred error or :ref:`ModbusDevice.NoError <enumitem_ModbusDevice_NoError>` if no error occurred. If the same error occurs multiple times this property does not change. Use the :ref:`errorOccurred() <signal_ModbusDevice_errorOccurred>` signal to detect multiple occurrences of the same error.

:**› Type**: :ref:`Error <enum_ModbusDevice_Error>`
:**› Signal**: errorChanged()
:**› Attributes**: Readonly


.. _property_ModbusDevice_errorString:

.. _signal_ModbusDevice_errorStringChanged:

.. index::
   single: errorString

errorString
+++++++++++

This property holds the current human readable error string corresponding to the current value in the :ref:`error <property_ModbusDevice_error>` property. It may include additional information such as failure reasons or locations.

:**› Type**: String
:**› Signal**: errorStringChanged()
:**› Attributes**: Readonly


.. _property_ModbusDevice_state:

.. _signal_ModbusDevice_stateChanged:

.. index::
   single: state

state
+++++

This property holds the current state of the Modbus device. See the :ref:`State <enum_ModbusDevice_State>` enumeration for details.

:**› Type**: :ref:`State <enum_ModbusDevice_State>`
:**› Default**: :ref:`ModbusDevice.UnconnectedState <enumitem_ModbusDevice_UnconnectedState>`
:**› Signal**: stateChanged()
:**› Attributes**: Readonly

Methods
*******


.. _method_ModbusDevice_connectDevice:

.. index::
   single: connectDevice

connectDevice()
+++++++++++++++

This method connects the device or master to the network. If :ref:`autoConnect <property_ModbusDevice_autoConnect>` is ``true`` calling this function is not necessary.

:**› Returns**: Boolean



.. _method_ModbusDevice_disconnectDevice:

.. index::
   single: disconnectDevice

disconnectDevice()
++++++++++++++++++

This method disconnects the device or master from the network. Set :ref:`autoConnect <property_ModbusDevice_autoConnect>` to ``false`` to make this function work properly.


Signals
*******


.. _signal_ModbusDevice_connected:

.. index::
   single: connected

connected()
+++++++++++

This signal is emitted when the connection to the network is established.



.. _signal_ModbusDevice_disconnected:

.. index::
   single: disconnected

disconnected()
++++++++++++++

This signal is emitted when the connection to the network is lost or closed.



.. _signal_ModbusDevice_errorOccurred:

.. index::
   single: errorOccurred

errorOccurred()
+++++++++++++++

This signal is emitted whenever an error has occurred, regardless of whether the :ref:`error <property_ModbusDevice_error>` property has changed or not. In contrast to the change notification signal of the :ref:`error <property_ModbusDevice_error>` property this signal is also emitted several times if a certain error occurs several times in succession.


Enumerations
************


.. _enum_ModbusDevice_Error:

.. index::
   single: Error

Error
+++++

This enumeration describes all possible errors which can occur when connecting to or communicating with other Modbus devices.

.. index::
   single: ModbusDevice.NoError
.. index::
   single: ModbusDevice.ReadError
.. index::
   single: ModbusDevice.WriteError
.. index::
   single: ModbusDevice.ConnectionError
.. index::
   single: ModbusDevice.ConfigurationError
.. index::
   single: ModbusDevice.TimeoutError
.. index::
   single: ModbusDevice.ProtocolError
.. index::
   single: ModbusDevice.ReplyAbortedError
.. index::
   single: ModbusDevice.UnknownError
.. list-table::
  :widths: auto
  :header-rows: 1

  * - Name
    - Value
    - Description

      .. _enumitem_ModbusDevice_NoError:
  * - ``ModbusDevice.NoError``
    - ``0``
    - No error occurred or was detected.

      .. _enumitem_ModbusDevice_ReadError:
  * - ``ModbusDevice.ReadError``
    - ``1``
    - An error occurred during a read operation.

      .. _enumitem_ModbusDevice_WriteError:
  * - ``ModbusDevice.WriteError``
    - ``2``
    - An error occurred during a write operation.

      .. _enumitem_ModbusDevice_ConnectionError:
  * - ``ModbusDevice.ConnectionError``
    - ``3``
    - An error occurred when attempting to open the serial port or TCP connection.

      .. _enumitem_ModbusDevice_ConfigurationError:
  * - ``ModbusDevice.ConfigurationError``
    - ``4``
    - An error occurred when attempting to set a configuration parameter.

      .. _enumitem_ModbusDevice_TimeoutError:
  * - ``ModbusDevice.TimeoutError``
    - ``5``
    - A timeout occurred during I/O. An I/O operation did not finish within a given time frame.

      .. _enumitem_ModbusDevice_ProtocolError:
  * - ``ModbusDevice.ProtocolError``
    - ``6``
    - A Modbus specific protocol error occurred.

      .. _enumitem_ModbusDevice_ReplyAbortedError:
  * - ``ModbusDevice.ReplyAbortedError``
    - ``7``
    - The reply was aborted due to a disconnection of the device.

      .. _enumitem_ModbusDevice_UnknownError:
  * - ``ModbusDevice.UnknownError``
    - ``8``
    - An unknown error occurred.


.. _enum_ModbusDevice_State:

.. index::
   single: State

State
+++++

This enumeration describes all possible states of the Modbus device.

.. index::
   single: ModbusDevice.UnconnectedState
.. index::
   single: ModbusDevice.ConnectingState
.. index::
   single: ModbusDevice.ConnectedState
.. index::
   single: ModbusDevice.ClosingState
.. list-table::
  :widths: auto
  :header-rows: 1

  * - Name
    - Value
    - Description

      .. _enumitem_ModbusDevice_UnconnectedState:
  * - ``ModbusDevice.UnconnectedState``
    - ``0``
    - The Modbus device is disconnected.

      .. _enumitem_ModbusDevice_ConnectingState:
  * - ``ModbusDevice.ConnectingState``
    - ``1``
    - The Modbus device is being connected.

      .. _enumitem_ModbusDevice_ConnectedState:
  * - ``ModbusDevice.ConnectedState``
    - ``2``
    - The Modbus device is connected.

      .. _enumitem_ModbusDevice_ClosingState:
  * - ``ModbusDevice.ClosingState``
    - ``3``
    - The Modbus device is closing/shutting down.
