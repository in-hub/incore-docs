
.. _object_OpcUaBrowseNode:


:index:`OpcUaBrowseNode`
------------------------

Description
***********

The OpcUaBrowseNode object contains information about a node discovered via :ref:`OpcUaClientNodeDiscovery <object_OpcUaClientNodeDiscovery>`.

This object was introduced in InCore 2.9.

:**› Inherits**: :ref:`Object <object_Object>`

Overview
********

Properties
++++++++++

.. hlist::
  :columns: 1

  * :ref:`browseName <property_OpcUaBrowseNode_browseName>`
  * :ref:`displayName <property_OpcUaBrowseNode_displayName>`
  * :ref:`nodeClass <property_OpcUaBrowseNode_nodeClass>`
  * :ref:`nodeId <property_OpcUaBrowseNode_nodeId>`
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


.. _property_OpcUaBrowseNode_browseName:

.. _signal_OpcUaBrowseNode_browseNameChanged:

.. index::
   single: browseName

browseName
++++++++++

This property holds the browse name of the discovered OPC UA node.

:**› Type**: String
:**› Signal**: browseNameChanged()
:**› Attributes**: Readonly


.. _property_OpcUaBrowseNode_displayName:

.. _signal_OpcUaBrowseNode_displayNameChanged:

.. index::
   single: displayName

displayName
+++++++++++

This property holds the display name of the discovered OPC UA node.

:**› Type**: String
:**› Signal**: displayNameChanged()
:**› Attributes**: Readonly


.. _property_OpcUaBrowseNode_nodeClass:

.. _signal_OpcUaBrowseNode_nodeClassChanged:

.. index::
   single: nodeClass

nodeClass
+++++++++

This property holds the node class of the discovered OPC UA node.

:**› Type**: :ref:`QOpcUa.NodeClass <enum_QOpcUa_NodeClass>`
:**› Default**: ``\enumitem{QOpcUa::NodeClass::Undefined}``
:**› Signal**: nodeClassChanged()
:**› Attributes**: Readonly


.. _property_OpcUaBrowseNode_nodeId:

.. _signal_OpcUaBrowseNode_nodeIdChanged:

.. index::
   single: nodeId

nodeId
++++++

This property holds the node ID of the discovered OPC UA node.

:**› Type**: `OpcUaNodeId <https://doc.qt.io/qt-5/qml-qtopcua-nodeid.html>`_
:**› Signal**: nodeIdChanged()
:**› Attributes**: Readonly

