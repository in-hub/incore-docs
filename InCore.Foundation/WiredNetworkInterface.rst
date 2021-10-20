
.. _object_WiredNetworkInterface:


:index:`WiredNetworkInterface`
------------------------------

Description
***********

The WiredNetworkInterface object represents one of the wired (ethernet) network interfaces of the device. The :ref:`mode <property_WiredNetworkInterface_mode>` property allows defining the network configuration method (static/DHCP). When working with static addresses many additional properties allow detailled configuration and customization. Additionally the provided configuration items can be used to make the settings available to generic property-based frontends.

:**› Inherits**: :ref:`NetworkInterface <object_NetworkInterface>`

Overview
********

Properties
++++++++++

.. hlist::
  :columns: 3

  * :ref:`address <property_WiredNetworkInterface_address>`
  * :ref:`addressItem <property_WiredNetworkInterface_addressItem>`
  * :ref:`dhcpServer <property_WiredNetworkInterface_dhcpServer>`
  * :ref:`dns <property_WiredNetworkInterface_dns>`
  * :ref:`dnsItem <property_WiredNetworkInterface_dnsItem>`
  * :ref:`domains <property_WiredNetworkInterface_domains>`
  * :ref:`domainsItem <property_WiredNetworkInterface_domainsItem>`
  * :ref:`gateway <property_WiredNetworkInterface_gateway>`
  * :ref:`gatewayItem <property_WiredNetworkInterface_gatewayItem>`
  * :ref:`index <property_WiredNetworkInterface_index>`
  * :ref:`indexItem <property_WiredNetworkInterface_indexItem>`
  * :ref:`ipv6AutoConfig <property_WiredNetworkInterface_ipv6AutoConfig>`
  * :ref:`ipv6AutoConfigItem <property_WiredNetworkInterface_ipv6AutoConfigItem>`
  * :ref:`linkLocalAddressing <property_WiredNetworkInterface_linkLocalAddressing>`
  * :ref:`linkLocalAddressingItem <property_WiredNetworkInterface_linkLocalAddressingItem>`
  * :ref:`mode <property_WiredNetworkInterface_mode>`
  * :ref:`modeItem <property_WiredNetworkInterface_modeItem>`
  * :ref:`multicastDNS <property_WiredNetworkInterface_multicastDNS>`
  * :ref:`multicastDNSItem <property_WiredNetworkInterface_multicastDNSItem>`
  * :ref:`ntp <property_WiredNetworkInterface_ntp>`
  * :ref:`ntpItem <property_WiredNetworkInterface_ntpItem>`
  * :ref:`vlan <property_WiredNetworkInterface_vlan>`
  * :ref:`vlanItem <property_WiredNetworkInterface_vlanItem>`
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

  * :ref:`Object.deserializeProperties() <method_Object_deserializeProperties>`
  * :ref:`Object.fromJson() <method_Object_fromJson>`
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

  * :ref:`Index <enum_WiredNetworkInterface_Index>`
  * :ref:`Mode <enum_WiredNetworkInterface_Mode>`
  * :ref:`NetworkInterface.DhcpClientIdentifier <enum_NetworkInterface_DhcpClientIdentifier>`
  * :ref:`NetworkInterface.Error <enum_NetworkInterface_Error>`
  * :ref:`NetworkInterface.OperationalState <enum_NetworkInterface_OperationalState>`
  * :ref:`NetworkInterface.SetupState <enum_NetworkInterface_SetupState>`



Properties
**********


.. _property_WiredNetworkInterface_address:

.. _signal_WiredNetworkInterface_addressChanged:

.. index::
   single: address

address
+++++++

This property holds a static IPv4 or IPv6 address for this interface and its prefix length, separated by a ``/`` character, e.g. ``192.168.2.19/24``. Multiple addresses (including prefix) can be specified and separated by space.

:**› Type**: String
:**› Signal**: addressChanged()
:**› Attributes**: Writable


.. _property_WiredNetworkInterface_addressItem:

.. index::
   single: addressItem

addressItem
+++++++++++

This property holds an internal :ref:`ConfigurationItem <object_ConfigurationItem>` instance for the :ref:`address <property_WiredNetworkInterface_address>` property.

:**› Type**: :ref:`ConfigurationItem <object_ConfigurationItem>`
:**› Attributes**: Readonly


.. _property_WiredNetworkInterface_dhcpServer:

.. _signal_WiredNetworkInterface_dhcpServerChanged:

.. index::
   single: dhcpServer

dhcpServer
++++++++++

This property holds an optional :ref:`DhcpServer <object_DhcpServer>` object which defines settings for a DHCP server started on this interface. This may be required when TCP/IP-based sensor and I/O modules are connected to this interface and obtain their configuration through DHCP.

:**› Type**: :ref:`DhcpServer <object_DhcpServer>`
:**› Signal**: dhcpServerChanged()
:**› Attributes**: Writable


.. _property_WiredNetworkInterface_dns:

.. _signal_WiredNetworkInterface_dnsChanged:

.. index::
   single: dns

dns
+++

This property holds a list of DNS servers which should be used for resolving hostnames to IP addresses. Multiple server addresses can be specified and separated by space. Each server address has to be a valid IPv4 or IPv6 address.

:**› Type**: String
:**› Signal**: dnsChanged()
:**› Attributes**: Writable


.. _property_WiredNetworkInterface_dnsItem:

.. index::
   single: dnsItem

dnsItem
+++++++

This property holds an internal :ref:`ConfigurationItem <object_ConfigurationItem>` instance for the :ref:`dns <property_WiredNetworkInterface_dns>` property.

:**› Type**: :ref:`ConfigurationItem <object_ConfigurationItem>`
:**› Attributes**: Readonly


.. _property_WiredNetworkInterface_domains:

.. _signal_WiredNetworkInterface_domainsChanged:

.. index::
   single: domains

domains
+++++++

This property holds a list of DNS search domains which should be resolved using the DNS servers on this interface. See the `Domains description in the systemd-networkd manpage <https://www.freedesktop.org/software/systemd/man/systemd.network.html#Domains=Domains>`_ for details on syntax and semantics.

:**› Type**: String
:**› Signal**: domainsChanged()
:**› Attributes**: Writable


.. _property_WiredNetworkInterface_domainsItem:

.. index::
   single: domainsItem

domainsItem
+++++++++++

This property holds an internal :ref:`ConfigurationItem <object_ConfigurationItem>` instance for the :ref:`domains <property_WiredNetworkInterface_domains>` property.

:**› Type**: :ref:`ConfigurationItem <object_ConfigurationItem>`
:**› Attributes**: Readonly


.. _property_WiredNetworkInterface_gateway:

.. _signal_WiredNetworkInterface_gatewayChanged:

.. index::
   single: gateway

gateway
+++++++

This property holds the gateway address for this interface. This is required to communicate with hosts outside of the configured subnet. Multiple gateways can be specified and separated by space. Each gateway address has to be a valid IPv4 or IPv6 address.

:**› Type**: String
:**› Signal**: gatewayChanged()
:**› Attributes**: Writable


.. _property_WiredNetworkInterface_gatewayItem:

.. index::
   single: gatewayItem

gatewayItem
+++++++++++

This property holds an internal :ref:`ConfigurationItem <object_ConfigurationItem>` instance for the :ref:`gateway <property_WiredNetworkInterface_gateway>` property.

:**› Type**: :ref:`ConfigurationItem <object_ConfigurationItem>`
:**› Attributes**: Readonly


.. _property_WiredNetworkInterface_index:

.. _signal_WiredNetworkInterface_indexChanged:

.. index::
   single: index

index
+++++

This property holds which physical network interface to configure through a certain instance.

:**› Type**: :ref:`Index <enum_WiredNetworkInterface_Index>`
:**› Default**: :ref:`WiredNetworkInterface.EthernetNone <enumitem_WiredNetworkInterface_EthernetNone>`
:**› Signal**: indexChanged()
:**› Attributes**: Writable


.. _property_WiredNetworkInterface_indexItem:

.. index::
   single: indexItem

indexItem
+++++++++

This property holds an internal :ref:`ConfigurationItem <object_ConfigurationItem>` instance for the :ref:`index <property_WiredNetworkInterface_index>` property.

:**› Type**: :ref:`ConfigurationItem <object_ConfigurationItem>`
:**› Attributes**: Readonly


.. _property_WiredNetworkInterface_ipv6AutoConfig:

.. _signal_WiredNetworkInterface_ipv6AutoConfigChanged:

.. index::
   single: ipv6AutoConfig

ipv6AutoConfig
++++++++++++++

This property holds whether to enable IPv6 auto configuration support. When enabled IPv6 Router Advertisements are received and processed and the DHCPv6 client is enabled on this interface. See the `IPv6AcceptRA description in the systemd-networkd manpage <https://www.freedesktop.org/software/systemd/man/systemd.network.html#IPv6AcceptRA=>`_ for details.

:**› Type**: Boolean
:**› Default**: ``true``
:**› Signal**: ipv6AutoConfigChanged()
:**› Attributes**: Writable


.. _property_WiredNetworkInterface_ipv6AutoConfigItem:

.. index::
   single: ipv6AutoConfigItem

ipv6AutoConfigItem
++++++++++++++++++

This property holds an internal :ref:`ConfigurationItem <object_ConfigurationItem>` instance for the :ref:`ipv6AutoConfig <property_WiredNetworkInterface_ipv6AutoConfig>` property.

:**› Type**: :ref:`ConfigurationItem <object_ConfigurationItem>`
:**› Attributes**: Readonly


.. _property_WiredNetworkInterface_linkLocalAddressing:

.. _signal_WiredNetworkInterface_linkLocalAddressingChanged:

.. index::
   single: linkLocalAddressing

linkLocalAddressing
+++++++++++++++++++

This property holds whether to enable link-local address autoconfiguration. See `Link-local address <https://en.wikipedia.org/wiki/Link-local_address>`_ for details.

:**› Type**: Boolean
:**› Default**: ``false``
:**› Signal**: linkLocalAddressingChanged()
:**› Attributes**: Writable


.. _property_WiredNetworkInterface_linkLocalAddressingItem:

.. index::
   single: linkLocalAddressingItem

linkLocalAddressingItem
+++++++++++++++++++++++

This property holds an internal :ref:`ConfigurationItem <object_ConfigurationItem>` instance for the :ref:`linkLocalAddressing <property_WiredNetworkInterface_linkLocalAddressing>` property.

:**› Type**: :ref:`ConfigurationItem <object_ConfigurationItem>`
:**› Attributes**: Readonly


.. _property_WiredNetworkInterface_mode:

.. _signal_WiredNetworkInterface_modeChanged:

.. index::
   single: mode

mode
++++

This property holds the configuration mode for this network interface. When set to :ref:`WiredNetworkInterface.ModeStatic <enumitem_WiredNetworkInterface_ModeStatic>` at least the :ref:`address <property_WiredNetworkInterface_address>` property has to be specified as well. Depending on the desired purpose of the interface, the :ref:`dns <property_WiredNetworkInterface_dns>` and :ref:`gateway <property_WiredNetworkInterface_gateway>` properties should be configured as well.

:**› Type**: :ref:`Mode <enum_WiredNetworkInterface_Mode>`
:**› Default**: :ref:`WiredNetworkInterface.ModeNone <enumitem_WiredNetworkInterface_ModeNone>`
:**› Signal**: modeChanged()
:**› Attributes**: Writable


.. _property_WiredNetworkInterface_modeItem:

.. index::
   single: modeItem

modeItem
++++++++

This property holds an internal :ref:`ConfigurationItem <object_ConfigurationItem>` instance for the :ref:`mode <property_WiredNetworkInterface_mode>` property.

:**› Type**: :ref:`ConfigurationItem <object_ConfigurationItem>`
:**› Attributes**: Readonly


.. _property_WiredNetworkInterface_multicastDNS:

.. _signal_WiredNetworkInterface_multicastDNSChanged:

.. index::
   single: multicastDNS

multicastDNS
++++++++++++

This property holds whether to enable multicast DNS support on this interface. When enabled, the device can be accessed via :ref:`System.hostname <property_System_hostname>`.local in the network. See `Multicast DNS <https://en.wikipedia.org/wiki/Multicast_DNS>`_ and `RFC 6762 <https://tools.ietf.org/html/rfc6762>`_ for details.

:**› Type**: Boolean
:**› Default**: ``false``
:**› Signal**: multicastDNSChanged()
:**› Attributes**: Writable


.. _property_WiredNetworkInterface_multicastDNSItem:

.. index::
   single: multicastDNSItem

multicastDNSItem
++++++++++++++++

This property holds an internal :ref:`ConfigurationItem <object_ConfigurationItem>` instance for the :ref:`multicastDNS <property_WiredNetworkInterface_multicastDNS>` property.

:**› Type**: :ref:`ConfigurationItem <object_ConfigurationItem>`
:**› Attributes**: Readonly


.. _property_WiredNetworkInterface_ntp:

.. _signal_WiredNetworkInterface_ntpChanged:

.. index::
   single: ntp

ntp
+++

This property holds a list of NTP servers which should be used for synchronizing the system clock of the device. Multiple server addresses can be specified (IPv4/IPv6 addresses and resolvable hostnames allowed) and separated by space.

:**› Type**: String
:**› Signal**: ntpChanged()
:**› Attributes**: Writable


.. _property_WiredNetworkInterface_ntpItem:

.. index::
   single: ntpItem

ntpItem
+++++++

This property holds an internal :ref:`ConfigurationItem <object_ConfigurationItem>` instance for the :ref:`ntp <property_WiredNetworkInterface_ntp>` property.

:**› Type**: :ref:`ConfigurationItem <object_ConfigurationItem>`
:**› Attributes**: Readonly


.. _property_WiredNetworkInterface_vlan:

.. _signal_WiredNetworkInterface_vlanChanged:

.. index::
   single: vlan

vlan
++++

This property holds the name of a VLAN to create on this interface.

:**› Type**: String
:**› Signal**: vlanChanged()
:**› Attributes**: Writable


.. _property_WiredNetworkInterface_vlanItem:

.. index::
   single: vlanItem

vlanItem
++++++++

This property holds an internal :ref:`ConfigurationItem <object_ConfigurationItem>` instance for the :ref:`vlan <property_WiredNetworkInterface_vlan>` property.

:**› Type**: :ref:`ConfigurationItem <object_ConfigurationItem>`
:**› Attributes**: Readonly

Enumerations
************


.. _enum_WiredNetworkInterface_Index:

.. index::
   single: Index

Index
+++++

This enumeration describes indexes for all supported wireless network interfaces.

.. index::
   single: WiredNetworkInterface.EthernetNone
.. index::
   single: WiredNetworkInterface.Ethernet1
.. index::
   single: WiredNetworkInterface.Ethernet2
.. list-table::
  :widths: auto
  :header-rows: 1

  * - Name
    - Value
    - Description

      .. _enumitem_WiredNetworkInterface_EthernetNone:
  * - ``WiredNetworkInterface.EthernetNone``
    - ``0``
    - The object does not represent a valid wired network interface.

      .. _enumitem_WiredNetworkInterface_Ethernet1:
  * - ``WiredNetworkInterface.Ethernet1``
    - ``1``
    - The object represents the first wired network interface.

      .. _enumitem_WiredNetworkInterface_Ethernet2:
  * - ``WiredNetworkInterface.Ethernet2``
    - ``2``
    - The object represents the second wired network interface.


.. _enum_WiredNetworkInterface_Mode:

.. index::
   single: Mode

Mode
++++

This enumeration describes all supported configuration modes for a wired network interface.

.. index::
   single: WiredNetworkInterface.ModeNone
.. index::
   single: WiredNetworkInterface.ModeStatic
.. index::
   single: WiredNetworkInterface.ModeDHCP
.. list-table::
  :widths: auto
  :header-rows: 1

  * - Name
    - Value
    - Description

      .. _enumitem_WiredNetworkInterface_ModeNone:
  * - ``WiredNetworkInterface.ModeNone``
    - ``0``
    - Do not configure, i.e. disable the network interface.

      .. _enumitem_WiredNetworkInterface_ModeStatic:
  * - ``WiredNetworkInterface.ModeStatic``
    - ``1``
    - Configure one or multiple static addresses and servers.

      .. _enumitem_WiredNetworkInterface_ModeDHCP:
  * - ``WiredNetworkInterface.ModeDHCP``
    - ``2``
    - Configure the interface automatically via DHCP and IPv6 Router Advertisements.


.. _example_WiredNetworkInterface:


Example
*******

.. code-block:: qml

    import InCore.Foundation 2.5
    
    Application {
        NetworkConfiguration {
            // autoconfigure ethernet interface via DHCP
            WiredNetworkInterface {
                index: WiredNetworkInterface.Ethernet1
                mode: WiredNetworkInterface.ModeDHCP
            }
    
            // configure ethernet interface with static settings
            WiredNetworkInterface {
                index: WiredNetworkInterface.Ethernet2
                mode: WiredNetworkInterface.ModeStatic
                address: "192.168.2.19/24"
                gateway: "192.168.2.254"
                dns: "192.168.2.1 192.168.2.2"
                domains: "example.org"
                ntp: "ntp1.example.org ntp2.example.org"
                multicastDNS: true
                routes: [
                    NetworkRoute {
                        destination: "192.168.3.0/24"
                        gateway: "192.168.2.253"
                    }
                ]
            }
        }
    }
    