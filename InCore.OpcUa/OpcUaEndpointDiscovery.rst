
.. _object_OpcUaEndpointDiscovery:


:index:`OpcUaEndpointDiscovery`
-------------------------------

Description
***********

Please refer to the `Qt OPC UA EndpointDiscovery QML type <https://doc.qt.io/QtOPCUA/qml-qtopcua-endpointdiscovery.html#->`_ documentation.


Overview
********

Properties
++++++++++

.. hlist::
  :columns: 1

  * `connection <https://doc.qt.io/QtOPCUA/qml-qtopcua-endpointdiscovery.html#connection-prop>`_
  * `count <https://doc.qt.io/QtOPCUA/qml-qtopcua-endpointdiscovery.html#count-prop>`_
  * `serverUrl <https://doc.qt.io/QtOPCUA/qml-qtopcua-endpointdiscovery.html#serverUrl-prop>`_
  * `status <https://doc.qt.io/QtOPCUA/qml-qtopcua-endpointdiscovery.html#status-prop>`_

Methods
+++++++

.. hlist::
  :columns: 1

  * `at <https://doc.qt.io/QtOPCUA/qml-qtopcua-endpointdiscovery.html#at-method>`_



Properties
**********


.. _property_OpcUaEndpointDiscovery_connection:

.. index::
   single: connection

connection
++++++++++

Please refer to the `Qt OPC UA EndpointDiscovery QML type <https://doc.qt.io/QtOPCUA/qml-qtopcua-endpointdiscovery.html#connection-prop>`_ documentation.

:**› Attributes**: Writable


.. _property_OpcUaEndpointDiscovery_count:

.. index::
   single: count

count
+++++

Please refer to the `Qt OPC UA EndpointDiscovery QML type <https://doc.qt.io/QtOPCUA/qml-qtopcua-endpointdiscovery.html#count-prop>`_ documentation.

:**› Attributes**: Readonly


.. _property_OpcUaEndpointDiscovery_serverUrl:

.. index::
   single: serverUrl

serverUrl
+++++++++

Please refer to the `Qt OPC UA EndpointDiscovery QML type <https://doc.qt.io/QtOPCUA/qml-qtopcua-endpointdiscovery.html#serverUrl-prop>`_ documentation.

:**› Attributes**: Writable


.. _property_OpcUaEndpointDiscovery_status:

.. index::
   single: status

status
++++++

Please refer to the `Qt OPC UA EndpointDiscovery QML type <https://doc.qt.io/QtOPCUA/qml-qtopcua-endpointdiscovery.html#status-prop>`_ documentation.

:**› Attributes**: Readonly

Methods
*******


.. _method_OpcUaEndpointDiscovery_at:

.. index::
   single: at

at(SignedInteger row)
+++++++++++++++++++++

Please refer to the `Qt OPC UA EndpointDiscovery QML type <https://doc.qt.io/QtOPCUA/qml-qtopcua-endpointdiscovery.html#at-method>`_ documentation.

:**› Returns**: :ref:`QOpcUaEndpointDescription <enum_OpcUaEndpointDiscovery_QOpcUaEndpointDescription>`



.. _example_OpcUaEndpointDiscovery:


Example
*******

.. code-block:: qml

    import InCore.Foundation 2.3
    import InCore.OpcUa 2.3
    
    Application {
        OpcUaClient {
            OpcUaEndpointDiscovery {
                serverUrl: "opc.tcp://192.168.1.2:4840"
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
    
            OpcUaConnection {
                id: connection
                backend: availableBackends[0]
                defaultConnection: true
            }
        }
    }
    