
.. _object_OpcUaClientNodeDiscovery:


:index:`OpcUaClientNodeDiscovery`
---------------------------------

Description
***********

The OpcUaClientNodeDiscovery object can be used to discover children :ref:`nodes <property_OpcUaClientNodeDiscovery_nodes>` of a certain :ref:`browseNodeId <property_OpcUaClientNodeDiscovery_browseNodeId>`{OPC/UA node} on a OPC/UA server. The :ref:`nodes <property_OpcUaClientNodeDiscovery_nodes>` property is populated automatically but can be refreshed at any time by calling the :ref:`update() <method_OpcUaClientNodeDiscovery_update>` method.

This object was introduced in InCore 2.6.

:**› Inherits**: :ref:`Object <object_Object>`

Overview
********

Properties
++++++++++

.. hlist::
  :columns: 1

  * :ref:`browseNodeId <property_OpcUaClientNodeDiscovery_browseNodeId>`
  * :ref:`nodes <property_OpcUaClientNodeDiscovery_nodes>`
  * :ref:`Object.objectId <property_Object_objectId>`
  * :ref:`Object.parent <property_Object_parent>`

Methods
+++++++

.. hlist::
  :columns: 1

  * :ref:`update() <method_OpcUaClientNodeDiscovery_update>`
  * :ref:`Object.deserializeProperties() <method_Object_deserializeProperties>`
  * :ref:`Object.fromJson() <method_Object_fromJson>`
  * :ref:`Object.serializeProperties() <method_Object_serializeProperties>`
  * :ref:`Object.toJson() <method_Object_toJson>`

Signals
+++++++

.. hlist::
  :columns: 1

  * :ref:`nodesDataChanged() <signal_OpcUaClientNodeDiscovery_nodesDataChanged>`
  * :ref:`Object.completed() <signal_Object_completed>`



Properties
**********


.. _property_OpcUaClientNodeDiscovery_browseNodeId:

.. _signal_OpcUaClientNodeDiscovery_browseNodeIdChanged:

.. index::
   single: browseNodeId

browseNodeId
++++++++++++

This property holds the node ID of the OPC/UA node whose children to discover.

:**› Type**: `OpcUaNodeId <https://doc.qt.io/QtOPCUA/qml-qtopcua-nodeid.html>`_
:**› Signal**: browseNodeIdChanged()
:**› Attributes**: Writable


.. _property_OpcUaClientNodeDiscovery_nodes:

.. _signal_OpcUaClientNodeDiscovery_nodesChanged:

.. index::
   single: nodes

nodes
+++++

This property holds the discovered OPC/UA nodes. Depending on the respective node class, each instance is either of type :ref:`OpcUaClientValueNode <object_OpcUaClientValueNode>` for value nodes, :ref:`OpcUaClientMethodNode <object_OpcUaClientMethodNode>` for method nodes or :ref:`OpcUaClientNode <object_OpcUaClientNode>` in all other cases.

:**› Type**: :ref:`List <object_List>`\<:ref:`OpcUaNode <enum_OpcUaClientNodeDiscovery_OpcUaNode>`>
:**› Signal**: nodesChanged()
:**› Attributes**: Readonly

Methods
*******


.. _method_OpcUaClientNodeDiscovery_update:

.. index::
   single: update

update()
++++++++

This method can be called to discover and update :ref:`nodes <property_OpcUaClientNodeDiscovery_nodes>` manually.


Signals
*******


.. _signal_OpcUaClientNodeDiscovery_nodesDataChanged:

.. index::
   single: nodesDataChanged

nodesDataChanged(SignedInteger index)
+++++++++++++++++++++++++++++++++++++

This signal is emitted whenever the :ref:`List.dataChanged() <signal_List_dataChanged>` signal is emitted, i.e. the item at ``index`` in the :ref:`nodes <property_OpcUaClientNodeDiscovery_nodes>` list itself emitted the dataChanged() signal.



.. _example_OpcUaClientNodeDiscovery:


Example
*******

.. code-block:: qml

    import InCore.Foundation 2.5
    import InCore.OpcUa 2.5
    
    Application {
        OpcUaClient {
            id: client
            OpcUaClientConnection {
                backend: availableBackends[0]
                defaultConnection: true
            }
    
            OpcUaEndpointDiscovery {
                id: endpointDiscovery
                serverUrl: "opc.tcp://localhost:4840"
                onEndpointsChanged: {
                    if (status.isGood) {
                        if (status.status === OpcUaStatus.GoodCompletesAsynchronusly)
                            return; // wait until finished
                        if (count > 0) {
                            console.log("Using endpoint", at(0).endpointUrl, at(0).securityPolicy);
                            connection.connectToEndpoint(at(0));
                        } else {
                            console.log("No endpoints retrieved")
                        }
                    } else {
                        console.log("Error fetching endpoints:", status.status);
                    }
                }
            }
    
            OpcUaClientNodeDiscovery {
                browseNodeId: OpcUaClientNodeId {
                    ns: "http://inhub.de/opcuaserverexample"
                    identifier: "s=Machine"
                }
                onNodesChanged: {
                    for(let i in nodes)
                    {
                        console.log("Discovered node", client.fullNodePath(nodes[i].nodeId))
                        if (nodes[i] instanceof OpcUaClientValueNode)
                        {
                            console.log("Monitoring value node", client.fullNodePath(nodes[i].nodeId))
                            nodes[i].valueChanged.connect( () => { console.log(nodes[i].browseName, nodes[i].value) })
                        }
                    }
                }
            }
        }
    }
    