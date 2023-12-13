
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

  * :ref:`applicationName <property_OpcUaServer_applicationName>`
  * :ref:`applicationUri <property_OpcUaServer_applicationUri>`
  * :ref:`enabled <property_OpcUaServer_enabled>`
  * :ref:`manufacturerName <property_OpcUaServer_manufacturerName>`
  * :ref:`namespaces <property_OpcUaServer_namespaces>`
  * :ref:`nodeSets <property_OpcUaServer_nodeSets>`
  * :ref:`port <property_OpcUaServer_port>`
  * :ref:`productName <property_OpcUaServer_productName>`
  * :ref:`productUri <property_OpcUaServer_productUri>`
  * :ref:`security <property_OpcUaServer_security>`
  * :ref:`softwareVersion <property_OpcUaServer_softwareVersion>`
  * :ref:`users <property_OpcUaServer_users>`
  * :ref:`Object.objectId <property_Object_objectId>`
  * :ref:`Object.parent <property_Object_parent>`

Methods
+++++++

.. hlist::
  :columns: 1

  * :ref:`syncAllNodes() <method_OpcUaServer_syncAllNodes>`
  * :ref:`syncNode() <method_OpcUaServer_syncNode>`
  * :ref:`Object.deserializeProperties() <method_Object_deserializeProperties>`
  * :ref:`Object.fromJson() <method_Object_fromJson>`
  * :ref:`Object.serializeProperties() <method_Object_serializeProperties>`
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


.. _property_OpcUaServer_applicationName:

.. _signal_OpcUaServer_applicationNameChanged:

.. index::
   single: applicationName

applicationName
+++++++++++++++

This property holds the name of the application which to report as part of the server status.

This property was introduced in InCore 2.8.

:**› Type**: String
:**› Default**: ``SIINEOS``
:**› Signal**: applicationNameChanged()
:**› Attributes**: Writable


.. _property_OpcUaServer_applicationUri:

.. _signal_OpcUaServer_applicationUriChanged:

.. index::
   single: applicationUri

applicationUri
++++++++++++++

This property holds the URI of the application which to report as part of the server status.

This property was introduced in InCore 2.8.

:**› Type**: String
:**› Default**: ``https://www.inhub.de/siineos``
:**› Signal**: applicationUriChanged()
:**› Attributes**: Writable


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


.. _property_OpcUaServer_manufacturerName:

.. _signal_OpcUaServer_manufacturerNameChanged:

.. index::
   single: manufacturerName

manufacturerName
++++++++++++++++

This property holds the name of the manufacturer which to report as part of the server status.

This property was introduced in InCore 2.8.

:**› Type**: String
:**› Default**: ``in.hub GmbH``
:**› Signal**: manufacturerNameChanged()
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


.. _property_OpcUaServer_productName:

.. _signal_OpcUaServer_productNameChanged:

.. index::
   single: productName

productName
+++++++++++

This property holds the name of the product which to report as part of the server status.

This property was introduced in InCore 2.8.

:**› Type**: String
:**› Default**: ``SIINEOS``
:**› Signal**: productNameChanged()
:**› Attributes**: Writable


.. _property_OpcUaServer_productUri:

.. _signal_OpcUaServer_productUriChanged:

.. index::
   single: productUri

productUri
++++++++++

This property holds the URI of the product which to report as part of the server status.

This property was introduced in InCore 2.8.

:**› Type**: String
:**› Default**: ``https://www.inhub.de/siineos``
:**› Signal**: productUriChanged()
:**› Attributes**: Writable


.. _property_OpcUaServer_security:

.. index::
   single: security

security
++++++++

This property holds the security settings for the server.

:**› Type**: :ref:`OpcUaServerSecurity <object_OpcUaServerSecurity>`
:**› Attributes**: Readonly


.. _property_OpcUaServer_softwareVersion:

.. _signal_OpcUaServer_softwareVersionChanged:

.. index::
   single: softwareVersion

softwareVersion
+++++++++++++++

This property holds the version of the software which to report as part of the server status.

This property was introduced in InCore 2.8.

:**› Type**: String
:**› Default**: ``2.8.0``
:**› Signal**: softwareVersionChanged()
:**› Attributes**: Writable


.. _property_OpcUaServer_users:

.. _signal_OpcUaServer_usersChanged:

.. index::
   single: users

users
+++++



:**› Type**: :ref:`List <object_List>`\<:ref:`OpcUaServerUser <object_OpcUaServerUser>`>
:**› Signal**: usersChanged()
:**› Attributes**: Readonly

Methods
*******


.. _method_OpcUaServer_syncAllNodes:

.. index::
   single: syncAllNodes

syncAllNodes()
++++++++++++++

This method synchronizes all nodes (which may have changed dynamically) with the underlying OPC UA server instance.

This method was introduced in InCore 2.6.



.. _method_OpcUaServer_syncNode:

.. index::
   single: syncNode

syncNode(:ref:`OpcUaServerNode <object_OpcUaServerNode>` startNode)
+++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

This method recursively synchronizes the given nodes with the underlying OPC UA server instance.

This method was introduced in InCore 2.6.


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

    import InCore.Foundation 2.8
    import InCore.OpcUa 2.8
    
    Application {
        OpcUaServer {
            security {
                securityPolicies: OpcUaServerSecurity.SecurityPolicyNone | OpcUaServerSecurity.SecurityPolicyBasic256Sha256 | OpcUaServerSecurity.SecurityPolicyAes128Sha256RsaOaep | OpcUaServerSecurity.SecurityPolicyAes256Sha256RsaPss
                userTokenPolicies: OpcUaServerSecurity.UserTokenPolicyAnonymous | OpcUaServerSecurity.UserTokenPolicyUsername | OpcUaServerSecurity.UserTokenPolicyCertificate
                privateKeyFile: "certs/pki/private/ua-test-server.key"
                certificateFile: "certs/pki/issued/ua-test-server.crt"
                sessionTrustListFiles: ["certs/pki/issued/ua-test-client.crt"]
                sessionIssuerListFiles: ["certs/pki/ca.crt"]
                sessionRevocationListFiles: ["certs/pki/crl.pem"]
                verifyApplicationUri: false
            }
    
            applicationUri: "urn:open62541.server.application"
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
    