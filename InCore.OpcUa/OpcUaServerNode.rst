
.. _object_OpcUaServerNode:


:index:`OpcUaServerNode`
------------------------

Description
***********



This object was introduced in InCore 2.3.

:**› Inherits**: :ref:`Object <object_Object>`
:**› Inherited by**: :ref:`OpcUaServerMethodNode <object_OpcUaServerMethodNode>`, :ref:`OpcUaServerObjectNode <object_OpcUaServerObjectNode>`, :ref:`OpcUaServerValueNode <object_OpcUaServerValueNode>`

Overview
********

Properties
++++++++++

.. hlist::
  :columns: 2

  * :ref:`browseName <property_OpcUaServerNode_browseName>`
  * :ref:`description <property_OpcUaServerNode_description>`
  * :ref:`displayName <property_OpcUaServerNode_displayName>`
  * :ref:`fullNodePath <property_OpcUaServerNode_fullNodePath>`
  * :ref:`identifier <property_OpcUaServerNode_identifier>`
  * :ref:`typeDefinition <property_OpcUaServerNode_typeDefinition>`
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

  * :ref:`Object.completed() <signal_Object_completed>`



Properties
**********


.. _property_OpcUaServerNode_browseName:

.. _signal_OpcUaServerNode_browseNameChanged:

.. index::
   single: browseName

browseName
++++++++++



:**› Type**: String
:**› Signal**: browseNameChanged()
:**› Attributes**: Writable


.. _property_OpcUaServerNode_description:

.. index::
   single: description

description
+++++++++++



:**› Type**: :ref:`OpcUaLocalizedText <object_OpcUaLocalizedText>`
:**› Attributes**: Readonly


.. _property_OpcUaServerNode_displayName:

.. index::
   single: displayName

displayName
+++++++++++



:**› Type**: :ref:`OpcUaLocalizedText <object_OpcUaLocalizedText>`
:**› Attributes**: Readonly


.. _property_OpcUaServerNode_fullNodePath:

.. _signal_OpcUaServerNode_fullNodePathChanged:

.. index::
   single: fullNodePath

fullNodePath
++++++++++++



:**› Type**: String
:**› Signal**: fullNodePathChanged()
:**› Attributes**: Readonly


.. _property_OpcUaServerNode_identifier:

.. _signal_OpcUaServerNode_identifierChanged:

.. index::
   single: identifier

identifier
++++++++++



:**› Type**: String
:**› Signal**: identifierChanged()
:**› Attributes**: Writable


.. _property_OpcUaServerNode_typeDefinition:

.. index::
   single: typeDefinition

typeDefinition
++++++++++++++

This property holds a node ID specifying the type definition which to use for this object. Consider setting the :ref:`OpcUaServerNodeId.ns0Id <property_OpcUaServerNodeId_ns0Id>` property when using predefined types from the OPC UA namespace 0.

This property was introduced in InCore 2.4.

:**› Type**: :ref:`OpcUaServerNodeId <object_OpcUaServerNodeId>`
:**› Attributes**: Readonly
