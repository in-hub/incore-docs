
.. _object_ModbusTcpServer:


:index:`ModbusTcpServer`
------------------------

Description
***********

The ModbusTcpServer object implements a :ref:`Modbus server <object_ModbusServer>` which communicates with Modbus masters (clients) via TCP network connections.

This object was introduced in InCore 2.0.

:**› Inherits**: :ref:`ModbusServer <object_ModbusServer>`

Overview
********

Properties
++++++++++

.. hlist::
  :columns: 2

  * :ref:`networkAddress <property_ModbusTcpServer_networkAddress>`
  * :ref:`networkPort <property_ModbusTcpServer_networkPort>`
  * :ref:`ModbusServer.address <property_ModbusServer_address>`
  * :ref:`ModbusServer.registers <property_ModbusServer_registers>`
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

  * :ref:`ModbusDevice.connectDevice() <method_ModbusDevice_connectDevice>`
  * :ref:`ModbusDevice.disconnectDevice() <method_ModbusDevice_disconnectDevice>`
  * :ref:`Object.deserializeProperties() <method_Object_deserializeProperties>`
  * :ref:`Object.fromJson() <method_Object_fromJson>`
  * :ref:`Object.toJson() <method_Object_toJson>`

Signals
+++++++

.. hlist::
  :columns: 1

  * :ref:`ModbusServer.dataErrorOccurred() <signal_ModbusServer_dataErrorOccurred>`
  * :ref:`ModbusServer.mapErrorOccurred() <signal_ModbusServer_mapErrorOccurred>`
  * :ref:`ModbusServer.registersDataChanged() <signal_ModbusServer_registersDataChanged>`
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


.. _property_ModbusTcpServer_networkAddress:

.. _signal_ModbusTcpServer_networkAddressChanged:

.. index::
   single: networkAddress

networkAddress
++++++++++++++

This property holds the local network address which to listen on for incoming connections. When set to ``0.0.0.0`` the server will listen on all addresses/interfaces.

:**› Type**: String
:**› Default**: ``0.0.0.0``
:**› Signal**: networkAddressChanged()
:**› Attributes**: Writable


.. _property_ModbusTcpServer_networkPort:

.. _signal_ModbusTcpServer_networkPortChanged:

.. index::
   single: networkPort

networkPort
+++++++++++

This property holds the network port which to listen on for incoming connections.

:**› Type**: SignedInteger
:**› Default**: ``502``
:**› Signal**: networkPortChanged()
:**› Attributes**: Writable


.. _example_ModbusTcpServer:


Example
*******

.. code-block:: qml

    import InCore.Foundation 2.0
    import InCore.Modbus 2.0
    
    Application {
    
        name: "Modbus TCP server/client example"
    
        Counter {
            id: counter
            running: counterEnabledReg.data
            startValue: 123
        }
    
        ModbusTcpServer {
            id: server
            address: 1
            networkPort: 1234
            networkAddress: "localhost"
    
            // expose 3 values at addresses 2…4 through one register definition
            ModbusRegister {
                type: ModbusRegister.Input
                address: 2
                count: 3
                data: [ 123, 456, 789 ]
            }
    
            ModbusRegister {
                id: counterEnabledReg
                type: ModbusRegister.Holding
                address: 0
                data: false
                onDataChanged: console.log("Counter enabled:", data)
            }
    
            ModbusRegister {
                id: counterReg
                type: ModbusRegister.Input
                address: 123
                data: counter.value
            }
    
            ModbusRegister {
                id: messageReg
                type: ModbusRegister.Input
                address: 0x1000
                count: 6
                dataType: ModbusRegister.String
                data: "Hello world!"
            }
    
            onConnected: console.log("Server accepting connections")
            onErrorOccurred: console.log("Server error:", errorString)
        }
    
        ModbusTcpClient {
            id: client
            networkAddress: server.networkAddress
            networkPort: server.networkPort
    
            numberOfRetries: 1
            timeout: 500
    
            ModbusSlave {
                address: server.address
    
                ModbusRegister {
                    type: counterEnabledReg.type
                    address: counterEnabledReg.address
                    data: client.state === ModbusTcpClient.ConnectedState
                }
    
                ModbusRegister {
                    type: counterReg.type
                    address: counterReg.address
                    onDataChanged: console.log( "Counter value:", data)
                }
    
                ModbusRegister {
                    type: messageReg.type
                    address: messageReg.address
                    count: messageReg.count
                    dataType: messageReg.dataType
                    onDataChanged: console.log("Message register content:", data)
                }
    
                Polling on registers { interval: 100 }
            }
    
            onConnected: console.log("Connected to Modbus TCP slave")
            onErrorOccurred: console.log("Client error:", errorString)
        }
    }
    