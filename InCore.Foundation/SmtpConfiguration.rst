
.. _object_SmtpConfiguration:


:index:`SmtpConfiguration`
--------------------------

Description
***********

The SmtpConfiguration object contains all properties required for sending a :ref:`Mail <object_Mail>` object via an SMTP server.

:**› Inherits**: :ref:`Object <object_Object>`

Overview
********

Properties
++++++++++

.. hlist::
  :columns: 2

  * :ref:`authenticationMethod <property_SmtpConfiguration_authenticationMethod>`
  * :ref:`encryptionMode <property_SmtpConfiguration_encryptionMode>`
  * :ref:`password <property_SmtpConfiguration_password>`
  * :ref:`port <property_SmtpConfiguration_port>`
  * :ref:`senderHostname <property_SmtpConfiguration_senderHostname>`
  * :ref:`server <property_SmtpConfiguration_server>`
  * :ref:`username <property_SmtpConfiguration_username>`
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

  * :ref:`Object.completed() <signal_Object_completed>`

Enumerations
++++++++++++

.. hlist::
  :columns: 1

  * :ref:`AuthMethod <enum_SmtpConfiguration_AuthMethod>`
  * :ref:`EncryptionMode <enum_SmtpConfiguration_EncryptionMode>`



Properties
**********


.. _property_SmtpConfiguration_authenticationMethod:

.. _signal_SmtpConfiguration_authenticationMethodChanged:

.. index::
   single: authenticationMethod

authenticationMethod
++++++++++++++++++++

This property holds the method to use when authenticating against the SMTP server.

This property was introduced in InCore 2.7.

:**› Type**: :ref:`AuthMethod <enum_SmtpConfiguration_AuthMethod>`
:**› Default**: :ref:`SmtpConfiguration.AuthNone <enumitem_SmtpConfiguration_AuthNone>`
:**› Signal**: authenticationMethodChanged()
:**› Attributes**: Writable


.. _property_SmtpConfiguration_encryptionMode:

.. _signal_SmtpConfiguration_encryptionModeChanged:

.. index::
   single: encryptionMode

encryptionMode
++++++++++++++

This property holds the encryption type to use when connection to the SMTP server. Encryption should only be disabled in special cases, i.e. when using an internal SMTP relay which does not require authentication. Otherwise username and password are sent unencrypted over the network.

This property was introduced in InCore 2.9.

:**› Type**: :ref:`EncryptionMode <enum_SmtpConfiguration_EncryptionMode>`
:**› Default**: :ref:`SmtpConfiguration.EncryptTLS <enumitem_SmtpConfiguration_EncryptTLS>`
:**› Signal**: encryptionModeChanged()
:**› Attributes**: Writable


.. _property_SmtpConfiguration_password:

.. _signal_SmtpConfiguration_passwordChanged:

.. index::
   single: password

password
++++++++

This property holds the password used for authenticating against the SMTP server.

:**› Type**: String
:**› Signal**: passwordChanged()
:**› Attributes**: Writable


.. _property_SmtpConfiguration_port:

.. _signal_SmtpConfiguration_portChanged:

.. index::
   single: port

port
++++

This property holds the TCP port of the SMTP server.

:**› Type**: SignedInteger
:**› Default**: ``25``
:**› Signal**: portChanged()
:**› Attributes**: Writable


.. _property_SmtpConfiguration_senderHostname:

.. _signal_SmtpConfiguration_senderHostnameChanged:

.. index::
   single: senderHostname

senderHostname
++++++++++++++

This property holds the hostname of the sender (i.e. the sending device). It is sent to the SMTP for informational purposes but may be used for anti-spam mechanisms as well. For this reason it's advisable to set a valid and publicly resolvable hostname when talking to public SMTP servers.

:**› Type**: String
:**› Signal**: senderHostnameChanged()
:**› Attributes**: Writable


.. _property_SmtpConfiguration_server:

.. _signal_SmtpConfiguration_serverChanged:

.. index::
   single: server

server
++++++

This property holds the hostname of the SMTP server to use for sending mails.

:**› Type**: String
:**› Signal**: serverChanged()
:**› Attributes**: Writable


.. _property_SmtpConfiguration_username:

.. _signal_SmtpConfiguration_usernameChanged:

.. index::
   single: username

username
++++++++

This property holds the username used for authenticating against the SMTP server.

:**› Type**: String
:**› Signal**: usernameChanged()
:**› Attributes**: Writable

Enumerations
************


.. _enum_SmtpConfiguration_AuthMethod:

.. index::
   single: AuthMethod

AuthMethod
++++++++++

This enumeration describes supported methods for authenticating against an SMTP server.

This enumeration was introduced in InCore 2.7.

.. index::
   single: SmtpConfiguration.AuthNone
.. index::
   single: SmtpConfiguration.AuthPlain
.. index::
   single: SmtpConfiguration.AuthLogin
.. index::
   single: SmtpConfiguration.AuthCramMd5
.. list-table::
  :widths: auto
  :header-rows: 1

  * - Name
    - Value
    - Description

      .. _enumitem_SmtpConfiguration_AuthNone:
  * - ``SmtpConfiguration.AuthNone``
    - ``0``
    - 

      .. _enumitem_SmtpConfiguration_AuthPlain:
  * - ``SmtpConfiguration.AuthPlain``
    - ``1``
    - 

      .. _enumitem_SmtpConfiguration_AuthLogin:
  * - ``SmtpConfiguration.AuthLogin``
    - ``2``
    - 

      .. _enumitem_SmtpConfiguration_AuthCramMd5:
  * - ``SmtpConfiguration.AuthCramMd5``
    - ``3``
    - 


.. _enum_SmtpConfiguration_EncryptionMode:

.. index::
   single: EncryptionMode

EncryptionMode
++++++++++++++



.. index::
   single: SmtpConfiguration.EncryptNone
.. index::
   single: SmtpConfiguration.EncryptSSL
.. index::
   single: SmtpConfiguration.EncryptTLS
.. list-table::
  :widths: auto
  :header-rows: 1

  * - Name
    - Value
    - Description

      .. _enumitem_SmtpConfiguration_EncryptNone:
  * - ``SmtpConfiguration.EncryptNone``
    - ``0``
    - 

      .. _enumitem_SmtpConfiguration_EncryptSSL:
  * - ``SmtpConfiguration.EncryptSSL``
    - ``1``
    - 

      .. _enumitem_SmtpConfiguration_EncryptTLS:
  * - ``SmtpConfiguration.EncryptTLS``
    - ``2``
    - 

Example
*******
See :ref:`Mail example <example_Mail>` on how to use SmtpConfiguration.
