
.. _object_MqttClient:


:index:`MqttClient`
-------------------

Description
***********

The MqttClient object represents the central access communicating with an MQTT broker. An MQTT client is a program or device that uses MQTT to create a network connection to an MQTT server, also called a broker. The connection request must contain a unique client identifier. Optionally, it can contain a Will Topic, Will Message, user name, and password.

Once a connection is created, a client can subscribe to topics via :ref:`MqttSubscription <object_MqttSubscription>` or publish own topics via :ref:`MqttPublication <object_MqttPublication>`.

:**› Inherits**: :ref:`ObjectArray <object_ObjectArray>`

Overview
********

Properties
++++++++++

.. hlist::
  :columns: 3

  * :ref:`autoConnect <property_MqttClient_autoConnect>`
  * :ref:`cleanSession <property_MqttClient_cleanSession>`
  * :ref:`clientId <property_MqttClient_clientId>`
  * :ref:`encryptConnection <property_MqttClient_encryptConnection>`
  * :ref:`error <property_MqttClient_error>`
  * :ref:`errorString <property_MqttClient_errorString>`
  * :ref:`hostname <property_MqttClient_hostname>`
  * :ref:`keepAlive <property_MqttClient_keepAlive>`
  * :ref:`password <property_MqttClient_password>`
  * :ref:`port <property_MqttClient_port>`
  * :ref:`protocolVersion <property_MqttClient_protocolVersion>`
  * :ref:`state <property_MqttClient_state>`
  * :ref:`username <property_MqttClient_username>`
  * :ref:`willMessage <property_MqttClient_willMessage>`
  * :ref:`willQoS <property_MqttClient_willQoS>`
  * :ref:`willRetain <property_MqttClient_willRetain>`
  * :ref:`willTopic <property_MqttClient_willTopic>`
  * :ref:`ObjectArray.objects <property_ObjectArray_objects>`
  * :ref:`Object.objectId <property_Object_objectId>`
  * :ref:`Object.parent <property_Object_parent>`

Methods
+++++++

.. hlist::
  :columns: 1

  * :ref:`connectToHost() <method_MqttClient_connectToHost>`
  * :ref:`connectToHostEncrypted() <method_MqttClient_connectToHostEncrypted>`
  * :ref:`disconnectFromHost() <method_MqttClient_disconnectFromHost>`
  * :ref:`requestPing() <method_MqttClient_requestPing>`
  * :ref:`Object.fromJson() <method_Object_fromJson>`
  * :ref:`Object.toJson() <method_Object_toJson>`

Signals
+++++++

.. hlist::
  :columns: 1

  * :ref:`brokerSessionRestored() <signal_MqttClient_brokerSessionRestored>`
  * :ref:`connected() <signal_MqttClient_connected>`
  * :ref:`disconnected() <signal_MqttClient_disconnected>`
  * :ref:`errorOccurred() <signal_MqttClient_errorOccurred>`
  * :ref:`pingResponseReceived() <signal_MqttClient_pingResponseReceived>`
  * :ref:`ObjectArray.objectsDataChanged() <signal_ObjectArray_objectsDataChanged>`
  * :ref:`Object.completed() <signal_Object_completed>`

Enumerations
++++++++++++

.. hlist::
  :columns: 1

  * :ref:`Error <enum_MqttClient_Error>`
  * :ref:`ProtocolVersion <enum_MqttClient_ProtocolVersion>`
  * :ref:`State <enum_MqttClient_State>`



Properties
**********


.. _property_MqttClient_autoConnect:

.. _signal_MqttClient_autoConnectChanged:

.. index::
   single: autoConnect

autoConnect
+++++++++++

This property holds whether the MQTT client should connect to the MQTT broker automatically. Keeping this option enabled will also make the client reconnect on connection errors.

:**› Type**: Boolean
:**› Default**: ``true``
:**› Signal**: autoConnectChanged()
:**› Attributes**: Writable


.. _property_MqttClient_cleanSession:

.. _signal_MqttClient_cleanSessionChanged:

.. index::
   single: cleanSession

cleanSession
++++++++++++

This property holds whether a persistent session is used or not. When the clean session flag is set to ``true``, the client does not request a persistent session. If the client reconnects after disconnecting for any reason all information and messages that are queued from a previous session are lost.

:**› Type**: Boolean
:**› Default**: ``true``
:**› Signal**: cleanSessionChanged()
:**› Attributes**: Writable


.. _property_MqttClient_clientId:

.. _signal_MqttClient_clientIdChanged:

.. index::
   single: clientId

clientId
++++++++

This property holds the client's identifier value. Each client needs to have a unique ID to be able to connect to an MQTT broker. If no client ID is specified it will be generated automatically when a connection is established.

:**› Type**: String
:**› Signal**: clientIdChanged()
:**› Attributes**: Writable


.. _property_MqttClient_encryptConnection:

.. _signal_MqttClient_encryptConnectionChanged:

.. index::
   single: encryptConnection

encryptConnection
+++++++++++++++++

This property holds whether to open SSL/TLS connections only. If disabled all traffic between MQTT client and broker is transmitted unencrypted and can be read or manipulated by an attacker easily.

:**› Type**: Boolean
:**› Default**: ``false``
:**› Signal**: encryptConnectionChanged()
:**› Attributes**: Writable


.. _property_MqttClient_error:

.. _signal_MqttClient_errorChanged:

.. index::
   single: error

error
+++++

This property holds the most recent error occured while connecting to an MQTT broker.

:**› Type**: :ref:`Error <enum_MqttClient_Error>`
:**› Default**: :ref:`MqttClient.NoError <enumitem_MqttClient_NoError>`
:**› Signal**: errorChanged()
:**› Attributes**: Readonly


.. _property_MqttClient_errorString:

.. _signal_MqttClient_errorStringChanged:

.. index::
   single: errorString

errorString
+++++++++++

This property holds the current human readable error string corresponding to the current value in the :ref:`error <property_MqttClient_error>` property. It may include additional information such as failure reasons or locations.

:**› Type**: String
:**› Signal**: errorStringChanged()
:**› Attributes**: Readonly


.. _property_MqttClient_hostname:

.. _signal_MqttClient_hostnameChanged:

.. index::
   single: hostname

hostname
++++++++

This property holds the hostname of the MQTT broker to connect to.

:**› Type**: String
:**› Signal**: hostnameChanged()
:**› Attributes**: Writable


.. _property_MqttClient_keepAlive:

.. _signal_MqttClient_keepAliveChanged:

.. index::
   single: keepAlive

keepAlive
+++++++++

This property holds the interval at which regular ping messages are sent to the broker. Once a connection to a broker is established, the client needs to send frequent updates to propagate it can still be reached. The interval between those updates is specified by this property. The interval is specified in milliseconds. The minimum value is ``1000``.

:**› Type**: SignedInteger
:**› Default**: ``60000``
:**› Signal**: keepAliveChanged()
:**› Attributes**: Writable


.. _property_MqttClient_password:

.. _signal_MqttClient_passwordChanged:

.. index::
   single: password

password
++++++++

This property holds the password used for authenticating to a broker.

:**› Type**: String
:**› Signal**: passwordChanged()
:**› Attributes**: Writable


.. _property_MqttClient_port:

.. _signal_MqttClient_portChanged:

.. index::
   single: port

port
++++

This property holds the port to connect to the MQTT broker.

:**› Type**: SignedInteger
:**› Default**: ``0``
:**› Signal**: portChanged()
:**› Attributes**: Writable


.. _property_MqttClient_protocolVersion:

.. _signal_MqttClient_protocolVersionChanged:

.. index::
   single: protocolVersion

protocolVersion
+++++++++++++++

This property holds the MQTT standard version to use for connections.

:**› Type**: :ref:`ProtocolVersion <enum_MqttClient_ProtocolVersion>`
:**› Default**: :ref:`MqttClient.MQTT_3_1_1 <enumitem_MqttClient_MQTT_3_1_1>`
:**› Signal**: protocolVersionChanged()
:**› Attributes**: Writable


.. _property_MqttClient_state:

.. _signal_MqttClient_stateChanged:

.. index::
   single: state

state
+++++

This property holds the current state of the MQTT client connection. See the :ref:`State <enum_MqttClient_State>` enumeration for more details.

:**› Type**: :ref:`State <enum_MqttClient_State>`
:**› Default**: :ref:`MqttClient.Disconnected <enumitem_MqttClient_Disconnected>`
:**› Signal**: stateChanged()
:**› Attributes**: Readonly


.. _property_MqttClient_username:

.. _signal_MqttClient_usernameChanged:

.. index::
   single: username

username
++++++++

This property holds the username used for authenticating to a broker.

:**› Type**: String
:**› Signal**: usernameChanged()
:**› Attributes**: Writable


.. _property_MqttClient_willMessage:

.. _signal_MqttClient_willMessageChanged:

.. index::
   single: willMessage

willMessage
+++++++++++

This property holds the payload of a Will Message. See `mosquitto.org <https://mosquitto.org/man/mqtt-7.html>`_ for more information on Will Messages.

:**› Type**: ArrayBuffer
:**› Signal**: willMessageChanged()
:**› Attributes**: Writable


.. _property_MqttClient_willQoS:

.. _signal_MqttClient_willQoSChanged:

.. index::
   single: willQoS

willQoS
+++++++

This property holds the QoS (Quality of Service) level for sending the Will Message stored in in the :ref:`willMessage <property_MqttClient_willMessage>` property.

:**› Type**: SignedInteger
:**› Default**: ``0``
:**› Signal**: willQoSChanged()
:**› Attributes**: Writable, Optional


.. _property_MqttClient_willRetain:

.. _signal_MqttClient_willRetainChanged:

.. index::
   single: willRetain

willRetain
++++++++++

This property holds whether the Will Message should be retained on the broker for future subscribers to receive.

:**› Type**: Boolean
:**› Default**: ``false``
:**› Signal**: willRetainChanged()
:**› Attributes**: Writable


.. _property_MqttClient_willTopic:

.. _signal_MqttClient_willTopicChanged:

.. index::
   single: willTopic

willTopic
+++++++++

This property holds the name of the topic to which to publish the Will Message.

:**› Type**: String
:**› Signal**: willTopicChanged()
:**› Attributes**: Writable

Methods
*******


.. _method_MqttClient_connectToHost:

.. index::
   single: connectToHost

connectToHost()
+++++++++++++++

This method initiates a connection to the MQTT broker. This method usually should not be called manually in favor of setting the :ref:`autoConnect <property_MqttClient_autoConnect>` property.



.. _method_MqttClient_connectToHostEncrypted:

.. index::
   single: connectToHostEncrypted

connectToHostEncrypted()
++++++++++++++++++++++++

This method initiates an encrypted connection to the MQTT broker. This method usually should not be called manually in favor of setting the :ref:`autoConnect <property_MqttClient_autoConnect>` property.



.. _method_MqttClient_disconnectFromHost:

.. index::
   single: disconnectFromHost

disconnectFromHost()
++++++++++++++++++++

This method disconnects from the MQTT broker. This method usually should not be called manually in favor of setting the :ref:`autoConnect <property_MqttClient_autoConnect>` property.



.. _method_MqttClient_requestPing:

.. index::
   single: requestPing

requestPing()
+++++++++++++

This method Sends a ping message to the broker and expects a reply. If the connection is active, the MQTT client will automatically send a ping message at keepAlive intervals. To check whether the ping is successful, connect to the :ref:`pingResponseReceived() <signal_MqttClient_pingResponseReceived>` signal. Returns ``true`` if the ping request could be sent.

:**› Returns**: Boolean


Signals
*******


.. _signal_MqttClient_brokerSessionRestored:

.. index::
   single: brokerSessionRestored

brokerSessionRestored()
+++++++++++++++++++++++

This signal is emitted after a client has successfully connected to a broker with the :ref:`cleanSession <property_MqttClient_cleanSession>` property set to ``false``, and the broker has restored the session. Sessions can be restored if a client has connected previously using the same :ref:`clientId <property_MqttClient_clientId>`.



.. _signal_MqttClient_connected:

.. index::
   single: connected

connected()
+++++++++++

This signal is emitted when a connection has been established.



.. _signal_MqttClient_disconnected:

.. index::
   single: disconnected

disconnected()
++++++++++++++

This signal is emitted when a connection has been closed. A connection may be closed when :ref:`disconnectFromHost() <method_MqttClient_disconnectFromHost>` is called or when the broker disconnects.



.. _signal_MqttClient_errorOccurred:

.. index::
   single: errorOccurred

errorOccurred()
+++++++++++++++

This signal is emitted whenever an error has occurred, regardless of whether the :ref:`error <property_MqttClient_error>` property has changed or not. In contrast to the change notification signal of the :ref:`error <property_MqttClient_error>` property this signal is also emitted several times if a certain error occurs several times in succession.



.. _signal_MqttClient_pingResponseReceived:

.. index::
   single: pingResponseReceived

pingResponseReceived()
++++++++++++++++++++++

This signal is emitted  after the broker responds to a :ref:`requestPing() <method_MqttClient_requestPing>` call or a :ref:`keepAlive <property_MqttClient_keepAlive>` ping message, and the connection is still valid.


Enumerations
************


.. _enum_MqttClient_Error:

.. index::
   single: Error

Error
+++++

This enumeration describes all the possible errors which can occur when connecting to an MQTT broker.

.. index::
   single: MqttClient.NoError
.. index::
   single: MqttClient.InvalidProtocolVersion
.. index::
   single: MqttClient.IdRejected
.. index::
   single: MqttClient.ServerUnavailable
.. index::
   single: MqttClient.BadUsernameOrPassword
.. index::
   single: MqttClient.NotAuthorized
.. index::
   single: MqttClient.TransportInvalid
.. index::
   single: MqttClient.ProtocolViolation
.. index::
   single: MqttClient.UnknownError
.. index::
   single: MqttClient.Mqtt5SpecificError
.. list-table::
  :widths: auto
  :header-rows: 1

  * - Name
    - Value
    - Description

      .. _enumitem_MqttClient_NoError:
  * - ``MqttClient.NoError``
    - ``0``
    - No error occurred or was detected.

      .. _enumitem_MqttClient_InvalidProtocolVersion:
  * - ``MqttClient.InvalidProtocolVersion``
    - ``1``
    - Invalid protocol version: the broker does not accept a connection using the specified protocol version.

      .. _enumitem_MqttClient_IdRejected:
  * - ``MqttClient.IdRejected``
    - ``2``
    - ID rejected: the client ID is malformed. This might be related to its length.

      .. _enumitem_MqttClient_ServerUnavailable:
  * - ``MqttClient.ServerUnavailable``
    - ``3``
    - Server unavailable: the network connection has been established, but the service is unavailable on the broker side.

      .. _enumitem_MqttClient_BadUsernameOrPassword:
  * - ``MqttClient.BadUsernameOrPassword``
    - ``4``
    - Bad username or password: the data in the username or password is malformed.

      .. _enumitem_MqttClient_NotAuthorized:
  * - ``MqttClient.NotAuthorized``
    - ``5``
    - Not authorized: the client is not authorized to connect.

      .. _enumitem_MqttClient_TransportInvalid:
  * - ``MqttClient.TransportInvalid``
    - ``256``
    - Invalid transport: the underlying transport caused an error. For example, the connection might have been interrupted unexpectedly.

      .. _enumitem_MqttClient_ProtocolViolation:
  * - ``MqttClient.ProtocolViolation``
    - ``257``
    - Protocol violation: the client encountered a protocol violation, and therefore closed the connection.

      .. _enumitem_MqttClient_UnknownError:
  * - ``MqttClient.UnknownError``
    - ``258``
    - Unknown error: an unknown error occurred.

      .. _enumitem_MqttClient_Mqtt5SpecificError:
  * - ``MqttClient.Mqtt5SpecificError``
    - ``259``
    - The error is related to MQTT protocol level 5. A reason code might provide more details.


.. _enum_MqttClient_ProtocolVersion:

.. index::
   single: ProtocolVersion

ProtocolVersion
+++++++++++++++

This enumeration describes The protocol version of the MQTT standard to use during communication with a broker.

.. index::
   single: MqttClient.MQTT_3_1
.. index::
   single: MqttClient.MQTT_3_1_1
.. index::
   single: MqttClient.MQTT_5_0
.. list-table::
  :widths: auto
  :header-rows: 1

  * - Name
    - Value
    - Description

      .. _enumitem_MqttClient_MQTT_3_1:
  * - ``MqttClient.MQTT_3_1``
    - ``3``
    - MQTT Standard 3.1.

      .. _enumitem_MqttClient_MQTT_3_1_1:
  * - ``MqttClient.MQTT_3_1_1``
    - ``4``
    - MQTT Standard 3.1.1, publicly referred to as version 4.

      .. _enumitem_MqttClient_MQTT_5_0:
  * - ``MqttClient.MQTT_5_0``
    - ``5``
    - MQTT Standard 5.0.


.. _enum_MqttClient_State:

.. index::
   single: State

State
+++++

This enumeration describes specifies the states a client can enter.

.. index::
   single: MqttClient.Disconnected
.. index::
   single: MqttClient.Connecting
.. index::
   single: MqttClient.Connected
.. list-table::
  :widths: auto
  :header-rows: 1

  * - Name
    - Value
    - Description

      .. _enumitem_MqttClient_Disconnected:
  * - ``MqttClient.Disconnected``
    - ``0``
    - The client is disconnected from the broker.

      .. _enumitem_MqttClient_Connecting:
  * - ``MqttClient.Connecting``
    - ``1``
    - A connection request has been made, but the broker has not approved the connection yet.

      .. _enumitem_MqttClient_Connected:
  * - ``MqttClient.Connected``
    - ``2``
    - The client is connected to the broker.


.. _example_MqttClient:


Example
*******

.. code-block:: qml

    import InCore.Foundation 2.0
    import InCore.Mqtt 2.0
    
    Application {
    
        name: "MqttClientExample"
    
        // create an MQTT client which subscribes a topic
        MqttClient {
            clientId: "MqttClientExample"
    
            // configure broker host parameters
            hostname: "mqtt.inhub.de"
            port: 1883
            username: "inhub"
            password: "mqtt"
            encryptConnection: true
            autoConnect: true
    
            // use MQTT 5 protocol
            protocolVersion: MqttClient.MQTT_5_0
    
            // send keepalive messages to broker every 5 seconds
            keepAlive: 5000
    
            willTopic: "incore/lastWords"
            willMessage: "Good bye!"
    
            // define example subscription
            MqttSubscription {
                MqttTopic {
                    name: "livingRoom/temperature"
                    onDataChanged: console.log(name, data)
                }
            }
        }
    }
    