
.. _object_UdpDatagram:


:index:`UdpDatagram`
--------------------

Description
***********

The UdpDatagram object contains data and meta data of a UDP datagram received through a :ref:`UdpSocket <object_UdpSocket>` object.

This object was introduced in InCore 2.3.

:**› Inherits**: :ref:`ByteArray <object_ByteArray>`

Overview
********

Properties
++++++++++

.. hlist::
  :columns: 2

  * :ref:`destinationAddress <property_UdpDatagram_destinationAddress>`
  * :ref:`destinationPort <property_UdpDatagram_destinationPort>`
  * :ref:`hopLimit <property_UdpDatagram_hopLimit>`
  * :ref:`senderAddress <property_UdpDatagram_senderAddress>`
  * :ref:`senderPort <property_UdpDatagram_senderPort>`
  * :ref:`ByteArray.arrayBuffer <property_ByteArray_arrayBuffer>`
  * :ref:`ByteArray.base64 <property_ByteArray_base64>`
  * :ref:`ByteArray.data <property_ByteArray_data>`
  * :ref:`ByteArray.hex <property_ByteArray_hex>`
  * :ref:`ByteArray.string <property_ByteArray_string>`
  * :ref:`Object.objectId <property_Object_objectId>`
  * :ref:`Object.parent <property_Object_parent>`

Methods
+++++++

.. hlist::
  :columns: 1

  * :ref:`ByteArray.remove() <method_ByteArray_remove>`
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


.. _property_UdpDatagram_destinationAddress:

.. _signal_UdpDatagram_destinationAddressChanged:

.. index::
   single: destinationAddress

destinationAddress
++++++++++++++++++

This property holds the destination address associated with this datagram. For a datagram received from the network, it is the address the peer node sent the datagram to, which can either be a local address of this machine or a multicast or broadcast address. For an outgoing datagrams, it is the address the datagram should be sent to.

:**› Type**: String
:**› Signal**: destinationAddressChanged()
:**› Attributes**: Writable


.. _property_UdpDatagram_destinationPort:

.. _signal_UdpDatagram_destinationPortChanged:

.. index::
   single: destinationPort

destinationPort
+++++++++++++++

This property holds the port number of the destination associated with this datagram. For a datagram received from the network, it is the local port number that the peer node sent the datagram to. For an outgoing datagram, it is the peer port the datagram should be sent to.

:**› Type**: SignedInteger
:**› Signal**: destinationPortChanged()
:**› Attributes**: Writable


.. _property_UdpDatagram_hopLimit:

.. _signal_UdpDatagram_hopLimitChanged:

.. index::
   single: hopLimit

hopLimit
++++++++

This property holds the hop count limit associated with this datagram to count. The hop count limit is the number of nodes that are allowed to forward the IP packet before it expires and an error is sent back to the sender of the datagram. In IPv4, this value is usually known as *time to live* (TTL).

It is usually not necessary to call this function on datagrams received from the network.

If this is an outgoing packet, this is the value to be set in the IP header upon sending. The valid range for the value is ``1`` to ``255``. This property also accepts a value of ``-1`` to indicate that the operating system should choose the value.

:**› Type**: SignedInteger
:**› Signal**: hopLimitChanged()
:**› Attributes**: Writable


.. _property_UdpDatagram_senderAddress:

.. _signal_UdpDatagram_senderAddressChanged:

.. index::
   single: senderAddress

senderAddress
+++++++++++++

This property holds the sender address associated with this datagram. For a datagram received from the network, it is the address of the peer node that sent the datagram. For an outgoing datagrams, it is the local address to be used when sending.

:**› Type**: String
:**› Signal**: senderAddressChanged()
:**› Attributes**: Writable


.. _property_UdpDatagram_senderPort:

.. _signal_UdpDatagram_senderPortChanged:

.. index::
   single: senderPort

senderPort
++++++++++

This property holds the port number of the sender associated with this datagram. For a datagram received from the network, it is the port number that the peer node sent the datagram from. For an outgoing datagram, it is the local port the datagram should be sent from.

:**› Type**: SignedInteger
:**› Signal**: senderPortChanged()
:**› Attributes**: Writable

