
.. _object_CloudOfThingsTransport:


:index:`CloudOfThingsTransport`
-------------------------------

Description
***********

The CloudOfThingsTransport object encapsulates the communication with the Cloud of Things. It is part of :ref:`CloudOfThingsClient <object_CloudOfThingsClient>`. Take a look at the :ref:`protocol <property_CloudOfThingsTransport_protocol>` property.

This object was introduced in InCore 2.0.

:**› Inherits**: :ref:`Object <object_Object>`

Overview
********

Properties
++++++++++

.. hlist::
  :columns: 2

  * :ref:`autoConnect <property_CloudOfThingsTransport_autoConnect>`
  * :ref:`cleanSessionMQTT <property_CloudOfThingsTransport_cleanSessionMQTT>`
  * :ref:`error <property_CloudOfThingsTransport_error>`
  * :ref:`errorString <property_CloudOfThingsTransport_errorString>`
  * :ref:`keepAlive <property_CloudOfThingsTransport_keepAlive>`
  * :ref:`protocol <property_CloudOfThingsTransport_protocol>`
  * :ref:`requestCredentialsIntervalREST <property_CloudOfThingsTransport_requestCredentialsIntervalREST>`
  * :ref:`requestOperationsIntervalMQTT <property_CloudOfThingsTransport_requestOperationsIntervalMQTT>`
  * :ref:`sendBufferInterval <property_CloudOfThingsTransport_sendBufferInterval>`
  * :ref:`state <property_CloudOfThingsTransport_state>`
  * :ref:`tenantForMQTT <property_CloudOfThingsTransport_tenantForMQTT>`
  * :ref:`Object.objectId <property_Object_objectId>`
  * :ref:`Object.parent <property_Object_parent>`

Methods
+++++++

.. hlist::
  :columns: 1

  * :ref:`connectToHost() <method_CloudOfThingsTransport_connectToHost>`
  * :ref:`disconnectFromHost() <method_CloudOfThingsTransport_disconnectFromHost>`
  * :ref:`requestPing() <method_CloudOfThingsTransport_requestPing>`
  * :ref:`Object.fromJson() <method_Object_fromJson>`
  * :ref:`Object.toJson() <method_Object_toJson>`

Signals
+++++++

.. hlist::
  :columns: 1

  * :ref:`connected() <signal_CloudOfThingsTransport_connected>`
  * :ref:`disconnected() <signal_CloudOfThingsTransport_disconnected>`
  * :ref:`errorOccurred() <signal_CloudOfThingsTransport_errorOccurred>`
  * :ref:`pingResponseReceived() <signal_CloudOfThingsTransport_pingResponseReceived>`
  * :ref:`Object.completed() <signal_Object_completed>`

Enumerations
++++++++++++

.. hlist::
  :columns: 1

  * :ref:`Error <enum_CloudOfThingsTransport_Error>`
  * :ref:`Protocol <enum_CloudOfThingsTransport_Protocol>`
  * :ref:`State <enum_CloudOfThingsTransport_State>`



Properties
**********


.. _property_CloudOfThingsTransport_autoConnect:

.. _signal_CloudOfThingsTransport_autoConnectChanged:

.. index::
   single: autoConnect

autoConnect
+++++++++++

This property holds whether the device should be connected automatically. If :ref:`autoConnect <property_CloudOfThingsTransport_autoConnect>` is ``true`` the client tries to reestablish the connection periodically whenever it has been lost.

This property was introduced in InCore 2.0.

:**› Type**: Boolean
:**› Default**: ``true``
:**› Signal**: autoConnectChanged()
:**› Attributes**: Writable


.. _property_CloudOfThingsTransport_cleanSessionMQTT:

.. index::
   single: cleanSessionMQTT

cleanSessionMQTT
++++++++++++++++

This property holds whether a persistent session is used or not. When the clean session flag is set to ``true``, the client does not request a persistent session. If the client reconnects after disconnecting for any reason all information and messages that are queued from a previous session are lost. This only has effect if protocol is ``MQTT``.

This property was introduced in InCore 2.0.

:**› Type**: Boolean
:**› Default**: ``false``
:**› Attributes**: Writable


.. _property_CloudOfThingsTransport_error:

.. _signal_CloudOfThingsTransport_errorChanged:

.. index::
   single: error

error
+++++

This property holds the most recently occurred error or :ref:`CloudOfThingsTransport.NoError <enumitem_CloudOfThingsTransport_NoError>` if no error occurred. If the same error occurs multiple times this property does not change. Use the :ref:`errorOccurred() <signal_CloudOfThingsTransport_errorOccurred>` signal to detect multiple occurrences of the same error.

:**› Type**: :ref:`Error <enum_CloudOfThingsTransport_Error>`
:**› Signal**: errorChanged()
:**› Attributes**: Readonly


.. _property_CloudOfThingsTransport_errorString:

.. _signal_CloudOfThingsTransport_errorStringChanged:

.. index::
   single: errorString

errorString
+++++++++++

This property holds the current human readable error string corresponding to the current value in the :ref:`error <property_CloudOfThingsTransport_error>` property. It may include additional information such as failure reasons or locations.

:**› Type**: String
:**› Signal**: errorStringChanged()
:**› Attributes**: Readonly


.. _property_CloudOfThingsTransport_keepAlive:

.. _signal_CloudOfThingsTransport_keepAliveChanged:

.. index::
   single: keepAlive

keepAlive
+++++++++

This property holds the interval in milliseconds in which the connectivity of the underlaying network is checked. If connection is lost and :ref:`autoConnect <property_CloudOfThingsTransport_autoConnect>` is set to ``true`` the transport will try to reconnect. If :ref:`protocol <property_CloudOfThingsTransport_protocol>` is set to :ref:`CloudOfThingsTransport.MQTT <enumitem_CloudOfThingsTransport_MQTT>` this property will be the interval at which regular ping messages are sent to the broker. If :ref:`protocol <property_CloudOfThingsTransport_protocol>` is set to :ref:`CloudOfThingsTransport.REST <enumitem_CloudOfThingsTransport_REST>` this interval will be used to make a connection to the Cloud of Things. If the tcp connection could be established the ping is considered successful and :ref:`pingResponseReceived() <signal_CloudOfThingsTransport_pingResponseReceived>` is emitted.

This property was introduced in InCore 2.0.

:**› Type**: SignedInteger
:**› Default**: ``5000``
:**› Signal**: keepAliveChanged()
:**› Attributes**: Writable


.. _property_CloudOfThingsTransport_protocol:

.. index::
   single: protocol

protocol
++++++++

This property holds the protocol which is used to communicate with the Cloud of Things. :ref:`CloudOfThingsTransport.MQTT <enumitem_CloudOfThingsTransport_MQTT>` uses less bandwidth but does not support all features (real time notifications).

This property was introduced in InCore 2.0.

:**› Type**: :ref:`Protocol <enum_CloudOfThingsTransport_Protocol>`
:**› Default**: :ref:`CloudOfThingsTransport.REST <enumitem_CloudOfThingsTransport_REST>`
:**› Attributes**: Writable


.. _property_CloudOfThingsTransport_requestCredentialsIntervalREST:

.. _signal_CloudOfThingsTransport_requestCredentialsIntervalRESTChanged:

.. index::
   single: requestCredentialsIntervalREST

requestCredentialsIntervalREST
++++++++++++++++++++++++++++++

This property holds the interval which is used to request device credentials from Cloud of Things. This property is only necessary if the first registration should be delayed and does normally not have to be changed. This only has effect if protocol is ``REST``.

This property was introduced in InCore 2.1.

:**› Type**: SignedInteger
:**› Default**: ``1000``
:**› Signal**: requestCredentialsIntervalRESTChanged()
:**› Attributes**: Writable


.. _property_CloudOfThingsTransport_requestOperationsIntervalMQTT:

.. _signal_CloudOfThingsTransport_requestOperationsIntervalMQTTChanged:

.. index::
   single: requestOperationsIntervalMQTT

requestOperationsIntervalMQTT
+++++++++++++++++++++++++++++

This property holds the interval in which pending operations from Cloud of Things are handled. A high interval saves bandwidth but increases the period until pending operations are handled. Set to ``0`` to disable this functionality. This only has effect if protocol is ``MQTT``.

This property was introduced in InCore 2.0.

:**› Type**: SignedInteger
:**› Default**: ``60000``
:**› Signal**: requestOperationsIntervalMQTTChanged()
:**› Attributes**: Writable


.. _property_CloudOfThingsTransport_sendBufferInterval:

.. index::
   single: sendBufferInterval

sendBufferInterval
++++++++++++++++++

This property holds the interval in which buffered :ref:`Measurement <object_Measurement>` and :ref:`Event <object_Event>` objects are sent. This reduces the risk of connection aborts due to too many requests. Usually this property can be left unchanged.

This property was introduced in InCore 2.0.

:**› Type**: SignedInteger
:**› Default**: ``1000``
:**› Attributes**: Writable


.. _property_CloudOfThingsTransport_state:

.. _signal_CloudOfThingsTransport_stateChanged:

.. index::
   single: state

state
+++++

This property holds the current state of the transport.

This property was introduced in InCore 2.0.

:**› Type**: :ref:`State <enum_CloudOfThingsTransport_State>`
:**› Default**: :ref:`CloudOfThingsTransport.Disconnected <enumitem_CloudOfThingsTransport_Disconnected>`
:**› Signal**: stateChanged()
:**› Attributes**: Readonly


.. _property_CloudOfThingsTransport_tenantForMQTT:

.. index::
   single: tenantForMQTT

tenantForMQTT
+++++++++++++

This property holds the name of the tenant at the Cloud of Things for communication via MQTT. It is used to communicate with the cloud via <tenantForMQTT>.ram.m2m.telekom.com.

This property was introduced in InCore 2.0.

:**› Type**: String
:**› Attributes**: Writable

Methods
*******


.. _method_CloudOfThingsTransport_connectToHost:

.. index::
   single: connectToHost

connectToHost()
+++++++++++++++

This method can be used to manually connect to the cloud. This method has no effect if property :ref:`state <property_CloudOfThingsTransport_state>` is not equal :ref:`CloudOfThingsTransport.Disconnected <enumitem_CloudOfThingsTransport_Disconnected>`.

This method was introduced in InCore 2.0.



.. _method_CloudOfThingsTransport_disconnectFromHost:

.. index::
   single: disconnectFromHost

disconnectFromHost()
++++++++++++++++++++

This method disconnects the client from the cloud. Make sure to set :ref:`autoConnect <property_CloudOfThingsTransport_autoConnect>` to ``false`` to avoid side effects.

This method was introduced in InCore 2.0.



.. _method_CloudOfThingsTransport_requestPing:

.. index::
   single: requestPing

requestPing()
+++++++++++++

This method sends a ping message. Connect to the pingResponseReceived() signal to check whether the ping was successful. Returns ``true`` if the ping request was sent successfully.

This method was introduced in InCore 2.0.


Signals
*******


.. _signal_CloudOfThingsTransport_connected:

.. index::
   single: connected

connected()
+++++++++++

This signal is emitted after the device successfully established a connection to the Cloud of Things. Usually there is some initial overhead before measurments or events are sent.

This signal was introduced in InCore 2.0.



.. _signal_CloudOfThingsTransport_disconnected:

.. index::
   single: disconnected

disconnected()
++++++++++++++

This signal is emitted when the underlying transport lost its connection.

This signal was introduced in InCore 2.0.



.. _signal_CloudOfThingsTransport_errorOccurred:

.. index::
   single: errorOccurred

errorOccurred()
+++++++++++++++

This signal is emitted whenever an error has occurred, regardless of whether the :ref:`error <property_CloudOfThingsTransport_error>` property has changed or not. In contrast to the change notification signal of the :ref:`error <property_CloudOfThingsTransport_error>` property this signal is also emitted several times if a certain error occurs several times in succession.



.. _signal_CloudOfThingsTransport_pingResponseReceived:

.. index::
   single: pingResponseReceived

pingResponseReceived()
++++++++++++++++++++++

This signal is emitted after :ref:`requestPing() <method_CloudOfThingsTransport_requestPing>` is called and the corresponding response has been received.This signal is also emitted when the repeated ping via timer responded.

This signal was introduced in InCore 2.0.


Enumerations
************


.. _enum_CloudOfThingsTransport_Error:

.. index::
   single: Error

Error
+++++

This enumeration describes all errors which can occur in CloudOfThingsTransport objects. The most recently occurred error is stored in the :ref:`error <property_CloudOfThingsTransport_error>` property.

.. index::
   single: CloudOfThingsTransport.NoError
.. index::
   single: CloudOfThingsTransport.MissingTenant
.. index::
   single: CloudOfThingsTransport.TransportError
.. list-table::
  :widths: auto
  :header-rows: 1

  * - Name
    - Value
    - Description

      .. _enumitem_CloudOfThingsTransport_NoError:
  * - ``CloudOfThingsTransport.NoError``
    - ``0``
    - No error occurred or was detected.

      .. _enumitem_CloudOfThingsTransport_MissingTenant:
  * - ``CloudOfThingsTransport.MissingTenant``
    - ``1``
    - Missing tenant: tenant and/or tenantForMQTT is empty.

      .. _enumitem_CloudOfThingsTransport_TransportError:
  * - ``CloudOfThingsTransport.TransportError``
    - ``2``
    - The underlaying transport had an error: .


.. _enum_CloudOfThingsTransport_Protocol:

.. index::
   single: Protocol

Protocol
++++++++

This enumeration describes the protocol types which can be used to communicate with the Cloud of Things.

This enumeration was introduced in InCore 2.0.

.. index::
   single: CloudOfThingsTransport.MQTT
.. index::
   single: CloudOfThingsTransport.REST
.. list-table::
  :widths: auto
  :header-rows: 1

  * - Name
    - Value
    - Description

      .. _enumitem_CloudOfThingsTransport_MQTT:
  * - ``CloudOfThingsTransport.MQTT``
    - ``0``
    - MQTT over port 8883 with SSL.

      .. _enumitem_CloudOfThingsTransport_REST:
  * - ``CloudOfThingsTransport.REST``
    - ``1``
    - REST over HTTPS.


.. _enum_CloudOfThingsTransport_State:

.. index::
   single: State

State
+++++

This enumeration describes the states a client can enter.

This enumeration was introduced in InCore 2.0.

.. index::
   single: CloudOfThingsTransport.Disconnected
.. index::
   single: CloudOfThingsTransport.Connecting
.. index::
   single: CloudOfThingsTransport.Connected
.. list-table::
  :widths: auto
  :header-rows: 1

  * - Name
    - Value
    - Description

      .. _enumitem_CloudOfThingsTransport_Disconnected:
  * - ``CloudOfThingsTransport.Disconnected``
    - ``0``
    - The client is disconnected from the cloud.

      .. _enumitem_CloudOfThingsTransport_Connecting:
  * - ``CloudOfThingsTransport.Connecting``
    - ``1``
    - A connection request has been made, but the cloud has not approved the connection yet.

      .. _enumitem_CloudOfThingsTransport_Connected:
  * - ``CloudOfThingsTransport.Connected``
    - ``2``
    - The client is connected to the cloud.

Example
*******
See :ref:`CloudOfThingsClient example <example_CloudOfThingsClient>` on how to use CloudOfThingsTransport.
