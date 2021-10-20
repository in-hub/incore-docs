
.. _object_ModbusRtuMaster:


:index:`ModbusRtuMaster`
------------------------

Description
***********

The ModbusRtuMaster object implements a Modbus RTU master which communicates with Modbus slaves via a serial port.

:**› Inherits**: :ref:`ModbusClient <object_ModbusClient>`
:**› Inherited by**: :ref:`ModbusBackplaneMaster <object_ModbusBackplaneMaster>`

Overview
********

Properties
++++++++++

.. hlist::
  :columns: 3

  * :ref:`baudRate <property_ModbusRtuMaster_baudRate>`
  * :ref:`dataBits <property_ModbusRtuMaster_dataBits>`
  * :ref:`interFrameDelay <property_ModbusRtuMaster_interFrameDelay>`
  * :ref:`parity <property_ModbusRtuMaster_parity>`
  * :ref:`portName <property_ModbusRtuMaster_portName>`
  * :ref:`stopBits <property_ModbusRtuMaster_stopBits>`
  * :ref:`turnaroundDelay <property_ModbusRtuMaster_turnaroundDelay>`
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


.. _property_ModbusRtuMaster_baudRate:

.. _signal_ModbusRtuMaster_baudRateChanged:

.. index::
   single: baudRate

baudRate
++++++++

This property holds the data baud rate of the serial port used for communicating with the Modbus RTU slave.

:**› Type**: :ref:`SerialPort.BaudRate <enum_SerialPort_BaudRate>`
:**› Default**: :ref:`SerialPort.Baud115200 <enumitem_SerialPort_Baud115200>`
:**› Signal**: baudRateChanged()
:**› Attributes**: Writable


.. _property_ModbusRtuMaster_dataBits:

.. _signal_ModbusRtuMaster_dataBitsChanged:

.. index::
   single: dataBits

dataBits
++++++++

This property holds the number of data bits of the serial port used for communicating with the Modbus RTU slave.

:**› Type**: :ref:`SerialPort.DataBits <enum_SerialPort_DataBits>`
:**› Default**: :ref:`SerialPort.Data8 <enumitem_SerialPort_Data8>`
:**› Signal**: dataBitsChanged()
:**› Attributes**: Writable


.. _property_ModbusRtuMaster_interFrameDelay:

.. _signal_ModbusRtuMaster_interFrameDelayChanged:

.. index::
   single: interFrameDelay

interFrameDelay
+++++++++++++++

This property holds the amount of microseconds for the silent interval between two consecutive Modbus messages. By default, a pre-calculated value according to the Modbus specification is used. An active or running connection is not affected by such delay changes. If this property is set to ``-1`` or to a number less than the pre-calculated delay then the pre-calculated value is used as frame delay.

:**› Type**: SignedInteger
:**› Signal**: interFrameDelayChanged()
:**› Attributes**: Writable


.. _property_ModbusRtuMaster_parity:

.. _signal_ModbusRtuMaster_parityChanged:

.. index::
   single: parity

parity
++++++

This property holds the parity mode of the serial port used for communicating with the Modbus RTU slave.

:**› Type**: :ref:`SerialPort.Parity <enum_SerialPort_Parity>`
:**› Default**: :ref:`SerialPort.NoParity <enumitem_SerialPort_NoParity>`
:**› Signal**: parityChanged()
:**› Attributes**: Writable


.. _property_ModbusRtuMaster_portName:

.. _signal_ModbusRtuMaster_portNameChanged:

.. index::
   single: portName

portName
++++++++

This property holds the name of the serial port used for communicating with the Modbus RTU slave.

:**› Type**: String
:**› Signal**: portNameChanged()
:**› Attributes**: Writable


.. _property_ModbusRtuMaster_stopBits:

.. _signal_ModbusRtuMaster_stopBitsChanged:

.. index::
   single: stopBits

stopBits
++++++++

This property holds the number of stop bits of the serial port used for communicating with the Modbus RTU slave.

:**› Type**: :ref:`SerialPort.StopBits <enum_SerialPort_StopBits>`
:**› Default**: :ref:`SerialPort.OneStop <enumitem_SerialPort_OneStop>`
:**› Signal**: stopBitsChanged()
:**› Attributes**: Writable


.. _property_ModbusRtuMaster_turnaroundDelay:

.. _signal_ModbusRtuMaster_turnaroundDelayChanged:

.. index::
   single: turnaroundDelay

turnaroundDelay
+++++++++++++++

This property holds the amount of milliseconds for the silent interval between a Modbus broadcast and a consecutive Modbus messages. Typically the turnaround delay is in the range of ``100`` to ``200`` milliseconds.

This property was introduced in InCore 2.5.

:**› Type**: SignedInteger
:**› Signal**: turnaroundDelayChanged()
:**› Attributes**: Writable


.. _example_ModbusRtuMaster:


Example
*******

.. code-block:: qml

    import InCore.Foundation 2.5
    import InCore.Modbus 2.5
    
    Application {
    
        name: "Modbus RTU master example"
    
        ModbusRtuMaster {
    
            // set serial port parameters
            portName: "ttyO1"
            baudRate: SerialPort.Baud500000
            dataBits: SerialPort.Data8
            parity: SerialPort.NoParity
            stopBits: SerialPort.OneStop
    
            ModbusSlave {
                // talk to slave with ID 5
                address: 5
    
                // read pressure from input register 7
                ModbusRegister {
                    id: pressure
                    type: ModbusRegister.Input
                    address: 7
                    onDataChanged: console.log("Pressure", data)
                }
    
                // read registers every 100 ms
                Polling on registers { interval: 100 }
            }
    
            // print error message if something goes wrong
            onErrorOccurred: console.log(errorString)
        }
    }
    