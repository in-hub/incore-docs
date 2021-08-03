
.. _object_BackplaneBusDevice:


:index:`BackplaneBusDevice`
---------------------------

Description
***********

The BackplaneBusDevice object represents a device on the backplane bus.

:**› Inherits**: :ref:`Object <object_Object>`
:**› Inherited by**: :ref:`EnergyAddonEN100 <object_EnergyAddonEN100>`

Overview
********

Properties
++++++++++

.. hlist::
  :columns: 1

  * :ref:`address <property_BackplaneBusDevice_address>`
  * :ref:`online <property_BackplaneBusDevice_online>`
  * :ref:`productId <property_BackplaneBusDevice_productId>`
  * :ref:`serialNumber <property_BackplaneBusDevice_serialNumber>`
  * :ref:`Object.objectId <property_Object_objectId>`
  * :ref:`Object.parent <property_Object_parent>`

Methods
+++++++

.. hlist::
  :columns: 1

  * :ref:`Object.deserializeProperties() <method_Object_deserializeProperties>`
  * :ref:`Object.fromJson() <method_Object_fromJson>`
  * :ref:`Object.toJson() <method_Object_toJson>`

Signals
+++++++

.. hlist::
  :columns: 1

  * :ref:`Object.completed() <signal_Object_completed>`



Properties
**********


.. _property_BackplaneBusDevice_address:

.. _signal_BackplaneBusDevice_addressChanged:

.. index::
   single: address

address
+++++++

This property holds the address of the device on the bus.

:**› Type**: UnsignedInteger
:**› Signal**: addressChanged()
:**› Attributes**: Writable


.. _property_BackplaneBusDevice_online:

.. _signal_BackplaneBusDevice_onlineChanged:

.. index::
   single: online

online
++++++

This property holds whether the device has been discovered on the bus and is online.

:**› Type**: Boolean
:**› Signal**: onlineChanged()
:**› Attributes**: Readonly


.. _property_BackplaneBusDevice_productId:

.. _signal_BackplaneBusDevice_productIdChanged:

.. index::
   single: productId

productId
+++++++++

This property holds the product ID of the device.

:**› Type**: UnsignedInteger
:**› Signal**: productIdChanged()
:**› Attributes**: Readonly


.. _property_BackplaneBusDevice_serialNumber:

.. _signal_BackplaneBusDevice_serialNumberChanged:

.. index::
   single: serialNumber

serialNumber
++++++++++++

This property holds the serial number of the device which is used for device discovery.

:**› Type**: UnsignedInteger
:**› Signal**: serialNumberChanged()
:**› Attributes**: Writable
