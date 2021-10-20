
.. _object_OpcUaServer:


:index:`OpcUaServer`
--------------------

Description
***********

The OpcUaServer object provides an OPC UA server to which :ref:`OpcUaServerNamespace <object_OpcUaServerNamespace>` objects with corresponding child nodes can be added.

This object was introduced in InCore 2.3.

:**› Inherits**: :ref:`Object <object_Object>`

Overview
********

Properties
++++++++++

.. hlist::
  :columns: 2

  * :ref:`enabled <property_OpcUaServer_enabled>`
  * :ref:`namespaces <property_OpcUaServer_namespaces>`
  * :ref:`nodeSets <property_OpcUaServer_nodeSets>`
  * :ref:`port <property_OpcUaServer_port>`
  * :ref:`security <property_OpcUaServer_security>`
  * :ref:`users <property_OpcUaServer_users>`
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

  * :ref:`namespacesDataChanged() <signal_OpcUaServer_namespacesDataChanged>`
  * :ref:`usersDataChanged() <signal_OpcUaServer_usersDataChanged>`
  * :ref:`Object.completed() <signal_Object_completed>`



Properties
**********


.. _property_OpcUaServer_enabled:

.. _signal_OpcUaServer_enabledChanged:

.. index::
   single: enabled

enabled
+++++++

This property holds whether the OPC UA server should listen for incoming connections.

:**› Type**: Boolean
:**› Default**: ``true``
:**› Signal**: enabledChanged()
:**› Attributes**: Writable


.. _property_OpcUaServer_namespaces:

.. _signal_OpcUaServer_namespacesChanged:

.. index::
   single: namespaces

namespaces
++++++++++



:**› Type**: :ref:`List <object_List>`\<:ref:`OpcUaServerNamespace <object_OpcUaServerNamespace>`>
:**› Signal**: namespacesChanged()
:**› Attributes**: Readonly


.. _property_OpcUaServer_nodeSets:

.. _signal_OpcUaServer_nodeSetsChanged:

.. index::
   single: nodeSets

nodeSets
++++++++

This property holds a list of OPC UA NodeSet files which to load at start.

This property was introduced in InCore 2.4.

:**› Type**: StringList
:**› Signal**: nodeSetsChanged()
:**› Attributes**: Writable


.. _property_OpcUaServer_port:

.. _signal_OpcUaServer_portChanged:

.. index::
   single: port

port
++++

This property holds the network port number which to listen at for incoming connections.

:**› Type**: SignedInteger
:**› Default**: ``4840``
:**› Signal**: portChanged()
:**› Attributes**: Writable


.. _property_OpcUaServer_security:

.. index::
   single: security

security
++++++++

This property holds the security settings for the server.

:**› Type**: :ref:`OpcUaServerSecurity <object_OpcUaServerSecurity>`
:**› Attributes**: Readonly


.. _property_OpcUaServer_users:

.. _signal_OpcUaServer_usersChanged:

.. index::
   single: users

users
+++++



:**› Type**: :ref:`List <object_List>`\<:ref:`OpcUaServerUser <object_OpcUaServerUser>`>
:**› Signal**: usersChanged()
:**› Attributes**: Readonly

Signals
*******


.. _signal_OpcUaServer_namespacesDataChanged:

.. index::
   single: namespacesDataChanged

namespacesDataChanged(SignedInteger index)
++++++++++++++++++++++++++++++++++++++++++

This signal is emitted whenever the :ref:`List.dataChanged() <signal_List_dataChanged>` signal is emitted, i.e. the item at ``index`` in the :ref:`namespaces <property_OpcUaServer_namespaces>` list itself emitted the dataChanged() signal.



.. _signal_OpcUaServer_usersDataChanged:

.. index::
   single: usersDataChanged

usersDataChanged(SignedInteger index)
+++++++++++++++++++++++++++++++++++++

This signal is emitted whenever the :ref:`List.dataChanged() <signal_List_dataChanged>` signal is emitted, i.e. the item at ``index`` in the :ref:`users <property_OpcUaServer_users>` list itself emitted the dataChanged() signal.



.. _example_OpcUaServer:


Example
*******

.. code-block:: qml

    import InCore.Foundation 2.5
    import InCore.OpcUa 2.5
    
    Application {
        OpcUaServer {
            security {
                policies: OpcUaServerSecurity.PolicyNone |
                          OpcUaServerSecurity.PolicyBasic256Sha256 |
                          OpcUaServerSecurity.PolicyAes128Sha256RsaOaep
                privateKeyFile: "certs/server_key.der"
                certificateFile: "certs/server_cert.der"
            }
    
            users: [ OpcUaServerUser { name: "user"; password: "secret" } ]
    
            OpcUaServerNamespace {
                uri: "http://inhub.de/opcuaserverexample"
                OpcUaServerObjectNode {
                    identifier: "s=Machine"
                    browseName: "Machine"
                    displayName.text: "My Machine"
                    description.text: "This is my awesome machine"
    
                    OpcUaServerValueNode {
                        identifier: "s=Machine.ExampleValue"
                        browseName: "ExampleValue"
                        displayName.text: "Example Value"
                        description.text: "This is an example value"
                        valueType: OpcUaType.Double
                        value: 123
                        property var t : Timer { onTriggered: parent.value = Math.random() }
                        readOnly: true
                    }
    
                    OpcUaServerMethodNode {
                        identifier: "s=Machine.RunMe"
                        browseName: "ExampleMethod"
                        displayName.text: "Example method"
                        method: (foo, bar) => {
                                    console.log("hello world:", foo, bar)
                                    return [ foo > 0, "thank you for calling" ]
                                }
                        inputArguments: [
                            OpcUaServerMethodArgument { name: "foo"; type: OpcUaType.Double },
                            OpcUaServerMethodArgument { name: "bar"; type: OpcUaType.String }
                        ]
                        outputArguments: [
                            OpcUaServerMethodArgument { name: "out1"; type: OpcUaType.Boolean; description.text: "Foo is positive" },
                            OpcUaServerMethodArgument { name: "out2"; type: OpcUaType.String }
                        ]
                    }
                }
            }
        }
    }
    