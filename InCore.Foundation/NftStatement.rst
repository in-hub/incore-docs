
.. _object_NftStatement:


:index:`NftStatement`
---------------------

Description
***********

The NftStatement object specifies the action performed when a packet matches a :ref:`rule <object_NftRule>`. It can be terminal and non-terminal. In a certain rule several non-terminal statements can be considered but only a single terminal statement.

See the `nftables documentation on statements <https://wiki.nftables.org/wiki-nftables/index.php/Quick_reference-nftables_in_10_minutes#Statements>`_ for further information.

This object was introduced in InCore 2.1.

:**› Inherits**: :ref:`Object <object_Object>`

Overview
********

Properties
++++++++++

.. hlist::
  :columns: 1

  * :ref:`arguments <property_NftStatement_arguments>`
  * :ref:`type <property_NftStatement_type>`
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

  * :ref:`Object.completed() <signal_Object_completed>`

Enumerations
++++++++++++

.. hlist::
  :columns: 1

  * :ref:`Type <enum_NftStatement_Type>`



Properties
**********


.. _property_NftStatement_arguments:

.. _signal_NftStatement_argumentsChanged:

.. index::
   single: arguments

arguments
+++++++++

This property holds the :ref:`type <property_NftStatement_type>`-specific arguments to the statement.

:**› Type**: StringList
:**› Signal**: argumentsChanged()
:**› Attributes**: Writable


.. _property_NftStatement_type:

.. _signal_NftStatement_typeChanged:

.. index::
   single: type

type
++++

This property holds the statement type specifying the action to perform when a packet matches a rule.

:**› Type**: :ref:`Type <enum_NftStatement_Type>`
:**› Default**: :ref:`NftStatement.None <enumitem_NftStatement_None>`
:**› Signal**: typeChanged()
:**› Attributes**: Writable

Enumerations
************


.. _enum_NftStatement_Type:

.. index::
   single: Type

Type
++++

This enumeration describes all supported statement types, i.e. actions.

.. index::
   single: NftStatement.None
.. index::
   single: NftStatement.Accept
.. index::
   single: NftStatement.Drop
.. index::
   single: NftStatement.Queue
.. index::
   single: NftStatement.Continue
.. index::
   single: NftStatement.Return
.. index::
   single: NftStatement.Jump
.. index::
   single: NftStatement.GoTo
.. index::
   single: NftStatement.Log
.. index::
   single: NftStatement.Reject
.. index::
   single: NftStatement.Counter
.. index::
   single: NftStatement.Limit
.. index::
   single: NftStatement.DNat
.. index::
   single: NftStatement.SNat
.. index::
   single: NftStatement.Masquerade
.. list-table::
  :widths: auto
  :header-rows: 1

  * - Name
    - Value
    - Description

      .. _enumitem_NftStatement_None:
  * - ``NftStatement.None``
    - ``0``
    - Do not perform any action, i.e. effectively disable the associated rule.

      .. _enumitem_NftStatement_Accept:
  * - ``NftStatement.Accept``
    - ``1``
    - Accept the packet and stop the remaining rules evaluation.

      .. _enumitem_NftStatement_Drop:
  * - ``NftStatement.Drop``
    - ``2``
    - Drop the packet and stop the remain rules evaluation.

      .. _enumitem_NftStatement_Queue:
  * - ``NftStatement.Queue``
    - ``3``
    - Queue the packet to userspace and stop the remain rules evaluation. See the `nftables queue reference <https://wiki.nftables.org/wiki-nftables/index.php/Quick_reference-nftables_in_10_minutes#Queue>`_ for details on possible :ref:`arguments <property_NftStatement_arguments>`.

      .. _enumitem_NftStatement_Continue:
  * - ``NftStatement.Continue``
    - ``4``
    - Continue the ruleset evaluation with the next rule.

      .. _enumitem_NftStatement_Return:
  * - ``NftStatement.Return``
    - ``5``
    - Return from the current chain and continue at the next rule of the last chain. In a base chain it is equivalent to :ref:`NftStatement.Accept <enumitem_NftStatement_Accept>`.

      .. _enumitem_NftStatement_Jump:
  * - ``NftStatement.Jump``
    - ``6``
    - Continue with the first rule of a chain named as specified in the :ref:`arguments <property_NftStatement_arguments>` property. It will continue at the next rule after a return statement is issued.

      .. _enumitem_NftStatement_GoTo:
  * - ``NftStatement.GoTo``
    - ``7``
    - Similar to :ref:`NftStatement.Jump <enumitem_NftStatement_Jump>` but after the new chain the evaluation will continue at the last chain instead of the one containing the goto statement.

      .. _enumitem_NftStatement_Log:
  * - ``NftStatement.Log``
    - ``8``
    - Write messages to the system log according to further parameters specified in the :ref:`arguments <property_NftStatement_arguments>` property. See the `nftables documentation on logging <https://wiki.nftables.org/wiki-nftables/index.php/Quick_reference-nftables_in_10_minutes#Log>`_ for details.

      .. _enumitem_NftStatement_Reject:
  * - ``NftStatement.Reject``
    - ``9``
    - Reject packet with optional protocol-specific reject reasons specified in the :ref:`arguments <property_NftStatement_arguments>` property. See the `nftables documentation on rejecting traffic <https://wiki.nftables.org/wiki-nftables/index.php/Rejecting_traffic>`_ and the `reject reference <https://wiki.nftables.org/wiki-nftables/index.php/Quick_reference-nftables_in_10_minutes#Reject>`_ for details.

      .. _enumitem_NftStatement_Counter:
  * - ``NftStatement.Counter``
    - ``10``
    - Count packets with optional settings specified in the :ref:`arguments <property_NftStatement_arguments>` property. See the `nftables documentation on Counters <https://wiki.nftables.org/wiki-nftables/index.php/Counters>`_ and the `counter reference <https://wiki.nftables.org/wiki-nftables/index.php/Quick_reference-nftables_in_10_minutes#Counter>`_ for details.

      .. _enumitem_NftStatement_Limit:
  * - ``NftStatement.Limit``
    - ``11``
    - Implement rate limiting with settings specified in the :ref:`arguments <property_NftStatement_arguments>` property. See the `nftables documentation on Rate limit matchings <https://wiki.nftables.org/wiki-nftables/index.php/Rate_limiting_matchings>`_ and the `limit reference <https://wiki.nftables.org/wiki-nftables/index.php/Quick_reference-nftables_in_10_minutes#Limit>`_ for details.

      .. _enumitem_NftStatement_DNat:
  * - ``NftStatement.DNat``
    - ``12``
    - Implement destination address translation with settings specified in the :ref:`arguments <property_NftStatement_arguments>` property. See the `nftables documentation on Source NAT <https://wiki.nftables.org/wiki-nftables/index.php/Performing_Network_Address_Translation_(NAT)#Source_NAT>`_ and the `Nat reference <https://wiki.nftables.org/wiki-nftables/index.php/Quick_reference-nftables_in_10_minutes#Nat>`_ for details.

      .. _enumitem_NftStatement_SNat:
  * - ``NftStatement.SNat``
    - ``13``
    - Implement source address translation with settings specified in the :ref:`arguments <property_NftStatement_arguments>` property. See the `nftables documentation on Destination NAT <https://wiki.nftables.org/wiki-nftables/index.php/Performing_Network_Address_Translation_(NAT)#Destination_NAT>`_ and the `Nat reference <https://wiki.nftables.org/wiki-nftables/index.php/Quick_reference-nftables_in_10_minutes#Nat>`_ for details.

      .. _enumitem_NftStatement_Masquerade:
  * - ``NftStatement.Masquerade``
    - ``14``
    - Implement masquerading with settings specified in the :ref:`arguments <property_NftStatement_arguments>` property. See the `nftables documentation on Masquerading <https://wiki.nftables.org/wiki-nftables/index.php/Performing_Network_Address_Translation_(NAT)#Masquerading>`_ and the `Nat reference <https://wiki.nftables.org/wiki-nftables/index.php/Quick_reference-nftables_in_10_minutes#Nat>`_ for details.

Example
*******
See :ref:`NftFirewall example <example_NftFirewall>` on how to use NftStatement.
