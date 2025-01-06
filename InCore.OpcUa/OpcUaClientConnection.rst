
.. _object_OpcUaClientConnection:


:index:`OpcUaClientConnection`
------------------------------

Description
***********



:**› Inherits**: :ref:`OpcUaConnection <object_OpcUaConnection>`

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

  * :ref:`connectToEndpoint() <method_OpcUaClientConnection_connectToEndpoint>`
  * :ref:`setAnonymousAuthentication() <method_OpcUaClientConnection_setAnonymousAuthentication>`
  * :ref:`setCertificateAuthentication() <method_OpcUaClientConnection_setCertificateAuthentication>`
  * :ref:`setUsernameAuthentication() <method_OpcUaClientConnection_setUsernameAuthentication>`
  * :ref:`setupEncryption() <method_OpcUaClientConnection_setupEncryption>`
  * `connectToEndpoint <https://doc.qt.io/QtOPCUA/qml-qtopcua-connection.html#connectToEndpoint-method>`_
  * `disconnectFromEndpoint <https://doc.qt.io/QtOPCUA/qml-qtopcua-connection.html#disconnectFromEndpoint-method>`_
  * `readNodeAttributes <https://doc.qt.io/QtOPCUA/qml-qtopcua-connection.html#readNodeAttributes-method>`_
  * `setAuthenticationInformation <https://doc.qt.io/QtOPCUA/qml-qtopcua-connection.html#setAuthenticationInformation-method>`_
  * `setConnection <https://doc.qt.io/QtOPCUA/qml-qtopcua-connection.html#setConnection-method>`_
  * `setDefaultConnection <https://doc.qt.io/QtOPCUA/qml-qtopcua-connection.html#setDefaultConnection-method>`_
  * `writeNodeAttributes <https://doc.qt.io/QtOPCUA/qml-qtopcua-connection.html#writeNodeAttributes-method>`_

Signals
+++++++

.. hlist::
  :columns: 1

  * `readNodeAttributesFinished <https://doc.qt.io/QtOPCUA/qml-qtopcua-connection.html#readNodeAttributesFinished-signal>`_
  * `writeNodeAttributesFinished <https://doc.qt.io/QtOPCUA/qml-qtopcua-connection.html#writeNodeAttributesFinished-signal>`_

Enumerations
++++++++++++

.. hlist::
  :columns: 1

  * :ref:`MessageSecurityMode <enum_OpcUaClientConnection_MessageSecurityMode>`



Properties
**********

Methods
*******


.. _method_OpcUaClientConnection_connectToEndpoint:

.. index::
   single: connectToEndpoint

connectToEndpoint(String endpointUrl, :ref:`MessageSecurityMode <enum_OpcUaClientConnection_MessageSecurityMode>` securityMode, String securityPolicy)
++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++





.. _method_OpcUaClientConnection_setAnonymousAuthentication:

.. index::
   single: setAnonymousAuthentication

setAnonymousAuthentication()
++++++++++++++++++++++++++++

This method sets the authentication type to anonymous authentication. This is the default authentication type and usually does not have to be set explicitly.

This method was introduced in InCore 2.7.



.. _method_OpcUaClientConnection_setCertificateAuthentication:

.. index::
   single: setCertificateAuthentication

setCertificateAuthentication(ArrayBuffer clientCertData, ArrayBuffer clientPrivateKeyData)
++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++





.. _method_OpcUaClientConnection_setUsernameAuthentication:

.. index::
   single: setUsernameAuthentication

setUsernameAuthentication(String username, String password)
+++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

This method sets the authentication type to user authentication and authenticates with given username and password.

This method was introduced in InCore 2.7.



.. _method_OpcUaClientConnection_setupEncryption:

.. index::
   single: setupEncryption

setupEncryption(ArrayBuffer clientCertificateData, String privateKeyData, ArrayBuffer trustedCertificateData, Boolean verifyServerCertificate)
++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

This method sets up connection encryption using the supplied X509 client certificate as well as the private key (the latter one in PEM format). The CA or server certificate has to be passed as trusted certificate, otherwise the client will not accept any server certificate.

This method was introduced in InCore 2.7.

:**› Returns**: Boolean


Enumerations
************


.. _enum_OpcUaClientConnection_MessageSecurityMode:

.. index::
   single: MessageSecurityMode

MessageSecurityMode
+++++++++++++++++++



.. index::
   single: OpcUaClientConnection.Invalid
.. index::
   single: OpcUaClientConnection.None
.. index::
   single: OpcUaClientConnection.Sign
.. index::
   single: OpcUaClientConnection.SignAndEncrypt
.. list-table::
  :widths: auto
  :header-rows: 1

  * - Name
    - Value
    - Description

      .. _enumitem_OpcUaClientConnection_Invalid:
  * - ``OpcUaClientConnection.Invalid``
    - ``0``
    - 

      .. _enumitem_OpcUaClientConnection_None:
  * - ``OpcUaClientConnection.None``
    - ``1``
    - 

      .. _enumitem_OpcUaClientConnection_Sign:
  * - ``OpcUaClientConnection.Sign``
    - ``2``
    - 

      .. _enumitem_OpcUaClientConnection_SignAndEncrypt:
  * - ``OpcUaClientConnection.SignAndEncrypt``
    - ``3``
    - 

Example
*******
See :ref:`OpcUaClient example <example_OpcUaClient>` on how to use OpcUaClientConnection.
