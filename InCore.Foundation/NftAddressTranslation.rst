
.. _object_NftAddressTranslation:


:index:`NftAddressTranslation`
------------------------------

Description
***********



This object was introduced in InCore 2.1.

:**› Inherits**: :ref:`NftFlow <object_NftFlow>`

Overview
********

Properties
++++++++++

.. hlist::
  :columns: 3

  * :ref:`masquerade <property_NftAddressTranslation_masquerade>`
  * :ref:`natDestinationAddress <property_NftAddressTranslation_natDestinationAddress>`
  * :ref:`natDestinationPort <property_NftAddressTranslation_natDestinationPort>`
  * :ref:`natSourceAddress <property_NftAddressTranslation_natSourceAddress>`
  * :ref:`NftFlow.destinationAddress <property_NftFlow_destinationAddress>`
  * :ref:`NftFlow.destinationPorts <property_NftFlow_destinationPorts>`
  * :ref:`NftFlow.inputInterface <property_NftFlow_inputInterface>`
  * :ref:`NftFlow.outputInterface <property_NftFlow_outputInterface>`
  * :ref:`NftFlow.protocol <property_NftFlow_protocol>`
  * :ref:`NftFlow.sourceAddress <property_NftFlow_sourceAddress>`
  * :ref:`NftFlow.sourcePorts <property_NftFlow_sourcePorts>`
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

  * :ref:`Object.deserializeProperties() <method_Object_deserializeProperties>`
  * :ref:`Object.fromJson() <method_Object_fromJson>`
  * :ref:`Object.serializeProperties() <method_Object_serializeProperties>`
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


.. _property_NftAddressTranslation_masquerade:

.. _signal_NftAddressTranslation_masqueradeChanged:

.. index::
   single: masquerade

masquerade
++++++++++

This property holds whether to masquerade connections, i.e. rewrite the source address of packets.

:**› Type**: Boolean
:**› Default**: ``false``
:**› Signal**: masqueradeChanged()
:**› Attributes**: Writable


.. _property_NftAddressTranslation_natDestinationAddress:

.. _signal_NftAddressTranslation_natDestinationAddressChanged:

.. index::
   single: natDestinationAddress

natDestinationAddress
+++++++++++++++++++++

This property holds the address to use for rewriting the destination address of packets.

:**› Type**: String
:**› Signal**: natDestinationAddressChanged()
:**› Attributes**: Writable


.. _property_NftAddressTranslation_natDestinationPort:

.. _signal_NftAddressTranslation_natDestinationPortChanged:

.. index::
   single: natDestinationPort

natDestinationPort
++++++++++++++++++

This property holds the NAT destination port which to forward packets to if it differs from the original destination port.

This property was introduced in InCore 2.7.

:**› Type**: SignedInteger
:**› Default**: ``0``
:**› Signal**: natDestinationPortChanged()
:**› Attributes**: Writable


.. _property_NftAddressTranslation_natSourceAddress:

.. _signal_NftAddressTranslation_natSourceAddressChanged:

.. index::
   single: natSourceAddress

natSourceAddress
++++++++++++++++

This property holds the address to use for rewriting the source address of packets.

:**› Type**: String
:**› Signal**: natSourceAddressChanged()
:**› Attributes**: Writable


.. _example_NftAddressTranslation:


Example
*******

.. code-block:: qml

    import InCore.Foundation 2.5
    
    NftFirewall {
        NftAddressTranslation {
            inputInterface: "usb0"
            destinationAddress: "192.168.123.1"
            natSourceAddress: "192.168.19.1"
            natDestinationAddress: "192.168.19.2"
        }
    
        onRulesetChanged: console.log(ruleset)
    }
    