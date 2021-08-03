
.. _object_OpcUaServerNodeId:


:index:`OpcUaServerNodeId`
--------------------------

Description
***********



This object was introduced in InCore 2.4.

:**› Inherits**: :ref:`Object <object_Object>`

Overview
********

Properties
++++++++++

.. hlist::
  :columns: 1

  * :ref:`identifier <property_OpcUaServerNodeId_identifier>`
  * :ref:`ns0Id <property_OpcUaServerNodeId_ns0Id>`
  * :ref:`nsIndex <property_OpcUaServerNodeId_nsIndex>`
  * :ref:`nsUri <property_OpcUaServerNodeId_nsUri>`
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

  * :ref:`Object.completed() <signal_Object_completed>`



Properties
**********


.. _property_OpcUaServerNodeId_identifier:

.. _signal_OpcUaServerNodeId_identifierChanged:

.. index::
   single: identifier

identifier
++++++++++



:**› Type**: String
:**› Signal**: identifierChanged()
:**› Attributes**: Writable


.. _property_OpcUaServerNodeId_ns0Id:

.. _signal_OpcUaServerNodeId_ns0IdChanged:

.. index::
   single: ns0Id

ns0Id
+++++

This property holds a node ID type from the OPC UA namespace 0. This property is ignored, if the :ref:`identifier <property_OpcUaServerNodeId_identifier>` property is set.

:**› Type**: :ref:`OpcUaNS0.Type <enum_OpcUaNS0_Type>`
:**› Default**: :ref:`OpcUaNS0.Unknown <enumitem_OpcUaNS0_Unknown>`
:**› Signal**: ns0IdChanged()
:**› Attributes**: Writable


.. _property_OpcUaServerNodeId_nsIndex:

.. _signal_OpcUaServerNodeId_nsIndexChanged:

.. index::
   single: nsIndex

nsIndex
+++++++



:**› Type**: SignedInteger
:**› Default**: ``0``
:**› Signal**: nsIndexChanged()
:**› Attributes**: Writable


.. _property_OpcUaServerNodeId_nsUri:

.. _signal_OpcUaServerNodeId_nsUriChanged:

.. index::
   single: nsUri

nsUri
+++++



:**› Type**: String
:**› Signal**: nsUriChanged()
:**› Attributes**: Writable

