
.. _object_TcpSocket:


:index:`TcpSocket`
------------------

Description
***********

The TcpSocket object TCP (Transmission Control Protocol) is a reliable, stream-oriented, connection-oriented transport protocol. It is especially well suited for continuous transmission of data. See the :ref:`IpSocket <object_IpSocket>` documentation for all supported properties, methods and signals.

This object was introduced in InCore 2.3.

:**› Inherits**: :ref:`IpSocket <object_IpSocket>`

Overview
********

Properties
++++++++++

.. hlist::
  :columns: 3

  * :ref:`IpSocket.autoConnect <property_IpSocket_autoConnect>`
  * :ref:`IpSocket.error <property_IpSocket_error>`
  * :ref:`IpSocket.errorString <property_IpSocket_errorString>`
  * :ref:`IpSocket.hostname <property_IpSocket_hostname>`
  * :ref:`IpSocket.keepAlive <property_IpSocket_keepAlive>`
  * :ref:`IpSocket.lowDelay <property_IpSocket_lowDelay>`
  * :ref:`IpSocket.multicastLoopback <property_IpSocket_multicastLoopback>`
  * :ref:`IpSocket.multicastTtl <property_IpSocket_multicastTtl>`
  * :ref:`IpSocket.pathMtu <property_IpSocket_pathMtu>`
  * :ref:`IpSocket.port <property_IpSocket_port>`
  * :ref:`IpSocket.protocol <property_IpSocket_protocol>`
  * :ref:`IpSocket.receiveBufferSize <property_IpSocket_receiveBufferSize>`
  * :ref:`IpSocket.sendBufferSize <property_IpSocket_sendBufferSize>`
  * :ref:`IpSocket.state <property_IpSocket_state>`
  * :ref:`IpSocket.typeOfService <property_IpSocket_typeOfService>`
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
  :columns: 2

  * :ref:`IpSocket.abort() <method_IpSocket_abort>`
  * :ref:`IpSocket.connectToHost() <method_IpSocket_connectToHost>`
  * :ref:`IpSocket.disconnectFromHost() <method_IpSocket_disconnectFromHost>`
  * :ref:`IoDevice.close() <method_IoDevice_close>`
  * :ref:`IoDevice.flush() <method_IoDevice_flush>`
  * :ref:`IoDevice.open() <method_IoDevice_open>`
  * :ref:`IoDevice.peekAll() <method_IoDevice_peekAll>`
  * :ref:`IoDevice.read() <method_IoDevice_read>`
  * :ref:`IoDevice.readAll() <method_IoDevice_readAll>`
  * :ref:`IoDevice.readLine() <method_IoDevice_readLine>`
  * :ref:`IoDevice.sync() <method_IoDevice_sync>`
  * :ref:`IoDevice.write() <method_IoDevice_write>`
  * :ref:`Object.fromJson() <method_Object_fromJson>`
  * :ref:`Object.toJson() <method_Object_toJson>`

Signals
+++++++

.. hlist::
  :columns: 1

  * :ref:`IpSocket.connected() <signal_IpSocket_connected>`
  * :ref:`IpSocket.disconnected() <signal_IpSocket_disconnected>`
  * :ref:`IpSocket.errorOccurred() <signal_IpSocket_errorOccurred>`
  * :ref:`IoDevice.lineAvailableForRead() <signal_IoDevice_lineAvailableForRead>`
  * :ref:`IoDevice.readyRead() <signal_IoDevice_readyRead>`
  * :ref:`Object.completed() <signal_Object_completed>`

Enumerations
++++++++++++

.. hlist::
  :columns: 1

  * :ref:`IpSocket.Error <enum_IpSocket_Error>`
  * :ref:`IpSocket.Protocol <enum_IpSocket_Protocol>`
  * :ref:`IpSocket.State <enum_IpSocket_State>`



Properties
**********


.. _example_TcpSocket:


Example
*******

.. code-block:: qml

    import InCore.Foundation 2.3
    
    TcpSocket {
        hostname: "10.1.2.3"
        port: 80
    
        onConnected: write("GET / HTTP/1.1\nHost: 10.1.2.3\n\n")
        onReadyRead: console.log(readAll())
    }
    