
.. _object_OpcUaServerObjectNode:


:index:`OpcUaServerObjectNode`
------------------------------

Description
***********



This object was introduced in InCore 2.3.

:**› Inherits**: :ref:`OpcUaServerNode <object_OpcUaServerNode>`
:**› Inherited by**: :ref:`OpcUaServerFolderNode <object_OpcUaServerFolderNode>`

Overview
********

Properties
++++++++++

.. hlist::
  :columns: 2

  * :ref:`nodes <property_OpcUaServerObjectNode_nodes>`
  * :ref:`OpcUaServerNode.browseName <property_OpcUaServerNode_browseName>`
  * :ref:`OpcUaServerNode.description <property_OpcUaServerNode_description>`
  * :ref:`OpcUaServerNode.displayName <property_OpcUaServerNode_displayName>`
  * :ref:`OpcUaServerNode.fullNodePath <property_OpcUaServerNode_fullNodePath>`
  * :ref:`OpcUaServerNode.identifier <property_OpcUaServerNode_identifier>`
  * :ref:`OpcUaServerNode.typeDefinition <property_OpcUaServerNode_typeDefinition>`
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

  * :ref:`nodesDataChanged() <signal_OpcUaServerObjectNode_nodesDataChanged>`
  * :ref:`Object.completed() <signal_Object_completed>`



Properties
**********


.. _property_OpcUaServerObjectNode_nodes:

.. _signal_OpcUaServerObjectNode_nodesChanged:

.. index::
   single: nodes

nodes
+++++



:**› Type**: :ref:`List <object_List>`\<:ref:`OpcUaServerNode <object_OpcUaServerNode>`>
:**› Signal**: nodesChanged()
:**› Attributes**: Readonly

Signals
*******


.. _signal_OpcUaServerObjectNode_nodesDataChanged:

.. index::
   single: nodesDataChanged

nodesDataChanged(SignedInteger index)
+++++++++++++++++++++++++++++++++++++

This signal is emitted whenever the :ref:`List.dataChanged() <signal_List_dataChanged>` signal is emitted, i.e. the item at ``index`` in the :ref:`nodes <property_OpcUaServerObjectNode_nodes>` list itself emitted the dataChanged() signal.


Example
*******
See :ref:`OpcUaServer example <example_OpcUaServer>` on how to use OpcUaServerObjectNode.
