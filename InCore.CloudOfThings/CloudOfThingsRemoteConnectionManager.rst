
.. _object_CloudOfThingsRemoteConnectionManager:


:index:`CloudOfThingsRemoteConnectionManager`
---------------------------------------------

Description
***********

The CloudOfThingsRemoteConnectionManager object can be used to enable remote access from the Cloud of Things. A separate tab 'remote access' will show up in Cloud of Things and let you configure endpoints. See also :ref:`enabled <property_CloudOfThingsRemoteConnectionManager_enabled>`

This object was introduced in InCore 1.1.

:**› Inherits**: :ref:`Object <object_Object>`

Overview
********

Properties
++++++++++

.. hlist::
  :columns: 1

  * :ref:`allowedEndpoints <property_CloudOfThingsRemoteConnectionManager_allowedEndpoints>`
  * :ref:`enabled <property_CloudOfThingsRemoteConnectionManager_enabled>`
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

  * :ref:`Object.completed() <signal_Object_completed>`

Enumerations
++++++++++++

.. hlist::
  :columns: 1

  * :ref:`SupportedProtocols <enum_CloudOfThingsRemoteConnectionManager_SupportedProtocols>`



Properties
**********


.. _property_CloudOfThingsRemoteConnectionManager_allowedEndpoints:

.. index::
   single: allowedEndpoints

allowedEndpoints
++++++++++++++++

This property holds a list of allowed hostnames to the endpoints. Each request from the cloud to a endpoint will be tested against this list and aborted if the hostname is not included. Use ``*`` as the first item in the list to disable this behaviour.

This property was introduced in InCore 1.1.

:**› Type**: StringList
:**› Attributes**: Writable


.. _property_CloudOfThingsRemoteConnectionManager_enabled:

.. index::
   single: enabled

enabled
+++++++

This property holds whether remote connections are enabled. If set to ``true`` a tab 'remote access' will show up in Cloud of Things and let you configure endpoints. See also :ref:`allowedEndpoints <property_CloudOfThingsRemoteConnectionManager_allowedEndpoints>`.

This property was introduced in InCore 1.1.

:**› Type**: Boolean
:**› Default**: ``false``
:**› Attributes**: Writable

Enumerations
************


.. _enum_CloudOfThingsRemoteConnectionManager_SupportedProtocols:

.. index::
   single: SupportedProtocols

SupportedProtocols
++++++++++++++++++

This enumeration describes the supported remote access protocols.

This enumeration was introduced in InCore 1.1.

.. index::
   single: CloudOfThingsRemoteConnectionManager.VNC
.. index::
   single: CloudOfThingsRemoteConnectionManager.Telnet
.. index::
   single: CloudOfThingsRemoteConnectionManager.Ssh
.. list-table::
  :widths: auto
  :header-rows: 1

  * - Name
    - Value
    - Description

      .. _enumitem_CloudOfThingsRemoteConnectionManager_VNC:
  * - ``CloudOfThingsRemoteConnectionManager.VNC``
    - ``0``
    - Start a VNC connection.

      .. _enumitem_CloudOfThingsRemoteConnectionManager_Telnet:
  * - ``CloudOfThingsRemoteConnectionManager.Telnet``
    - ``1``
    - Connect to the Endpoint via Telnet.

      .. _enumitem_CloudOfThingsRemoteConnectionManager_Ssh:
  * - ``CloudOfThingsRemoteConnectionManager.Ssh``
    - ``2``
    - Start a ssh connection.

Example
*******
See :ref:`CloudOfThingsClient example <example_CloudOfThingsClient>` on how to use CloudOfThingsRemoteConnectionManager.
