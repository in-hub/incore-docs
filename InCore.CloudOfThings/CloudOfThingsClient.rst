
.. _object_CloudOfThingsClient:


:index:`CloudOfThingsClient`
----------------------------

Description
***********

The CloudOfThingsClient object is used to connect to the Cloud of Things. A tenant is required to use the cloud and each device has to be registered.

:**› Inherits**: :ref:`Object <object_Object>`

Overview
********

Properties
++++++++++

.. hlist::
  :columns: 2

  * :ref:`clientId <property_CloudOfThingsClient_clientId>`
  * :ref:`error <property_CloudOfThingsClient_error>`
  * :ref:`errorString <property_CloudOfThingsClient_errorString>`
  * :ref:`iccid <property_CloudOfThingsClient_iccid>`
  * :ref:`imei <property_CloudOfThingsClient_imei>`
  * :ref:`imsi <property_CloudOfThingsClient_imsi>`
  * :ref:`objects <property_CloudOfThingsClient_objects>`
  * :ref:`registrator <property_CloudOfThingsClient_registrator>`
  * :ref:`remoteConnectionManager <property_CloudOfThingsClient_remoteConnectionManager>`
  * :ref:`tenant <property_CloudOfThingsClient_tenant>`
  * :ref:`transport <property_CloudOfThingsClient_transport>`
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

  * :ref:`errorOccurred() <signal_CloudOfThingsClient_errorOccurred>`
  * :ref:`objectsDataChanged() <signal_CloudOfThingsClient_objectsDataChanged>`
  * :ref:`Object.completed() <signal_Object_completed>`

Enumerations
++++++++++++

.. hlist::
  :columns: 1

  * :ref:`Error <enum_CloudOfThingsClient_Error>`



Properties
**********


.. _property_CloudOfThingsClient_clientId:

.. _signal_CloudOfThingsClient_clientIdChanged:

.. index::
   single: clientId

clientId
++++++++

This property holds the clientId of this device. Normally this is the MAC address of eth0.

:**› Type**: String
:**› Signal**: clientIdChanged()
:**› Attributes**: Readonly


.. _property_CloudOfThingsClient_error:

.. _signal_CloudOfThingsClient_errorChanged:

.. index::
   single: error

error
+++++

This property holds the most recently occurred error or :ref:`CloudOfThingsClient.NoError <enumitem_CloudOfThingsClient_NoError>` if no error occurred. If the same error occurs multiple times this property does not change. Use the :ref:`errorOccurred() <signal_CloudOfThingsClient_errorOccurred>` signal to detect multiple occurrences of the same error.

:**› Type**: :ref:`Error <enum_CloudOfThingsClient_Error>`
:**› Signal**: errorChanged()
:**› Attributes**: Readonly


.. _property_CloudOfThingsClient_errorString:

.. _signal_CloudOfThingsClient_errorStringChanged:

.. index::
   single: errorString

errorString
+++++++++++

This property holds the current human readable error string corresponding to the current value in the :ref:`error <property_CloudOfThingsClient_error>` property. It may include additional information such as failure reasons or locations.

:**› Type**: String
:**› Signal**: errorStringChanged()
:**› Attributes**: Readonly


.. _property_CloudOfThingsClient_iccid:

.. _signal_CloudOfThingsClient_iccidChanged:

.. index::
   single: iccid

iccid
+++++

This property holds the `ICCID <https://en.wikipedia.org/wiki/SIM_card#ICCID>`_ of the currently used SIM card. Every change of this property is transmitted to Cloud of Things. See :ref:`MobileNetworkInterface <object_MobileNetworkInterface>` for more information.

:**› Type**: String
:**› Signal**: iccidChanged()
:**› Attributes**: Writable


.. _property_CloudOfThingsClient_imei:

.. _signal_CloudOfThingsClient_imeiChanged:

.. index::
   single: imei

imei
++++

This property holds the `IMEI <https://en.wikipedia.org/wiki/International_Mobile_Equipment_Identity>`_ of the modem device. Every change of this property is transmitted to Cloud of Things. See :ref:`MobileNetworkInterface <object_MobileNetworkInterface>` for more information.

:**› Type**: String
:**› Signal**: imeiChanged()
:**› Attributes**: Writable


.. _property_CloudOfThingsClient_imsi:

.. _signal_CloudOfThingsClient_imsiChanged:

.. index::
   single: imsi

imsi
++++

This property holds the `IMSI <https://en.wikipedia.org/wiki/International_mobile_subscriber_identity>`_ of the currently used SIM card. Every change of this property is transmitted to Cloud of Things. See :ref:`MobileNetworkInterface <object_MobileNetworkInterface>` for more information.

:**› Type**: String
:**› Signal**: imsiChanged()
:**› Attributes**: Writable


.. _property_CloudOfThingsClient_objects:

.. _signal_CloudOfThingsClient_objectsChanged:

.. index::
   single: objects

objects
+++++++

This property holds a list of objects. This can be used for objects that require a CloudOfThingsClient as parent.

:**› Type**: :ref:`List <object_List>`\<:ref:`Object <object_Object>`>
:**› Signal**: objectsChanged()
:**› Attributes**: Readonly


.. _property_CloudOfThingsClient_registrator:

.. _signal_CloudOfThingsClient_registratorChanged:

.. index::
   single: registrator

registrator
+++++++++++

This property holds the device registrator used to either do the bootstrap or connect with given credentials.

:**› Type**: :ref:`CloudOfThingsDeviceRegistrator <object_CloudOfThingsDeviceRegistrator>`
:**› Signal**: registratorChanged()
:**› Attributes**: Readonly


.. _property_CloudOfThingsClient_remoteConnectionManager:

.. _signal_CloudOfThingsClient_remoteConnectionManagerChanged:

.. index::
   single: remoteConnectionManager

remoteConnectionManager
+++++++++++++++++++++++

This property holds a remote connection manager. If its property :ref:`CloudOfThingsRemoteConnectionManager.enabled <property_CloudOfThingsRemoteConnectionManager_enabled>` is ``true`` you can configure remote connections in the cloud. Restrict the trusted end points to :ref:`CloudOfThingsRemoteConnectionManager.allowedEndpoints <property_CloudOfThingsRemoteConnectionManager_allowedEndpoints>`.

This property was introduced in InCore 1.1.

:**› Type**: :ref:`CloudOfThingsRemoteConnectionManager <object_CloudOfThingsRemoteConnectionManager>`
:**› Signal**: remoteConnectionManagerChanged()
:**› Attributes**: Readonly


.. _property_CloudOfThingsClient_tenant:

.. index::
   single: tenant

tenant
++++++

This property holds the name of the tenant at the Cloud of Things. Currently it is only used to communicate with the cloud for remote access. It is identical to your cloud access via <tenant>.ram.m2m.telekom.com.

:**› Type**: String
:**› Attributes**: Writable


.. _property_CloudOfThingsClient_transport:

.. _signal_CloudOfThingsClient_transportChanged:

.. index::
   single: transport

transport
+++++++++

This property holds the communication layer which decides which protocol is used to cummunicate with the Cloud of Things.

This property was introduced in InCore 2.0.

:**› Type**: :ref:`CloudOfThingsTransport <object_CloudOfThingsTransport>`
:**› Signal**: transportChanged()
:**› Attributes**: Readonly

Signals
*******


.. _signal_CloudOfThingsClient_errorOccurred:

.. index::
   single: errorOccurred

errorOccurred()
+++++++++++++++

This signal is emitted whenever an error has occurred, regardless of whether the :ref:`error <property_CloudOfThingsClient_error>` property has changed or not. In contrast to the change notification signal of the :ref:`error <property_CloudOfThingsClient_error>` property this signal is also emitted several times if a certain error occurs several times in succession.



.. _signal_CloudOfThingsClient_objectsDataChanged:

.. index::
   single: objectsDataChanged

objectsDataChanged(SignedInteger index)
+++++++++++++++++++++++++++++++++++++++

This signal is emitted whenever the :ref:`List.dataChanged() <signal_List_dataChanged>` signal is emitted, i.e. the item at ``index`` in the :ref:`objects <property_CloudOfThingsClient_objects>` list itself emitted the dataChanged() signal.


Enumerations
************


.. _enum_CloudOfThingsClient_Error:

.. index::
   single: Error

Error
+++++

This enumeration describes all errors which can occur in CloudOfThingsClient objects. The most recently occurred error is stored in the :ref:`error <property_CloudOfThingsClient_error>` property.

.. index::
   single: CloudOfThingsClient.NoError
.. index::
   single: CloudOfThingsClient.MissingTenant
.. list-table::
  :widths: auto
  :header-rows: 1

  * - Name
    - Value
    - Description

      .. _enumitem_CloudOfThingsClient_NoError:
  * - ``CloudOfThingsClient.NoError``
    - ``0``
    - No error occurred or was detected.

      .. _enumitem_CloudOfThingsClient_MissingTenant:
  * - ``CloudOfThingsClient.MissingTenant``
    - ``1``
    - tenant is not set.


.. _example_CloudOfThingsClient:


Example
*******

.. code-block:: qml

    import InCore.Foundation 2.0
    import InCore.CloudOfThings 2.0
    
    Application {
    
        //timer for manually reconnects
        Timer {
            id: timer
            repeat: false
            interval: 5000
            onTriggered: transport.connectToHost()
        }
    
        CloudOfThingsClient {
            id: client
            tenant: "mustercloud"
    
            transport {
                id: transport
    
                protocol: CloudOfThingsTransport.MQTT
                tenantForMQTT: "nb-iot"
                cleanSessionMQTT: false
    
                //set high interval values to reduce traffic
                requestOperationsIntervalMQTT: 10 * 60 * 1000
    
                autoConnect: false
                keepAlive: 2000
    
                //log important state changes
                onConnected: console.log( "Cloud of Things client connected" )
                onErrorChanged: console.log( "oh... error occurred", errorString )
    
                onDisconnected: timer.restart()
            }
    
            remoteConnectionManager {
                enabled: true
    
                //default [ "*" ]
                allowedEndpoints: [ "localhost", "vnc.yourTestServ.er" ]
            }
    
            registrator {
                isRegistered: true
                password: "y0urAwes@meP4ssword"
            }
    
            //do your stuff here
            /*
            CloudOfThingsMeasurementWriter
            {
                ...
            }
    
            CloudOfThingsEventWriter
            {
                ...
            }
            */
        }
    }
    