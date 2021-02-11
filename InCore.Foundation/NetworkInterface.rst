
.. _object_NetworkInterface:


:index:`NetworkInterface`
-------------------------

Description
***********

The NetworkInterface object is an abstract base object for all kind of specific network interface objects such as :ref:`WiredNetworkInterface <object_WiredNetworkInterface>`, :ref:`WirelessNetworkInterface <object_WirelessNetworkInterface>` and :ref:`MobileNetworkInterface <object_MobileNetworkInterface>`. It provides common properties and enumerations which apply to all network interfaces and implements common configuration mechanisms.

:**› Inherits**: :ref:`ConfigurationObject <object_ConfigurationObject>`
:**› Inherited by**: :ref:`MobileNetworkInterface <object_MobileNetworkInterface>`, :ref:`WiredNetworkInterface <object_WiredNetworkInterface>`, :ref:`WirelessNetworkInterface <object_WirelessNetworkInterface>`

Overview
********

Properties
++++++++++

.. hlist::
  :columns: 3

  * :ref:`dhcpClientIdentifier <property_NetworkInterface_dhcpClientIdentifier>`
  * :ref:`enabled <property_NetworkInterface_enabled>`
  * :ref:`enabledItem <property_NetworkInterface_enabledItem>`
  * :ref:`error <property_NetworkInterface_error>`
  * :ref:`errorString <property_NetworkInterface_errorString>`
  * :ref:`hardwareAddress <property_NetworkInterface_hardwareAddress>`
  * :ref:`hardwareAddressItem <property_NetworkInterface_hardwareAddressItem>`
  * :ref:`hardwareName <property_NetworkInterface_hardwareName>`
  * :ref:`networkAddresses <property_NetworkInterface_networkAddresses>`
  * :ref:`operationalState <property_NetworkInterface_operationalState>`
  * :ref:`setupState <property_NetworkInterface_setupState>`
  * :ref:`useRoutes <property_NetworkInterface_useRoutes>`
  * :ref:`useRoutesItem <property_NetworkInterface_useRoutesItem>`
  * :ref:`ConfigurationObject.items <property_ConfigurationObject_items>`
  * :ref:`ConfigurationObject.name <property_ConfigurationObject_name>`
  * :ref:`ConfigurationObject.nameItem <property_ConfigurationObject_nameItem>`
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

  * :ref:`errorOccurred() <signal_NetworkInterface_errorOccurred>`
  * :ref:`ConfigurationObject.itemsDataChanged() <signal_ConfigurationObject_itemsDataChanged>`
  * :ref:`Object.completed() <signal_Object_completed>`

Enumerations
++++++++++++

.. hlist::
  :columns: 1

  * :ref:`DhcpClientIdentifier <enum_NetworkInterface_DhcpClientIdentifier>`
  * :ref:`Error <enum_NetworkInterface_Error>`
  * :ref:`OperationalState <enum_NetworkInterface_OperationalState>`
  * :ref:`SetupState <enum_NetworkInterface_SetupState>`



Properties
**********


.. _property_NetworkInterface_dhcpClientIdentifier:

.. _signal_NetworkInterface_dhcpClientIdentifierChanged:

.. index::
   single: dhcpClientIdentifier

dhcpClientIdentifier
++++++++++++++++++++

This property holds the DHCPv4 client identifier to use when sending DHCP requests. For all options the MAC address of the corresponding network interface is used to generate a unique identifier. When set to :ref:`NetworkInterface.MacIdentifier <enumitem_NetworkInterface_MacIdentifier>` the MAC address is used directly. Otherwise an RFC4361-compliant client ID is generated based on the MAC address.

:**› Type**: :ref:`DhcpClientIdentifier <enum_NetworkInterface_DhcpClientIdentifier>`
:**› Default**: :ref:`NetworkInterface.MacIdentifier <enumitem_NetworkInterface_MacIdentifier>`
:**› Signal**: dhcpClientIdentifierChanged()
:**› Attributes**: Writable, Optional


.. _property_NetworkInterface_enabled:

.. _signal_NetworkInterface_enabledChanged:

.. index::
   single: enabled

enabled
+++++++

This property holds whether the network interface is enabled at all. If enabled the interface is managed and configured by the system according to the settings represented by other properties in this object and derived objects.

:**› Type**: Boolean
:**› Default**: ``false``
:**› Signal**: enabledChanged()
:**› Attributes**: Writable


.. _property_NetworkInterface_enabledItem:

.. index::
   single: enabledItem

enabledItem
+++++++++++

This property holds an internal :ref:`ConfigurationItem <object_ConfigurationItem>` instance for the :ref:`enabled <property_NetworkInterface_enabled>` property.

:**› Type**: :ref:`ConfigurationItem <object_ConfigurationItem>`
:**› Attributes**: Readonly


.. _property_NetworkInterface_error:

.. _signal_NetworkInterface_errorChanged:

.. index::
   single: error

error
+++++

This property holds the most recently occurred error or :ref:`NetworkInterface.NoError <enumitem_NetworkInterface_NoError>` if no error occurred. If the same error occurs multiple times this property does not change. Use the :ref:`errorOccurred() <signal_NetworkInterface_errorOccurred>` signal to detect multiple occurrences of the same error.

:**› Type**: :ref:`Error <enum_NetworkInterface_Error>`
:**› Signal**: errorChanged()
:**› Attributes**: Readonly


.. _property_NetworkInterface_errorString:

.. _signal_NetworkInterface_errorStringChanged:

.. index::
   single: errorString

errorString
+++++++++++

This property holds the current human readable error string corresponding to the current value in the :ref:`error <property_NetworkInterface_error>` property. It may include additional information such as failure reasons or locations.

:**› Type**: String
:**› Signal**: errorStringChanged()
:**› Attributes**: Readonly


.. _property_NetworkInterface_hardwareAddress:

.. _signal_NetworkInterface_hardwareAddressChanged:

.. index::
   single: hardwareAddress

hardwareAddress
+++++++++++++++

This property holds the hardware address of the network interface, usually the MAC address.

:**› Type**: String
:**› Signal**: hardwareAddressChanged()
:**› Attributes**: Readonly


.. _property_NetworkInterface_hardwareAddressItem:

.. index::
   single: hardwareAddressItem

hardwareAddressItem
+++++++++++++++++++

This property holds an internal :ref:`ConfigurationItem <object_ConfigurationItem>` instance for the :ref:`hardwareAddress <property_NetworkInterface_hardwareAddress>` property.

:**› Type**: :ref:`ConfigurationItem <object_ConfigurationItem>`
:**› Attributes**: Readonly


.. _property_NetworkInterface_hardwareName:

.. index::
   single: hardwareName

hardwareName
++++++++++++

This property holds the unique hardware name of the network interface as seen by the operating system, e.g. ``eth0``.

:**› Type**: String
:**› Attributes**: Readonly


.. _property_NetworkInterface_networkAddresses:

.. _signal_NetworkInterface_networkAddressesChanged:

.. index::
   single: networkAddresses

networkAddresses
++++++++++++++++

This property holds the actual IP addresses in effect which have been assigned by the network or configured by the user.

This property was introduced in InCore 1.1.

:**› Type**: StringList
:**› Signal**: networkAddressesChanged()
:**› Attributes**: Readonly


.. _property_NetworkInterface_operationalState:

.. _signal_NetworkInterface_operationalStateChanged:

.. index::
   single: operationalState

operationalState
++++++++++++++++

This property holds the operational state of the network interface. The most common case is to check whether the operational state equals :ref:`NetworkInterface.Routable <enumitem_NetworkInterface_Routable>` in order to determine whether the device is ready to communicate with certain hosts or networks. See the :ref:`NetworkInterface.OperationalState <enum_NetworkInterface_OperationalState>` enumeration for more details.

:**› Type**: :ref:`OperationalState <enum_NetworkInterface_OperationalState>`
:**› Default**: :ref:`NetworkInterface.NoOperation <enumitem_NetworkInterface_NoOperation>`
:**› Signal**: operationalStateChanged()
:**› Attributes**: Readonly


.. _property_NetworkInterface_setupState:

.. _signal_NetworkInterface_setupStateChanged:

.. index::
   single: setupState

setupState
++++++++++

This property holds the setup state of the network interface which specifies the state and progress of the interface configuration. The most common case is to check whether the setup state equals :ref:`NetworkInterface.Configured <enumitem_NetworkInterface_Configured>` which indicates that the network interface has been configured successfully. See the :ref:`NetworkInterface.SetupState <enum_NetworkInterface_SetupState>` enumeration for more details.

:**› Type**: :ref:`SetupState <enum_NetworkInterface_SetupState>`
:**› Default**: :ref:`NetworkInterface.NoSetup <enumitem_NetworkInterface_NoSetup>`
:**› Signal**: setupStateChanged()
:**› Attributes**: Readonly


.. _property_NetworkInterface_useRoutes:

.. _signal_NetworkInterface_useRoutesChanged:

.. index::
   single: useRoutes

useRoutes
+++++++++

This property holds whether to add the routes received during the configuration process to the routing table (e.g. routes advertisted by DHCP servers). This can be important when using multiple network interfaces which would normally lead to multiple default routes being added to the routing table. If in this case not all network gateways have access to the internet, the internet connectivity of the device itself can be impacted as well and may not work reliable and deterministic. By setting this property to ``false`` except for one specific interface the device will access the internet and non-local networks through the specific interface.

:**› Type**: Boolean
:**› Default**: ``true``
:**› Signal**: useRoutesChanged()
:**› Attributes**: Writable


.. _property_NetworkInterface_useRoutesItem:

.. index::
   single: useRoutesItem

useRoutesItem
+++++++++++++

This property holds an internal :ref:`ConfigurationItem <object_ConfigurationItem>` instance for the :ref:`useRoutes <property_NetworkInterface_useRoutes>` property.

:**› Type**: :ref:`ConfigurationItem <object_ConfigurationItem>`
:**› Attributes**: Readonly

Signals
*******


.. _signal_NetworkInterface_errorOccurred:

.. index::
   single: errorOccurred

errorOccurred()
+++++++++++++++

This signal is emitted whenever an error has occurred, regardless of whether the :ref:`error <property_NetworkInterface_error>` property has changed or not. In contrast to the change notification signal of the :ref:`error <property_NetworkInterface_error>` property this signal is also emitted several times if a certain error occurs several times in succession.


Enumerations
************


.. _enum_NetworkInterface_DhcpClientIdentifier:

.. index::
   single: DhcpClientIdentifier

DhcpClientIdentifier
++++++++++++++++++++

This enumeration describes the DHCPv4 client identifier to use when sending DHCP requests.

.. index::
   single: NetworkInterface.MacIdentifier
.. index::
   single: NetworkInterface.DhcpUniqueIdentifier
.. list-table::
  :widths: auto
  :header-rows: 1

  * - Name
    - Value
    - Description

      .. _enumitem_NetworkInterface_MacIdentifier:
  * - ``NetworkInterface.MacIdentifier``
    - ``0``
    - Use the MAC address of the interface as DHCP client identifier.

      .. _enumitem_NetworkInterface_DhcpUniqueIdentifier:
  * - ``NetworkInterface.DhcpUniqueIdentifier``
    - ``1``
    - Use an RFC4361-compliant client ID (based on the MAC address) as DUID.


.. _enum_NetworkInterface_Error:

.. index::
   single: Error

Error
+++++

This enumeration describes all errors which can occur in NetworkInterface objects. The most recently occurred error is stored in the :ref:`error <property_NetworkInterface_error>` property.

.. index::
   single: NetworkInterface.NoError
.. index::
   single: NetworkInterface.InvalidIndex
.. index::
   single: NetworkInterface.InvalidConfigurationError
.. index::
   single: NetworkInterface.ConfigurationUpdateError
.. index::
   single: NetworkInterface.ConfigurationApplyError
.. index::
   single: NetworkInterface.SystemError
.. index::
   single: NetworkInterface.DeviceUnlockError
.. index::
   single: NetworkInterface.InvalidCountryCode
.. index::
   single: NetworkInterface.OperationNotSupportedError
.. index::
   single: NetworkInterface.DeviceNotReadyError
.. index::
   single: NetworkInterface.InvalidAddressError
.. index::
   single: NetworkInterface.EmptyMessageError
.. index::
   single: NetworkInterface.MessageCreateError
.. index::
   single: NetworkInterface.MessageSendError
.. index::
   single: NetworkInterface.MessageDeleteError
.. list-table::
  :widths: auto
  :header-rows: 1

  * - Name
    - Value
    - Description

      .. _enumitem_NetworkInterface_NoError:
  * - ``NetworkInterface.NoError``
    - ``0``
    - No error occurred or was detected.

      .. _enumitem_NetworkInterface_InvalidIndex:
  * - ``NetworkInterface.InvalidIndex``
    - ``1``
    - Invalid interface index.

      .. _enumitem_NetworkInterface_InvalidConfigurationError:
  * - ``NetworkInterface.InvalidConfigurationError``
    - ``2``
    - Invalid or empty configuration.

      .. _enumitem_NetworkInterface_ConfigurationUpdateError:
  * - ``NetworkInterface.ConfigurationUpdateError``
    - ``3``
    - Can't update configuration - likely configuration files could not be opened for writing.

      .. _enumitem_NetworkInterface_ConfigurationApplyError:
  * - ``NetworkInterface.ConfigurationApplyError``
    - ``4``
    - Can't apply configuration likely due to system service errors.

      .. _enumitem_NetworkInterface_SystemError:
  * - ``NetworkInterface.SystemError``
    - ``5``
    - System error.

      .. _enumitem_NetworkInterface_DeviceUnlockError:
  * - ``NetworkInterface.DeviceUnlockError``
    - ``6``
    - Device could not be unlocked, e.g. due to missing or invalid PIN.

      .. _enumitem_NetworkInterface_InvalidCountryCode:
  * - ``NetworkInterface.InvalidCountryCode``
    - ``7``
    - Specified country code is invalid or could not be set.

      .. _enumitem_NetworkInterface_OperationNotSupportedError:
  * - ``NetworkInterface.OperationNotSupportedError``
    - ``8``
    - The requested operation is not supported by the the interface.

      .. _enumitem_NetworkInterface_DeviceNotReadyError:
  * - ``NetworkInterface.DeviceNotReadyError``
    - ``9``
    - The device for the network interface is not available or not ready yet.

      .. _enumitem_NetworkInterface_InvalidAddressError:
  * - ``NetworkInterface.InvalidAddressError``
    - ``10``
    - The address (e.g. SMS recipient number) is empty.

      .. _enumitem_NetworkInterface_EmptyMessageError:
  * - ``NetworkInterface.EmptyMessageError``
    - ``11``
    - The message (e.g. SMS text) is empty.

      .. _enumitem_NetworkInterface_MessageCreateError:
  * - ``NetworkInterface.MessageCreateError``
    - ``12``
    - The message could not be created for sending.

      .. _enumitem_NetworkInterface_MessageSendError:
  * - ``NetworkInterface.MessageSendError``
    - ``13``
    - The message could not be sent, likely due to a network error or an invalid address.

      .. _enumitem_NetworkInterface_MessageDeleteError:
  * - ``NetworkInterface.MessageDeleteError``
    - ``14``
    - The message could not be deleted.


.. _enum_NetworkInterface_OperationalState:

.. index::
   single: OperationalState

OperationalState
++++++++++++++++

This enumeration describes all operational states a network interface can enter.

.. index::
   single: NetworkInterface.NoOperation
.. index::
   single: NetworkInterface.Off
.. index::
   single: NetworkInterface.NoCarrier
.. index::
   single: NetworkInterface.Dormant
.. index::
   single: NetworkInterface.Carrier
.. index::
   single: NetworkInterface.Degraded
.. index::
   single: NetworkInterface.Routable
.. list-table::
  :widths: auto
  :header-rows: 1

  * - Name
    - Value
    - Description

      .. _enumitem_NetworkInterface_NoOperation:
  * - ``NetworkInterface.NoOperation``
    - ``0``
    - The device is not operated at all.

      .. _enumitem_NetworkInterface_Off:
  * - ``NetworkInterface.Off``
    - ``1``
    - The device is powered down.

      .. _enumitem_NetworkInterface_NoCarrier:
  * - ``NetworkInterface.NoCarrier``
    - ``2``
    - The device is powered up, but it does not yet have a carrier.

      .. _enumitem_NetworkInterface_Dormant:
  * - ``NetworkInterface.Dormant``
    - ``3``
    - The device has a carrier, but is not yet ready for normal traffic.

      .. _enumitem_NetworkInterface_Carrier:
  * - ``NetworkInterface.Carrier``
    - ``4``
    - The link has a carrier.

      .. _enumitem_NetworkInterface_Degraded:
  * - ``NetworkInterface.Degraded``
    - ``5``
    - The link has carrier and addresses valid on the local link configured.

      .. _enumitem_NetworkInterface_Routable:
  * - ``NetworkInterface.Routable``
    - ``6``
    - The link has carrier and routable address configured.


.. _enum_NetworkInterface_SetupState:

.. index::
   single: SetupState

SetupState
++++++++++

This enumeration describes all setup states a network interface can enter.

.. index::
   single: NetworkInterface.NoSetup
.. index::
   single: NetworkInterface.Pending
.. index::
   single: NetworkInterface.Failed
.. index::
   single: NetworkInterface.Configuring
.. index::
   single: NetworkInterface.Configured
.. index::
   single: NetworkInterface.Unmanaged
.. index::
   single: NetworkInterface.Linger
.. list-table::
  :widths: auto
  :header-rows: 1

  * - Name
    - Value
    - Description

      .. _enumitem_NetworkInterface_NoSetup:
  * - ``NetworkInterface.NoSetup``
    - ``0``
    - The link is not set up.

      .. _enumitem_NetworkInterface_Pending:
  * - ``NetworkInterface.Pending``
    - ``1``
    - udev is still processing the link, we don't yet know if we will manage it.

      .. _enumitem_NetworkInterface_Failed:
  * - ``NetworkInterface.Failed``
    - ``2``
    - networkd failed to manage the link.

      .. _enumitem_NetworkInterface_Configuring:
  * - ``NetworkInterface.Configuring``
    - ``3``
    - System is in the process of retrieving configuration or configuring the link.

      .. _enumitem_NetworkInterface_Configured:
  * - ``NetworkInterface.Configured``
    - ``4``
    - The link has been configured successfully.

      .. _enumitem_NetworkInterface_Unmanaged:
  * - ``NetworkInterface.Unmanaged``
    - ``5``
    - The link is not managed by networkd.

      .. _enumitem_NetworkInterface_Linger:
  * - ``NetworkInterface.Linger``
    - ``6``
    - The link is gone, but has not yet been dropped by networkd.
