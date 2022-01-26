
.. _object_WirelessNetworkInterface:


:index:`WirelessNetworkInterface`
---------------------------------

Description
***********

The WirelessNetworkInterface object represents a wireless network interface attached to the device. It provides all required settings to act as a wireless network client (:ref:`ssid <property_WirelessNetworkInterface_ssid>`/:ref:`passphrase <property_WirelessNetworkInterface_passphrase>`). Additionally the provided configuration items can be used to make the settings available to generic property-based frontends.

:**› Inherits**: :ref:`NetworkInterface <object_NetworkInterface>`

Overview
********

Properties
++++++++++

.. hlist::
  :columns: 3

  * :ref:`availableNetworks <property_WirelessNetworkInterface_availableNetworks>`
  * :ref:`countryCode <property_WirelessNetworkInterface_countryCode>`
  * :ref:`countryCodeItem <property_WirelessNetworkInterface_countryCodeItem>`
  * :ref:`index <property_WirelessNetworkInterface_index>`
  * :ref:`indexItem <property_WirelessNetworkInterface_indexItem>`
  * :ref:`passphrase <property_WirelessNetworkInterface_passphrase>`
  * :ref:`passphraseItem <property_WirelessNetworkInterface_passphraseItem>`
  * :ref:`ssid <property_WirelessNetworkInterface_ssid>`
  * :ref:`ssidItem <property_WirelessNetworkInterface_ssidItem>`
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

  * :ref:`scanAvailableNetworks() <method_WirelessNetworkInterface_scanAvailableNetworks>`
  * :ref:`Object.deserializeProperties() <method_Object_deserializeProperties>`
  * :ref:`Object.fromJson() <method_Object_fromJson>`
  * :ref:`Object.serializeProperties() <method_Object_serializeProperties>`
  * :ref:`Object.toJson() <method_Object_toJson>`

Signals
+++++++

.. hlist::
  :columns: 1

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

  * :ref:`Index <enum_WirelessNetworkInterface_Index>`
  * :ref:`NetworkInterface.DhcpClientIdentifier <enum_NetworkInterface_DhcpClientIdentifier>`
  * :ref:`NetworkInterface.Error <enum_NetworkInterface_Error>`
  * :ref:`NetworkInterface.OperationalState <enum_NetworkInterface_OperationalState>`
  * :ref:`NetworkInterface.SetupState <enum_NetworkInterface_SetupState>`



Properties
**********


.. _property_WirelessNetworkInterface_availableNetworks:

.. _signal_WirelessNetworkInterface_availableNetworksChanged:

.. index::
   single: availableNetworks

availableNetworks
+++++++++++++++++

This property holds a list with information about all available wireless networks found during the last scan. Every list entry contains several properties including ``ssid``, ``signal``, ``mode``, ``wpa`, ``frequency`` and ``privacy``. Per default this list is updated every 30 s. It's also possible to manually trigger a network scan by calling :ref:`scanAvailableNetworks() <method_WirelessNetworkInterface_scanAvailableNetworks>`.

This property was introduced in InCore 2.5.

:**› Type**: List
:**› Signal**: availableNetworksChanged()
:**› Attributes**: Writable


.. _property_WirelessNetworkInterface_countryCode:

.. _signal_WirelessNetworkInterface_countryCodeChanged:

.. index::
   single: countryCode

countryCode
+++++++++++

This property holds a country code used to set the wireless regulatory domain. This controls which channels, bandwidths and transmission powers are used to comply with the respective national laws. Per default the `world` domain with limited channels and transmission power is used.

See `ISO 3166-1 alpha-2 <https://en.wikipedia.org/wiki/ISO_3166-1_alpha-2>`_ for details and a code list table.

:**› Type**: String
:**› Signal**: countryCodeChanged()
:**› Attributes**: Writable


.. _property_WirelessNetworkInterface_countryCodeItem:

.. index::
   single: countryCodeItem

countryCodeItem
+++++++++++++++

This property holds an internal :ref:`ConfigurationItem <object_ConfigurationItem>` instance for the :ref:`countryCode <property_WirelessNetworkInterface_countryCode>` property.

:**› Type**: :ref:`ConfigurationItem <object_ConfigurationItem>`
:**› Attributes**: Readonly


.. _property_WirelessNetworkInterface_index:

.. _signal_WirelessNetworkInterface_indexChanged:

.. index::
   single: index

index
+++++

This property holds the index of the wireless network interface which to represent and configure through this object instance.

:**› Type**: :ref:`Index <enum_WirelessNetworkInterface_Index>`
:**› Default**: :ref:`WirelessNetworkInterface.WirelessNone <enumitem_WirelessNetworkInterface_WirelessNone>`
:**› Signal**: indexChanged()
:**› Attributes**: Writable


.. _property_WirelessNetworkInterface_indexItem:

.. index::
   single: indexItem

indexItem
+++++++++

This property holds an internal :ref:`ConfigurationItem <object_ConfigurationItem>` instance for the :ref:`index <property_WirelessNetworkInterface_index>` property.

:**› Type**: :ref:`ConfigurationItem <object_ConfigurationItem>`
:**› Attributes**: Readonly


.. _property_WirelessNetworkInterface_passphrase:

.. _signal_WirelessNetworkInterface_passphraseChanged:

.. index::
   single: passphrase

passphrase
++++++++++

This property holds the passphrase (pre-shared key) to use for connecting to the wireless network. The minimum length for WPA/WPA2 passphrases is 8 characters. When setting an invalid passphrase the :ref:`NetworkInterface.InvalidConfigurationError <enumitem_NetworkInterface_InvalidConfigurationError>` error will be raised.

:**› Type**: String
:**› Signal**: passphraseChanged()
:**› Attributes**: Writable


.. _property_WirelessNetworkInterface_passphraseItem:

.. index::
   single: passphraseItem

passphraseItem
++++++++++++++

This property holds an internal :ref:`ConfigurationItem <object_ConfigurationItem>` instance for the :ref:`passphrase <property_WirelessNetworkInterface_passphrase>` property.

:**› Type**: :ref:`ConfigurationItem <object_ConfigurationItem>`
:**› Attributes**: Readonly


.. _property_WirelessNetworkInterface_ssid:

.. _signal_WirelessNetworkInterface_ssidChanged:

.. index::
   single: ssid

ssid
++++

This property holds the SSID, i.e. the wireless network name, which to connect to. The maximum length is 31 characters. When setting an invalid SSID the :ref:`NetworkInterface.InvalidConfigurationError <enumitem_NetworkInterface_InvalidConfigurationError>` error will be raised.

:**› Type**: String
:**› Signal**: ssidChanged()
:**› Attributes**: Writable


.. _property_WirelessNetworkInterface_ssidItem:

.. index::
   single: ssidItem

ssidItem
++++++++

This property holds an internal :ref:`ConfigurationItem <object_ConfigurationItem>` instance for the :ref:`ssid <property_WirelessNetworkInterface_ssid>` property.

:**› Type**: :ref:`ConfigurationItem <object_ConfigurationItem>`
:**› Attributes**: Readonly

Methods
*******


.. _method_WirelessNetworkInterface_scanAvailableNetworks:

.. index::
   single: scanAvailableNetworks

scanAvailableNetworks()
+++++++++++++++++++++++

This method tells the wireless network interface to scan all available networks. When finished, the :ref:`availableNetworks <property_WirelessNetworkInterface_availableNetworks>` property is updated.

This method was introduced in InCore 2.5.


Enumerations
************


.. _enum_WirelessNetworkInterface_Index:

.. index::
   single: Index

Index
+++++

This enumeration describes indexes for all supported wireless network interfaces.

.. index::
   single: WirelessNetworkInterface.WirelessNone
.. index::
   single: WirelessNetworkInterface.Wireless1
.. index::
   single: WirelessNetworkInterface.Wireless2
.. list-table::
  :widths: auto
  :header-rows: 1

  * - Name
    - Value
    - Description

      .. _enumitem_WirelessNetworkInterface_WirelessNone:
  * - ``WirelessNetworkInterface.WirelessNone``
    - ``0``
    - The object does not represent a valid wireless network interface.

      .. _enumitem_WirelessNetworkInterface_Wireless1:
  * - ``WirelessNetworkInterface.Wireless1``
    - ``1``
    - The object represents the first wireless network interface.

      .. _enumitem_WirelessNetworkInterface_Wireless2:
  * - ``WirelessNetworkInterface.Wireless2``
    - ``2``
    - The object represents the second wireless network interface.


.. _example_WirelessNetworkInterface:


Example
*******

.. code-block:: qml

    import InCore.Foundation 2.5
    
    Application {
        NetworkConfiguration {
            WirelessNetworkInterface {
                index: WirelessNetworkInterface.Wireless1
                ssid: "inhub"
                passphrase: "MyS3cr3tP4ssw0rd"
                countryCode: "DE"
                onAvailableNetworksChanged: console.log(JSON.stringify(availableNetworks))
            }
        }
    }
    