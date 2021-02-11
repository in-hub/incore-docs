
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

  * :ref:`Object.fromJson() <method_Object_fromJson>`
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

This property holds a list of OPC UA related objects, such as :ref:`OpcUaConnection <object_OpcUaConnection>`.

:**› Type**: :ref:`List <object_List>`\<:ref:`QObject <enum_OpcUaClient_QObject>`>
:**› Signal**: objectsChanged()
:**› Attributes**: Readonly

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

    import InCore.Foundation 2.3
    import InCore.OpcUa 2.3
    
    Application {
        OpcUaClient {
            OpcUaEndpointDiscovery { }
    
            OpcUaConnection { }
    
            OpcUaNodeId {
                identifier: "s=Machine"
                ns: "Demo Namespace"
                id: machineNodeId
            }
    
    
            OpcUaMethodNode {
                nodeId: OpcUaNodeId {
                    identifier: "s=Machine.Stop"
                    ns: "Demo Namespace"
                }
    
                objectNodeId: machineNodeId
                id: stopMethod
            }
        }
    }
    