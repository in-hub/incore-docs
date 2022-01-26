
.. _object_ModbusTcpClient:


:index:`ModbusTcpClient`
------------------------

Description
***********

The ModbusTcpClient object implements a Modbus TCP client which communicates with Modbus slaves (servers) via TCP network connections.

:**› Inherits**: :ref:`ModbusClient <object_ModbusClient>`

Overview
********

Properties
++++++++++

.. hlist::
  :columns: 2

  * :ref:`lowDelay <property_ModbusTcpClient_lowDelay>`
  * :ref:`networkAddress <property_ModbusTcpClient_networkAddress>`
  * :ref:`networkPort <property_ModbusTcpClient_networkPort>`
  * :ref:`ModbusClient.numberOfRetries <property_ModbusClient_numberOfRetries>`
  * :ref:`ModbusClient.slaves <property_ModbusClient_slaves>`
  * :ref:`ModbusClient.timeout <property_ModbusClient_timeout>`
  * :ref:`ModbusDevice.autoConnect <property_ModbusDevice_autoConnect>`
  * :ref:`ModbusDevice.error <property_ModbusDevice_error>`
  * :ref:`ModbusDevice.errorString <property_ModbusDevice_errorString>`
  * :ref:`ModbusDevice.state <property_ModbusDevice_state>`
  * :ref:`Object.objectId <property_Object_objectId>`
  * :ref:`Object.parent <property_Object_parent>`

Methods
+++++++

.. hlist::
  :columns: 1

  * :ref:`ModbusClient.pollSlaves() <method_ModbusClient_pollSlaves>`
  * :ref:`ModbusDevice.connectDevice() <method_ModbusDevice_connectDevice>`
  * :ref:`ModbusDevice.disconnectDevice() <method_ModbusDevice_disconnectDevice>`
  * :ref:`Object.deserializeProperties() <method_Object_deserializeProperties>`
  * :ref:`Object.fromJson() <method_Object_fromJson>`
  * :ref:`Object.serializeProperties() <method_Object_serializeProperties>`
  * :ref:`Object.toJson() <method_Object_toJson>`

Signals
+++++++

.. hlist::
  :columns: 1

  * :ref:`ModbusClient.slavesDataChanged() <signal_ModbusClient_slavesDataChanged>`
  * :ref:`ModbusDevice.connected() <signal_ModbusDevice_connected>`
  * :ref:`ModbusDevice.disconnected() <signal_ModbusDevice_disconnected>`
  * :ref:`ModbusDevice.errorOccurred() <signal_ModbusDevice_errorOccurred>`
  * :ref:`Object.completed() <signal_Object_completed>`

Enumerations
++++++++++++

.. hlist::
  :columns: 1

  * :ref:`ModbusDevice.Error <enum_ModbusDevice_Error>`
  * :ref:`ModbusDevice.State <enum_ModbusDevice_State>`



Properties
**********


.. _property_ModbusTcpClient_lowDelay:

.. _signal_ModbusTcpClient_lowDelayChanged:

.. index::
   single: lowDelay

lowDelay
++++++++

This property holds whether to optimize the underlying TCP/IP socket for low latency by setting the ``TCP_NODELAY`` option and disabling Nagle's algorithm.

This property was introduced in InCore 2.5.

:**› Type**: Boolean
:**› Default**: ``false``
:**› Signal**: lowDelayChanged()
:**› Attributes**: Writable


.. _property_ModbusTcpClient_networkAddress:

.. _signal_ModbusTcpClient_networkAddressChanged:

.. index::
   single: networkAddress

networkAddress
++++++++++++++

This property holds the host address of the Modbus TCP server which to connect to.

:**› Type**: String
:**› Default**: ``127.0.0.1``
:**› Signal**: networkAddressChanged()
:**› Attributes**: Writable


.. _property_ModbusTcpClient_networkPort:

.. _signal_ModbusTcpClient_networkPortChanged:

.. index::
   single: networkPort

networkPort
+++++++++++

This property holds the network port of the Modbus TCP server which to connect to.

:**› Type**: SignedInteger
:**› Default**: ``502``
:**› Signal**: networkPortChanged()
:**› Attributes**: Writable


.. _example_ModbusTcpClient:


Example
*******

.. code-block:: qml

    import InCore.Foundation 2.5
    import InCore.Modbus 2.5
    
    Application {
    
        name: "Modbus TCP client example"
    
        ModbusTcpClient {
            // set address to connect to
            networkAddress: "192.168.10.19"
    
            // change retry and timeout configuration
            numberOfRetries: 1
            timeout: 500
    
            ModbusSlave {
                address: 1
    
                // define Modbus register for temperature
                ModbusRegister {
                    id: temperature
                    type: ModbusRegister.Input
                    address: 1
                    onDataChanged: console.log("Temperature", data)
                }
    
                // define special Modbus register device name stored as string
                ModbusRegister {
                    type: ModbusRegister.Holding
                    address: 0x1000
                    count: 8
                    dataType: ModbusRegister.String
                    onDataChanged: console.log("Device name", data)
                }
    
                // read all registers every 50 ms
                Polling on registers { interval: 50 }
            }
    
            // print information message when connected
            onConnected: console.log("Connected to Modbus TCP slave")
    
            // print error message if something goes wrong
            onErrorOccurred: console.log(errorString)
        }
    }
    