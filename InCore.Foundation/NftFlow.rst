
.. _object_NftFlow:


:index:`NftFlow`
----------------

Description
***********



This object was introduced in InCore 2.1.

:**› Inherits**: :ref:`NftTable <object_NftTable>`
:**› Inherited by**: :ref:`NftAddressTranslation <object_NftAddressTranslation>`

Overview
********

Properties
++++++++++

.. hlist::
  :columns: 2

  * :ref:`destinationAddress <property_NftFlow_destinationAddress>`
  * :ref:`destinationPorts <property_NftFlow_destinationPorts>`
  * :ref:`inputInterface <property_NftFlow_inputInterface>`
  * :ref:`outputInterface <property_NftFlow_outputInterface>`
  * :ref:`protocol <property_NftFlow_protocol>`
  * :ref:`sourceAddress <property_NftFlow_sourceAddress>`
  * :ref:`sourcePorts <property_NftFlow_sourcePorts>`
  * :ref:`NftTable.chains <property_NftTable_chains>`
  * :ref:`NftTable.enabled <property_NftTable_enabled>`
  * :ref:`NftTable.family <property_NftTable_family>`
  * :ref:`NftTable.name <property_NftTable_name>`
  * :ref:`Object.objectId <property_Object_objectId>`
  * :ref:`Object.parent <property_Object_parent>`

Methods
+++++++

.. hlist::
  :columns: 1

  * :ref:`Object.fromJson() <method_Object_fromJson>`
  * :ref:`Object.toJson() <method_Object_toJson>`

Signals
+++++++

.. hlist::
  :columns: 1

  * :ref:`NftTable.chainsDataChanged() <signal_NftTable_chainsDataChanged>`
  * :ref:`Object.completed() <signal_Object_completed>`

Enumerations
++++++++++++

.. hlist::
  :columns: 1

  * :ref:`NftTable.Family <enum_NftTable_Family>`



Properties
**********


.. _property_NftFlow_destinationAddress:

.. _signal_NftFlow_destinationAddressChanged:

.. index::
   single: destinationAddress

destinationAddress
++++++++++++++++++

This property holds the destination address to transmit traffic to for this flow.

:**› Type**: String
:**› Signal**: destinationAddressChanged()
:**› Attributes**: Writable


.. _property_NftFlow_destinationPorts:

.. _signal_NftFlow_destinationPortsChanged:

.. index::
   single: destinationPorts

destinationPorts
++++++++++++++++

This property holds the source ports used by flow implementations, e.g. ``[ 80, 443 ]``.

:**› Type**: Variant
:**› Signal**: destinationPortsChanged()
:**› Attributes**: Writable


.. _property_NftFlow_inputInterface:

.. _signal_NftFlow_inputInterfaceChanged:

.. index::
   single: inputInterface

inputInterface
++++++++++++++

This property holds the network interface to receive traffic from for this flow.

:**› Type**: String
:**› Signal**: inputInterfaceChanged()
:**› Attributes**: Writable


.. _property_NftFlow_outputInterface:

.. _signal_NftFlow_outputInterfaceChanged:

.. index::
   single: outputInterface

outputInterface
+++++++++++++++

This property holds the network interface to transmit traffic to for this flow.

:**› Type**: String
:**› Signal**: outputInterfaceChanged()
:**› Attributes**: Writable


.. _property_NftFlow_protocol:

.. _signal_NftFlow_protocolChanged:

.. index::
   single: protocol

protocol
++++++++



:**› Type**: :ref:`NftRule.Protocol <enum_NftRule_Protocol>`
:**› Signal**: protocolChanged()
:**› Attributes**: Writable


.. _property_NftFlow_sourceAddress:

.. _signal_NftFlow_sourceAddressChanged:

.. index::
   single: sourceAddress

sourceAddress
+++++++++++++

This property holds the source address to receive traffic from for this flow.

:**› Type**: String
:**› Signal**: sourceAddressChanged()
:**› Attributes**: Writable


.. _property_NftFlow_sourcePorts:

.. _signal_NftFlow_sourcePortsChanged:

.. index::
   single: sourcePorts

sourcePorts
+++++++++++

This property holds the source ports used by flow implementations, e.g. ``80``, ``"!= 33-45"`` or ``[ 80, 443 ]``.

:**› Type**: Variant
:**› Signal**: sourcePortsChanged()
:**› Attributes**: Writable