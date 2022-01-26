
.. _object_MobileNetworkInterface:


:index:`MobileNetworkInterface`
-------------------------------

Description
***********

The MobileNetworkInterface object represents a mobile network interface (i.e. a modem device such as an LTE USB stick) and manages connections to a mobile (cellular) network. In order to start a connection, the :ref:`apn <property_MobileNetworkInterface_apn>`, :ref:`username <property_MobileNetworkInterface_username>` and :ref:`password <property_MobileNetworkInterface_password>` need to be set. A connection will be established to available networks automatically. The current modem and connectivity state can always be read through the :ref:`state <property_MobileNetworkInterface_state>` property.

.. important:: A MobileNetworkInterface object always has to be a child of a :ref:`NetworkConfiguration <object_NetworkConfiguration>` object in order to work properly. Otherwise the modem device will connect to the mobile network only without establishing a data connection.

:**› Inherits**: :ref:`NetworkInterface <object_NetworkInterface>`

Overview
********

Properties
++++++++++

.. hlist::
  :columns: 3

  * :ref:`allowRoaming <property_MobileNetworkInterface_allowRoaming>`
  * :ref:`allowRoamingItem <property_MobileNetworkInterface_allowRoamingItem>`
  * :ref:`apn <property_MobileNetworkInterface_apn>`
  * :ref:`apnItem <property_MobileNetworkInterface_apnItem>`
  * :ref:`authenticationType <property_MobileNetworkInterface_authenticationType>`
  * :ref:`authenticationTypeItem <property_MobileNetworkInterface_authenticationTypeItem>`
  * :ref:`deviceManufacturer <property_MobileNetworkInterface_deviceManufacturer>`
  * :ref:`deviceModel <property_MobileNetworkInterface_deviceModel>`
  * :ref:`establishIpConnection <property_MobileNetworkInterface_establishIpConnection>`
  * :ref:`establishIpConnectionItem <property_MobileNetworkInterface_establishIpConnectionItem>`
  * :ref:`iccid <property_MobileNetworkInterface_iccid>`
  * :ref:`imei <property_MobileNetworkInterface_imei>`
  * :ref:`imsi <property_MobileNetworkInterface_imsi>`
  * :ref:`number <property_MobileNetworkInterface_number>`
  * :ref:`numberItem <property_MobileNetworkInterface_numberItem>`
  * :ref:`password <property_MobileNetworkInterface_password>`
  * :ref:`passwordItem <property_MobileNetworkInterface_passwordItem>`
  * :ref:`pin <property_MobileNetworkInterface_pin>`
  * :ref:`pinItem <property_MobileNetworkInterface_pinItem>`
  * :ref:`signalQuality <property_MobileNetworkInterface_signalQuality>`
  * :ref:`state <property_MobileNetworkInterface_state>`
  * :ref:`username <property_MobileNetworkInterface_username>`
  * :ref:`usernameItem <property_MobileNetworkInterface_usernameItem>`
  * :ref:`NetworkInterface.dhcpClientIdentifier <property_NetworkInterface_dhcpClientIdentifier>`
  * :ref:`NetworkInterface.enabled <property_NetworkInterface_enabled>`
  * :ref:`NetworkInterface.enabledItem <property_NetworkInterface_enabledItem>`
  * :ref:`NetworkInterface.error <property_NetworkInterface_error>`
  * :ref:`NetworkInterface.errorString <property_NetworkInterface_errorString>`
  * :ref:`NetworkInterface.hardwareAddress <property_NetworkInterface_hardwareAddress>`
  * :ref:`NetworkInterface.hardwareAddressItem <property_NetworkInterface_hardwareAddressItem>`
  * :ref:`NetworkInterface.hardwareName <property_NetworkInterface_hardwareName>`
  * :ref:`NetworkInterface.networkAddresses <property_NetworkInterface_networkAddresses>`
  * :ref:`NetworkInterface.operationalState <property_NetworkInterface_operationalState>`
  * :ref:`NetworkInterface.routes <property_NetworkInterface_routes>`
  * :ref:`NetworkInterface.setupState <property_NetworkInterface_setupState>`
  * :ref:`NetworkInterface.useRoutes <property_NetworkInterface_useRoutes>`
  * :ref:`NetworkInterface.useRoutesItem <property_NetworkInterface_useRoutesItem>`
  * :ref:`ConfigurationObject.items <property_ConfigurationObject_items>`
  * :ref:`ConfigurationObject.name <property_ConfigurationObject_name>`
  * :ref:`ConfigurationObject.nameItem <property_ConfigurationObject_nameItem>`
  * :ref:`Object.objectId <property_Object_objectId>`
  * :ref:`Object.parent <property_Object_parent>`

Methods
+++++++

.. hlist::
  :columns: 1

  * :ref:`sendMessage() <method_MobileNetworkInterface_sendMessage>`
  * :ref:`Object.deserializeProperties() <method_Object_deserializeProperties>`
  * :ref:`Object.fromJson() <method_Object_fromJson>`
  * :ref:`Object.serializeProperties() <method_Object_serializeProperties>`
  * :ref:`Object.toJson() <method_Object_toJson>`

Signals
+++++++

.. hlist::
  :columns: 2

  * :ref:`connected() <signal_MobileNetworkInterface_connected>`
  * :ref:`disconnected() <signal_MobileNetworkInterface_disconnected>`
  * :ref:`messageReceived() <signal_MobileNetworkInterface_messageReceived>`
  * :ref:`messageSent() <signal_MobileNetworkInterface_messageSent>`
  * :ref:`NetworkInterface.errorOccurred() <signal_NetworkInterface_errorOccurred>`
  * :ref:`NetworkInterface.routesDataChanged() <signal_NetworkInterface_routesDataChanged>`
  * :ref:`ConfigurationObject.aboutToBeUpdated() <signal_ConfigurationObject_aboutToBeUpdated>`
  * :ref:`ConfigurationObject.itemsDataChanged() <signal_ConfigurationObject_itemsDataChanged>`
  * :ref:`ConfigurationObject.updated() <signal_ConfigurationObject_updated>`
  * :ref:`Object.completed() <signal_Object_completed>`

Enumerations
++++++++++++

.. hlist::
  :columns: 1

  * :ref:`AuthenticationType <enum_MobileNetworkInterface_AuthenticationType>`
  * :ref:`State <enum_MobileNetworkInterface_State>`
  * :ref:`NetworkInterface.DhcpClientIdentifier <enum_NetworkInterface_DhcpClientIdentifier>`
  * :ref:`NetworkInterface.Error <enum_NetworkInterface_Error>`
  * :ref:`NetworkInterface.OperationalState <enum_NetworkInterface_OperationalState>`
  * :ref:`NetworkInterface.SetupState <enum_NetworkInterface_SetupState>`



Properties
**********


.. _property_MobileNetworkInterface_allowRoaming:

.. _signal_MobileNetworkInterface_allowRoamingChanged:

.. index::
   single: allowRoaming

allowRoaming
++++++++++++

This property holds whether data connections are allowed during roaming. If disabled the device will be offline if the home network is not available.

:**› Type**: Boolean
:**› Default**: ``false``
:**› Signal**: allowRoamingChanged()
:**› Attributes**: Writable


.. _property_MobileNetworkInterface_allowRoamingItem:

.. index::
   single: allowRoamingItem

allowRoamingItem
++++++++++++++++

This property holds an internal :ref:`ConfigurationItem <object_ConfigurationItem>` instance for the :ref:`allowRoaming <property_MobileNetworkInterface_allowRoaming>` property.

:**› Type**: :ref:`ConfigurationItem <object_ConfigurationItem>`
:**› Attributes**: Readonly


.. _property_MobileNetworkInterface_apn:

.. _signal_MobileNetworkInterface_apnChanged:

.. index::
   single: apn

apn
+++

This property holds the `access point name <https://en.wikipedia.org/wiki/Access_Point_Name>`_ to use for the mobile connection.

:**› Type**: String
:**› Signal**: apnChanged()
:**› Attributes**: Writable


.. _property_MobileNetworkInterface_apnItem:

.. index::
   single: apnItem

apnItem
+++++++

This property holds an internal :ref:`ConfigurationItem <object_ConfigurationItem>` instance for the :ref:`apn <property_MobileNetworkInterface_apn>` property.

:**› Type**: :ref:`ConfigurationItem <object_ConfigurationItem>`
:**› Attributes**: Readonly


.. _property_MobileNetworkInterface_authenticationType:

.. _signal_MobileNetworkInterface_authenticationTypeChanged:

.. index::
   single: authenticationType

authenticationType
++++++++++++++++++



This property was introduced in InCore 2.3.

:**› Type**: :ref:`AuthenticationType <enum_MobileNetworkInterface_AuthenticationType>`
:**› Default**: :ref:`MobileNetworkInterface.UnknownAuthentication <enumitem_MobileNetworkInterface_UnknownAuthentication>`
:**› Signal**: authenticationTypeChanged()
:**› Attributes**: Writable


.. _property_MobileNetworkInterface_authenticationTypeItem:

.. index::
   single: authenticationTypeItem

authenticationTypeItem
++++++++++++++++++++++

This property holds an internal :ref:`ConfigurationItem <object_ConfigurationItem>` instance for the :ref:`authenticationType <property_MobileNetworkInterface_authenticationType>` property.

:**› Type**: :ref:`ConfigurationItem <object_ConfigurationItem>`
:**› Attributes**: Readonly


.. _property_MobileNetworkInterface_deviceManufacturer:

.. _signal_MobileNetworkInterface_deviceManufacturerChanged:

.. index::
   single: deviceManufacturer

deviceManufacturer
++++++++++++++++++

This property holds the manufacturer name of the modem device.

This property was introduced in InCore 2.3.

:**› Type**: String
:**› Signal**: deviceManufacturerChanged()
:**› Attributes**: Readonly


.. _property_MobileNetworkInterface_deviceModel:

.. _signal_MobileNetworkInterface_deviceModelChanged:

.. index::
   single: deviceModel

deviceModel
+++++++++++

This property holds the model name of the modem device.

:**› Type**: String
:**› Signal**: deviceModelChanged()
:**› Attributes**: Readonly


.. _property_MobileNetworkInterface_establishIpConnection:

.. _signal_MobileNetworkInterface_establishIpConnectionChanged:

.. index::
   single: establishIpConnection

establishIpConnection
+++++++++++++++++++++

This property holds whether to establish an IP-based data connection. When set to ``false``, the modem will only register on the cellular network and remain in the :ref:`MobileNetworkInterface.StateRegistered <enumitem_MobileNetworkInterface_StateRegistered>` state. In this state it's possible to send and receive text messages (SMS).

This property was introduced in InCore 2.4.

:**› Type**: Boolean
:**› Default**: ``true``
:**› Signal**: establishIpConnectionChanged()
:**› Attributes**: Writable


.. _property_MobileNetworkInterface_establishIpConnectionItem:

.. index::
   single: establishIpConnectionItem

establishIpConnectionItem
+++++++++++++++++++++++++

This property holds an internal :ref:`ConfigurationItem <object_ConfigurationItem>` instance for the :ref:`establishIpConnection <property_MobileNetworkInterface_establishIpConnection>` property.

:**› Type**: :ref:`ConfigurationItem <object_ConfigurationItem>`
:**› Attributes**: Readonly


.. _property_MobileNetworkInterface_iccid:

.. _signal_MobileNetworkInterface_iccidChanged:

.. index::
   single: iccid

iccid
+++++

This property holds the `ICCID <https://en.wikipedia.org/wiki/SIM_card#ICCID>`_ of the currently used SIM card.

:**› Type**: String
:**› Signal**: iccidChanged()
:**› Attributes**: Readonly


.. _property_MobileNetworkInterface_imei:

.. _signal_MobileNetworkInterface_imeiChanged:

.. index::
   single: imei

imei
++++

This property holds the `IMEI <https://en.wikipedia.org/wiki/International_Mobile_Equipment_Identity>`_ of the modem device.

:**› Type**: String
:**› Signal**: imeiChanged()
:**› Attributes**: Readonly


.. _property_MobileNetworkInterface_imsi:

.. _signal_MobileNetworkInterface_imsiChanged:

.. index::
   single: imsi

imsi
++++

This property holds the `IMSI <https://en.wikipedia.org/wiki/International_mobile_subscriber_identity>`_ of the currently used SIM card.

:**› Type**: String
:**› Signal**: imsiChanged()
:**› Attributes**: Readonly


.. _property_MobileNetworkInterface_number:

.. _signal_MobileNetworkInterface_numberChanged:

.. index::
   single: number

number
++++++

This property holds the telephone number to dial for establishing a data connection.

:**› Type**: String
:**› Default**: ``*99#``
:**› Signal**: numberChanged()
:**› Attributes**: Writable


.. _property_MobileNetworkInterface_numberItem:

.. index::
   single: numberItem

numberItem
++++++++++

This property holds an internal :ref:`ConfigurationItem <object_ConfigurationItem>` instance for the :ref:`number <property_MobileNetworkInterface_number>` property.

:**› Type**: :ref:`ConfigurationItem <object_ConfigurationItem>`
:**› Attributes**: Readonly


.. _property_MobileNetworkInterface_password:

.. _signal_MobileNetworkInterface_passwordChanged:

.. index::
   single: password

password
++++++++

This property holds the password for authenticating with the mobile network.

:**› Type**: String
:**› Signal**: passwordChanged()
:**› Attributes**: Writable


.. _property_MobileNetworkInterface_passwordItem:

.. index::
   single: passwordItem

passwordItem
++++++++++++

This property holds an internal :ref:`ConfigurationItem <object_ConfigurationItem>` instance for the :ref:`password <property_MobileNetworkInterface_password>` property.

:**› Type**: :ref:`ConfigurationItem <object_ConfigurationItem>`
:**› Attributes**: Readonly


.. _property_MobileNetworkInterface_pin:

.. _signal_MobileNetworkInterface_pinChanged:

.. index::
   single: pin

pin
+++

This property holds the PIN used to unlock the SIM card. It's only required if the SIM card needs to be unlocked.

:**› Type**: String
:**› Signal**: pinChanged()
:**› Attributes**: Writable


.. _property_MobileNetworkInterface_pinItem:

.. index::
   single: pinItem

pinItem
+++++++

This property holds an internal :ref:`ConfigurationItem <object_ConfigurationItem>` instance for the :ref:`pin <property_MobileNetworkInterface_pin>` property.

:**› Type**: :ref:`ConfigurationItem <object_ConfigurationItem>`
:**› Attributes**: Readonly


.. _property_MobileNetworkInterface_signalQuality:

.. _signal_MobileNetworkInterface_signalQualityChanged:

.. index::
   single: signalQuality

signalQuality
+++++++++++++

This property holds the current signal quality in percent (0-100) of the dominant access technology the device is using to communicate with the network.

:**› Type**: SignedInteger
:**› Signal**: signalQualityChanged()
:**› Attributes**: Readonly


.. _property_MobileNetworkInterface_state:

.. _signal_MobileNetworkInterface_stateChanged:

.. index::
   single: state

state
+++++

This property holds the current state of the modem device and its connectivity.

:**› Type**: :ref:`State <enum_MobileNetworkInterface_State>`
:**› Signal**: stateChanged()
:**› Attributes**: Readonly


.. _property_MobileNetworkInterface_username:

.. _signal_MobileNetworkInterface_usernameChanged:

.. index::
   single: username

username
++++++++

This property holds the username for authenticating with the mobile network.

:**› Type**: String
:**› Signal**: usernameChanged()
:**› Attributes**: Writable


.. _property_MobileNetworkInterface_usernameItem:

.. index::
   single: usernameItem

usernameItem
++++++++++++

This property holds an internal :ref:`ConfigurationItem <object_ConfigurationItem>` instance for the :ref:`username <property_MobileNetworkInterface_username>` property.

:**› Type**: :ref:`ConfigurationItem <object_ConfigurationItem>`
:**› Attributes**: Readonly

Methods
*******


.. _method_MobileNetworkInterface_sendMessage:

.. index::
   single: sendMessage

sendMessage(String recipientNumbers, String text)
+++++++++++++++++++++++++++++++++++++++++++++++++

This method sends a text message (SMS) using the modem. The phone number(s) of the SMS recipient(s) have to be supplied in the ``recipientNumbers`` argument. To send more than one SMS separate the phone numbers with comma. Included spaces will be removed. If the message text in the ``text`` parameter contains non-ASCII characters the Unicode (UCS-2) encoding is used which requires 2 bytes per character. This may be relevant if the number of SMS that can be sent in a time period is limited. 

It returns ``true`` if the send operation has been initiated successfully. Errors occurring while sending the SMS are signaled through the :ref:`NetworkInterface.error <property_NetworkInterface_error>` property.

This method was introduced in InCore 2.3.

:**› Returns**: Boolean


Signals
*******


.. _signal_MobileNetworkInterface_connected:

.. index::
   single: connected

connected()
+++++++++++

This signal is emitted when a data connection has been established, i.e. :ref:`state <property_MobileNetworkInterface_state>` changed to :ref:`MobileNetworkInterface.StateConnected <enumitem_MobileNetworkInterface_StateConnected>`.



.. _signal_MobileNetworkInterface_disconnected:

.. index::
   single: disconnected

disconnected()
++++++++++++++

This signal is emitted when the connection to the mobile network has been closed, i.e. :ref:`state <property_MobileNetworkInterface_state>` is not :ref:`MobileNetworkInterface.StateConnected <enumitem_MobileNetworkInterface_StateConnected>` yet/any longer.



.. _signal_MobileNetworkInterface_messageReceived:

.. index::
   single: messageReceived

messageReceived(String messageText, String messageId)
+++++++++++++++++++++++++++++++++++++++++++++++++++++

This signal is emitted when a text message (SMS) has been received. The message text is available trough the `m̀essageText`` argument. The internal ID of the received message is supplied in the ``messageId`` argument.

This signal was introduced in InCore 2.3.



.. _signal_MobileNetworkInterface_messageSent:

.. index::
   single: messageSent

messageSent(String messageId)
+++++++++++++++++++++++++++++

This signal is emitted when a text message (SMS) has been sent successfully. It's not emitted if an error occurred while sending. The internal ID of the sent message is supplied in the ``messageId`` argument

This signal was introduced in InCore 2.3.


Enumerations
************


.. _enum_MobileNetworkInterface_AuthenticationType:

.. index::
   single: AuthenticationType

AuthenticationType
++++++++++++++++++



.. index::
   single: MobileNetworkInterface.UnknownAuthentication
.. index::
   single: MobileNetworkInterface.NoAuthentication
.. index::
   single: MobileNetworkInterface.PAP
.. index::
   single: MobileNetworkInterface.CHAP
.. index::
   single: MobileNetworkInterface.MSCHAP
.. index::
   single: MobileNetworkInterface.MSCHAPv2
.. index::
   single: MobileNetworkInterface.EAP
.. list-table::
  :widths: auto
  :header-rows: 1

  * - Name
    - Value
    - Description

      .. _enumitem_MobileNetworkInterface_UnknownAuthentication:
  * - ``MobileNetworkInterface.UnknownAuthentication``
    - ``0``
    - 

      .. _enumitem_MobileNetworkInterface_NoAuthentication:
  * - ``MobileNetworkInterface.NoAuthentication``
    - ``1``
    - 

      .. _enumitem_MobileNetworkInterface_PAP:
  * - ``MobileNetworkInterface.PAP``
    - ``2``
    - 

      .. _enumitem_MobileNetworkInterface_CHAP:
  * - ``MobileNetworkInterface.CHAP``
    - ``3``
    - 

      .. _enumitem_MobileNetworkInterface_MSCHAP:
  * - ``MobileNetworkInterface.MSCHAP``
    - ``4``
    - 

      .. _enumitem_MobileNetworkInterface_MSCHAPv2:
  * - ``MobileNetworkInterface.MSCHAPv2``
    - ``5``
    - 

      .. _enumitem_MobileNetworkInterface_EAP:
  * - ``MobileNetworkInterface.EAP``
    - ``6``
    - 


.. _enum_MobileNetworkInterface_State:

.. index::
   single: State

State
+++++

This enumeration describes all possible states of the modem device represented by the object.

.. index::
   single: MobileNetworkInterface.StateNoDevice
.. index::
   single: MobileNetworkInterface.StateFailed
.. index::
   single: MobileNetworkInterface.StateUnknown
.. index::
   single: MobileNetworkInterface.StateInitializing
.. index::
   single: MobileNetworkInterface.StateLocked
.. index::
   single: MobileNetworkInterface.StateDisabled
.. index::
   single: MobileNetworkInterface.StateDisabling
.. index::
   single: MobileNetworkInterface.StateEnabling
.. index::
   single: MobileNetworkInterface.StateEnabled
.. index::
   single: MobileNetworkInterface.StateSearching
.. index::
   single: MobileNetworkInterface.StateRegistered
.. index::
   single: MobileNetworkInterface.StateDisconnecting
.. index::
   single: MobileNetworkInterface.StateConnecting
.. index::
   single: MobileNetworkInterface.StateConnected
.. list-table::
  :widths: auto
  :header-rows: 1

  * - Name
    - Value
    - Description

      .. _enumitem_MobileNetworkInterface_StateNoDevice:
  * - ``MobileNetworkInterface.StateNoDevice``
    - ``0``
    - Could not find a modem device.

      .. _enumitem_MobileNetworkInterface_StateFailed:
  * - ``MobileNetworkInterface.StateFailed``
    - ``1``
    - The modem is unusable.

      .. _enumitem_MobileNetworkInterface_StateUnknown:
  * - ``MobileNetworkInterface.StateUnknown``
    - ``2``
    - The modem is in an unknown state.

      .. _enumitem_MobileNetworkInterface_StateInitializing:
  * - ``MobileNetworkInterface.StateInitializing``
    - ``3``
    - The modem is currently being initialized.

      .. _enumitem_MobileNetworkInterface_StateLocked:
  * - ``MobileNetworkInterface.StateLocked``
    - ``4``
    - The modem needs to be unlocked with a PIN.

      .. _enumitem_MobileNetworkInterface_StateDisabled:
  * - ``MobileNetworkInterface.StateDisabled``
    - ``5``
    - The modem is not enabled and is powered down.

      .. _enumitem_MobileNetworkInterface_StateDisabling:
  * - ``MobileNetworkInterface.StateDisabling``
    - ``6``
    - The modem is currently transitioning to the :ref:`MobileNetworkInterface.StateDisabled <enumitem_MobileNetworkInterface_StateDisabled>` state.

      .. _enumitem_MobileNetworkInterface_StateEnabling:
  * - ``MobileNetworkInterface.StateEnabling``
    - ``7``
    - The modem is currently transitioning to the :ref:`MobileNetworkInterface.StateEnabled <enumitem_MobileNetworkInterface_StateEnabled>` state.

      .. _enumitem_MobileNetworkInterface_StateEnabled:
  * - ``MobileNetworkInterface.StateEnabled``
    - ``8``
    - The modem is enabled and powered on but not registered with a network provider and not available for data connections.

      .. _enumitem_MobileNetworkInterface_StateSearching:
  * - ``MobileNetworkInterface.StateSearching``
    - ``9``
    - The modem is searching for a network provider to register with.

      .. _enumitem_MobileNetworkInterface_StateRegistered:
  * - ``MobileNetworkInterface.StateRegistered``
    - ``10``
    - The modem is registered with a network provider and data connections may be available for use.

      .. _enumitem_MobileNetworkInterface_StateDisconnecting:
  * - ``MobileNetworkInterface.StateDisconnecting``
    - ``11``
    - The modem is disconnecting and deactivating the last active packet data bearer. This state will not be entered if more than one packet data bearer is active and one of the active bearers is deactivated.

      .. _enumitem_MobileNetworkInterface_StateConnecting:
  * - ``MobileNetworkInterface.StateConnecting``
    - ``12``
    - The modem is activating and connecting the first packet data bearer. Subsequent bearer activations when another bearer is already active do not cause this state to be entered.

      .. _enumitem_MobileNetworkInterface_StateConnected:
  * - ``MobileNetworkInterface.StateConnected``
    - ``13``
    - One or more packet data bearers is active and connected, i.e. the device is online.


.. _example_MobileNetworkInterface:


Example
*******

.. code-block:: qml

    import InCore.Foundation 2.5
    
    Application {
        NetworkConfiguration {
            MobileNetworkInterface {
                id: wwan0
    
                // configure connection parameters
                apn: "internet.myprovider.de"
                username: "inhub"
                password: "MyS3cr3tP4ssw0rd"
                // print basic information when completed
                onCompleted: {
                    console.log("Device model:", deviceModel)
                    console.log("IMEI:", imei)
                    console.log("IMSI:", imsi)
                }
                // continuously print signal quality
                onSignalQualityChanged: {
                    console.log("Signal quality:", signalQuality)
                }
                // print state information
                onConnected: console.log("I'm online :-)")
                onDisconnected: console.log("I'm offline :-(")
                onStateChanged: console.log("Modem state", state)
    
                onMessageReceived: console.log(("SMS received: \"%1\"").arg(messageText))
            }
        }
    
        Counter {
            id: smsCounter
            interval: 30000
            onValueChanged: wwan0.sendMessage("+49123456789, +49135798642", ("Hello world! This is SMS number %1.").arg(value))
        }
    }
    