
.. _object_WebSocket:


:index:`WebSocket`
------------------

Description
***********

The WebSocket object provides WebSockets-based communication with a WebSockets server. WebSockets is a web technology providing full-duplex communications channels over a single TCP connection. The WebSocket protocol was standardized by the IETF as `RFC 6455 <https://tools.ietf.org/html/rfc6455>`_ in 2011.

The object can be used in two ways. When used as :ref:`IoDevice <object_IoDevice>`, :ref:`IoDevice.open() <method_IoDevice_open>` needs to be called and data can afterwards be read and written using the corresponding :ref:`IoDevice <object_IoDevice>` methods. Alternatively text and binary messages can be sent and received directly after calling :ref:`connectToHost() <method_WebSocket_connectToHost>`.

This object was introduced in InCore 2.3.

:**› Inherits**: :ref:`IoDevice <object_IoDevice>`

Overview
********

Properties
++++++++++

.. hlist::
  :columns: 3

  * :ref:`autoConnect <property_WebSocket_autoConnect>`
  * :ref:`error <property_WebSocket_error>`
  * :ref:`errorString <property_WebSocket_errorString>`
  * :ref:`state <property_WebSocket_state>`
  * :ref:`subProtocol <property_WebSocket_subProtocol>`
  * :ref:`url <property_WebSocket_url>`
  * :ref:`IoDevice.append <property_IoDevice_append>`
  * :ref:`IoDevice.atEnd <property_IoDevice_atEnd>`
  * :ref:`IoDevice.autoOpen <property_IoDevice_autoOpen>`
  * :ref:`IoDevice.bytesAvailable <property_IoDevice_bytesAvailable>`
  * :ref:`IoDevice.canReadLine <property_IoDevice_canReadLine>`
  * :ref:`IoDevice.deviceErrorString <property_IoDevice_deviceErrorString>`
  * :ref:`IoDevice.isOpen <property_IoDevice_isOpen>`
  * :ref:`IoDevice.isWritable <property_IoDevice_isWritable>`
  * :ref:`IoDevice.nameArgument <property_IoDevice_nameArgument>`
  * :ref:`IoDevice.pos <property_IoDevice_pos>`
  * :ref:`IoDevice.readOnly <property_IoDevice_readOnly>`
  * :ref:`IoDevice.size <property_IoDevice_size>`
  * :ref:`IoDevice.truncate <property_IoDevice_truncate>`
  * :ref:`IoDevice.unbuffered <property_IoDevice_unbuffered>`
  * :ref:`Object.objectId <property_Object_objectId>`
  * :ref:`Object.parent <property_Object_parent>`

Methods
+++++++

.. hlist::
  :columns: 3

  * :ref:`connectToHost() <method_WebSocket_connectToHost>`
  * :ref:`disconnectFromHost() <method_WebSocket_disconnectFromHost>`
  * :ref:`sendBinaryMessage() <method_WebSocket_sendBinaryMessage>`
  * :ref:`sendTextMessage() <method_WebSocket_sendTextMessage>`
  * :ref:`IoDevice.close() <method_IoDevice_close>`
  * :ref:`IoDevice.flush() <method_IoDevice_flush>`
  * :ref:`IoDevice.open() <method_IoDevice_open>`
  * :ref:`IoDevice.peekAll() <method_IoDevice_peekAll>`
  * :ref:`IoDevice.read() <method_IoDevice_read>`
  * :ref:`IoDevice.readAll() <method_IoDevice_readAll>`
  * :ref:`IoDevice.readLine() <method_IoDevice_readLine>`
  * :ref:`IoDevice.sync() <method_IoDevice_sync>`
  * :ref:`IoDevice.write() <method_IoDevice_write>`
  * :ref:`Object.deserializeProperties() <method_Object_deserializeProperties>`
  * :ref:`Object.fromJson() <method_Object_fromJson>`
  * :ref:`Object.toJson() <method_Object_toJson>`

Signals
+++++++

.. hlist::
  :columns: 2

  * :ref:`binaryMessageReceived() <signal_WebSocket_binaryMessageReceived>`
  * :ref:`connected() <signal_WebSocket_connected>`
  * :ref:`disconnected() <signal_WebSocket_disconnected>`
  * :ref:`errorOccurred() <signal_WebSocket_errorOccurred>`
  * :ref:`ipSocketErrorOccurred() <signal_WebSocket_ipSocketErrorOccurred>`
  * :ref:`sslErrorOccurred() <signal_WebSocket_sslErrorOccurred>`
  * :ref:`textMessageReceived() <signal_WebSocket_textMessageReceived>`
  * :ref:`IoDevice.lineAvailableForRead() <signal_IoDevice_lineAvailableForRead>`
  * :ref:`IoDevice.readyRead() <signal_IoDevice_readyRead>`
  * :ref:`Object.completed() <signal_Object_completed>`

Enumerations
++++++++++++

.. hlist::
  :columns: 1

  * :ref:`Error <enum_WebSocket_Error>`
  * :ref:`State <enum_WebSocket_State>`



Properties
**********


.. _property_WebSocket_autoConnect:

.. _signal_WebSocket_autoConnectChanged:

.. index::
   single: autoConnect

autoConnect
+++++++++++

This property holds whether the TCP connection should be established automatically. Keeping this option enabled will also make the object reconnect on connection errors.

:**› Type**: Boolean
:**› Default**: ``true``
:**› Signal**: autoConnectChanged()
:**› Attributes**: Writable


.. _property_WebSocket_error:

.. _signal_WebSocket_errorChanged:

.. index::
   single: error

error
+++++

This property holds the most recently occurred error or :ref:`WebSocket.NoError <enumitem_WebSocket_NoError>` if no error occurred. If the same error occurs multiple times this property does not change. Use the :ref:`errorOccurred() <signal_WebSocket_errorOccurred>` signal to detect multiple occurrences of the same error.

:**› Type**: :ref:`Error <enum_WebSocket_Error>`
:**› Signal**: errorChanged()
:**› Attributes**: Readonly


.. _property_WebSocket_errorString:

.. _signal_WebSocket_errorStringChanged:

.. index::
   single: errorString

errorString
+++++++++++

This property holds the current human readable error string corresponding to the current value in the :ref:`error <property_WebSocket_error>` property. It may include additional information such as failure reasons or locations.

:**› Type**: String
:**› Signal**: errorStringChanged()
:**› Attributes**: Readonly


.. _property_WebSocket_state:

.. _signal_WebSocket_stateChanged:

.. index::
   single: state

state
+++++

This property holds the current state of the WebSocket.

:**› Type**: :ref:`State <enum_WebSocket_State>`
:**› Default**: :ref:`WebSocket.Closed <enumitem_WebSocket_Closed>`
:**› Signal**: stateChanged()
:**› Attributes**: Writable


.. _property_WebSocket_subProtocol:

.. _signal_WebSocket_subProtocolChanged:

.. index::
   single: subProtocol

subProtocol
+++++++++++

This property holds the application-specific subprotocol to request from the WebSockets server. See `RFC6455 Section 1.9 <https://tools.ietf.org/html/rfc6455#section-1.9>`_ for details.

:**› Type**: String
:**› Signal**: subProtocolChanged()
:**› Attributes**: Writable


.. _property_WebSocket_url:

.. _signal_WebSocket_urlChanged:

.. index::
   single: url

url
+++

This property holds the URL of the WebSockets server, e.g. ``ws://ws.example.org:8000`` or ``wss://ws.example.org:8000``.

:**› Type**: String
:**› Signal**: urlChanged()
:**› Attributes**: Writable

Methods
*******


.. _method_WebSocket_connectToHost:

.. index::
   single: connectToHost

connectToHost()
+++++++++++++++

This method initiates a connection to the WebSockets server specified in the :ref:`url <property_WebSocket_url>` property. It's called automatically by :ref:`IoDevice.open() <method_IoDevice_open>`.



.. _method_WebSocket_disconnectFromHost:

.. index::
   single: disconnectFromHost

disconnectFromHost()
++++++++++++++++++++

This method disconnects from the WebSockets server. It's called automatically by :ref:`IoDevice.close() <method_IoDevice_close>`.



.. _method_WebSocket_sendBinaryMessage:

.. index::
   single: sendBinaryMessage

sendBinaryMessage(ArrayBuffer message)
++++++++++++++++++++++++++++++++++++++

This method sends the specified binary ``message`` to the WebSockets server. This method is also called by :ref:`IoDevice.write() <method_IoDevice_write>`.

:**› Returns**: SignedBigInteger



.. _method_WebSocket_sendTextMessage:

.. index::
   single: sendTextMessage

sendTextMessage(String message)
+++++++++++++++++++++++++++++++

This method sends the specified text ``message`` to the WebSockets server.

:**› Returns**: SignedBigInteger


Signals
*******


.. _signal_WebSocket_binaryMessageReceived:

.. index::
   single: binaryMessageReceived

binaryMessageReceived(ArrayBuffer message)
++++++++++++++++++++++++++++++++++++++++++

This signal is emitted when a binary message is received. ``message`` contains the bytes received. When the :ref:`IoDevice <object_IoDevice>` is opened, this signal is also handled internally to fill the internal read buffer and emit the :ref:`IoDevice.readyRead() <signal_IoDevice_readyRead>` signal.



.. _signal_WebSocket_connected:

.. index::
   single: connected

connected()
+++++++++++

This signal is emitted after the WebSockets connection has been established successfully.



.. _signal_WebSocket_disconnected:

.. index::
   single: disconnected

disconnected()
++++++++++++++

This signal is emitted when the WebSockets connection has been disconnected.



.. _signal_WebSocket_errorOccurred:

.. index::
   single: errorOccurred

errorOccurred()
+++++++++++++++

This signal is emitted whenever an error has occurred, regardless of whether the :ref:`error <property_WebSocket_error>` property has changed or not. In contrast to the change notification signal of the :ref:`error <property_WebSocket_error>` property this signal is also emitted several times if a certain error occurs several times in succession.



.. _signal_WebSocket_ipSocketErrorOccurred:

.. index::
   single: ipSocketErrorOccurred

ipSocketErrorOccurred(:ref:`IpSocket.Error <enum_IpSocket_Error>` socketError)
++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

This signal is emitted when an :ref:`IpSocket <object_IpSocket>`-specific error has occurred.



.. _signal_WebSocket_sslErrorOccurred:

.. index::
   single: sslErrorOccurred

sslErrorOccurred(String errorString)
++++++++++++++++++++++++++++++++++++

This signal is emitted when an TLS/SSL-related error has occurred.



.. _signal_WebSocket_textMessageReceived:

.. index::
   single: textMessageReceived

textMessageReceived(String message)
+++++++++++++++++++++++++++++++++++

This signal is emitted when a text message is received. ``message`` contains the bytes received.


Enumerations
************


.. _enum_WebSocket_Error:

.. index::
   single: Error

Error
+++++

This enumeration describes all errors which can occur in WebSocket objects. The most recently occurred error is stored in the :ref:`error <property_WebSocket_error>` property.

.. index::
   single: WebSocket.NoError
.. index::
   single: WebSocket.IpSocketError
.. index::
   single: WebSocket.NotOpenError
.. index::
   single: WebSocket.SslError
.. list-table::
  :widths: auto
  :header-rows: 1

  * - Name
    - Value
    - Description

      .. _enumitem_WebSocket_NoError:
  * - ``WebSocket.NoError``
    - ``0``
    - No error occurred or was detected.

      .. _enumitem_WebSocket_IpSocketError:
  * - ``WebSocket.IpSocketError``
    - ``1``
    - IpSocket-specific error occurred.

      .. _enumitem_WebSocket_NotOpenError:
  * - ``WebSocket.NotOpenError``
    - ``2``
    - Socket is not opened, so messages can't be sent.

      .. _enumitem_WebSocket_SslError:
  * - ``WebSocket.SslError``
    - ``3``
    - Error while establishing TLS/SSL connection.


.. _enum_WebSocket_State:

.. index::
   single: State

State
+++++

This enumeration describes the different states in which a WebSocket can be.

.. index::
   single: WebSocket.Connecting
.. index::
   single: WebSocket.Open
.. index::
   single: WebSocket.Closing
.. index::
   single: WebSocket.Closed
.. list-table::
  :widths: auto
  :header-rows: 1

  * - Name
    - Value
    - Description

      .. _enumitem_WebSocket_Connecting:
  * - ``WebSocket.Connecting``
    - ``0``
    - The WebSocket has started establishing a connection.

      .. _enumitem_WebSocket_Open:
  * - ``WebSocket.Open``
    - ``1``
    - The WebSocket connection is established and ready for sending/receiving messages.

      .. _enumitem_WebSocket_Closing:
  * - ``WebSocket.Closing``
    - ``2``
    - The WebSocket is about to close (data may still be waiting to be written).

      .. _enumitem_WebSocket_Closed:
  * - ``WebSocket.Closed``
    - ``3``
    - The WebSocket is not connected.


.. _example_WebSocket:


Example
*******

.. code-block:: qml

    import InCore.Foundation 2.3
    
    Application {
        WebSocket {
            url: "wss://echo.websocket.org"
            onConnected: {
                console.log("Connected to", url)
                sendTextMessage("Hello world, this is a message from InCore!")
            }
            onTextMessageReceived: console.log("Received message:", message)
        }
    }
    