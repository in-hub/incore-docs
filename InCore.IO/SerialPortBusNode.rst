
.. _object_SerialPortBusNode:


:index:`SerialPortBusNode`
--------------------------

Description
***********

The SerialPortBusNode object provides properties for communicating with a device via a serial port and manages the communication via a :ref:`SerialPortBus <object_SerialPortBus>`.

This object was introduced in InCore 2.2.

:**› Inherits**: :ref:`Object <object_Object>`
:**› Inherited by**: :ref:`AlphasenseOpcN3 <object_AlphasenseOpcN3>`, :ref:`SensirionHDLC <object_SensirionHDLC>`

Overview
********

Properties
++++++++++

.. hlist::
  :columns: 1

  * :ref:`bus <property_SerialPortBusNode_bus>`
  * :ref:`portName <property_SerialPortBusNode_portName>`
  * :ref:`responseTimeout <property_SerialPortBusNode_responseTimeout>`
  * :ref:`serialPort <property_SerialPortBusNode_serialPort>`
  * :ref:`Object.objectId <property_Object_objectId>`
  * :ref:`Object.parent <property_Object_parent>`

Methods
+++++++

.. hlist::
  :columns: 1

  * :ref:`Object.deserializeProperties() <method_Object_deserializeProperties>`
  * :ref:`Object.fromJson() <method_Object_fromJson>`
  * :ref:`Object.serializeProperties() <method_Object_serializeProperties>`
  * :ref:`Object.toJson() <method_Object_toJson>`

Signals
+++++++

.. hlist::
  :columns: 1

  * :ref:`Object.completed() <signal_Object_completed>`



Properties
**********


.. _property_SerialPortBusNode_bus:

.. _signal_SerialPortBusNode_busChanged:

.. index::
   single: bus

bus
+++

This property holds the bus which to use for reading and writing data from a serial port. If not set a global bus with default :ref:`SerialPortBus.maximumActiveEndpointCount <property_SerialPortBus_maximumActiveEndpointCount>` is used.

:**› Type**: :ref:`SerialPortBus <object_SerialPortBus>`
:**› Signal**: busChanged()
:**› Attributes**: Writable, Optional


.. _property_SerialPortBusNode_portName:

.. _signal_SerialPortBusNode_portNameChanged:

.. index::
   single: portName

portName
++++++++

This property holds an alias for the :ref:`SerialPort.portName <property_SerialPort_portName>` property of :ref:`serialPort <property_SerialPortBusNode_serialPort>`. It allows using modifiers such as :ref:`Select <object_Select>` on the port name.

This property was introduced in InCore 2.5.

:**› Type**: String
:**› Signal**: portNameChanged()
:**› Attributes**: Writable


.. _property_SerialPortBusNode_responseTimeout:

.. _signal_SerialPortBusNode_responseTimeoutChanged:

.. index::
   single: responseTimeout

responseTimeout
+++++++++++++++

This property holds the number of milliseconds to wait for a response from the device after sending a data frame.

:**› Type**: SignedInteger
:**› Default**: ``5000``
:**› Signal**: responseTimeoutChanged()
:**› Attributes**: Writable


.. _property_SerialPortBusNode_serialPort:

.. _signal_SerialPortBusNode_serialPortChanged:

.. index::
   single: serialPort

serialPort
++++++++++

This property holds the serial port to use for communicating with the device via the :ref:`bus <property_SerialPortBusNode_bus>`.

:**› Type**: :ref:`SerialPort <object_SerialPort>`
:**› Signal**: serialPortChanged()
:**› Attributes**: Writable
