
.. _object_OpcUaClient:


:index:`OpcUaClient`
--------------------

Description
***********

The OpcUaClient object is a container object for all OPC UA related objects. It is required to directly instantiate objects from the `Qt OPC UA QML module <https://doc.qt.io/QtOPCUA/qtopcua-qmlmodule.html}>`_. Alternatively these objects can be used as properties within any InCore object.

:**› Inherits**: :ref:`Object <object_Object>`

Overview
********

Properties
++++++++++

.. hlist::
  :columns: 1

  * :ref:`objects <property_OpcUaClient_objects>`
  * :ref:`Object.objectId <property_Object_objectId>`
  * :ref:`Object.parent <property_Object_parent>`

Methods
+++++++

.. hlist::
  :columns: 1

  * :ref:`fullNodePath() <method_OpcUaClient_fullNodePath>`
  * :ref:`Object.deserializeProperties() <method_Object_deserializeProperties>`
  * :ref:`Object.fromJson() <method_Object_fromJson>`
  * :ref:`Object.serializeProperties() <method_Object_serializeProperties>`
  * :ref:`Object.toJson() <method_Object_toJson>`

Signals
+++++++

.. hlist::
  :columns: 1

  * :ref:`objectsDataChanged() <signal_OpcUaClient_objectsDataChanged>`
  * :ref:`Object.completed() <signal_Object_completed>`



Properties
**********


.. _property_OpcUaClient_objects:

.. _signal_OpcUaClient_objectsChanged:

.. index::
   single: objects

objects
+++++++

This property holds a list of OPC UA related objects, such as :ref:`OpcUaClientConnection <object_OpcUaClientConnection>`.

:**› Type**: :ref:`List <object_List>`\<Object>
:**› Signal**: objectsChanged()
:**› Attributes**: Readonly

Methods
*******


.. _method_OpcUaClient_fullNodePath:

.. index::
   single: fullNodePath

fullNodePath(:ref:`OpcUaNodeIdType <enum_OpcUaClient_OpcUaNodeIdType>` nodeId)
++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

This method returns the full node path, i.e. namespace + identifier of the given node ID.

This method was introduced in InCore 2.6.

:**› Returns**: String


Signals
*******


.. _signal_OpcUaClient_objectsDataChanged:

.. index::
   single: objectsDataChanged

objectsDataChanged(SignedInteger index)
+++++++++++++++++++++++++++++++++++++++

This signal is emitted whenever the :ref:`List.dataChanged() <signal_List_dataChanged>` signal is emitted, i.e. the item at ``index`` in the :ref:`objects <property_OpcUaClient_objects>` list itself emitted the dataChanged() signal.



.. _example_OpcUaClient:


Example
*******

.. code-block:: qml

    import InCore.Foundation 2.5
    import InCore.OpcUa 2.5
    
    Application {
        OpcUaClient {
            OpcUaClientConnection {
                // ...
            }
    
            OpcUaClientNodeId {
                identifier: "s=Machine"
                ns: "Example Namespace"
                id: machineNodeId
            }
    
            OpcUaClientValueNode {
                nodeId: OpcUaClientRelativeNodeId {
                    startNode: machineNodeId
                    path: [ OpcUaClientRelativeNodePath { ns: "Example Namespace"; browseName: "Example Value" } ]
                }
                onValueChanged: console.log("Example value", value)
            }
        }
    }
    