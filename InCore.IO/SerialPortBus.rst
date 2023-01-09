
.. _object_SerialPortBus:


:index:`SerialPortBus`
----------------------

Description
***********

The SerialPortBus object provides an abstract bus of endpoints connected through multiple serial ports. The bus manages the data transfer from/to the endpoints while enforcing certain communication patterns for the ports, e.g. limiting the number of simultaneously open serial ports through the :ref:`maximumActiveEndpointCount <property_SerialPortBus_maximumActiveEndpointCount>` property.

This object was introduced in InCore 2.0.

:**› Inherits**: :ref:`Object <object_Object>`

Overview
********

Properties
++++++++++

.. hlist::
  :columns: 1

  * :ref:`maximumActiveEndpointCount <property_SerialPortBus_maximumActiveEndpointCount>`
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


.. _property_SerialPortBus_maximumActiveEndpointCount:

.. _signal_SerialPortBus_maximumActiveEndpointCountChanged:

.. index::
   single: maximumActiveEndpointCount

maximumActiveEndpointCount
++++++++++++++++++++++++++

This property holds the maximum number of active endpoints. This allows limiting the total number of simultaneously opened serial ports, e.g. to work around limitations of the USB host controller when working with many USB serial converter devices.

:**› Type**: SignedInteger
:**› Default**: ``8``
:**› Signal**: maximumActiveEndpointCountChanged()
:**› Attributes**: Writable

