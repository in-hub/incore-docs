
.. _object_NftTable:


:index:`NftTable`
-----------------

Description
***********

The NftTable object represents a `nftables table <https://wiki.nftables.org/wiki-nftables/index.php/Configuring_tables>`_. It consists of a set of :ref:`chains <property_NftTable_chains>` which are being processed depending on the :ref:`family <property_NftTable_family>` property.

This object was introduced in InCore 2.1.

:**› Inherits**: :ref:`Object <object_Object>`
:**› Inherited by**: :ref:`NftAddressTranslation <object_NftAddressTranslation>`, :ref:`NftFlow <object_NftFlow>`

Overview
********

Properties
++++++++++

.. hlist::
  :columns: 1

  * :ref:`chains <property_NftTable_chains>`
  * :ref:`enabled <property_NftTable_enabled>`
  * :ref:`family <property_NftTable_family>`
  * :ref:`name <property_NftTable_name>`
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

  * :ref:`chainsDataChanged() <signal_NftTable_chainsDataChanged>`
  * :ref:`Object.completed() <signal_Object_completed>`

Enumerations
++++++++++++

.. hlist::
  :columns: 1

  * :ref:`Family <enum_NftTable_Family>`



Properties
**********


.. _property_NftTable_chains:

.. _signal_NftTable_chainsChanged:

.. index::
   single: chains

chains
++++++

This property holds a list of chains for this table.

:**› Type**: :ref:`List <object_List>`\<:ref:`NftChain <object_NftChain>`>
:**› Signal**: chainsChanged()
:**› Attributes**: Readonly


.. _property_NftTable_enabled:

.. _signal_NftTable_enabledChanged:

.. index::
   single: enabled

enabled
+++++++

This property holds whether the table is enabled, i.e. it should be included in the :ref:`firewall <object_NftFirewall>` configuration.

:**› Type**: Boolean
:**› Default**: ``true``
:**› Signal**: enabledChanged()
:**› Attributes**: Writable


.. _property_NftTable_family:

.. _signal_NftTable_familyChanged:

.. index::
   single: family

family
++++++

This property holds the family of the Netfilter table. See the :ref:`NftTable.Family <enum_NftTable_Family>` enum for details.

:**› Type**: :ref:`Family <enum_NftTable_Family>`
:**› Default**: :ref:`NftTable.IP <enumitem_NftTable_IP>`
:**› Signal**: familyChanged()
:**› Attributes**: Writable


.. _property_NftTable_name:

.. _signal_NftTable_nameChanged:

.. index::
   single: name

name
++++

This property holds the name of the firewall table, e.g. ``filter``.

:**› Type**: String
:**› Signal**: nameChanged()
:**› Attributes**: Writable

Signals
*******


.. _signal_NftTable_chainsDataChanged:

.. index::
   single: chainsDataChanged

chainsDataChanged(SignedInteger index)
++++++++++++++++++++++++++++++++++++++

This signal is emitted whenever the :ref:`List.dataChanged() <signal_List_dataChanged>` signal is emitted, i.e. the item at ``index`` in the :ref:`chains <property_NftTable_chains>` list itself emitted the dataChanged() signal.


Enumerations
************


.. _enum_NftTable_Family:

.. index::
   single: Family

Family
++++++

This enumeration describes supported address families for which traffic/packets can be processed by tables. See the `nftables documentation on families <https://wiki.nftables.org/wiki-nftables/index.php/Nftables_families>`_ for further details

.. index::
   single: NftTable.IP
.. index::
   single: NftTable.IP6
.. index::
   single: NftTable.INet
.. index::
   single: NftTable.ARP
.. index::
   single: NftTable.Bridge
.. index::
   single: NftTable.NetDev
.. list-table::
  :widths: auto
  :header-rows: 1

  * - Name
    - Value
    - Description

      .. _enumitem_NftTable_IP:
  * - ``NftTable.IP``
    - ``0``
    - Tables of this family will see IPv4 traffic/packets.

      .. _enumitem_NftTable_IP6:
  * - ``NftTable.IP6``
    - ``1``
    - Tables of this family will see IPv6 traffic/packets.

      .. _enumitem_NftTable_INet:
  * - ``NftTable.INet``
    - ``2``
    - Tables of this family will see both IPv4/IPv6 traffic/packets, designed to improve dual stack support. Both IPv4/IPv6 packets will traverse the same rules. Rules for IPv4 packets won't affect IPv6 packets. Rules for both L3 protocol will affect both.

      .. _enumitem_NftTable_ARP:
  * - ``NftTable.ARP``
    - ``3``
    - Tables of this family will see ARP-level (i.e, L2) traffic, before any L3 handling is done.

      .. _enumitem_NftTable_Bridge:
  * - ``NftTable.Bridge``
    - ``4``
    - Tables of this family will see traffic/packets traversing bridges (i.e. switching). No assumptions are made about L3 protocols.

      .. _enumitem_NftTable_NetDev:
  * - ``NftTable.NetDev``
    - ``5``
    - This family provides the ingress hook, that allows classifying packets that the driver has just passed up to the networking stack. This means the table sees all network traffic for the NIC getting in. No assumptions are made about L2 or L3 protocols, therefore ARP traffic can be filtered from here.

Example
*******
See :ref:`NftFirewall example <example_NftFirewall>` on how to use NftTable.
