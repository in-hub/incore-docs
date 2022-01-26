
.. _object_OpcUaNodeAttribute:


:index:`OpcUaNodeAttribute`
---------------------------

Description
***********

The OpcUaNodeAttribute object contains the 22 node attributes defined in OPC-UA part 4, 5. See the `Qt OPC UA NodeAttributes enumeration <https://doc.qt.io/QtOPCUA/qopcua.html#NodeAttribute-enum>`_ for details.

This object was introduced in InCore 2.4.

:**› Inherits**: :ref:`Object <object_Object>`

Overview
********

Properties
++++++++++

.. hlist::
  :columns: 1

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

Enumerations
++++++++++++

.. hlist::
  :columns: 1

  * :ref:`NodeAttribute <enum_OpcUaNodeAttribute_NodeAttribute>`



Properties
**********

Enumerations
************


.. _enum_OpcUaNodeAttribute_NodeAttribute:

.. index::
   single: NodeAttribute

NodeAttribute
+++++++++++++



.. index::
   single: OpcUaNodeAttribute.None
.. index::
   single: OpcUaNodeAttribute.NodeId
.. index::
   single: OpcUaNodeAttribute.NodeClass
.. index::
   single: OpcUaNodeAttribute.BrowseName
.. index::
   single: OpcUaNodeAttribute.DisplayName
.. index::
   single: OpcUaNodeAttribute.Description
.. index::
   single: OpcUaNodeAttribute.WriteMask
.. index::
   single: OpcUaNodeAttribute.UserWriteMask
.. index::
   single: OpcUaNodeAttribute.IsAbstract
.. index::
   single: OpcUaNodeAttribute.Symmetric
.. index::
   single: OpcUaNodeAttribute.InverseName
.. index::
   single: OpcUaNodeAttribute.ContainsNoLoops
.. index::
   single: OpcUaNodeAttribute.EventNotifier
.. index::
   single: OpcUaNodeAttribute.Value
.. index::
   single: OpcUaNodeAttribute.DataType
.. index::
   single: OpcUaNodeAttribute.ValueRank
.. index::
   single: OpcUaNodeAttribute.ArrayDimensions
.. index::
   single: OpcUaNodeAttribute.AccessLevel
.. index::
   single: OpcUaNodeAttribute.UserAccessLevel
.. index::
   single: OpcUaNodeAttribute.MinimumSamplingInterval
.. index::
   single: OpcUaNodeAttribute.Historizing
.. index::
   single: OpcUaNodeAttribute.Executable
.. index::
   single: OpcUaNodeAttribute.UserExecutable
.. list-table::
  :widths: auto
  :header-rows: 1

  * - Name
    - Value
    - Description

      .. _enumitem_OpcUaNodeAttribute_None:
  * - ``OpcUaNodeAttribute.None``
    - ``0``
    - 

      .. _enumitem_OpcUaNodeAttribute_NodeId:
  * - ``OpcUaNodeAttribute.NodeId``
    - ``1``
    - 

      .. _enumitem_OpcUaNodeAttribute_NodeClass:
  * - ``OpcUaNodeAttribute.NodeClass``
    - ``2``
    - 

      .. _enumitem_OpcUaNodeAttribute_BrowseName:
  * - ``OpcUaNodeAttribute.BrowseName``
    - ``4``
    - 

      .. _enumitem_OpcUaNodeAttribute_DisplayName:
  * - ``OpcUaNodeAttribute.DisplayName``
    - ``8``
    - 

      .. _enumitem_OpcUaNodeAttribute_Description:
  * - ``OpcUaNodeAttribute.Description``
    - ``16``
    - 

      .. _enumitem_OpcUaNodeAttribute_WriteMask:
  * - ``OpcUaNodeAttribute.WriteMask``
    - ``32``
    - 

      .. _enumitem_OpcUaNodeAttribute_UserWriteMask:
  * - ``OpcUaNodeAttribute.UserWriteMask``
    - ``64``
    - 

      .. _enumitem_OpcUaNodeAttribute_IsAbstract:
  * - ``OpcUaNodeAttribute.IsAbstract``
    - ``128``
    - 

      .. _enumitem_OpcUaNodeAttribute_Symmetric:
  * - ``OpcUaNodeAttribute.Symmetric``
    - ``256``
    - 

      .. _enumitem_OpcUaNodeAttribute_InverseName:
  * - ``OpcUaNodeAttribute.InverseName``
    - ``512``
    - 

      .. _enumitem_OpcUaNodeAttribute_ContainsNoLoops:
  * - ``OpcUaNodeAttribute.ContainsNoLoops``
    - ``1024``
    - 

      .. _enumitem_OpcUaNodeAttribute_EventNotifier:
  * - ``OpcUaNodeAttribute.EventNotifier``
    - ``2048``
    - 

      .. _enumitem_OpcUaNodeAttribute_Value:
  * - ``OpcUaNodeAttribute.Value``
    - ``4096``
    - 

      .. _enumitem_OpcUaNodeAttribute_DataType:
  * - ``OpcUaNodeAttribute.DataType``
    - ``8192``
    - 

      .. _enumitem_OpcUaNodeAttribute_ValueRank:
  * - ``OpcUaNodeAttribute.ValueRank``
    - ``16384``
    - 

      .. _enumitem_OpcUaNodeAttribute_ArrayDimensions:
  * - ``OpcUaNodeAttribute.ArrayDimensions``
    - ``32768``
    - 

      .. _enumitem_OpcUaNodeAttribute_AccessLevel:
  * - ``OpcUaNodeAttribute.AccessLevel``
    - ``65536``
    - 

      .. _enumitem_OpcUaNodeAttribute_UserAccessLevel:
  * - ``OpcUaNodeAttribute.UserAccessLevel``
    - ``131072``
    - 

      .. _enumitem_OpcUaNodeAttribute_MinimumSamplingInterval:
  * - ``OpcUaNodeAttribute.MinimumSamplingInterval``
    - ``262144``
    - 

      .. _enumitem_OpcUaNodeAttribute_Historizing:
  * - ``OpcUaNodeAttribute.Historizing``
    - ``524288``
    - 

      .. _enumitem_OpcUaNodeAttribute_Executable:
  * - ``OpcUaNodeAttribute.Executable``
    - ``1048576``
    - 

      .. _enumitem_OpcUaNodeAttribute_UserExecutable:
  * - ``OpcUaNodeAttribute.UserExecutable``
    - ``2097152``
    - 

