
.. _object_TcpServer:


:index:`TcpServer`
------------------

Description
***********

The TcpServer object provides a TCP server which listens for incoming TCP connections at a given :ref:`port <property_TcpServer_port>`.

This object was introduced in InCore 2.3.

:**› Inherits**: :ref:`Object <object_Object>`

Overview
********

Properties
++++++++++

.. hlist::
  :columns: 1

  * :ref:`connections <property_TcpServer_connections>`
  * :ref:`listening <property_TcpServer_listening>`
  * :ref:`localHost <property_TcpServer_localHost>`
  * :ref:`port <property_TcpServer_port>`
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

  * :ref:`acceptError() <signal_TcpServer_acceptError>`
  * :ref:`connectionAccepted() <signal_TcpServer_connectionAccepted>`
  * :ref:`connectionsDataChanged() <signal_TcpServer_connectionsDataChanged>`
  * :ref:`Object.completed() <signal_Object_completed>`



Properties
**********


.. _property_TcpServer_connections:

.. _signal_TcpServer_connectionsChanged:

.. index::
   single: connections

connections
+++++++++++

This property holds a list of open connections. Whenever a socket is closed, it is removed from the list and destroyed automatically.

:**› Type**: :ref:`List <object_List>`\<:ref:`TcpSocket <object_TcpSocket>`>
:**› Signal**: connectionsChanged()
:**› Attributes**: Readonly


.. _property_TcpServer_listening:

.. _signal_TcpServer_listeningChanged:

.. index::
   single: listening

listening
+++++++++

This property holds whether the server should listen for incoming connections.

:**› Type**: Boolean
:**› Default**: ``true``
:**› Signal**: listeningChanged()
:**› Attributes**: Writable


.. _property_TcpServer_localHost:

.. _signal_TcpServer_localHostChanged:

.. index::
   single: localHost

localHost
+++++++++

This property holds whether the server should listen for incoming connections on the local loopback interface only.

:**› Type**: Boolean
:**› Default**: ``false``
:**› Signal**: localHostChanged()
:**› Attributes**: Writable


.. _property_TcpServer_port:

.. _signal_TcpServer_portChanged:

.. index::
   single: port

port
++++

This property holds the network port number which to listen at for incoming connections.

:**› Type**: SignedInteger
:**› Default**: ``0``
:**› Signal**: portChanged()
:**› Attributes**: Writable

Signals
*******


.. _signal_TcpServer_acceptError:

.. index::
   single: acceptError

acceptError(:ref:`IpSocket.Error <enum_IpSocket_Error>` error)
++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

This signal is emitted whenever an error occurs while accepting a new incoming connection. The error code is provided in the first argument.



.. _signal_TcpServer_connectionAccepted:

.. index::
   single: connectionAccepted

connectionAccepted(:ref:`TcpSocket <object_TcpSocket>` connection)
++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

This signal is emitted whenever a connection has been accepted successfully. The connection is provided in the first argument and is ready to be read from or written to.



.. _signal_TcpServer_connectionsDataChanged:

.. index::
   single: connectionsDataChanged

connectionsDataChanged(SignedInteger index)
+++++++++++++++++++++++++++++++++++++++++++

This signal is emitted whenever the :ref:`List.dataChanged() <signal_List_dataChanged>` signal is emitted, i.e. the item at ``index`` in the :ref:`connections <property_TcpServer_connections>` list itself emitted the dataChanged() signal.



.. _example_TcpServer:


Example
*******

.. code-block:: qml

    import InCore.Foundation 2.5
    
    TcpServer {
        port: 1234
    
        onConnectionAccepted: (connection) => {
            connection.write("Hello world\n")
            connection.readyRead.connect( () => {
                console.log("Client sent:", connection.readAll())
            } );
        }
    }
    