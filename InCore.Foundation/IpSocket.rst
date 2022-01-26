
.. _object_IpSocket:


:index:`IpSocket`
-----------------

Description
***********

The IpSocket object is the base object for :ref:`TcpSocket <object_TcpSocket>` and :ref:`UdpSocket <object_UdpSocket>` and provides all common socket functionality.

TCP (Transmission Control Protocol) is a reliable, stream-oriented, connection-oriented transport protocol. UDP (User Datagram Protocol) is an unreliable, datagram-oriented, connectionless protocol. In practice, this means that TCP is better suited for continuous transmission of data, whereas the more lightweight UDP can be used when reliability isn't important.

The IpSocket API unifies most of the differences between the two protocols. For example, although UDP is connectionless, :ref:`connectToHost() <method_IpSocket_connectToHost>` establishes a virtual connection for UDP sockets, enabling you to use the socket in more or less the same way regardless of the underlying protocol. Internally, :ref:`UdpSocket <object_UdpSocket>` remembers the address and port and functions like :ref:`IoDevice.read() <method_IoDevice_read>` and :ref:`IoDevice.write() <method_IoDevice_write>` use these values.

This object was introduced in InCore 2.3.

:**› Inherits**: :ref:`IoDevice <object_IoDevice>`
:**› Inherited by**: :ref:`TcpSocket <object_TcpSocket>`, :ref:`UdpSocket <object_UdpSocket>`

Overview
********

Properties
++++++++++

.. hlist::
  :columns: 3

  * :ref:`autoConnect <property_IpSocket_autoConnect>`
  * :ref:`error <property_IpSocket_error>`
  * :ref:`errorString <property_IpSocket_errorString>`
  * :ref:`hostname <property_IpSocket_hostname>`
  * :ref:`keepAlive <property_IpSocket_keepAlive>`
  * :ref:`lowDelay <property_IpSocket_lowDelay>`
  * :ref:`multicastLoopback <property_IpSocket_multicastLoopback>`
  * :ref:`multicastTtl <property_IpSocket_multicastTtl>`
  * :ref:`pathMtu <property_IpSocket_pathMtu>`
  * :ref:`port <property_IpSocket_port>`
  * :ref:`protocol <property_IpSocket_protocol>`
  * :ref:`receiveBufferSize <property_IpSocket_receiveBufferSize>`
  * :ref:`sendBufferSize <property_IpSocket_sendBufferSize>`
  * :ref:`state <property_IpSocket_state>`
  * :ref:`typeOfService <property_IpSocket_typeOfService>`
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

  * :ref:`abort() <method_IpSocket_abort>`
  * :ref:`connectToHost() <method_IpSocket_connectToHost>`
  * :ref:`disconnectFromHost() <method_IpSocket_disconnectFromHost>`
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
  * :ref:`Object.serializeProperties() <method_Object_serializeProperties>`
  * :ref:`Object.toJson() <method_Object_toJson>`

Signals
+++++++

.. hlist::
  :columns: 1

  * :ref:`connected() <signal_IpSocket_connected>`
  * :ref:`disconnected() <signal_IpSocket_disconnected>`
  * :ref:`errorOccurred() <signal_IpSocket_errorOccurred>`
  * :ref:`IoDevice.lineAvailableForRead() <signal_IoDevice_lineAvailableForRead>`
  * :ref:`IoDevice.readyRead() <signal_IoDevice_readyRead>`
  * :ref:`Object.completed() <signal_Object_completed>`

Enumerations
++++++++++++

.. hlist::
  :columns: 1

  * :ref:`Error <enum_IpSocket_Error>`
  * :ref:`Protocol <enum_IpSocket_Protocol>`
  * :ref:`State <enum_IpSocket_State>`



Properties
**********


.. _property_IpSocket_autoConnect:

.. _signal_IpSocket_autoConnectChanged:

.. index::
   single: autoConnect

autoConnect
+++++++++++

This property holds whether the TCP connection should be established automatically. Keeping this option enabled will also make the object reconnect on connection errors.

:**› Type**: Boolean
:**› Default**: ``true``
:**› Signal**: autoConnectChanged()
:**› Attributes**: Writable


.. _property_IpSocket_error:

.. _signal_IpSocket_errorChanged:

.. index::
   single: error

error
+++++

This property holds the most recently occurred error or :ref:`IpSocket.NoError <enumitem_IpSocket_NoError>` if no error occurred. If the same error occurs multiple times this property does not change. Use the :ref:`errorOccurred() <signal_IpSocket_errorOccurred>` signal to detect multiple occurrences of the same error.

:**› Type**: :ref:`Error <enum_IpSocket_Error>`
:**› Signal**: errorChanged()
:**› Attributes**: Readonly


.. _property_IpSocket_errorString:

.. _signal_IpSocket_errorStringChanged:

.. index::
   single: errorString

errorString
+++++++++++

This property holds the current human readable error string corresponding to the current value in the :ref:`error <property_IpSocket_error>` property. It may include additional information such as failure reasons or locations.

:**› Type**: String
:**› Signal**: errorStringChanged()
:**› Attributes**: Readonly


.. _property_IpSocket_hostname:

.. _signal_IpSocket_hostnameChanged:

.. index::
   single: hostname

hostname
++++++++

This property holds the name or address of the host which to establish an IP connection to.

:**› Type**: String
:**› Signal**: hostnameChanged()
:**› Attributes**: Writable


.. _property_IpSocket_keepAlive:

.. _signal_IpSocket_keepAliveChanged:

.. index::
   single: keepAlive

keepAlive
+++++++++

This property holds whether to enable the ``SO_KEEPALIVE`` socket option.

:**› Type**: Boolean
:**› Default**: ``false``
:**› Signal**: keepAliveChanged()
:**› Attributes**: Writable


.. _property_IpSocket_lowDelay:

.. _signal_IpSocket_lowDelayChanged:

.. index::
   single: lowDelay

lowDelay
++++++++

This property holds whether to optimize the socket for low latency. For TCP connections this sets the ``TCP_NODELAY`` option and disable Nagle's algorithm.

:**› Type**: Boolean
:**› Default**: ``false``
:**› Signal**: lowDelayChanged()
:**› Attributes**: Writable


.. _property_IpSocket_multicastLoopback:

.. _signal_IpSocket_multicastLoopbackChanged:

.. index::
   single: multicastLoopback

multicastLoopback
+++++++++++++++++

This property holds whether to enable the ``IP_MULTICAST_LOOP`` (multicast loopback) socket option.

:**› Type**: Boolean
:**› Default**: ``false``
:**› Signal**: multicastLoopbackChanged()
:**› Attributes**: Writable


.. _property_IpSocket_multicastTtl:

.. _signal_IpSocket_multicastTtlChanged:

.. index::
   single: multicastTtl

multicastTtl
++++++++++++

This property holds an integer value to set ``IP_MULTICAST_TTL`` (TTL for multicast datagrams) socket option.

:**› Type**: SignedInteger
:**› Default**: ``0``
:**› Signal**: multicastTtlChanged()
:**› Attributes**: Writable


.. _property_IpSocket_pathMtu:

.. _signal_IpSocket_pathMtuChanged:

.. index::
   single: pathMtu

pathMtu
+++++++

This property holds the Path Maximum Transmission Unit (PMTU) value currently known by the IP stack, if any. The value can be changed for IPv6 connections only, affecting the MTU for transmission.

:**› Type**: SignedInteger
:**› Default**: ``0``
:**› Signal**: pathMtuChanged()
:**› Attributes**: Writable


.. _property_IpSocket_port:

.. _signal_IpSocket_portChanged:

.. index::
   single: port

port
++++

This property holds the network port number of the host which to establish an IP connection to.

:**› Type**: SignedInteger
:**› Default**: ``-1``
:**› Signal**: portChanged()
:**› Attributes**: Writable


.. _property_IpSocket_protocol:

.. _signal_IpSocket_protocolChanged:

.. index::
   single: protocol

protocol
++++++++

This property holds network layer protocol to use for the IP connection.

:**› Type**: :ref:`Protocol <enum_IpSocket_Protocol>`
:**› Default**: :ref:`IpSocket.AnyIPProtocol <enumitem_IpSocket_AnyIPProtocol>`
:**› Signal**: protocolChanged()
:**› Attributes**: Writable


.. _property_IpSocket_receiveBufferSize:

.. _signal_IpSocket_receiveBufferSizeChanged:

.. index::
   single: receiveBufferSize

receiveBufferSize
+++++++++++++++++

This property holds the socket receive buffer size in bytes at the OS level. This maps to the ``SO_RCVBUF`` socket option.

:**› Type**: SignedInteger
:**› Default**: ``0``
:**› Signal**: receiveBufferSizeChanged()
:**› Attributes**: Writable


.. _property_IpSocket_sendBufferSize:

.. _signal_IpSocket_sendBufferSizeChanged:

.. index::
   single: sendBufferSize

sendBufferSize
++++++++++++++

This property holds the socket send buffer size in bytes at the OS level. This maps to the ``SO_SNDBUF`` socket option.

:**› Type**: SignedInteger
:**› Default**: ``0``
:**› Signal**: sendBufferSizeChanged()
:**› Attributes**: Writable


.. _property_IpSocket_state:

.. _signal_IpSocket_stateChanged:

.. index::
   single: state

state
+++++

This property holds the current state of the IP connection.

:**› Type**: :ref:`State <enum_IpSocket_State>`
:**› Default**: :ref:`IpSocket.Disconnected <enumitem_IpSocket_Disconnected>`
:**› Signal**: stateChanged()
:**› Attributes**: Writable


.. _property_IpSocket_typeOfService:

.. _signal_IpSocket_typeOfServiceChanged:

.. index::
   single: typeOfService

typeOfService
+++++++++++++

This property holds the value for the ``IP_TOS``. See the `TypeOfService table <https://doc.qt.io/qt-5/qabstractsocket.html#SocketOption-enum>`_ for supported values.

:**› Type**: SignedInteger
:**› Default**: ``0``
:**› Signal**: typeOfServiceChanged()
:**› Attributes**: Writable

Methods
*******


.. _method_IpSocket_abort:

.. index::
   single: abort

abort()
+++++++

This method aborts the current connection and resets the socket. Unlike :ref:`disconnectFromHost() <method_IpSocket_disconnectFromHost>`, this function immediately closes the socket, discarding any pending data in the write buffer.



.. _method_IpSocket_connectToHost:

.. index::
   single: connectToHost

connectToHost()
+++++++++++++++

This method attempts to make a connection to :ref:`hostname <property_IpSocket_hostname>` on the given :ref:`port <property_IpSocket_port>`. The :ref:`protocol <property_IpSocket_protocol>` property is used to specify which network protocol to use (e.g. IPv4 or IPv6).

The socket is opened in the given openMode and first enters :ref:`IpSocket.HostLookup <enumitem_IpSocket_HostLookup>` state, then performs a host name lookup of :ref:`hostname <property_IpSocket_hostname>`. If the lookup succeeds, the socket enters :ref:`IpSocket.Connecting <enumitem_IpSocket_Connecting>` state. It then attempts to connect to the address or addresses returned by the lookup. Finally, if a connection is established, the socket enters :ref:`IpSocket.Connected <enumitem_IpSocket_Connected>` and emits the :ref:`connected() <signal_IpSocket_connected>` signal.

At any point, the socket can emit the :ref:`errorOccurred() <signal_IpSocket_errorOccurred>` signal.



.. _method_IpSocket_disconnectFromHost:

.. index::
   single: disconnectFromHost

disconnectFromHost()
++++++++++++++++++++

This method attempts to close the socket. If there is pending data waiting to be written, the socket will enter :ref:`IpSocket.Closing <enumitem_IpSocket_Closing>` state and wait until all data has been written. Eventually, it will enter :ref:`IpSocket.Disconnected <enumitem_IpSocket_Disconnected>` and emit the :ref:`disconnected() <signal_IpSocket_disconnected>` signal.


Signals
*******


.. _signal_IpSocket_connected:

.. index::
   single: connected

connected()
+++++++++++

This signal is emitted after a connection has been established successfully.



.. _signal_IpSocket_disconnected:

.. index::
   single: disconnected

disconnected()
++++++++++++++

This signal is emitted when the socket has been disconnected.



.. _signal_IpSocket_errorOccurred:

.. index::
   single: errorOccurred

errorOccurred()
+++++++++++++++

This signal is emitted whenever an error has occurred, regardless of whether the :ref:`error <property_IpSocket_error>` property has changed or not. In contrast to the change notification signal of the :ref:`error <property_IpSocket_error>` property this signal is also emitted several times if a certain error occurs several times in succession.


Enumerations
************


.. _enum_IpSocket_Error:

.. index::
   single: Error

Error
+++++

This enumeration describes all errors which can occur in IpSocket objects. The most recently occurred error is stored in the :ref:`error <property_IpSocket_error>` property.

.. index::
   single: IpSocket.NoError
.. index::
   single: IpSocket.EmptyHostNameError
.. index::
   single: IpSocket.PortNumberOutOfRangeError
.. index::
   single: IpSocket.DatagramWriteError
.. index::
   single: IpSocket.ConnectionRefusedError
.. index::
   single: IpSocket.RemoteHostClosedError
.. index::
   single: IpSocket.HostNotFoundError
.. index::
   single: IpSocket.SocketAccessError
.. index::
   single: IpSocket.SocketResourceError
.. index::
   single: IpSocket.SocketTimeoutError
.. index::
   single: IpSocket.DatagramTooLargeError
.. index::
   single: IpSocket.NetworkError
.. index::
   single: IpSocket.AddressInUseError
.. index::
   single: IpSocket.SocketAddressNotAvailableError
.. index::
   single: IpSocket.UnsupportedSocketOperationError
.. index::
   single: IpSocket.UnfinishedSocketOperationError
.. index::
   single: IpSocket.ProxyAuthenticationRequiredError
.. index::
   single: IpSocket.SslHandshakeFailedError
.. index::
   single: IpSocket.ProxyConnectionRefusedError
.. index::
   single: IpSocket.ProxyConnectionClosedError
.. index::
   single: IpSocket.ProxyConnectionTimeoutError
.. index::
   single: IpSocket.ProxyNotFoundError
.. index::
   single: IpSocket.ProxyProtocolError
.. index::
   single: IpSocket.OperationError
.. index::
   single: IpSocket.SslInternalError
.. index::
   single: IpSocket.SslInvalidUserDataError
.. index::
   single: IpSocket.TemporaryError
.. list-table::
  :widths: auto
  :header-rows: 1

  * - Name
    - Value
    - Description

      .. _enumitem_IpSocket_NoError:
  * - ``IpSocket.NoError``
    - ``0``
    - No error occurred or was detected.

      .. _enumitem_IpSocket_EmptyHostNameError:
  * - ``IpSocket.EmptyHostNameError``
    - ``1``
    - No/empty hostname specified.

      .. _enumitem_IpSocket_PortNumberOutOfRangeError:
  * - ``IpSocket.PortNumberOutOfRangeError``
    - ``2``
    - Port number out of range (1–65535).

      .. _enumitem_IpSocket_DatagramWriteError:
  * - ``IpSocket.DatagramWriteError``
    - ``3``
    - The specified datagram is invalid and therefore could not be written.

      .. _enumitem_IpSocket_ConnectionRefusedError:
  * - ``IpSocket.ConnectionRefusedError``
    - ``10``
    - The connection was refused by the peer (or timed out).

      .. _enumitem_IpSocket_RemoteHostClosedError:
  * - ``IpSocket.RemoteHostClosedError``
    - ``11``
    - The remote host closed the connection. Note that the client socket (i.e., this socket) will be closed after the remote close notification has been sent.

      .. _enumitem_IpSocket_HostNotFoundError:
  * - ``IpSocket.HostNotFoundError``
    - ``12``
    - The host address was not found.

      .. _enumitem_IpSocket_SocketAccessError:
  * - ``IpSocket.SocketAccessError``
    - ``13``
    - The socket operation failed because the application lacked the required privileges.

      .. _enumitem_IpSocket_SocketResourceError:
  * - ``IpSocket.SocketResourceError``
    - ``14``
    - The local system ran out of resources (e.g., too many sockets).

      .. _enumitem_IpSocket_SocketTimeoutError:
  * - ``IpSocket.SocketTimeoutError``
    - ``15``
    - The socket operation timed out.

      .. _enumitem_IpSocket_DatagramTooLargeError:
  * - ``IpSocket.DatagramTooLargeError``
    - ``16``
    - The datagram was larger than the operating system's limit (which can be as low as 8192 bytes).

      .. _enumitem_IpSocket_NetworkError:
  * - ``IpSocket.NetworkError``
    - ``17``
    - An error occurred with the network (e.g., the network cable was accidentally plugged out).

      .. _enumitem_IpSocket_AddressInUseError:
  * - ``IpSocket.AddressInUseError``
    - ``18``
    - The address specified to bind is already in use and was set to be exclusive.

      .. _enumitem_IpSocket_SocketAddressNotAvailableError:
  * - ``IpSocket.SocketAddressNotAvailableError``
    - ``19``
    - The address specified to bind does not belong to the host.

      .. _enumitem_IpSocket_UnsupportedSocketOperationError:
  * - ``IpSocket.UnsupportedSocketOperationError``
    - ``20``
    - The requested socket operation is not supported by the local operating system (e.g., lack of IPv6 support).

      .. _enumitem_IpSocket_UnfinishedSocketOperationError:
  * - ``IpSocket.UnfinishedSocketOperationError``
    - ``21``
    - The last operation attempted has not finished yet (still in progress in the background).

      .. _enumitem_IpSocket_ProxyAuthenticationRequiredError:
  * - ``IpSocket.ProxyAuthenticationRequiredError``
    - ``22``
    - The socket is using a proxy, and the proxy requires authentication.

      .. _enumitem_IpSocket_SslHandshakeFailedError:
  * - ``IpSocket.SslHandshakeFailedError``
    - ``23``
    - The SSL/TLS handshake failed, so the connection was closed (only used in SslSocket).

      .. _enumitem_IpSocket_ProxyConnectionRefusedError:
  * - ``IpSocket.ProxyConnectionRefusedError``
    - ``24``
    - Could not contact the proxy server because the connection to that server was denied.

      .. _enumitem_IpSocket_ProxyConnectionClosedError:
  * - ``IpSocket.ProxyConnectionClosedError``
    - ``25``
    - The connection to the proxy server was closed unexpectedly (before the connection to the final peer was established).

      .. _enumitem_IpSocket_ProxyConnectionTimeoutError:
  * - ``IpSocket.ProxyConnectionTimeoutError``
    - ``26``
    - The connection to the proxy server timed out or the proxy server stopped responding in the authentication phase.

      .. _enumitem_IpSocket_ProxyNotFoundError:
  * - ``IpSocket.ProxyNotFoundError``
    - ``27``
    - The proxy address (or the application proxy) was not found.

      .. _enumitem_IpSocket_ProxyProtocolError:
  * - ``IpSocket.ProxyProtocolError``
    - ``28``
    - The connection negotiation with the proxy server failed, because the response from the proxy server could not be understood.

      .. _enumitem_IpSocket_OperationError:
  * - ``IpSocket.OperationError``
    - ``29``
    - An operation was attempted while the socket was in a state that did not permit it.

      .. _enumitem_IpSocket_SslInternalError:
  * - ``IpSocket.SslInternalError``
    - ``30``
    - The SSL library being used reported an internal error. This is probably the result of a bad installation or misconfiguration of the library.

      .. _enumitem_IpSocket_SslInvalidUserDataError:
  * - ``IpSocket.SslInvalidUserDataError``
    - ``31``
    - Invalid data (certificate, key, cypher, etc.) was provided and its use resulted in an error in the SSL library.

      .. _enumitem_IpSocket_TemporaryError:
  * - ``IpSocket.TemporaryError``
    - ``32``
    - A temporary error occurred (e.g., operation would block and socket is non-blocking).


.. _enum_IpSocket_Protocol:

.. index::
   single: Protocol

Protocol
++++++++

This enumeration describes the network layer protocol values supported by :ref:`IpSocket <object_IpSocket>`-based objects.

.. index::
   single: IpSocket.UnknownProtocol
.. index::
   single: IpSocket.IPv4Protocol
.. index::
   single: IpSocket.IPv6Protocol
.. index::
   single: IpSocket.AnyIPProtocol
.. list-table::
  :widths: auto
  :header-rows: 1

  * - Name
    - Value
    - Description

      .. _enumitem_IpSocket_UnknownProtocol:
  * - ``IpSocket.UnknownProtocol``
    - ``-1``
    - Other than IPv4 and IPv6.

      .. _enumitem_IpSocket_IPv4Protocol:
  * - ``IpSocket.IPv4Protocol``
    - ``0``
    - IPv4.

      .. _enumitem_IpSocket_IPv6Protocol:
  * - ``IpSocket.IPv6Protocol``
    - ``1``
    - IPv6.

      .. _enumitem_IpSocket_AnyIPProtocol:
  * - ``IpSocket.AnyIPProtocol``
    - ``2``
    - Either IPv4 or IPv6.


.. _enum_IpSocket_State:

.. index::
   single: State

State
+++++

This enumeration describes the different states in which a socket can be.

.. index::
   single: IpSocket.Disconnected
.. index::
   single: IpSocket.HostLookup
.. index::
   single: IpSocket.Connecting
.. index::
   single: IpSocket.Connected
.. index::
   single: IpSocket.Bound
.. index::
   single: IpSocket.Closing
.. list-table::
  :widths: auto
  :header-rows: 1

  * - Name
    - Value
    - Description

      .. _enumitem_IpSocket_Disconnected:
  * - ``IpSocket.Disconnected``
    - ``0``
    - The socket is not connected.

      .. _enumitem_IpSocket_HostLookup:
  * - ``IpSocket.HostLookup``
    - ``1``
    - The socket is performing a host name lookup.

      .. _enumitem_IpSocket_Connecting:
  * - ``IpSocket.Connecting``
    - ``2``
    - The socket has started establishing a connection.

      .. _enumitem_IpSocket_Connected:
  * - ``IpSocket.Connected``
    - ``3``
    - A connection is established.

      .. _enumitem_IpSocket_Bound:
  * - ``IpSocket.Bound``
    - ``4``
    - The socket is bound to an address and port.

      .. _enumitem_IpSocket_Closing:
  * - ``IpSocket.Closing``
    - ``6``
    - The socket is about to close (data may still be waiting to be written).
