
.. _object_JsonRpcServer:


:index:`JsonRpcServer`
----------------------

Description
***********

The JsonRpcServer object provides a `JSON-RPC 2.0 compliant <https://www.jsonrpc.org/specification>`_ server. Basic network parameters can be customized through the :ref:`port <property_JsonRpcServer_port>` and :ref:`localHost <property_JsonRpcServer_localHost>` properties. In order to expose functions and properties via JSON-RPC a :ref:`JsonRpcService <object_JsonRpcService>` has to be defined and assigned to the :ref:`service <property_JsonRpcServer_service>` property.

:**› Inherits**: :ref:`Object <object_Object>`

Overview
********

Properties
++++++++++

.. hlist::
  :columns: 1

  * :ref:`debugRpcMessages <property_JsonRpcServer_debugRpcMessages>`
  * :ref:`localHost <property_JsonRpcServer_localHost>`
  * :ref:`port <property_JsonRpcServer_port>`
  * :ref:`service <property_JsonRpcServer_service>`
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


.. _property_JsonRpcServer_service:

.. _signal_JsonRpcServer_serviceChanged:

.. index::
   single: service

service
+++++++

This property holds a reference to a :ref:`JsonRpcService <object_JsonRpcService>` object which exposes the desired functions and properties.

:**› Type**: :ref:`JsonRpcService <object_JsonRpcService>`
:**› Signal**: serviceChanged()
:**› Attributes**: Writable

Example
*******
See :ref:`JsonRpcService example <example_JsonRpcService>` on how to use JsonRpcServer.
