
.. _object_NftRule:


:index:`NftRule`
----------------

Description
***********



This object was introduced in InCore 2.1.

:**› Inherits**: :ref:`Object <object_Object>`

Overview
********

Properties
++++++++++

.. hlist::
  :columns: 2

  * :ref:`connectionStates <property_NftRule_connectionStates>`
  * :ref:`destinationAddress <property_NftRule_destinationAddress>`
  * :ref:`destinationPorts <property_NftRule_destinationPorts>`
  * :ref:`enabled <property_NftRule_enabled>`
  * :ref:`inputInterface <property_NftRule_inputInterface>`
  * :ref:`nonTerminalStatements <property_NftRule_nonTerminalStatements>`
  * :ref:`outputInterface <property_NftRule_outputInterface>`
  * :ref:`protocol <property_NftRule_protocol>`
  * :ref:`sourceAddress <property_NftRule_sourceAddress>`
  * :ref:`sourcePorts <property_NftRule_sourcePorts>`
  * :ref:`statement <property_NftRule_statement>`
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

  * :ref:`nonTerminalStatementsDataChanged() <signal_NftRule_nonTerminalStatementsDataChanged>`
  * :ref:`Object.completed() <signal_Object_completed>`

Enumerations
++++++++++++

.. hlist::
  :columns: 1

  * :ref:`ConnectionStates <enum_NftRule_ConnectionStates>`
  * :ref:`Protocol <enum_NftRule_Protocol>`
  * :ref:`Statement <enum_NftRule_Statement>`



Properties
**********


.. _property_NftRule_connectionStates:

.. _signal_NftRule_connectionStatesChanged:

.. index::
   single: connectionStates

connectionStates
++++++++++++++++



:**› Type**: :ref:`ConnectionStates <enum_NftRule_ConnectionStates>`
:**› Default**: :ref:`NftRule.AllStates <enumitem_NftRule_AllStates>`
:**› Signal**: connectionStatesChanged()
:**› Attributes**: Writable


.. _property_NftRule_destinationAddress:

.. _signal_NftRule_destinationAddressChanged:

.. index::
   single: destinationAddress

destinationAddress
++++++++++++++++++



:**› Type**: String
:**› Signal**: destinationAddressChanged()
:**› Attributes**: Writable


.. _property_NftRule_destinationPorts:

.. _signal_NftRule_destinationPortsChanged:

.. index::
   single: destinationPorts

destinationPorts
++++++++++++++++

This property holds the destination ports to apply this rule to. See the :ref:`sourcePorts <property_NftRule_sourcePorts>` property for details on syntax and possible values.

:**› Type**: Variant
:**› Signal**: destinationPortsChanged()
:**› Attributes**: Writable


.. _property_NftRule_enabled:

.. _signal_NftRule_enabledChanged:

.. index::
   single: enabled

enabled
+++++++

This property holds whether the rule is enabled, i.e. it should be included in the corresponding :ref:`chain <object_NftChain>`.

:**› Type**: Boolean
:**› Default**: ``true``
:**› Signal**: enabledChanged()
:**› Attributes**: Writable


.. _property_NftRule_inputInterface:

.. _signal_NftRule_inputInterfaceChanged:

.. index::
   single: inputInterface

inputInterface
++++++++++++++



:**› Type**: String
:**› Signal**: inputInterfaceChanged()
:**› Attributes**: Writable


.. _property_NftRule_nonTerminalStatements:

.. _signal_NftRule_nonTerminalStatementsChanged:

.. index::
   single: nonTerminalStatements

nonTerminalStatements
+++++++++++++++++++++



:**› Type**: :ref:`List <object_List>`\<:ref:`NftStatement <object_NftStatement>`>
:**› Signal**: nonTerminalStatementsChanged()
:**› Attributes**: Readonly


.. _property_NftRule_outputInterface:

.. _signal_NftRule_outputInterfaceChanged:

.. index::
   single: outputInterface

outputInterface
+++++++++++++++



:**› Type**: String
:**› Signal**: outputInterfaceChanged()
:**› Attributes**: Writable


.. _property_NftRule_protocol:

.. _signal_NftRule_protocolChanged:

.. index::
   single: protocol

protocol
++++++++



:**› Type**: :ref:`Protocol <enum_NftRule_Protocol>`
:**› Default**: :ref:`NftRule.AllProtocols <enumitem_NftRule_AllProtocols>`
:**› Signal**: protocolChanged()
:**› Attributes**: Writable


.. _property_NftRule_sourceAddress:

.. _signal_NftRule_sourceAddressChanged:

.. index::
   single: sourceAddress

sourceAddress
+++++++++++++



:**› Type**: String
:**› Signal**: sourceAddressChanged()
:**› Attributes**: Writable


.. _property_NftRule_sourcePorts:

.. _signal_NftRule_sourcePortsChanged:

.. index::
   single: sourcePorts

sourcePorts
+++++++++++

This property holds the source ports to apply this rule to. Syntax and possible values:

* ``80`` – only port 80
* ``"!= 33-45"`` – all ports but 33-45
* ``[ 80, 443 ]`` - ports 80 and 443


:**› Type**: Variant
:**› Signal**: sourcePortsChanged()
:**› Attributes**: Writable


.. _property_NftRule_statement:

.. _signal_NftRule_statementChanged:

.. index::
   single: statement

statement
+++++++++



:**› Type**: :ref:`NftStatement <object_NftStatement>`
:**› Signal**: statementChanged()
:**› Attributes**: Readonly

Signals
*******


.. _signal_NftRule_nonTerminalStatementsDataChanged:

.. index::
   single: nonTerminalStatementsDataChanged

nonTerminalStatementsDataChanged(SignedInteger index)
+++++++++++++++++++++++++++++++++++++++++++++++++++++

This signal is emitted whenever the :ref:`List.dataChanged() <signal_List_dataChanged>` signal is emitted, i.e. the item at ``index`` in the :ref:`nonTerminalStatements <property_NftRule_nonTerminalStatements>` list itself emitted the dataChanged() signal.


Enumerations
************


.. _enum_NftRule_ConnectionStates:

.. index::
   single: ConnectionStates

ConnectionStates
++++++++++++++++



.. index::
   single: NftRule.New
.. index::
   single: NftRule.Established
.. index::
   single: NftRule.Related
.. index::
   single: NftRule.Untracked
.. index::
   single: NftRule.AllStates
.. list-table::
  :widths: auto
  :header-rows: 1

  * - Name
    - Value
    - Description

      .. _enumitem_NftRule_New:
  * - ``NftRule.New``
    - ``1``
    - 

      .. _enumitem_NftRule_Established:
  * - ``NftRule.Established``
    - ``2``
    - 

      .. _enumitem_NftRule_Related:
  * - ``NftRule.Related``
    - ``4``
    - 

      .. _enumitem_NftRule_Untracked:
  * - ``NftRule.Untracked``
    - ``8``
    - 

      .. _enumitem_NftRule_AllStates:
  * - ``NftRule.AllStates``
    - ``15``
    - 


.. _enum_NftRule_Protocol:

.. index::
   single: Protocol

Protocol
++++++++



.. index::
   single: NftRule.Tcp
.. index::
   single: NftRule.Udp
.. index::
   single: NftRule.UdpLite
.. index::
   single: NftRule.Icmp
.. index::
   single: NftRule.Icmpv6
.. index::
   single: NftRule.Esp
.. index::
   single: NftRule.Ah
.. index::
   single: NftRule.Sctp
.. index::
   single: NftRule.Dccp
.. index::
   single: NftRule.AllProtocols
.. list-table::
  :widths: auto
  :header-rows: 1

  * - Name
    - Value
    - Description

      .. _enumitem_NftRule_Tcp:
  * - ``NftRule.Tcp``
    - ``0``
    - 

      .. _enumitem_NftRule_Udp:
  * - ``NftRule.Udp``
    - ``1``
    - 

      .. _enumitem_NftRule_UdpLite:
  * - ``NftRule.UdpLite``
    - ``2``
    - 

      .. _enumitem_NftRule_Icmp:
  * - ``NftRule.Icmp``
    - ``3``
    - 

      .. _enumitem_NftRule_Icmpv6:
  * - ``NftRule.Icmpv6``
    - ``4``
    - 

      .. _enumitem_NftRule_Esp:
  * - ``NftRule.Esp``
    - ``5``
    - 

      .. _enumitem_NftRule_Ah:
  * - ``NftRule.Ah``
    - ``6``
    - 

      .. _enumitem_NftRule_Sctp:
  * - ``NftRule.Sctp``
    - ``7``
    - 

      .. _enumitem_NftRule_Dccp:
  * - ``NftRule.Dccp``
    - ``8``
    - 

      .. _enumitem_NftRule_AllProtocols:
  * - ``NftRule.AllProtocols``
    - ``9``
    - 


.. _enum_NftRule_Statement:

.. index::
   single: Statement

Statement
+++++++++



.. index::
   single: NftRule.Accept
.. index::
   single: NftRule.Drop
.. index::
   single: NftRule.Queue
.. index::
   single: NftRule.Continue
.. index::
   single: NftRule.Return
.. index::
   single: NftRule.Jump
.. index::
   single: NftRule.GoTo
.. index::
   single: NftRule.Log
.. index::
   single: NftRule.Reject
.. index::
   single: NftRule.Counter
.. index::
   single: NftRule.Limit
.. index::
   single: NftRule.Nat
.. list-table::
  :widths: auto
  :header-rows: 1

  * - Name
    - Value
    - Description

      .. _enumitem_NftRule_Accept:
  * - ``NftRule.Accept``
    - ``0``
    - 

      .. _enumitem_NftRule_Drop:
  * - ``NftRule.Drop``
    - ``1``
    - 

      .. _enumitem_NftRule_Queue:
  * - ``NftRule.Queue``
    - ``2``
    - 

      .. _enumitem_NftRule_Continue:
  * - ``NftRule.Continue``
    - ``3``
    - 

      .. _enumitem_NftRule_Return:
  * - ``NftRule.Return``
    - ``4``
    - 

      .. _enumitem_NftRule_Jump:
  * - ``NftRule.Jump``
    - ``5``
    - 

      .. _enumitem_NftRule_GoTo:
  * - ``NftRule.GoTo``
    - ``6``
    - 

      .. _enumitem_NftRule_Log:
  * - ``NftRule.Log``
    - ``7``
    - 

      .. _enumitem_NftRule_Reject:
  * - ``NftRule.Reject``
    - ``8``
    - 

      .. _enumitem_NftRule_Counter:
  * - ``NftRule.Counter``
    - ``9``
    - 

      .. _enumitem_NftRule_Limit:
  * - ``NftRule.Limit``
    - ``10``
    - 

      .. _enumitem_NftRule_Nat:
  * - ``NftRule.Nat``
    - ``11``
    - 

Example
*******
See :ref:`NftFirewall example <example_NftFirewall>` on how to use NftRule.
