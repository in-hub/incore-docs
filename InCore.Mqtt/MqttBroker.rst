
.. _object_MqttBroker:


:index:`MqttBroker`
-------------------

Description
***********

The MqttBroker object creates an MQTT broker listening for connections. An MQTT broker manages the exchange of subscribed and published topics for all connected clients.

:**› Inherits**: :ref:`Object <object_Object>`

Overview
********

Properties
++++++++++

.. hlist::
  :columns: 2

  * :ref:`aclFile <property_MqttBroker_aclFile>`
  * :ref:`allowAnonymous <property_MqttBroker_allowAnonymous>`
  * :ref:`enabled <property_MqttBroker_enabled>`
  * :ref:`internal <property_MqttBroker_internal>`
  * :ref:`maxConnections <property_MqttBroker_maxConnections>`
  * :ref:`passwordFile <property_MqttBroker_passwordFile>`
  * :ref:`port <property_MqttBroker_port>`
  * :ref:`tlsCaFile <property_MqttBroker_tlsCaFile>`
  * :ref:`tlsCertificateFile <property_MqttBroker_tlsCertificateFile>`
  * :ref:`tlsCiphers <property_MqttBroker_tlsCiphers>`
  * :ref:`tlsKeyFile <property_MqttBroker_tlsKeyFile>`
  * :ref:`websocketsPort <property_MqttBroker_websocketsPort>`
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

  * :ref:`Object.completed() <signal_Object_completed>`



Properties
**********


.. _property_MqttBroker_aclFile:

.. _signal_MqttBroker_aclFileChanged:

.. index::
   single: aclFile

aclFile
+++++++

This property holds the path to Mosquitto ACL file managed externally via ``mosquitto_passwd``. See the `mosquitto.conf man page <https://mosquitto.org/man/mosquitto-conf-5.html#idm35>`_ for details.

This property was introduced in InCore 2.3.

:**› Type**: String
:**› Signal**: aclFileChanged()
:**› Attributes**: Writable


.. _property_MqttBroker_allowAnonymous:

.. _signal_MqttBroker_allowAnonymousChanged:

.. index::
   single: allowAnonymous

allowAnonymous
++++++++++++++

This property holds whether clients that connect without providing a username are allowed to connect.

This property was introduced in InCore 2.3.

:**› Type**: Boolean
:**› Default**: ``true``
:**› Signal**: allowAnonymousChanged()
:**› Attributes**: Writable


.. _property_MqttBroker_enabled:

.. _signal_MqttBroker_enabledChanged:

.. index::
   single: enabled

enabled
+++++++

This property holds whether the broker is enabled. If set to ``false`` the broker process is stopped.

:**› Type**: Boolean
:**› Default**: ``true``
:**› Signal**: enabledChanged()
:**› Attributes**: Writable


.. _property_MqttBroker_internal:

.. _signal_MqttBroker_internalChanged:

.. index::
   single: internal

internal
++++++++

This property holds whether the broker should listen for incoming connections on the local loopback interface only. If set to ``true`` the broker will not be reachable by other hosts on the network but internal clients such as docker containers (:ref:`DockerContainer <object_DockerContainer>`) only.

:**› Type**: Boolean
:**› Default**: ``true``
:**› Signal**: internalChanged()
:**› Attributes**: Writable


.. _property_MqttBroker_maxConnections:

.. _signal_MqttBroker_maxConnectionsChanged:

.. index::
   single: maxConnections

maxConnections
++++++++++++++

This property holds the maximum number of connections which the broker is allowed to manage concurrently.

:**› Type**: SignedInteger
:**› Default**: ``-1``
:**› Signal**: maxConnectionsChanged()
:**› Attributes**: Writable, Optional


.. _property_MqttBroker_passwordFile:

.. _signal_MqttBroker_passwordFileChanged:

.. index::
   single: passwordFile

passwordFile
++++++++++++

This property holds the path to Mosquitto password file managed externally via ``mosquitto_passwd``. See the `mosquitto_passwd man page <https://mosquitto.org/man/mosquitto_passwd-1.html>`_ for details.

This property was introduced in InCore 2.3.

:**› Type**: String
:**› Signal**: passwordFileChanged()
:**› Attributes**: Writable


.. _property_MqttBroker_port:

.. _signal_MqttBroker_portChanged:

.. index::
   single: port

port
++++

This property holds the TCP port number which the broker is listening at for incoming connections.

:**› Type**: SignedInteger
:**› Default**: ``1883``
:**› Signal**: portChanged()
:**› Attributes**: Writable


.. _property_MqttBroker_tlsCaFile:

.. _signal_MqttBroker_tlsCaFileChanged:

.. index::
   single: tlsCaFile

tlsCaFile
+++++++++

This property holds the path to a TLS/SSL CA file used when establishing encrypted connections to the broker via secure Websockets.

This property was introduced in InCore 2.3.

:**› Type**: String
:**› Signal**: tlsCaFileChanged()
:**› Attributes**: Writable


.. _property_MqttBroker_tlsCertificateFile:

.. _signal_MqttBroker_tlsCertificateFileChanged:

.. index::
   single: tlsCertificateFile

tlsCertificateFile
++++++++++++++++++

This property holds the path to a TLS/SSL certificate file used when establishing encrypted connections to the broker via secure Websockets.

This property was introduced in InCore 2.3.

:**› Type**: String
:**› Signal**: tlsCertificateFileChanged()
:**› Attributes**: Writable


.. _property_MqttBroker_tlsCiphers:

.. _signal_MqttBroker_tlsCiphersChanged:

.. index::
   single: tlsCiphers

tlsCiphers
++++++++++

This property holds the list of allowed TLS/SSL ciphers for secure Websockets connections, each separated with a colon. Available ciphers can be obtained using the ``openssl ciphers`` command.

This property was introduced in InCore 2.3.

:**› Type**: String
:**› Signal**: tlsCiphersChanged()
:**› Attributes**: Writable


.. _property_MqttBroker_tlsKeyFile:

.. _signal_MqttBroker_tlsKeyFileChanged:

.. index::
   single: tlsKeyFile

tlsKeyFile
++++++++++

This property holds the path to a TLS/SSL key file used when establishing encrypted connections to the broker via secure Websockets.

This property was introduced in InCore 2.3.

:**› Type**: String
:**› Signal**: tlsKeyFileChanged()
:**› Attributes**: Writable


.. _property_MqttBroker_websocketsPort:

.. _signal_MqttBroker_websocketsPortChanged:

.. index::
   single: websocketsPort

websocketsPort
++++++++++++++

This property holds the network port number at which to listen for Websockets connections.

This property was introduced in InCore 2.3.

:**› Type**: SignedInteger
:**› Default**: ``-1``
:**› Signal**: websocketsPortChanged()
:**› Attributes**: Writable


.. _example_MqttBroker:


Example
*******

.. code-block:: qml

    import InCore.Foundation 2.3
    import InCore.Mqtt 2.3
    
    Application {
    
        name: "MqttBrokerExample"
    
        Settings {
            id: settings
            property bool brokerEnabled : true;
        }
    
        // start an MQTT broker if enabled via settings
        MqttBroker {
            enabled: settings.brokerEnabled
            internal: false
        }
    }
    