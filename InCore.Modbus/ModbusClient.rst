
.. _object_ModbusClient:


:index:`ModbusClient`
---------------------

Description
***********

The ModbusClient object is the base class for all Modbus clients (masters) and manages a number of Modbus slaves to communicate with.

:**› Inherits**: :ref:`ModbusDevice <object_ModbusDevice>`
:**› Inherited by**: :ref:`ModbusRtuMaster <object_ModbusRtuMaster>`, :ref:`ModbusTcpClient <object_ModbusTcpClient>`

Overview
********

Properties
++++++++++

.. hlist::
  :columns: 2

  * :ref:`numberOfRetries <property_ModbusClient_numberOfRetries>`
  * :ref:`slaves <property_ModbusClient_slaves>`
  * :ref:`timeout <property_ModbusClient_timeout>`
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

  * :ref:`pollSlaves() <method_ModbusClient_pollSlaves>`
  * :ref:`ModbusDevice.connectDevice() <method_ModbusDevice_connectDevice>`
  * :ref:`ModbusDevice.disconnectDevice() <method_ModbusDevice_disconnectDevice>`
  * :ref:`Object.fromJson() <method_Object_fromJson>`
  * :ref:`Object.toJson() <method_Object_toJson>`

Signals
+++++++

.. hlist::
  :columns: 1

  * :ref:`slavesDataChanged() <signal_ModbusClient_slavesDataChanged>`
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


.. _property_ModbusClient_numberOfRetries:

.. _signal_ModbusClient_numberOfRetriesChanged:

.. index::
   single: numberOfRetries

numberOfRetries
+++++++++++++++

This property holds the number of retries a client will perform before a request fails.

:**› Type**: SignedInteger
:**› Default**: ``3``
:**› Signal**: numberOfRetriesChanged()
:**› Attributes**: Writable


.. _property_ModbusClient_slaves:

.. _signal_ModbusClient_slavesChanged:

.. index::
   single: slaves

slaves
++++++

This property holds a list of all slaves.

:**› Type**: :ref:`List <object_List>`\<:ref:`ModbusSlave <object_ModbusSlave>`>
:**› Signal**: slavesChanged()
:**› Attributes**: Readonly


.. _property_ModbusClient_timeout:

.. _signal_ModbusClient_timeoutChanged:

.. index::
   single: timeout

timeout
+++++++

This property holds the timeout value used by this client

:**› Type**: SignedInteger
:**› Default**: ``1000``
:**› Signal**: timeoutChanged()
:**› Attributes**: Writable

Methods
*******


.. _method_ModbusClient_pollSlaves:

.. index::
   single: pollSlaves

pollSlaves()
++++++++++++

This method polls the :ref:`slaves <property_ModbusClient_slaves>` property. It is called automatically when using a :ref:`Polling <object_Polling>` property modifier on this property and usually does not have to be called manually.


Signals
*******


.. _signal_ModbusClient_slavesDataChanged:

.. index::
   single: slavesDataChanged

slavesDataChanged(SignedInteger index)
++++++++++++++++++++++++++++++++++++++

This signal is emitted whenever the :ref:`List.dataChanged() <signal_List_dataChanged>` signal is emitted, i.e. the item at ``index`` in the :ref:`slaves <property_ModbusClient_slaves>` list itself emitted the dataChanged() signal.

