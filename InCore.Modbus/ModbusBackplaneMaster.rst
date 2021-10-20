
.. _object_ModbusBackplaneMaster:


:index:`ModbusBackplaneMaster`
------------------------------

Description
***********

The ModbusBackplaneMaster object implements a master for the Modbus-based backplane bus available on HUB-GM200 devices.

:**› Inherits**: :ref:`ModbusRtuMaster <object_ModbusRtuMaster>`

Overview
********

Properties
++++++++++

.. hlist::
  :columns: 3

  * :ref:`ModbusRtuMaster.baudRate <property_ModbusRtuMaster_baudRate>`
  * :ref:`ModbusRtuMaster.dataBits <property_ModbusRtuMaster_dataBits>`
  * :ref:`ModbusRtuMaster.interFrameDelay <property_ModbusRtuMaster_interFrameDelay>`
  * :ref:`ModbusRtuMaster.parity <property_ModbusRtuMaster_parity>`
  * :ref:`ModbusRtuMaster.portName <property_ModbusRtuMaster_portName>`
  * :ref:`ModbusRtuMaster.stopBits <property_ModbusRtuMaster_stopBits>`
  * :ref:`ModbusRtuMaster.turnaroundDelay <property_ModbusRtuMaster_turnaroundDelay>`
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

