
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

  * :ref:`password <property_SmtpConfiguration_password>`
  * :ref:`port <property_SmtpConfiguration_port>`
  * :ref:`senderHostname <property_SmtpConfiguration_senderHostname>`
  * :ref:`server <property_SmtpConfiguration_server>`
  * :ref:`tls <property_SmtpConfiguration_tls>`
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



Properties
**********


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


.. _property_SmtpConfiguration_tls:

.. _signal_SmtpConfiguration_tlsChanged:

.. index::
   single: tls

tls
+++

This property holds whether to encrypt the connection to the SMTP server via TLS. TLS support should only be disabled in special cases, i.e. when using an internal SMTP relay which does not require authentication. Otherwise username and password are sent unencrypted over the network.

:**› Type**: Boolean
:**› Default**: ``true``
:**› Signal**: tlsChanged()
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

Example
*******
See :ref:`Mail example <example_Mail>` on how to use SmtpConfiguration.
