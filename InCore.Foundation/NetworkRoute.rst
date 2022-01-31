
.. _object_NetworkRoute:


:index:`NetworkRoute`
---------------------

Description
***********

The NetworkRoute object represents a route in TCP/IP networks and can be attached to :ref:`NetworkInterface <object_NetworkInterface>` objects.

This object was introduced in InCore 2.3.

:**› Inherits**: :ref:`Object <object_Object>`

Overview
********

Properties
++++++++++

.. hlist::
  :columns: 2

  * :ref:`destination <property_NetworkRoute_destination>`
  * :ref:`gateway <property_NetworkRoute_gateway>`
  * :ref:`metric <property_NetworkRoute_metric>`
  * :ref:`mtu <property_NetworkRoute_mtu>`
  * :ref:`protocol <property_NetworkRoute_protocol>`
  * :ref:`scope <property_NetworkRoute_scope>`
  * :ref:`source <property_NetworkRoute_source>`
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

  * :ref:`Protocol <enum_NetworkRoute_Protocol>`
  * :ref:`Scope <enum_NetworkRoute_Scope>`



Properties
**********


.. _property_NetworkRoute_destination:

.. _signal_NetworkRoute_destinationChanged:

.. index::
   single: destination

destination
+++++++++++

This property holds the destination host or network of the route. For networks, it has to be followed by a slash and the prefix length.

:**› Type**: String
:**› Signal**: destinationChanged()
:**› Attributes**: Writable


.. _property_NetworkRoute_gateway:

.. _signal_NetworkRoute_gatewayChanged:

.. index::
   single: gateway

gateway
+++++++

This property holds the gateway of the route.

:**› Type**: String
:**› Signal**: gatewayChanged()
:**› Attributes**: Writable


.. _property_NetworkRoute_metric:

.. _signal_NetworkRoute_metricChanged:

.. index::
   single: metric

metric
++++++

This property holds the metric of the route.

:**› Type**: SignedInteger
:**› Signal**: metricChanged()
:**› Attributes**: Writable


.. _property_NetworkRoute_mtu:

.. _signal_NetworkRoute_mtuChanged:

.. index::
   single: mtu

mtu
+++

This property holds the maximum transmission unit in bytes to set for the route.

:**› Type**: SignedInteger
:**› Signal**: mtuChanged()
:**› Attributes**: Writable


.. _property_NetworkRoute_protocol:

.. _signal_NetworkRoute_protocolChanged:

.. index::
   single: protocol

protocol
++++++++

This property holds the routing protocol identifier of the route.

:**› Type**: :ref:`Protocol <enum_NetworkRoute_Protocol>`
:**› Default**: :ref:`NetworkRoute.Static <enumitem_NetworkRoute_Static>`
:**› Signal**: protocolChanged()
:**› Attributes**: Writable


.. _property_NetworkRoute_scope:

.. _signal_NetworkRoute_scopeChanged:

.. index::
   single: scope

scope
+++++

This property holds the scope of the IPv4 route. It's not used for IPv6 routes.

:**› Type**: :ref:`Scope <enum_NetworkRoute_Scope>`
:**› Default**: :ref:`NetworkRoute.Global <enumitem_NetworkRoute_Global>`
:**› Signal**: scopeChanged()
:**› Attributes**: Writable


.. _property_NetworkRoute_source:

.. _signal_NetworkRoute_sourceChanged:

.. index::
   single: source

source
++++++

This property holds the optional source prefix of the route, possibly followed by a slash and the prefix length.

:**› Type**: String
:**› Signal**: sourceChanged()
:**› Attributes**: Writable

Enumerations
************


.. _enum_NetworkRoute_Protocol:

.. index::
   single: Protocol

Protocol
++++++++

This enumeration describes the supported routing protocol identifiers.

.. index::
   single: NetworkRoute.Kernel
.. index::
   single: NetworkRoute.Boot
.. index::
   single: NetworkRoute.Static
.. index::
   single: NetworkRoute.RA
.. index::
   single: NetworkRoute.Dhcp
.. list-table::
  :widths: auto
  :header-rows: 1

  * - Name
    - Value
    - Description

      .. _enumitem_NetworkRoute_Kernel:
  * - ``NetworkRoute.Kernel``
    - ``0``
    - The route was installed by the kernel during autoconfiguration.

      .. _enumitem_NetworkRoute_Boot:
  * - ``NetworkRoute.Boot``
    - ``1``
    - The route was installed during the bootup sequence.

      .. _enumitem_NetworkRoute_Static:
  * - ``NetworkRoute.Static``
    - ``2``
    - The route was installed manually to override dynamic routing.

      .. _enumitem_NetworkRoute_RA:
  * - ``NetworkRoute.RA``
    - ``3``
    - The route was installed by Router Discovery protocol.

      .. _enumitem_NetworkRoute_Dhcp:
  * - ``NetworkRoute.Dhcp``
    - ``4``
    - The route was installed by DHCP client.


.. _enum_NetworkRoute_Scope:

.. index::
   single: Scope

Scope
+++++

This enumeration describes the supported scopes for IPv4 routes.

.. index::
   single: NetworkRoute.Global
.. index::
   single: NetworkRoute.Site
.. index::
   single: NetworkRoute.Link
.. index::
   single: NetworkRoute.Host
.. index::
   single: NetworkRoute.Nowhere
.. list-table::
  :widths: auto
  :header-rows: 1

  * - Name
    - Value
    - Description

      .. _enumitem_NetworkRoute_Global:
  * - ``NetworkRoute.Global``
    - ``0``
    - The route can reach hosts more than one hop away.

      .. _enumitem_NetworkRoute_Site:
  * - ``NetworkRoute.Site``
    - ``1``
    - An interior route in the local autonomous system.

      .. _enumitem_NetworkRoute_Link:
  * - ``NetworkRoute.Link``
    - ``2``
    - The route can only reach hosts on the local network (one hop away).

      .. _enumitem_NetworkRoute_Host:
  * - ``NetworkRoute.Host``
    - ``3``
    - The route will not leave the local machine (used for internal addresses like 127.0.0.1).

      .. _enumitem_NetworkRoute_Nowhere:
  * - ``NetworkRoute.Nowhere``
    - ``4``
    - The destination doesn't exist.

