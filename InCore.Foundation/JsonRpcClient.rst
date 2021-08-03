
.. _object_JsonRpcClient:


:index:`JsonRpcClient`
----------------------

Description
***********

The JsonRpcClient object provides a `JSON-RPC 2.0 compliant <https://www.jsonrpc.org/specification>`_ client which connects to the JSON-RPC server specified through the :ref:`hostname <property_JsonRpcClient_hostname>` property. Calls can be made through the :ref:`call() <method_JsonRpcClient_call>` method. Properties can be read and written using the :ref:`getProperty() <method_JsonRpcClient_getProperty>` and :ref:`setProperty() <method_JsonRpcClient_setProperty>` methods.

This object was introduced in InCore 2.2.

:**› Inherits**: :ref:`Object <object_Object>`

Overview
********

Properties
++++++++++

.. hlist::
  :columns: 1

  * :ref:`debugRpcMessages <property_JsonRpcClient_debugRpcMessages>`
  * :ref:`hostname <property_JsonRpcClient_hostname>`
  * :ref:`path <property_JsonRpcClient_path>`
  * :ref:`protocol <property_JsonRpcClient_protocol>`
  * :ref:`Object.objectId <property_Object_objectId>`
  * :ref:`Object.parent <property_Object_parent>`

Methods
+++++++

.. hlist::
  :columns: 1

  * :ref:`call() <method_JsonRpcClient_call>`
  * :ref:`getProperty() <method_JsonRpcClient_getProperty>`
  * :ref:`setProperty() <method_JsonRpcClient_setProperty>`
  * :ref:`Object.deserializeProperties() <method_Object_deserializeProperties>`
  * :ref:`Object.fromJson() <method_Object_fromJson>`
  * :ref:`Object.toJson() <method_Object_toJson>`

Signals
+++++++

.. hlist::
  :columns: 1

  * :ref:`errorCodeReceived() <signal_JsonRpcClient_errorCodeReceived>`
  * :ref:`errorDataReceived() <signal_JsonRpcClient_errorDataReceived>`
  * :ref:`errorMessageReceived() <signal_JsonRpcClient_errorMessageReceived>`
  * :ref:`Object.completed() <signal_Object_completed>`



Properties
**********


.. _property_JsonRpcClient_debugRpcMessages:

.. _signal_JsonRpcClient_debugRpcMessagesChanged:

.. index::
   single: debugRpcMessages

debugRpcMessages
++++++++++++++++

This property holds whether to log received and sent RPC messages to the console for debugging purposes.

:**› Type**: Boolean
:**› Default**: ``false``
:**› Signal**: debugRpcMessagesChanged()
:**› Attributes**: Writable


.. _property_JsonRpcClient_hostname:

.. _signal_JsonRpcClient_hostnameChanged:

.. index::
   single: hostname

hostname
++++++++

This property holds the host name or address of the JSON-RPC server.

:**› Type**: String
:**› Default**: ``localhost``
:**› Signal**: hostnameChanged()
:**› Attributes**: Writable


.. _property_JsonRpcClient_path:

.. _signal_JsonRpcClient_pathChanged:

.. index::
   single: path

path
++++

This property holds the URL path of the RPC endpoint.

:**› Type**: String
:**› Default**: ``/rpc``
:**› Signal**: pathChanged()
:**› Attributes**: Writable


.. _property_JsonRpcClient_protocol:

.. _signal_JsonRpcClient_protocolChanged:

.. index::
   single: protocol

protocol
++++++++

This property holds the protocol to use for sending the JSON-RPC requests. Valid values are ``http`` and ``https``

:**› Type**: String
:**› Default**: ``http``
:**› Signal**: protocolChanged()
:**› Attributes**: Writable

Methods
*******


.. _method_JsonRpcClient_call:

.. index::
   single: call

call(String name, List arguments, JSValue callback)
+++++++++++++++++++++++++++++++++++++++++++++++++++

This method calls the method specified by parameter `name` with the arguments specified in parameter ``arguments``. It returns ``true`` if the call request could be initiated succesfully. This does not neccessarily mean that the call itself was successful. Use the :ref:`errorCodeReceived() <signal_JsonRpcClient_errorCodeReceived>`, :ref:`errorDataReceived() <signal_JsonRpcClient_errorDataReceived>` or :ref:`errorMessageReceived() <signal_JsonRpcClient_errorMessageReceived>` signals to detect and handle actual RPC errors. When the call succeeded, the return value will be passed to the given callback as the first argument.

:**› Returns**: Boolean



.. _method_JsonRpcClient_getProperty:

.. index::
   single: getProperty

getProperty(String name, JSValue callback)
++++++++++++++++++++++++++++++++++++++++++

This method wraps a call to the :ref:`getProperty() <method_JsonRpcClient_getProperty>` method implemented by :ref:`JsonRpcService <object_JsonRpcService>`. Whenever a property is received, the given callback is called with the result as the first argument.

:**› Returns**: Boolean



.. _method_JsonRpcClient_setProperty:

.. index::
   single: setProperty

setProperty(String name, Variant value)
+++++++++++++++++++++++++++++++++++++++

This method wraps a call to the :ref:`setProperty() <method_JsonRpcClient_setProperty>` method implemented by :ref:`JsonRpcService <object_JsonRpcService>`.

:**› Returns**: Boolean


Signals
*******


.. _signal_JsonRpcClient_errorCodeReceived:

.. index::
   single: errorCodeReceived

errorCodeReceived(String name, SignedInteger errorCode)
+++++++++++++++++++++++++++++++++++++++++++++++++++++++

This signal is emitted whenever an RPC error response with an error code other than 0 is received.



.. _signal_JsonRpcClient_errorDataReceived:

.. index::
   single: errorDataReceived

errorDataReceived(String name, Variant errorData)
+++++++++++++++++++++++++++++++++++++++++++++++++

This signal is emitted whenever an RPC error response with valid error data is received.



.. _signal_JsonRpcClient_errorMessageReceived:

.. index::
   single: errorMessageReceived

errorMessageReceived(String name, String errorMessage)
++++++++++++++++++++++++++++++++++++++++++++++++++++++

This signal is emitted whenever an RPC error response with a valid error message is received.


Example
*******
See :ref:`JsonRpcService example <example_JsonRpcService>` on how to use JsonRpcClient.
