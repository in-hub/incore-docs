
.. _object_OpcUaServerValueNode:


:index:`OpcUaServerValueNode`
-----------------------------

Description
***********



This object was introduced in InCore 2.3.

:**› Inherits**: :ref:`OpcUaServerNode <object_OpcUaServerNode>`

Overview
********

Properties
++++++++++

.. hlist::
  :columns: 2

  * :ref:`readOnly <property_OpcUaServerValueNode_readOnly>`
  * :ref:`unit <property_OpcUaServerValueNode_unit>`
  * :ref:`value <property_OpcUaServerValueNode_value>`
  * :ref:`valueType <property_OpcUaServerValueNode_valueType>`
  * :ref:`OpcUaServerNode.browseName <property_OpcUaServerNode_browseName>`
  * :ref:`OpcUaServerNode.description <property_OpcUaServerNode_description>`
  * :ref:`OpcUaServerNode.displayName <property_OpcUaServerNode_displayName>`
  * :ref:`OpcUaServerNode.enabled <property_OpcUaServerNode_enabled>`
  * :ref:`OpcUaServerNode.fullNodePath <property_OpcUaServerNode_fullNodePath>`
  * :ref:`OpcUaServerNode.identifier <property_OpcUaServerNode_identifier>`
  * :ref:`OpcUaServerNode.typeDefinition <property_OpcUaServerNode_typeDefinition>`
  * :ref:`Object.objectId <property_Object_objectId>`
  * :ref:`Object.parent <property_Object_parent>`

Methods
+++++++

.. hlist::
  :columns: 1

  * :ref:`OpcUaServerNode.removeFromServer() <method_OpcUaServerNode_removeFromServer>`
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


.. _property_OpcUaServerValueNode_unit:

.. _signal_OpcUaServerValueNode_unitChanged:

.. index::
   single: unit

unit
++++

This property holds one of the units as defined per http://www.opcfoundation.org/UA/units/un/cefact

This property was introduced in InCore 2.4.

:**› Type**: :ref:`Measurement.Unit <enum_Measurement_Unit>`
:**› Default**: :ref:`Measurement.NoUnit <enumitem_Measurement_NoUnit>`
:**› Signal**: unitChanged()
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
