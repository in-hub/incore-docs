
.. _object_OpcUaServerMethodNode:


:index:`OpcUaServerMethodNode`
------------------------------

Description
***********



:**› Inherits**: :ref:`OpcUaServerNode <object_OpcUaServerNode>`

Overview
********

Properties
++++++++++

.. hlist::
  :columns: 2

  * :ref:`inputArguments <property_OpcUaServerMethodNode_inputArguments>`
  * :ref:`method <property_OpcUaServerMethodNode_method>`
  * :ref:`outputArguments <property_OpcUaServerMethodNode_outputArguments>`
  * :ref:`OpcUaServerNode.browseName <property_OpcUaServerNode_browseName>`
  * :ref:`OpcUaServerNode.description <property_OpcUaServerNode_description>`
  * :ref:`OpcUaServerNode.displayName <property_OpcUaServerNode_displayName>`
  * :ref:`OpcUaServerNode.fullNodePath <property_OpcUaServerNode_fullNodePath>`
  * :ref:`OpcUaServerNode.identifier <property_OpcUaServerNode_identifier>`
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

  * :ref:`inputArgumentsDataChanged() <signal_OpcUaServerMethodNode_inputArgumentsDataChanged>`
  * :ref:`outputArgumentsDataChanged() <signal_OpcUaServerMethodNode_outputArgumentsDataChanged>`
  * :ref:`Object.completed() <signal_Object_completed>`



Properties
**********


.. _property_OpcUaServerMethodNode_inputArguments:

.. _signal_OpcUaServerMethodNode_inputArgumentsChanged:

.. index::
   single: inputArguments

inputArguments
++++++++++++++



:**› Type**: :ref:`List <object_List>`\<:ref:`OpcUaServerMethodArgument <object_OpcUaServerMethodArgument>`>
:**› Signal**: inputArgumentsChanged()
:**› Attributes**: Readonly


.. _property_OpcUaServerMethodNode_method:

.. _signal_OpcUaServerMethodNode_methodChanged:

.. index::
   single: method

method
++++++



:**› Type**: JSValue
:**› Signal**: methodChanged()
:**› Attributes**: Writable


.. _property_OpcUaServerMethodNode_outputArguments:

.. _signal_OpcUaServerMethodNode_outputArgumentsChanged:

.. index::
   single: outputArguments

outputArguments
+++++++++++++++



:**› Type**: :ref:`List <object_List>`\<:ref:`OpcUaServerMethodArgument <object_OpcUaServerMethodArgument>`>
:**› Signal**: outputArgumentsChanged()
:**› Attributes**: Readonly

Signals
*******


.. _signal_OpcUaServerMethodNode_inputArgumentsDataChanged:

.. index::
   single: inputArgumentsDataChanged

inputArgumentsDataChanged(SignedInteger index)
++++++++++++++++++++++++++++++++++++++++++++++

This signal is emitted whenever the :ref:`List.dataChanged() <signal_List_dataChanged>` signal is emitted, i.e. the item at ``index`` in the :ref:`inputArguments <property_OpcUaServerMethodNode_inputArguments>` list itself emitted the dataChanged() signal.



.. _signal_OpcUaServerMethodNode_outputArgumentsDataChanged:

.. index::
   single: outputArgumentsDataChanged

outputArgumentsDataChanged(SignedInteger index)
+++++++++++++++++++++++++++++++++++++++++++++++

This signal is emitted whenever the :ref:`List.dataChanged() <signal_List_dataChanged>` signal is emitted, i.e. the item at ``index`` in the :ref:`outputArguments <property_OpcUaServerMethodNode_outputArguments>` list itself emitted the dataChanged() signal.


Example
*******
See :ref:`OpcUaServer example <example_OpcUaServer>` on how to use OpcUaServerMethodNode.
