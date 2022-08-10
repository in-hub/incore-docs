
.. _object_JsonRpcServer:


:index:`JsonRpcServer`
----------------------

Description
***********

The JsonRpcServer object provides a `JSON-RPC 2.0 compliant <https://www.jsonrpc.org/specification>`_ server. Basic network parameters can be customized through the :ref:`port <property_JsonRpcServer_port>` and :ref:`localHost <property_JsonRpcServer_localHost>` properties. In order to expose functions and properties via JSON-RPC at least one :ref:`JsonRpcService <object_JsonRpcService>` has to be defined and assigned to the :ref:`services <property_JsonRpcServer_services>` property.

:**› Inherits**: :ref:`Object <object_Object>`

Overview
********

Properties
++++++++++

.. hlist::
  :columns: 1

  * :ref:`debugRpcMessages <property_JsonRpcServer_debugRpcMessages>`
  * :ref:`localHost <property_JsonRpcServer_localHost>`
  * :ref:`name <property_JsonRpcServer_name>`
  * :ref:`port <property_JsonRpcServer_port>`
  * :ref:`services <property_JsonRpcServer_services>`
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

  * :ref:`servicesDataChanged() <signal_JsonRpcServer_servicesDataChanged>`
  * :ref:`Object.completed() <signal_Object_completed>`



Properties
**********


.. _property_JsonRpcServer_debugRpcMessages:

.. _signal_JsonRpcServer_debugRpcMessagesChanged:

.. index::
   single: debugRpcMessages

debugRpcMessages
++++++++++++++++

This property holds whether to log received and sent RPC messages to the console for debugging purposes.

This property was introduced in InCore 2.2.

:**› Type**: Boolean
:**› Default**: ``false``
:**› Signal**: debugRpcMessagesChanged()
:**› Attributes**: Writable


.. _property_JsonRpcServer_localHost:

.. _signal_JsonRpcServer_localHostChanged:

.. index::
   single: localHost

localHost
+++++++++

This property holds whether the server should listen for incoming connections on the local loopback interface only. If set to ``true`` the server will not be reachable by other hosts on the network but internal clients such as docker containers (:ref:`DockerContainer <object_DockerContainer>`) only. Additionally the :ref:`WebServerService <object_WebServerService>` proxies requests to the default port ``5080`` to a local server. This means if :ref:`WebServerService <object_WebServerService>` is used and the JSON-RPC server should not be exposed on non-local network interfaces a :ref:`port <property_JsonRpcServer_port>` other than ``5080`` has to be used.

:**› Type**: Boolean
:**› Default**: ``true``
:**› Signal**: localHostChanged()
:**› Attributes**: Writable


.. _property_JsonRpcServer_name:

.. _signal_JsonRpcServer_nameChanged:

.. index::
   single: name

name
++++

This property holds the local socket name which the JSON-RPC server should listen at. If set, :ref:`port <property_JsonRpcServer_port>` is ignored and the server is listening on an UNIX domain socket instead of a TCP port.

This property was introduced in InCore 2.6.

:**› Type**: String
:**› Signal**: nameChanged()
:**› Attributes**: Writable


.. _property_JsonRpcServer_port:

.. _signal_JsonRpcServer_portChanged:

.. index::
   single: port

port
++++

This property holds the TCP port of the JSON-RPC server.

:**› Type**: SignedInteger
:**› Default**: ``5080``
:**› Signal**: portChanged()
:**› Attributes**: Writable


.. _property_JsonRpcServer_services:

.. _signal_JsonRpcServer_servicesChanged:

.. index::
   single: services

services
++++++++

This property holds a list of :ref:`JsonRpcService <object_JsonRpcService>` objects which exposes the desired functions and properties.

This property was introduced in InCore 2.5.

:**› Type**: :ref:`List <object_List>`\<:ref:`JsonRpcService <object_JsonRpcService>`>
:**› Signal**: servicesChanged()
:**› Attributes**: Readonly

Signals
*******


.. _signal_JsonRpcServer_servicesDataChanged:

.. index::
   single: servicesDataChanged

servicesDataChanged(SignedInteger index)
++++++++++++++++++++++++++++++++++++++++

This signal is emitted whenever the :ref:`List.dataChanged() <signal_List_dataChanged>` signal is emitted, i.e. the item at ``index`` in the :ref:`services <property_JsonRpcServer_services>` list itself emitted the dataChanged() signal.


Example
*******
See :ref:`JsonRpcService example <example_JsonRpcService>` on how to use JsonRpcServer.
