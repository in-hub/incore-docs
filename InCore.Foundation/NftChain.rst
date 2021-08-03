
.. _object_NftChain:


:index:`NftChain`
-----------------

Description
***********

The NftChain object represents a `nftables chain <https://wiki.nftables.org/wiki-nftables/index.php/Configuring_chains>`_. It consists of a set of :ref:`rules <property_NftChain_rules>` which are being processed depending on the :ref:`type <property_NftChain_type>`, :ref:`hook <property_NftChain_hook>`, :ref:`priority <property_NftChain_priority>` and :ref:`policy <property_NftChain_policy>` properties.

This object was introduced in InCore 2.1.

:**› Inherits**: :ref:`Object <object_Object>`

Overview
********

Properties
++++++++++

.. hlist::
  :columns: 2

  * :ref:`enabled <property_NftChain_enabled>`
  * :ref:`hook <property_NftChain_hook>`
  * :ref:`name <property_NftChain_name>`
  * :ref:`policy <property_NftChain_policy>`
  * :ref:`priority <property_NftChain_priority>`
  * :ref:`rawRules <property_NftChain_rawRules>`
  * :ref:`rules <property_NftChain_rules>`
  * :ref:`type <property_NftChain_type>`
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

  * :ref:`rulesDataChanged() <signal_NftChain_rulesDataChanged>`
  * :ref:`Object.completed() <signal_Object_completed>`

Enumerations
++++++++++++

.. hlist::
  :columns: 1

  * :ref:`Hook <enum_NftChain_Hook>`
  * :ref:`Policy <enum_NftChain_Policy>`
  * :ref:`Priority <enum_NftChain_Priority>`
  * :ref:`Type <enum_NftChain_Type>`



Properties
**********


.. _property_NftChain_enabled:

.. _signal_NftChain_enabledChanged:

.. index::
   single: enabled

enabled
+++++++

This property holds whether the chain is enabled, i.e. it should be included in the corresponding :ref:`table <object_NftTable>`.

:**› Type**: Boolean
:**› Default**: ``true``
:**› Signal**: enabledChanged()
:**› Attributes**: Writable


.. _property_NftChain_hook:

.. _signal_NftChain_hookChanged:

.. index::
   single: hook

hook
++++

This property holds a the stage of the packet while it's being processed through the kernel. See the `nftables documentation on chains <https://wiki.nftables.org/wiki-nftables/index.php/Quick_reference-nftables_in_10_minutes#Chains>`_ for details

:**› Type**: :ref:`Hook <enum_NftChain_Hook>`
:**› Default**: :ref:`NftChain.Input <enumitem_NftChain_Input>`
:**› Signal**: hookChanged()
:**› Attributes**: Writable


.. _property_NftChain_name:

.. _signal_NftChain_nameChanged:

.. index::
   single: name

name
++++

This property holds the name of the firewall chain, e.g. ``input``.

:**› Type**: String
:**› Signal**: nameChanged()
:**› Attributes**: Writable


.. _property_NftChain_policy:

.. _signal_NftChain_policyChanged:

.. index::
   single: policy

policy
++++++

This property holds the default verdict statement to control the flow in the chain. See the :ref:`Policy <enum_NftChain_Policy>` enumeration or details.

:**› Type**: :ref:`Policy <enum_NftChain_Policy>`
:**› Default**: :ref:`NftChain.Accept <enumitem_NftChain_Accept>`
:**› Signal**: policyChanged()
:**› Attributes**: Writable


.. _property_NftChain_priority:

.. _signal_NftChain_priorityChanged:

.. index::
   single: priority

priority
++++++++

This property holds a number used to order the chains or to set them between some Netfilter operations. See the `nftables documentation on chains <https://wiki.nftables.org/wiki-nftables/index.php/Quick_reference-nftables_in_10_minutes#Chains>`_ for details

:**› Type**: :ref:`Priority <enum_NftChain_Priority>`
:**› Default**: :ref:`NftChain.FilterPriority <enumitem_NftChain_FilterPriority>`
:**› Signal**: priorityChanged()
:**› Attributes**: Writable


.. _property_NftChain_rawRules:

.. _signal_NftChain_rawRulesChanged:

.. index::
   single: rawRules

rawRules
++++++++

This property holds a list of nftables rules as defined inside nftables chains, e.g. ``[ "ip daddr 8.8.8.8 counter packets 0 bytes 0", "tcp dport ssh counter packets 0 bytes 0" ]``.

Consider using :ref:`NftRule <object_NftRule>` objects with the :ref:`rules <property_NftChain_rules>` property.

.. seealso::

	 * `nftables documentation on rules <https://wiki.nftables.org/wiki-nftables/index.php/Simple_rule_management>`_
	 * `nftables quick reference on rules <https://wiki.nftables.org/wiki-nftables/index.php/Quick_reference-nftables_in_10_minutes#Rules>`_ 

:**› Type**: StringList
:**› Signal**: rawRulesChanged()
:**› Attributes**: Writable


.. _property_NftChain_rules:

.. _signal_NftChain_rulesChanged:

.. index::
   single: rules

rules
+++++

This property holds a list of nftables rules described by :ref:`NftRule <object_NftRule>` objects.

:**› Type**: :ref:`List <object_List>`\<:ref:`NftRule <object_NftRule>`>
:**› Signal**: rulesChanged()
:**› Attributes**: Readonly


.. _property_NftChain_type:

.. _signal_NftChain_typeChanged:

.. index::
   single: type

type
++++

This property holds the type of the nftables chain. See the `nftables documentation on chains <https://wiki.nftables.org/wiki-nftables/index.php/Quick_reference-nftables_in_10_minutes#Chains>`_ for details

:**› Type**: :ref:`Type <enum_NftChain_Type>`
:**› Default**: :ref:`NftChain.Filter <enumitem_NftChain_Filter>`
:**› Signal**: typeChanged()
:**› Attributes**: Writable

Signals
*******


.. _signal_NftChain_rulesDataChanged:

.. index::
   single: rulesDataChanged

rulesDataChanged(SignedInteger index)
+++++++++++++++++++++++++++++++++++++

This signal is emitted whenever the :ref:`List.dataChanged() <signal_List_dataChanged>` signal is emitted, i.e. the item at ``index`` in the :ref:`rules <property_NftChain_rules>` list itself emitted the dataChanged() signal.


Enumerations
************


.. _enum_NftChain_Hook:

.. index::
   single: Hook

Hook
++++

This enumeration describes stages of the packet processing at which the chains are processed.

.. index::
   single: NftChain.Prerouting
.. index::
   single: NftChain.Input
.. index::
   single: NftChain.Forward
.. index::
   single: NftChain.Output
.. index::
   single: NftChain.Postrouting
.. index::
   single: NftChain.Ingress
.. list-table::
  :widths: auto
  :header-rows: 1

  * - Name
    - Value
    - Description

      .. _enumitem_NftChain_Prerouting:
  * - ``NftChain.Prerouting``
    - ``0``
    - Process chain before routing decision when it's not known if packets are addressed to the local or remote systems.

      .. _enumitem_NftChain_Input:
  * - ``NftChain.Input``
    - ``1``
    - Process chain after the routing decision for packets which are directed to the local system and/or processes running in system.

      .. _enumitem_NftChain_Forward:
  * - ``NftChain.Forward``
    - ``2``
    - Process chain after the routing decision for packets which are not directed to the local system and/or processes running in system.

      .. _enumitem_NftChain_Output:
  * - ``NftChain.Output``
    - ``3``
    - Process chain for packets originating from processes on the local system.

      .. _enumitem_NftChain_Postrouting:
  * - ``NftChain.Postrouting``
    - ``4``
    - Process chain after the routing decision for packets leaving the local system.

      .. _enumitem_NftChain_Ingress:
  * - ``NftChain.Ingress``
    - ``5``
    - Process chain to filter traffic even before prerouting, right after the packet is received by the NIC driver. This hook is available for the :ref:`NftTable.NetDev <enumitem_NftTable_NetDev>` family only.


.. _enum_NftChain_Policy:

.. index::
   single: Policy

Policy
++++++



.. index::
   single: NftChain.Accept
.. index::
   single: NftChain.Drop
.. index::
   single: NftChain.Queue
.. index::
   single: NftChain.Continue
.. index::
   single: NftChain.Return
.. list-table::
  :widths: auto
  :header-rows: 1

  * - Name
    - Value
    - Description

      .. _enumitem_NftChain_Accept:
  * - ``NftChain.Accept``
    - ``0``
    - 

      .. _enumitem_NftChain_Drop:
  * - ``NftChain.Drop``
    - ``1``
    - 

      .. _enumitem_NftChain_Queue:
  * - ``NftChain.Queue``
    - ``2``
    - 

      .. _enumitem_NftChain_Continue:
  * - ``NftChain.Continue``
    - ``3``
    - 

      .. _enumitem_NftChain_Return:
  * - ``NftChain.Return``
    - ``4``
    - 


.. _enum_NftChain_Priority:

.. index::
   single: Priority

Priority
++++++++

This enumeration describes priorities which can be used to order the chains or to put them before or after some Netfilter internal operations. For example, a chain on the prerouting hook with the priority ``-300`` will be placed before connection tracking operations.

.. index::
   single: NftChain.FirstPriority
.. index::
   single: NftChain.ConnTrackDefragPriority
.. index::
   single: NftChain.RawPriority
.. index::
   single: NftChain.SeLinuxFirstPriority
.. index::
   single: NftChain.ConnTrackPriority
.. index::
   single: NftChain.ManglePriority
.. index::
   single: NftChain.DestinationNatPriority
.. index::
   single: NftChain.FilterPriority
.. index::
   single: NftChain.SecurityPriority
.. index::
   single: NftChain.SourceNatPriority
.. index::
   single: NftChain.SeLinuxLastPriority
.. index::
   single: NftChain.ConnTrackHelperPriority
.. index::
   single: NftChain.ConnTrackConfirmPriority
.. index::
   single: NftChain.LastPriority
.. list-table::
  :widths: auto
  :header-rows: 1

  * - Name
    - Value
    - Description

      .. _enumitem_NftChain_FirstPriority:
  * - ``NftChain.FirstPriority``
    - ``-2147483648``
    - Highest priority to process the chain before all other chains with lower priorities.

      .. _enumitem_NftChain_ConnTrackDefragPriority:
  * - ``NftChain.ConnTrackDefragPriority``
    - ``-400``
    - Priority of defragmentation.

      .. _enumitem_NftChain_RawPriority:
  * - ``NftChain.RawPriority``
    - ``-300``
    - Traditional priority of the raw table placed before connection tracking operation.

      .. _enumitem_NftChain_SeLinuxFirstPriority:
  * - ``NftChain.SeLinuxFirstPriority``
    - ``-225``
    - Priority for SELinux operations.

      .. _enumitem_NftChain_ConnTrackPriority:
  * - ``NftChain.ConnTrackPriority``
    - ``-200``
    - Priority for connection tracking operations.

      .. _enumitem_NftChain_ManglePriority:
  * - ``NftChain.ManglePriority``
    - ``-150``
    - Priority for mangle operations.

      .. _enumitem_NftChain_DestinationNatPriority:
  * - ``NftChain.DestinationNatPriority``
    - ``-100``
    - Priority for chains implementing destination NAT.

      .. _enumitem_NftChain_FilterPriority:
  * - ``NftChain.FilterPriority``
    - ``0``
    - Priority for chains implementing packet filtering operations.

      .. _enumitem_NftChain_SecurityPriority:
  * - ``NftChain.SecurityPriority``
    - ``50``
    - Priority for chains implementing source NAT.

      .. _enumitem_NftChain_SourceNatPriority:
  * - ``NftChain.SourceNatPriority``
    - ``100``
    - Place of security table where secmark can be set for example.

      .. _enumitem_NftChain_SeLinuxLastPriority:
  * - ``NftChain.SeLinuxLastPriority``
    - ``225``
    - Priority for SELinux at packet exit.

      .. _enumitem_NftChain_ConnTrackHelperPriority:
  * - ``NftChain.ConnTrackHelperPriority``
    - ``300``
    - Priority for connection tracking at exit.

      .. _enumitem_NftChain_ConnTrackConfirmPriority:
  * - ``NftChain.ConnTrackConfirmPriority``
    - ``2147483646``
    - Priority for connection tracking confirmation operations.

      .. _enumitem_NftChain_LastPriority:
  * - ``NftChain.LastPriority``
    - ``2147483647``
    - Lowest priority to process the chain after all other chains with higher priorities.


.. _enum_NftChain_Type:

.. index::
   single: Type

Type
++++

This enumeration describes supported chain types to implement different kinds of operations.

.. index::
   single: NftChain.Filter
.. index::
   single: NftChain.Rule
.. index::
   single: NftChain.Nat
.. list-table::
  :widths: auto
  :header-rows: 1

  * - Name
    - Value
    - Description

      .. _enumitem_NftChain_Filter:
  * - ``NftChain.Filter``
    - ``0``
    - Implement a packet filter chain. This is supported by the :ref:`NftTable.ARP <enumitem_NftTable_ARP>`, :ref:`NftTable.Bridge <enumitem_NftTable_Bridge>`, :ref:`NftTable.IP <enumitem_NftTable_IP>`, :ref:`NftTable.IP6 <enumitem_NftTable_IP6>` and :ref:`NftTable.INet <enumitem_NftTable_INet>` table families.

      .. _enumitem_NftChain_Rule:
  * - ``NftChain.Rule``
    - ``1``
    - 

      .. _enumitem_NftChain_Nat:
  * - ``NftChain.Nat``
    - ``2``
    - Perform Networking Address Translation (NAT). The first packet that belongs to a flow always hits this chain, follow up packets not. Therefore, never use this chain for filtering. This is supported by the :ref:`NftTable.IP <enumitem_NftTable_IP>` and :ref:`NftTable.IP6 <enumitem_NftTable_IP6>` table families.

Example
*******
See :ref:`NftFirewall example <example_NftFirewall>` on how to use NftChain.
