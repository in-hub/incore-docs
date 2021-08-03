
.. _object_ModbusSlave:


:index:`ModbusSlave`
--------------------

Description
***********

The ModbusSlave object represents a remote Modbus slave and is instantiated inside an appropriate :ref:`ModbusClient <object_ModbusClient>` object. It implements :ref:`register <object_ModbusRegister>` read and write operations through the Modbus client.

:**› Inherits**: :ref:`Object <object_Object>`

Overview
********

Properties
++++++++++

.. hlist::
  :columns: 2

  * :ref:`address <property_ModbusSlave_address>`
  * :ref:`enabled <property_ModbusSlave_enabled>`
  * :ref:`error <property_ModbusSlave_error>`
  * :ref:`errorString <property_ModbusSlave_errorString>`
  * :ref:`interBlockDelay <property_ModbusSlave_interBlockDelay>`
  * :ref:`maximumBlockGap <property_ModbusSlave_maximumBlockGap>`
  * :ref:`maximumBlockLength <property_ModbusSlave_maximumBlockLength>`
  * :ref:`pollMode <property_ModbusSlave_pollMode>`
  * :ref:`registers <property_ModbusSlave_registers>`
  * :ref:`Object.objectId <property_Object_objectId>`
  * :ref:`Object.parent <property_Object_parent>`

Methods
+++++++

.. hlist::
  :columns: 1

  * :ref:`pollRegisters() <method_ModbusSlave_pollRegisters>`
  * :ref:`Object.deserializeProperties() <method_Object_deserializeProperties>`
  * :ref:`Object.fromJson() <method_Object_fromJson>`
  * :ref:`Object.toJson() <method_Object_toJson>`

Signals
+++++++

.. hlist::
  :columns: 1

  * :ref:`errorOccurred() <signal_ModbusSlave_errorOccurred>`
  * :ref:`registersDataChanged() <signal_ModbusSlave_registersDataChanged>`
  * :ref:`Object.completed() <signal_Object_completed>`

Enumerations
++++++++++++

.. hlist::
  :columns: 1

  * :ref:`Error <enum_ModbusSlave_Error>`
  * :ref:`PollMode <enum_ModbusSlave_PollMode>`



Properties
**********


.. _property_ModbusSlave_address:

.. _signal_ModbusSlave_addressChanged:

.. index::
   single: address

address
+++++++

This property holds the address of the Modbus slave. It is also known as slave ID.

:**› Type**: SignedInteger
:**› Default**: ``0``
:**› Signal**: addressChanged()
:**› Attributes**: Writable


.. _property_ModbusSlave_enabled:

.. _signal_ModbusSlave_enabledChanged:

.. index::
   single: enabled

enabled
+++++++

This property holds whether the slave is enabled or not. Polling on :ref:`registers <property_ModbusSlave_registers>` will only work when :ref:`enabled <property_ModbusSlave_enabled>` is ``true``.

:**› Type**: Boolean
:**› Default**: ``true``
:**› Signal**: enabledChanged()
:**› Attributes**: Writable


.. _property_ModbusSlave_error:

.. _signal_ModbusSlave_errorChanged:

.. index::
   single: error

error
+++++

This property holds the most recently occurred error or :ref:`ModbusSlave.NoError <enumitem_ModbusSlave_NoError>` if no error occurred. If the same error occurs multiple times this property does not change. Use the :ref:`errorOccurred() <signal_ModbusSlave_errorOccurred>` signal to detect multiple occurrences of the same error.

:**› Type**: :ref:`Error <enum_ModbusSlave_Error>`
:**› Signal**: errorChanged()
:**› Attributes**: Readonly


.. _property_ModbusSlave_errorString:

.. _signal_ModbusSlave_errorStringChanged:

.. index::
   single: errorString

errorString
+++++++++++

This property holds the current human readable error string corresponding to the current value in the :ref:`error <property_ModbusSlave_error>` property. It may include additional information such as failure reasons or locations.

:**› Type**: String
:**› Signal**: errorStringChanged()
:**› Attributes**: Readonly


.. _property_ModbusSlave_interBlockDelay:

.. _signal_ModbusSlave_interBlockDelayChanged:

.. index::
   single: interBlockDelay

interBlockDelay
+++++++++++++++

This property holds the delay which between :ref:`registers <property_ModbusSlave_registers>` pollings. The configured delay applies to all :ref:`poll modes <property_ModbusSlave_pollMode>`.

:**› Type**: SignedInteger
:**› Default**: ``0``
:**› Signal**: interBlockDelayChanged()
:**› Attributes**: Writable, Optional


.. _property_ModbusSlave_maximumBlockGap:

.. _signal_ModbusSlave_maximumBlockGapChanged:

.. index::
   single: maximumBlockGap

maximumBlockGap
+++++++++++++++

This property holds the greatest distance between the addresses of two :ref:`registers <object_ModbusRegister>`. If the distance does not exceed this value, requests to read individual registers are combined to block read requests. This property has an effect only if :ref:`pollMode <property_ModbusSlave_pollMode>` is set to:ref:`ModbusSlave.PollRegisterBlocks <enumitem_ModbusSlave_PollRegisterBlocks>`.

:**› Type**: SignedInteger
:**› Default**: ``0``
:**› Signal**: maximumBlockGapChanged()
:**› Attributes**: Writable, Optional


.. _property_ModbusSlave_maximumBlockLength:

.. _signal_ModbusSlave_maximumBlockLengthChanged:

.. index::
   single: maximumBlockLength

maximumBlockLength
++++++++++++++++++

This property holds the maximum number of modbus registers which are allowed to be combined in one block. Reduce this number if you encounter problems when requesting large register blocks. This property affects requests of combined registers only. If the maximum block length is set lower than a :ref:`registers count <property_ModbusRegister_count>` it will be ignored and the :ref:`ModbusRegister <object_ModbusRegister>` will be polled at one block anyway. This property only has an effect if :ref:`pollMode <property_ModbusSlave_pollMode>` is set to :ref:`ModbusSlave.PollRegisterBlocks <enumitem_ModbusSlave_PollRegisterBlocks>`.

This property was introduced in InCore 2.1.

:**› Type**: SignedInteger
:**› Default**: ``128``
:**› Signal**: maximumBlockLengthChanged()
:**› Attributes**: Writable, Optional


.. _property_ModbusSlave_pollMode:

.. _signal_ModbusSlave_pollModeChanged:

.. index::
   single: pollMode

pollMode
++++++++

This property holds the used poll mode. Setting this property to :ref:`ModbusSlave.PollRegisterBlocks <enumitem_ModbusSlave_PollRegisterBlocks>` can save bus traffic by reducing the Modbus protocol overhead of the individual requests.

:**› Type**: :ref:`PollMode <enum_ModbusSlave_PollMode>`
:**› Default**: :ref:`ModbusSlave.PollSingleRegisters <enumitem_ModbusSlave_PollSingleRegisters>`
:**› Signal**: pollModeChanged()
:**› Attributes**: Writable


.. _property_ModbusSlave_registers:

.. _signal_ModbusSlave_registersChanged:

.. index::
   single: registers

registers
+++++++++

This property holds a list of registers to read or write from the Modbus slave.

:**› Type**: :ref:`List <object_List>`\<:ref:`ModbusRegister <object_ModbusRegister>`>
:**› Signal**: registersChanged()
:**› Attributes**: Readonly, Requires :ref:`Polling <object_Polling>`

Methods
*******


.. _method_ModbusSlave_pollRegisters:

.. index::
   single: pollRegisters

pollRegisters()
+++++++++++++++

This method polls the :ref:`registers <property_ModbusSlave_registers>` property. It is called automatically when using a :ref:`Polling <object_Polling>` property modifier on this property and usually does not have to be called manually.


Signals
*******


.. _signal_ModbusSlave_errorOccurred:

.. index::
   single: errorOccurred

errorOccurred()
+++++++++++++++

This signal is emitted whenever an error has occurred, regardless of whether the :ref:`error <property_ModbusSlave_error>` property has changed or not. In contrast to the change notification signal of the :ref:`error <property_ModbusSlave_error>` property this signal is also emitted several times if a certain error occurs several times in succession.



.. _signal_ModbusSlave_registersDataChanged:

.. index::
   single: registersDataChanged

registersDataChanged(SignedInteger index)
+++++++++++++++++++++++++++++++++++++++++

This signal is emitted whenever the :ref:`List.dataChanged() <signal_List_dataChanged>` signal is emitted, i.e. the item at ``index`` in the :ref:`registers <property_ModbusSlave_registers>` list itself emitted the dataChanged() signal.


Enumerations
************


.. _enum_ModbusSlave_Error:

.. index::
   single: Error

Error
+++++

This enumeration describes all errors which can occur in ModbusSlave objects. The most recently occurred error is stored in the :ref:`error <property_ModbusSlave_error>` property.

.. index::
   single: ModbusSlave.NoError
.. index::
   single: ModbusSlave.InvalidClientError
.. index::
   single: ModbusSlave.ClientNotConnectedError
.. index::
   single: ModbusSlave.ReadError
.. index::
   single: ModbusSlave.WriteError
.. index::
   single: ModbusSlave.RequestError
.. list-table::
  :widths: auto
  :header-rows: 1

  * - Name
    - Value
    - Description

      .. _enumitem_ModbusSlave_NoError:
  * - ``ModbusSlave.NoError``
    - ``0``
    - No error occurred or was detected.

      .. _enumitem_ModbusSlave_InvalidClientError:
  * - ``ModbusSlave.InvalidClientError``
    - ``1``
    - Can't send requests without a ModbusClient parent.

      .. _enumitem_ModbusSlave_ClientNotConnectedError:
  * - ``ModbusSlave.ClientNotConnectedError``
    - ``2``
    - Can't send requests when modbus client is not connected.

      .. _enumitem_ModbusSlave_ReadError:
  * - ``ModbusSlave.ReadError``
    - ``3``
    - An error occurred while reading data from the Modbus slave.

      .. _enumitem_ModbusSlave_WriteError:
  * - ``ModbusSlave.WriteError``
    - ``4``
    - An error occurred while writing data to the Modbus slave.

      .. _enumitem_ModbusSlave_RequestError:
  * - ``ModbusSlave.RequestError``
    - ``5``
    - A general error occurred while sending a request to the Modbus slave.


.. _enum_ModbusSlave_PollMode:

.. index::
   single: PollMode

PollMode
++++++++

This enumeration describes supported modes when using :ref:`Polling <object_Polling>` on the :ref:`registers <property_ModbusSlave_registers>` property.

.. index::
   single: ModbusSlave.PollSingleRegisters
.. index::
   single: ModbusSlave.PollRegisterBlocks
.. list-table::
  :widths: auto
  :header-rows: 1

  * - Name
    - Value
    - Description

      .. _enumitem_ModbusSlave_PollSingleRegisters:
  * - ``ModbusSlave.PollSingleRegisters``
    - ``0``
    - Each register is polled individually.

      .. _enumitem_ModbusSlave_PollRegisterBlocks:
  * - ``ModbusSlave.PollRegisterBlocks``
    - ``1``
    - The slave will group registers in blocks and poll each block.


.. _example_ModbusSlave:


Example
*******

.. code-block:: qml

    import InCore.Foundation 2.0
    import InCore.Modbus 2.0
    
    Application {
    
        name: "Modbus slave example"
    
        ModbusRtuMaster {
    
            ModbusSlave {
                address: 1
    
                pollMode: ModbusSlave.PollSingleRegisters //default
                interBlockDelay: 100
                // each register will be polled with a delay of 100 ms
    
                // read temperature from input register 7
                ModbusRegister {
                    id: temperature1
                    type: ModbusRegister.Input
                    dataType: ModbusRegister.UnsignedSmallInteger
                    address: 7
                    onDataChanged: console.log("Temperature1", data)
                }
                ModbusRegister {
                    id: humidity1
                    type: ModbusRegister.Input
                    dataType: ModbusRegister.Float
                    address: 10
                    count: 2
                    onDataChanged: console.log("Humidity1", data)
                }
            }
    
            ModbusSlave {
                address: 2
                pollMode: ModbusSlave.PollRegisterBlocks
                maximumBlockGap: 2
                // both registers will be polled in one request
                // this can reduce traffic significantly if the registers are nearby
    
                // read temperature from input register 7
                ModbusRegister {
                    id: temperature2
                    type: ModbusRegister.Input
                    dataType: ModbusRegister.UnsignedSmallInteger
                    address: 7
                    onDataChanged: console.log("Temperature2", data)
                }
    
                ModbusRegister {
                    id: humidity2
                    type: ModbusRegister.Input
                    dataType: ModbusRegister.Float
                    address: 10
                    count: 2
                    onDataChanged: console.log("Humidity2", data)
                }
            }
    
            // read all registers from all slaves every 5 seconds
            Polling on slaves { interval: 5000 }
        }
    }
    