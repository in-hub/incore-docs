
.. _object_MqttListener:


:index:`MqttListener`
---------------------

Description
***********

The MqttListener object represents a listener of an MQTT broker. A listener provides access to a broker via the configured :ref:`port <property_MqttListener_port>`.

This object was introduced in InCore 2.6.

:**› Inherits**: :ref:`Object <object_Object>`

Overview
********

Properties
++++++++++

.. hlist::
  :columns: 2

  * :ref:`aclFile <property_MqttListener_aclFile>`
  * :ref:`allowAnonymous <property_MqttListener_allowAnonymous>`
  * :ref:`internal <property_MqttListener_internal>`
  * :ref:`passwordFile <property_MqttListener_passwordFile>`
  * :ref:`port <property_MqttListener_port>`
  * :ref:`protocol <property_MqttListener_protocol>`
  * :ref:`tlsCaFile <property_MqttListener_tlsCaFile>`
  * :ref:`tlsCertificateFile <property_MqttListener_tlsCertificateFile>`
  * :ref:`tlsCiphers <property_MqttListener_tlsCiphers>`
  * :ref:`tlsKeyFile <property_MqttListener_tlsKeyFile>`
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

  * :ref:`Protocol <enum_MqttListener_Protocol>`



Properties
**********


.. _property_MqttListener_aclFile:

.. _signal_MqttListener_aclFileChanged:

.. index::
   single: aclFile

aclFile
+++++++

This property holds the path to an external Mosquitto ACL file.See the `mosquitto.conf man page <https://mosquitto.org/man/mosquitto-conf-5.html#idm35>`_ for details.

This property was introduced in InCore 2.3.

:**› Type**: String
:**› Signal**: aclFileChanged()
:**› Attributes**: Writable


.. _property_MqttListener_allowAnonymous:

.. _signal_MqttListener_allowAnonymousChanged:

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


.. _property_MqttListener_internal:

.. _signal_MqttListener_internalChanged:

.. index::
   single: internal

internal
++++++++

This property holds whether the broker should listen for incoming connections on the local loopback interface only. If set to ``true`` the broker will not be reachable by other hosts on the network but internal clients such as docker containers (:ref:`DockerContainer <object_DockerContainer>`) only.

:**› Type**: Boolean
:**› Default**: ``true``
:**› Signal**: internalChanged()
:**› Attributes**: Writable


.. _property_MqttListener_passwordFile:

.. _signal_MqttListener_passwordFileChanged:

.. index::
   single: passwordFile

passwordFile
++++++++++++

This property holds the path to Mosquitto password file managed externally via ``mosquitto_passwd``. See the `mosquitto_passwd man page <https://mosquitto.org/man/mosquitto_passwd-1.html>`_ for details.

This property was introduced in InCore 2.3.

:**› Type**: String
:**› Signal**: passwordFileChanged()
:**› Attributes**: Writable


.. _property_MqttListener_port:

.. _signal_MqttListener_portChanged:

.. index::
   single: port

port
++++

This property holds the TCP port number which the broker should listen at for incoming connections.

:**› Type**: SignedInteger
:**› Default**: ``-1``
:**› Signal**: portChanged()
:**› Attributes**: Writable


.. _property_MqttListener_protocol:

.. _signal_MqttListener_protocolChanged:

.. index::
   single: protocol

protocol
++++++++

This property holds the protocol which to use for communication with clients.

:**› Type**: :ref:`Protocol <enum_MqttListener_Protocol>`
:**› Default**: :ref:`MqttListener.Mqtt <enumitem_MqttListener_Mqtt>`
:**› Signal**: protocolChanged()
:**› Attributes**: Writable


.. _property_MqttListener_tlsCaFile:

.. _signal_MqttListener_tlsCaFileChanged:

.. index::
   single: tlsCaFile

tlsCaFile
+++++++++

This property holds the path to a TLS/SSL CA file used when establishing encrypted connections to the broker via secure Websockets.

This property was introduced in InCore 2.8.

:**› Type**: String
:**› Signal**: tlsCaFileChanged()
:**› Attributes**: Writable


.. _property_MqttListener_tlsCertificateFile:

.. _signal_MqttListener_tlsCertificateFileChanged:

.. index::
   single: tlsCertificateFile

tlsCertificateFile
++++++++++++++++++

This property holds the path to a TLS/SSL certificate file used when establishing encrypted connections to the broker via secure Websockets.

This property was introduced in InCore 2.8.

:**› Type**: String
:**› Signal**: tlsCertificateFileChanged()
:**› Attributes**: Writable


.. _property_MqttListener_tlsCiphers:

.. _signal_MqttListener_tlsCiphersChanged:

.. index::
   single: tlsCiphers

tlsCiphers
++++++++++

This property holds the list of allowed TLS/SSL ciphers for secure Websockets connections, each separated with a colon. Available ciphers can be obtained using the ``openssl ciphers`` command.

This property was introduced in InCore 2.8.

:**› Type**: String
:**› Signal**: tlsCiphersChanged()
:**› Attributes**: Writable


.. _property_MqttListener_tlsKeyFile:

.. _signal_MqttListener_tlsKeyFileChanged:

.. index::
   single: tlsKeyFile

tlsKeyFile
++++++++++

This property holds the path to a TLS/SSL key file used when establishing encrypted connections to the broker via secure Websockets.

This property was introduced in InCore 2.8.

:**› Type**: String
:**› Signal**: tlsKeyFileChanged()
:**› Attributes**: Writable

Enumerations
************


.. _enum_MqttListener_Protocol:

.. index::
   single: Protocol

Protocol
++++++++



.. index::
   single: MqttListener.Mqtt
.. index::
   single: MqttListener.Websockets
.. list-table::
  :widths: auto
  :header-rows: 1

  * - Name
    - Value
    - Description

      .. _enumitem_MqttListener_Mqtt:
  * - ``MqttListener.Mqtt``
    - ``0``
    - 

      .. _enumitem_MqttListener_Websockets:
  * - ``MqttListener.Websockets``
    - ``1``
    - 

