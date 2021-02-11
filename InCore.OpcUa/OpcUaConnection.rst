
.. _object_OpcUaConnection:


:index:`OpcUaConnection`
------------------------

Description
***********

Please refer to the `Qt OPC UA Connection QML type <https://doc.qt.io/QtOPCUA/qml-qtopcua-connection.html#->`_ documentation.


Overview
********

Properties
++++++++++

.. hlist::
  :columns: 2

  * `authenticationInformation <https://doc.qt.io/QtOPCUA/qml-qtopcua-connection.html#authenticationInformation-prop>`_
  * `availableBackends <https://doc.qt.io/QtOPCUA/qml-qtopcua-connection.html#availableBackends-prop>`_
  * `backend <https://doc.qt.io/QtOPCUA/qml-qtopcua-connection.html#backend-prop>`_
  * `connected <https://doc.qt.io/QtOPCUA/qml-qtopcua-connection.html#connected-prop>`_
  * `connection <https://doc.qt.io/QtOPCUA/qml-qtopcua-connection.html#connection-prop>`_
  * `currentEndpoint <https://doc.qt.io/QtOPCUA/qml-qtopcua-connection.html#currentEndpoint-prop>`_
  * `defaultConnection <https://doc.qt.io/QtOPCUA/qml-qtopcua-connection.html#defaultConnection-prop>`_
  * `namespaces <https://doc.qt.io/QtOPCUA/qml-qtopcua-connection.html#namespaces-prop>`_
  * `supportedSecurityPolicies <https://doc.qt.io/QtOPCUA/qml-qtopcua-connection.html#supportedSecurityPolicies-prop>`_
  * `supportedUserTokenTypes <https://doc.qt.io/QtOPCUA/qml-qtopcua-connection.html#supportedUserTokenTypes-prop>`_

Methods
+++++++

.. hlist::
  :columns: 2

  * `connectToEndpoint <https://doc.qt.io/QtOPCUA/qml-qtopcua-connection.html#connectToEndpoint-method>`_
  * `disconnectFromEndpoint <https://doc.qt.io/QtOPCUA/qml-qtopcua-connection.html#disconnectFromEndpoint-method>`_
  * `readNodeAttributes <https://doc.qt.io/QtOPCUA/qml-qtopcua-connection.html#readNodeAttributes-method>`_
  * `setAuthenticationInformation <https://doc.qt.io/QtOPCUA/qml-qtopcua-connection.html#setAuthenticationInformation-method>`_
  * `setConnection <https://doc.qt.io/QtOPCUA/qml-qtopcua-connection.html#setConnection-method>`_
  * `setDefaultConnection <https://doc.qt.io/QtOPCUA/qml-qtopcua-connection.html#setDefaultConnection-method>`_
  * `setDefaultConnection <https://doc.qt.io/QtOPCUA/qml-qtopcua-connection.html#setDefaultConnection-method>`_
  * `writeNodeAttributes <https://doc.qt.io/QtOPCUA/qml-qtopcua-connection.html#writeNodeAttributes-method>`_

Signals
+++++++

.. hlist::
  :columns: 1

  * `readNodeAttributesFinished <https://doc.qt.io/QtOPCUA/qml-qtopcua-connection.html#readNodeAttributesFinished-signal>`_
  * `writeNodeAttributesFinished <https://doc.qt.io/QtOPCUA/qml-qtopcua-connection.html#writeNodeAttributesFinished-signal>`_



Properties
**********


.. _property_OpcUaConnection_authenticationInformation:

.. index::
   single: authenticationInformation

authenticationInformation
+++++++++++++++++++++++++

Please refer to the `Qt OPC UA Connection QML type <https://doc.qt.io/QtOPCUA/qml-qtopcua-connection.html#authenticationInformation-prop>`_ documentation.

:**› Attributes**: Writable


.. _property_OpcUaConnection_availableBackends:

.. index::
   single: availableBackends

availableBackends
+++++++++++++++++

Please refer to the `Qt OPC UA Connection QML type <https://doc.qt.io/QtOPCUA/qml-qtopcua-connection.html#availableBackends-prop>`_ documentation.

:**› Attributes**: Readonly


.. _property_OpcUaConnection_backend:

.. index::
   single: backend

backend
+++++++

Please refer to the `Qt OPC UA Connection QML type <https://doc.qt.io/QtOPCUA/qml-qtopcua-connection.html#backend-prop>`_ documentation.

:**› Attributes**: Writable


.. _property_OpcUaConnection_connected:

.. index::
   single: connected

connected
+++++++++

Please refer to the `Qt OPC UA Connection QML type <https://doc.qt.io/QtOPCUA/qml-qtopcua-connection.html#connected-prop>`_ documentation.

:**› Attributes**: Readonly


.. _property_OpcUaConnection_connection:

.. index::
   single: connection

connection
++++++++++

Please refer to the `Qt OPC UA Connection QML type <https://doc.qt.io/QtOPCUA/qml-qtopcua-connection.html#connection-prop>`_ documentation.

:**› Attributes**: Writable


.. _property_OpcUaConnection_currentEndpoint:

.. index::
   single: currentEndpoint

currentEndpoint
+++++++++++++++

Please refer to the `Qt OPC UA Connection QML type <https://doc.qt.io/QtOPCUA/qml-qtopcua-connection.html#currentEndpoint-prop>`_ documentation.

:**› Attributes**: Readonly


.. _property_OpcUaConnection_defaultConnection:

.. index::
   single: defaultConnection

defaultConnection
+++++++++++++++++

Please refer to the `Qt OPC UA Connection QML type <https://doc.qt.io/QtOPCUA/qml-qtopcua-connection.html#defaultConnection-prop>`_ documentation.

:**› Attributes**: Writable


.. _property_OpcUaConnection_namespaces:

.. index::
   single: namespaces

namespaces
++++++++++

Please refer to the `Qt OPC UA Connection QML type <https://doc.qt.io/QtOPCUA/qml-qtopcua-connection.html#namespaces-prop>`_ documentation.

:**› Attributes**: Readonly


.. _property_OpcUaConnection_supportedSecurityPolicies:

.. index::
   single: supportedSecurityPolicies

supportedSecurityPolicies
+++++++++++++++++++++++++

Please refer to the `Qt OPC UA Connection QML type <https://doc.qt.io/QtOPCUA/qml-qtopcua-connection.html#supportedSecurityPolicies-prop>`_ documentation.

:**› Attributes**: Readonly


.. _property_OpcUaConnection_supportedUserTokenTypes:

.. index::
   single: supportedUserTokenTypes

supportedUserTokenTypes
+++++++++++++++++++++++

Please refer to the `Qt OPC UA Connection QML type <https://doc.qt.io/QtOPCUA/qml-qtopcua-connection.html#supportedUserTokenTypes-prop>`_ documentation.

:**› Attributes**: Readonly

Methods
*******


.. _method_OpcUaConnection_connectToEndpoint:

.. index::
   single: connectToEndpoint

connectToEndpoint(:ref:`QOpcUaEndpointDescription <enum_OpcUaConnection_QOpcUaEndpointDescription>` endpointDescription)
++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

Please refer to the `Qt OPC UA Connection QML type <https://doc.qt.io/QtOPCUA/qml-qtopcua-connection.html#connectToEndpoint-method>`_ documentation.



.. _method_OpcUaConnection_disconnectFromEndpoint:

.. index::
   single: disconnectFromEndpoint

disconnectFromEndpoint()
++++++++++++++++++++++++

Please refer to the `Qt OPC UA Connection QML type <https://doc.qt.io/QtOPCUA/qml-qtopcua-connection.html#disconnectFromEndpoint-method>`_ documentation.



.. _method_OpcUaConnection_readNodeAttributes:

.. index::
   single: readNodeAttributes

readNodeAttributes(JSValue value)
+++++++++++++++++++++++++++++++++

Please refer to the `Qt OPC UA Connection QML type <https://doc.qt.io/QtOPCUA/qml-qtopcua-connection.html#readNodeAttributes-method>`_ documentation.

:**› Returns**: Boolean



.. _method_OpcUaConnection_writeNodeAttributes:

.. index::
   single: writeNodeAttributes

writeNodeAttributes(JSValue value)
++++++++++++++++++++++++++++++++++

Please refer to the `Qt OPC UA Connection QML type <https://doc.qt.io/QtOPCUA/qml-qtopcua-connection.html#writeNodeAttributes-method>`_ documentation.

:**› Returns**: Boolean


Signals
*******


.. _signal_OpcUaConnection_readNodeAttributesFinished:

.. index::
   single: readNodeAttributesFinished

readNodeAttributesFinished(Variant value)
+++++++++++++++++++++++++++++++++++++++++

Please refer to the `Qt OPC UA Connection QML type <https://doc.qt.io/QtOPCUA/qml-qtopcua-connection.html#readNodeAttributesFinished-signal>`_ documentation.



.. _signal_OpcUaConnection_writeNodeAttributesFinished:

.. index::
   single: writeNodeAttributesFinished

writeNodeAttributesFinished(Variant value)
++++++++++++++++++++++++++++++++++++++++++

Please refer to the `Qt OPC UA Connection QML type <https://doc.qt.io/QtOPCUA/qml-qtopcua-connection.html#writeNodeAttributesFinished-signal>`_ documentation.


