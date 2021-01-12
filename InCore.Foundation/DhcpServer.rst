
.. _object_DhcpServer:


:index:`DhcpServer`
-------------------

Description
***********

The DhcpServer object holds properties required for a basic DHCP server functionality on a :ref:`WiredNetworkInterface <object_WiredNetworkInterface>`. For proper function the underlying network interface has to be configured with a static IP address.

:**› Inherits**: :ref:`Object <object_Object>`

Overview
********

Properties
++++++++++

.. hlist::
  :columns: 1

  * :ref:`poolOffset <property_DhcpServer_poolOffset>`
  * :ref:`poolSize <property_DhcpServer_poolSize>`
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


.. _property_DhcpServer_poolOffset:

.. _signal_DhcpServer_poolOffsetChanged:

.. index::
   single: poolOffset

poolOffset
++++++++++

This property holds a number specifying the first IP address to assign to DHCP clients, i.e. ``10`` if IP addresses should start e.g. from ``192.168.5.10``.

:**› Type**: SignedInteger
:**› Default**: ``0``
:**› Signal**: poolOffsetChanged()
:**› Attributes**: Writable


.. _property_DhcpServer_poolSize:

.. _signal_DhcpServer_poolSizeChanged:

.. index::
   single: poolSize

poolSize
++++++++

This property holds a number specifying how many IP addresses to assign to DHCP clients starting from :ref:`poolOffset <property_DhcpServer_poolOffset>`.

:**› Type**: SignedInteger
:**› Default**: ``0``
:**› Signal**: poolSizeChanged()
:**› Attributes**: Writable


.. _example_DhcpServer:


Example
*******

.. code-block:: qml

    import InCore.Foundation 2.0
    
    Application {
        NetworkConfiguration {
            // configure simple DHCP server on second ethernet interface
            WiredNetworkInterface {
                index: WiredNetworkInterface.Ethernet2
                mode: WiredNetworkInterface.ModeStatic
                address: "192.168.2.1/24"
                dhcpServer: DhcpServer {
                    // assign 192.168.2.100 and 192.168.2.101 to clients
                    poolOffset: 100
                    poolSize: 2
                }
            }
        }
    }
    