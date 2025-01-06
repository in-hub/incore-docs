
.. _object_SpiDevice:


:index:`SpiDevice`
------------------

Description
***********

The SpiDevice object represents a generic SPI device operating on a parent :ref:`SpiBus <object_SpiBus>` object. Data can be written to an SPI slave at address :ref:`address <property_SpiDevice_address>` using :ref:`write() <method_SpiDevice_write>` and read from an SPI slave using :ref:`read() <method_SpiDevice_read>`.

:**› Inherits**: :ref:`Object <object_Object>`
:**› Inherited by**: :ref:`Ade9000 <object_Ade9000>`

Overview
********

Properties
++++++++++

.. hlist::
  :columns: 1

  * :ref:`address <property_SpiDevice_address>`
  * :ref:`Object.objectId <property_Object_objectId>`
  * :ref:`Object.parent <property_Object_parent>`

Methods
+++++++

.. hlist::
  :columns: 1

  * :ref:`read() <method_SpiDevice_read>`
  * :ref:`transfer() <method_SpiDevice_transfer>`
  * :ref:`write() <method_SpiDevice_write>`
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


.. _property_SpiDevice_address:

.. _signal_SpiDevice_addressChanged:

.. index::
   single: address

address
+++++++

This property holds the bus address of the SPI device. It's up to the actual :ref:`SpiBus <object_SpiBus>` implementation to select the corresponding slave.

:**› Type**: UnsignedInteger
:**› Default**: ``0``
:**› Signal**: addressChanged()
:**› Attributes**: Writable

Methods
*******


.. _method_SpiDevice_read:

.. index::
   single: read

read(UnsignedInteger bytes)
+++++++++++++++++++++++++++

This method reads the specified number of bytes from the SPI slave. Returns an empty buffer if the transfer failed.

:**› Returns**: ArrayBuffer



.. _method_SpiDevice_transfer:

.. index::
   single: transfer

transfer(ArrayBuffer data)
++++++++++++++++++++++++++

This method transfers the specified bytes to the SPI slave and returns the received bytes (or empty data if transfer failed).

:**› Returns**: ArrayBuffer



.. _method_SpiDevice_write:

.. index::
   single: write

write(ArrayBuffer data)
+++++++++++++++++++++++

This method writes the specified bytes to the SPI slave. Returns ``false`` if the transfer failed.

:**› Returns**: Boolean


