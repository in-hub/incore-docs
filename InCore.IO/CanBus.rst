
.. _object_CanBus:


:index:`CanBus`
---------------

Description
***********

The CanBus object represents the CAN bus attached to the device and allows communication with other devices on the bus.

This object was introduced in InCore 2.0.

:**› Inherits**: :ref:`Object <object_Object>`

Overview
********

Properties
++++++++++

.. hlist::
  :columns: 2

  * :ref:`bitRate <property_CanBus_bitRate>`
  * :ref:`busStatus <property_CanBus_busStatus>`
  * :ref:`currentFrame <property_CanBus_currentFrame>`
  * :ref:`error <property_CanBus_error>`
  * :ref:`errorFilter <property_CanBus_errorFilter>`
  * :ref:`errorString <property_CanBus_errorString>`
  * :ref:`loopback <property_CanBus_loopback>`
  * :ref:`pipes <property_CanBus_pipes>`
  * :ref:`rawFilters <property_CanBus_rawFilters>`
  * :ref:`receiveOwnKey <property_CanBus_receiveOwnKey>`
  * :ref:`resetDelay <property_CanBus_resetDelay>`
  * :ref:`state <property_CanBus_state>`
  * :ref:`Object.objectId <property_Object_objectId>`
  * :ref:`Object.parent <property_Object_parent>`

Methods
+++++++

.. hlist::
  :columns: 1

  * :ref:`clear() <method_CanBus_clear>`
  * :ref:`pollBusStatus() <method_CanBus_pollBusStatus>`
  * :ref:`reset() <method_CanBus_reset>`
  * :ref:`writeFrame() <method_CanBus_writeFrame>`
  * :ref:`Object.deserializeProperties() <method_Object_deserializeProperties>`
  * :ref:`Object.fromJson() <method_Object_fromJson>`
  * :ref:`Object.toJson() <method_Object_toJson>`

Signals
+++++++

.. hlist::
  :columns: 1

  * :ref:`errorOccurred() <signal_CanBus_errorOccurred>`
  * :ref:`frameReceived() <signal_CanBus_frameReceived>`
  * :ref:`pipesDataChanged() <signal_CanBus_pipesDataChanged>`
  * :ref:`rawFiltersDataChanged() <signal_CanBus_rawFiltersDataChanged>`
  * :ref:`Object.completed() <signal_Object_completed>`

Enumerations
++++++++++++

.. hlist::
  :columns: 1

  * :ref:`BusStatus <enum_CanBus_BusStatus>`
  * :ref:`Error <enum_CanBus_Error>`
  * :ref:`State <enum_CanBus_State>`



Properties
**********


.. _property_CanBus_bitRate:

.. index::
   single: bitRate

bitRate
+++++++

This property holds the CAN bitrate in bits per second.

:**› Type**: SignedInteger
:**› Default**: ``250000``
:**› Attributes**: Writable


.. _property_CanBus_busStatus:

.. _signal_CanBus_busStatusChanged:

.. index::
   single: busStatus

busStatus
+++++++++

This property holds the current CAN bus status.

This property was introduced in InCore 2.2.

:**› Type**: :ref:`BusStatus <enum_CanBus_BusStatus>`
:**› Signal**: busStatusChanged()
:**› Attributes**: Readonly, Requires :ref:`Polling <object_Polling>`


.. _property_CanBus_currentFrame:

.. _signal_CanBus_currentFrameChanged:

.. index::
   single: currentFrame

currentFrame
++++++++++++

This property holds the CAN frame which has been received most recently. This property is updated automatically whenever new frames are received. Every frame should therefore be processsed in a handler for the :ref:`frameReceived() <signal_CanBus_frameReceived>` or :ref:`currentFrameChanged() <signal_CanBus_currentFrameChanged>` signals immediately.

:**› Type**: :ref:`CanFrame <object_CanFrame>`
:**› Signal**: currentFrameChanged()
:**› Attributes**: Readonly


.. _property_CanBus_error:

.. _signal_CanBus_errorChanged:

.. index::
   single: error

error
+++++

This property holds the most recently occurred error or :ref:`CanBus.NoError <enumitem_CanBus_NoError>` if no error occurred. If the same error occurs multiple times this property does not change. Use the :ref:`errorOccurred() <signal_CanBus_errorOccurred>` signal to detect multiple occurrences of the same error.

:**› Type**: :ref:`Error <enum_CanBus_Error>`
:**› Signal**: errorChanged()
:**› Attributes**: Readonly


.. _property_CanBus_errorFilter:

.. _signal_CanBus_errorFilterChanged:

.. index::
   single: errorFilter

errorFilter
+++++++++++

This property holds the type of error that should be forwarded via the current connection.

:**› Type**: :ref:`CanFrame.Errors <enum_CanFrame_Errors>`
:**› Signal**: errorFilterChanged()
:**› Attributes**: Writable


.. _property_CanBus_errorString:

.. _signal_CanBus_errorStringChanged:

.. index::
   single: errorString

errorString
+++++++++++

This property holds the current human readable error string corresponding to the current value in the :ref:`error <property_CanBus_error>` property. It may include additional information such as failure reasons or locations.

:**› Type**: String
:**› Signal**: errorStringChanged()
:**› Attributes**: Readonly


.. _property_CanBus_loopback:

.. _signal_CanBus_loopbackChanged:

.. index::
   single: loopback

loopback
++++++++

This property holds whether the CAN bus should operate in loopback mode. Loopback means, whenever a CAN frame is transmitted on the CAN bus, a local echo of this frame is sent to all applications connected to this CAN device.

:**› Type**: Boolean
:**› Signal**: loopbackChanged()
:**› Attributes**: Writable


.. _property_CanBus_pipes:

.. _signal_CanBus_pipesChanged:

.. index::
   single: pipes

pipes
+++++

This property holds a list of CAN communication pipes to operate on the bus. Any incoming CAN frames processed by one or multiple attached pipes will not be available through the :ref:`currentFrame <property_CanBus_currentFrame>` property. See :ref:`CanPipe <object_CanPipe>` for details.

:**› Type**: :ref:`List <object_List>`\<:ref:`CanPipe <object_CanPipe>`>
:**› Signal**: pipesChanged()
:**› Attributes**: Readonly


.. _property_CanBus_rawFilters:

.. _signal_CanBus_rawFiltersChanged:

.. index::
   single: rawFilters

rawFilters
++++++++++

This property holds a list of CAN filters used for filtering CAN frames received on the bus. See :ref:`CanFilter <object_CanFilter>` for details.

:**› Type**: :ref:`List <object_List>`\<:ref:`CanFilter <object_CanFilter>`>
:**› Signal**: rawFiltersChanged()
:**› Attributes**: Readonly


.. _property_CanBus_receiveOwnKey:

.. _signal_CanBus_receiveOwnKeyChanged:

.. index::
   single: receiveOwnKey

receiveOwnKey
+++++++++++++

This property holds whether the CAN device receives its own send frames. This can be used to check if the transmission was successful.

:**› Type**: Boolean
:**› Signal**: receiveOwnKeyChanged()
:**› Attributes**: Writable


.. _property_CanBus_resetDelay:

.. index::
   single: resetDelay

resetDelay
++++++++++

This property holds the number of milliseconds after which to reset the bus in case of a bus-off condition.

:**› Type**: SignedInteger
:**› Default**: ``1000``
:**› Attributes**: Writable


.. _property_CanBus_state:

.. _signal_CanBus_stateChanged:

.. index::
   single: state

state
+++++

This property holds the current state of the CAN bus.

:**› Type**: :ref:`State <enum_CanBus_State>`
:**› Signal**: stateChanged()
:**› Attributes**: Readonly

Methods
*******


.. _method_CanBus_clear:

.. index::
   single: clear

clear()
+++++++

This method Clears the devices input and output buffers. This function only operates on :ref:`CanBus <object_CanBus>` buffers. Frames that are already written to the CAN driver or CAN hardware layer, or that are not yet read from these layers, are not cleared by this function.



.. _method_CanBus_pollBusStatus:

.. index::
   single: pollBusStatus

pollBusStatus()
+++++++++++++++

This method polls the :ref:`busStatus <property_CanBus_busStatus>` property. It is called automatically when using a :ref:`Polling <object_Polling>` property modifier on this property and usually does not have to be called manually.



.. _method_CanBus_reset:

.. index::
   single: reset

reset()
+++++++

This method performs a CAN controller reset to release the CAN controller from bus off state, if possible.

Note: CAN controller resets disturb the running communication and may take up to one second to complete. Only call this function to recover from bus errors.

This method was introduced in InCore 2.2.



.. _method_CanBus_writeFrame:

.. index::
   single: writeFrame

writeFrame(Variant frame)
+++++++++++++++++++++++++

This method Writes frame to the CAN bus and returns ``true`` on success; otherwise ``false``. If an error occurs the :ref:`errorOccurred() <signal_CanBus_errorOccurred>` signal is emitted.

As per CAN bus specification, frames of type remote transfer request (RTR) do not have a payload, but a length from 0 to 8 (including). This length indicates the expected response payload length from the remote party. Therefore when sending a RTR frame using this function it may still be required to set an arbitrary payload on frame. The length of the arbitrary payload is what is set as size expectation for the RTR frame.

:**› Returns**: Boolean


Signals
*******


.. _signal_CanBus_errorOccurred:

.. index::
   single: errorOccurred

errorOccurred()
+++++++++++++++

This signal is emitted whenever an error has occurred, regardless of whether the :ref:`error <property_CanBus_error>` property has changed or not. In contrast to the change notification signal of the :ref:`error <property_CanBus_error>` property this signal is also emitted several times if a certain error occurs several times in succession.



.. _signal_CanBus_frameReceived:

.. index::
   single: frameReceived

frameReceived()
+++++++++++++++

This signal is emitted whenever a CAN frame has been received and is available in the :ref:`currentFrame <property_CanBus_currentFrame>` property. React to this signal or :ref:`currentFrameChanged() <signal_CanBus_currentFrameChanged>` immediately in order to handle the received data since :ref:`currentFrame <property_CanBus_currentFrame>` can be updated again at any time.



.. _signal_CanBus_pipesDataChanged:

.. index::
   single: pipesDataChanged

pipesDataChanged(SignedInteger index)
+++++++++++++++++++++++++++++++++++++

This signal is emitted whenever the :ref:`List.dataChanged() <signal_List_dataChanged>` signal is emitted, i.e. the item at ``index`` in the :ref:`pipes <property_CanBus_pipes>` list itself emitted the dataChanged() signal.



.. _signal_CanBus_rawFiltersDataChanged:

.. index::
   single: rawFiltersDataChanged

rawFiltersDataChanged(SignedInteger index)
++++++++++++++++++++++++++++++++++++++++++

This signal is emitted whenever the :ref:`List.dataChanged() <signal_List_dataChanged>` signal is emitted, i.e. the item at ``index`` in the :ref:`rawFilters <property_CanBus_rawFilters>` list itself emitted the dataChanged() signal.


Enumerations
************


.. _enum_CanBus_BusStatus:

.. index::
   single: BusStatus

BusStatus
+++++++++

This enumeration describes all possible states of the CAN bus.

This enumeration was introduced in InCore 2.2.

.. index::
   single: CanBus.Unknown
.. index::
   single: CanBus.Good
.. index::
   single: CanBus.Warning
.. index::
   single: CanBus.Error
.. index::
   single: CanBus.BusOff
.. list-table::
  :widths: auto
  :header-rows: 1

  * - Name
    - Value
    - Description

      .. _enumitem_CanBus_Unknown:
  * - ``CanBus.Unknown``
    - ``0``
    - The CAN bus status is unknown.

      .. _enumitem_CanBus_Good:
  * - ``CanBus.Good``
    - ``1``
    - The CAN controller is fully operational.

      .. _enumitem_CanBus_Warning:
  * - ``CanBus.Warning``
    - ``2``
    - The CAN controller is in warning status.

      .. _enumitem_CanBus_Error:
  * - ``CanBus.Error``
    - ``3``
    - The CAN controller is in error status (no longer sending CAN frames).

      .. _enumitem_CanBus_BusOff:
  * - ``CanBus.BusOff``
    - ``4``
    - The CAN controller is in bus off status (disconnected from the CAN bus).


.. _enum_CanBus_Error:

.. index::
   single: Error

Error
+++++

This enumeration describes all errors which can occur in CanBus objects. The most recently occurred error is stored in the :ref:`error <property_CanBus_error>` property.

.. index::
   single: CanBus.NoError
.. index::
   single: CanBus.ReadError
.. index::
   single: CanBus.WriteError
.. index::
   single: CanBus.ConnectionError
.. index::
   single: CanBus.ConfigurationError
.. index::
   single: CanBus.WriteFrameDataError
.. index::
   single: CanBus.UnknownError
.. list-table::
  :widths: auto
  :header-rows: 1

  * - Name
    - Value
    - Description

      .. _enumitem_CanBus_NoError:
  * - ``CanBus.NoError``
    - ``0``
    - No error occurred or was detected.

      .. _enumitem_CanBus_ReadError:
  * - ``CanBus.ReadError``
    - ``1``
    - An error occurred during a read operation.

      .. _enumitem_CanBus_WriteError:
  * - ``CanBus.WriteError``
    - ``2``
    - An error occurred during a write operation.

      .. _enumitem_CanBus_ConnectionError:
  * - ``CanBus.ConnectionError``
    - ``3``
    - An error occurred while attempting to open the CAN bus.

      .. _enumitem_CanBus_ConfigurationError:
  * - ``CanBus.ConfigurationError``
    - ``4``
    - An error occurred when attempting to set a configuration parameter.

      .. _enumitem_CanBus_WriteFrameDataError:
  * - ``CanBus.WriteFrameDataError``
    - ``5``
    - An invalid frame was passed to writeFrame().

      .. _enumitem_CanBus_UnknownError:
  * - ``CanBus.UnknownError``
    - ``6``
    - An unknown error occurred.


.. _enum_CanBus_State:

.. index::
   single: State

State
+++++

This enumeration describes all possible states of the CAN device connection.

.. index::
   single: CanBus.UnconnectedState
.. index::
   single: CanBus.ConnectingState
.. index::
   single: CanBus.ConnectedState
.. index::
   single: CanBus.ClosingState
.. list-table::
  :widths: auto
  :header-rows: 1

  * - Name
    - Value
    - Description

      .. _enumitem_CanBus_UnconnectedState:
  * - ``CanBus.UnconnectedState``
    - ``0``
    - The device is disconnected.

      .. _enumitem_CanBus_ConnectingState:
  * - ``CanBus.ConnectingState``
    - ``1``
    - Connecting to the device.

      .. _enumitem_CanBus_ConnectedState:
  * - ``CanBus.ConnectedState``
    - ``2``
    - The device is connected.

      .. _enumitem_CanBus_ClosingState:
  * - ``CanBus.ClosingState``
    - ``3``
    - Closing device connection.


.. _example_CanBus:


Example
*******

.. code-block:: qml

    import InCore.Foundation 2.0
    import InCore.IO 2.0
    
    Application {
    
        CanBus {
            id: bus
            onFrameReceived: {
                if( currentFrame.frameId === temperatureFrame.frameId )
                {
                    console.log("Remote device temperature:", parseFloat(currentFrame.payload.string))
                }
                else
                {
                    console.log("Received CAN frame with ID", currentFrame.frameId, "and payload", currentFrame.payload.hex)
                }
            }
        }
    
        CanFrame {
            id: testFrame
            payload.data: [ 0xde, 0xad, 0xbe, 0xef ]
        }
    
        CanFrame {
            id: temperatureFrame
            frameId: 1
        }
    
        System {
            id: system
            Polling on deviceTemperature { }
        }
    
        Timer {
            onTriggered: {
                testFrame.frameId = 100 + Math.floor(Math.random() * 100)
                bus.writeFrame(testFrame)
    
                temperatureFrame.payload.string = system.deviceTemperature.toString()
                bus.writeFrame(temperatureFrame)
            }
        }
    }
    