
.. _object_ModbusServer:


:index:`ModbusServer`
---------------------

Description
***********

The ModbusServer object is the base class for all Modbus servers (slaves) and manages a number of slaves to communicate with.

This object was introduced in InCore 2.0.

:**› Inherits**: :ref:`ModbusDevice <object_ModbusDevice>`
:**› Inherited by**: :ref:`ModbusRtuSlave <object_ModbusRtuSlave>`, :ref:`ModbusTcpServer <object_ModbusTcpServer>`

Overview
********

Properties
++++++++++

.. hlist::
  :columns: 2

  * :ref:`address <property_ModbusServer_address>`
  * :ref:`registers <property_ModbusServer_registers>`
  * :ref:`ModbusDevice.activityLed <property_ModbusDevice_activityLed>`
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
  * :ref:`Object.serializeProperties() <method_Object_serializeProperties>`
  * :ref:`Object.toJson() <method_Object_toJson>`

Signals
+++++++

.. hlist::
  :columns: 1

  * :ref:`dataErrorOccurred() <signal_ModbusServer_dataErrorOccurred>`
  * :ref:`mapErrorOccurred() <signal_ModbusServer_mapErrorOccurred>`
  * :ref:`registersDataChanged() <signal_ModbusServer_registersDataChanged>`
  * :ref:`ModbusDevice.connected() <signal_ModbusDevice_connected>`
  * :ref:`ModbusDevice.disconnected() <signal_ModbusDevice_disconnected>`
  * :ref:`ModbusDevice.errorOccurred() <signal_ModbusDevice_errorOccurred>`
  * :ref:`Object.completed() <signal_Object_completed>`

Enumerations
++++++++++++

.. hlist::
  :columns: 1

  * :ref:`ModbusDevice.BusInterface <enum_ModbusDevice_BusInterface>`
  * :ref:`ModbusDevice.Error <enum_ModbusDevice_Error>`
  * :ref:`ModbusDevice.State <enum_ModbusDevice_State>`



Properties
**********


.. _property_ModbusServer_address:

.. _signal_ModbusServer_addressChanged:

.. index::
   single: address

address
+++++++

This property holds the address (slave ID) of the local Modbus server.

:**› Type**: SignedInteger
:**› Signal**: addressChanged()
:**› Attributes**: Writable


.. _property_ModbusServer_registers:

.. _signal_ModbusServer_registersChanged:

.. index::
   single: registers

registers
+++++++++

This property holds a list of Modbus registers to make available to Modbus clients.

:**› Type**: :ref:`List <object_List>`\<:ref:`ModbusRegister <object_ModbusRegister>`>
:**› Signal**: registersChanged()
:**› Attributes**: Readonly

Signals
*******


.. _signal_ModbusServer_dataErrorOccurred:

.. index::
   single: dataErrorOccurred

dataErrorOccurred()
+++++++++++++++++++

This signal is emitted in very rare cases when the update the internal data map fails. This happens if the internal register map is out of sync due to an inconsistent property update order.



.. _signal_ModbusServer_mapErrorOccurred:

.. index::
   single: mapErrorOccurred

mapErrorOccurred()
++++++++++++++++++

This signal is emitted whenever an error occurs while building or updating the internal register map. This usually indicates a problem with the :ref:`type <property_ModbusRegister_type>`, :ref:`address <property_ModbusRegister_address>` or :ref:`count <property_ModbusRegister_count>` of one or multiple :ref:`Modbus registers <object_ModbusRegister>`.



.. _signal_ModbusServer_registersDataChanged:

.. index::
   single: registersDataChanged

registersDataChanged(SignedInteger index)
+++++++++++++++++++++++++++++++++++++++++

This signal is emitted whenever the :ref:`List.dataChanged() <signal_List_dataChanged>` signal is emitted, i.e. the item at ``index`` in the :ref:`registers <property_ModbusServer_registers>` list itself emitted the dataChanged() signal.

