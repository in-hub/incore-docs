
.. _object_OpcUaServerValueNode:


:index:`OpcUaServerValueNode`
-----------------------------

Description
***********



:**› Inherits**: :ref:`OpcUaServerNode <object_OpcUaServerNode>`

Overview
********

Properties
++++++++++

.. hlist::
  :columns: 2

  * :ref:`readOnly <property_OpcUaServerValueNode_readOnly>`
  * :ref:`value <property_OpcUaServerValueNode_value>`
  * :ref:`valueType <property_OpcUaServerValueNode_valueType>`
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

  * :ref:`Object.completed() <signal_Object_completed>`



Properties
**********


.. _property_OpcUaServerValueNode_readOnly:

.. _signal_OpcUaServerValueNode_readOnlyChanged:

.. index::
   single: readOnly

readOnly
++++++++

This property holds whether the :ref:`value <property_OpcUaServerValueNode_value>` can be read only by clients. Keep at ``false`` to allow clients writing the node's value.

:**› Type**: Boolean
:**› Default**: ``false``
:**› Signal**: readOnlyChanged()
:**› Attributes**: Writable


.. _property_OpcUaServerValueNode_value:

.. _signal_OpcUaServerValueNode_valueChanged:

.. index::
   single: value

value
+++++



:**› Type**: Variant
:**› Signal**: valueChanged()
:**› Attributes**: Writable


.. _property_OpcUaServerValueNode_valueType:

.. _signal_OpcUaServerValueNode_valueTypeChanged:

.. index::
   single: valueType

valueType
+++++++++



:**› Type**: :ref:`OpcUaType.Type <enum_OpcUaType_Type>`
:**› Signal**: valueTypeChanged()
:**› Attributes**: Writable

Example
*******
See :ref:`OpcUaServer example <example_OpcUaServer>` on how to use OpcUaServerValueNode.
