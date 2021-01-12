
.. _object_ModbusRtuSlave:


:index:`ModbusRtuSlave`
-----------------------

Description
***********

The ModbusRtuSlave object implements a Modbus RTU slave which communicates with a Modbus RTU master via a serial port.

This object was introduced in InCore 2.0.

:**› Inherits**: :ref:`ModbusServer <object_ModbusServer>`

Overview
********

Properties
++++++++++

.. hlist::
  :columns: 2

  * :ref:`baudRate <property_ModbusRtuSlave_baudRate>`
  * :ref:`dataBits <property_ModbusRtuSlave_dataBits>`
  * :ref:`parity <property_ModbusRtuSlave_parity>`
  * :ref:`portName <property_ModbusRtuSlave_portName>`
  * :ref:`stopBits <property_ModbusRtuSlave_stopBits>`
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


.. _property_ModbusRtuSlave_baudRate:

.. _signal_ModbusRtuSlave_baudRateChanged:

.. index::
   single: baudRate

baudRate
++++++++

This property holds the data baud rate of the serial port used for communicating with the Modbus RTU master.

:**› Type**: :ref:`SerialPort.BaudRate <enum_SerialPort_BaudRate>`
:**› Default**: :ref:`SerialPort.Baud115200 <enumitem_SerialPort_Baud115200>`
:**› Signal**: baudRateChanged()
:**› Attributes**: Writable


.. _property_ModbusRtuSlave_dataBits:

.. _signal_ModbusRtuSlave_dataBitsChanged:

.. index::
   single: dataBits

dataBits
++++++++

This property holds the number of data bits of the serial port used for communicating with the Modbus RTU master.

:**› Type**: :ref:`SerialPort.DataBits <enum_SerialPort_DataBits>`
:**› Default**: :ref:`SerialPort.Data8 <enumitem_SerialPort_Data8>`
:**› Signal**: dataBitsChanged()
:**› Attributes**: Writable


.. _property_ModbusRtuSlave_parity:

.. _signal_ModbusRtuSlave_parityChanged:

.. index::
   single: parity

parity
++++++

This property holds the parity mode of the serial port used for communicating with the Modbus RTU master.

:**› Type**: :ref:`SerialPort.Parity <enum_SerialPort_Parity>`
:**› Default**: :ref:`SerialPort.NoParity <enumitem_SerialPort_NoParity>`
:**› Signal**: parityChanged()
:**› Attributes**: Writable


.. _property_ModbusRtuSlave_portName:

.. _signal_ModbusRtuSlave_portNameChanged:

.. index::
   single: portName

portName
++++++++

This property holds the name of the serial port used for communicating with the Modbus RTU master.

:**› Type**: String
:**› Signal**: portNameChanged()
:**› Attributes**: Writable


.. _property_ModbusRtuSlave_stopBits:

.. _signal_ModbusRtuSlave_stopBitsChanged:

.. index::
   single: stopBits

stopBits
++++++++

This property holds the number of stop bits of the serial port used for communicating with the Modbus RTU master.

:**› Type**: :ref:`SerialPort.StopBits <enum_SerialPort_StopBits>`
:**› Default**: :ref:`SerialPort.OneStop <enumitem_SerialPort_OneStop>`
:**› Signal**: stopBitsChanged()
:**› Attributes**: Writable


.. _example_ModbusRtuSlave:


Example
*******

.. code-block:: qml

    import InCore.Foundation 2.0
    import InCore.Modbus 2.0
    import InCore.IO 2.0
    
    Application {
    
        name: "Modbus RTU slave example"
    
        System {
            id: system
            Polling on cpuLoad { }
            Polling on deviceHumidity { }
            Polling on deviceTemperature { }
        }
    
        LED {
            index: LED.StatusBlue
            value: ledReg.data
        }
    
        ModbusRtuSlave {
            id: slave
            address: 1
            portName: "ttyO1"
            baudRate: SerialPort.Baud250000
    
            // expose CPU load as float (address 0+1)
            ModbusRegister {
                type: ModbusRegister.Input
                address: 0
                dataType: ModbusRegister.Float
                count: 2
                data: system.cpuLoad
            }
    
            // expose device temperature and humidity at address 2+3
            ModbusRegister {
                type: ModbusRegister.Input
                address: 2
                count: 2
                data: [ system.deviceTemperature, system.deviceHumidity ]
            }
    
            // control blue status LED through coil 0
            ModbusRegister {
                id: ledReg
                type: ModbusRegister.Coil
                address: 0
            }
        }
    }
    