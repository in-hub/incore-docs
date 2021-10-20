
.. _object_OpcUaServerSecurity:


:index:`OpcUaServerSecurity`
----------------------------

Description
***********



This object was introduced in InCore 2.3.

:**› Inherits**: :ref:`Object <object_Object>`

Overview
********

Properties
++++++++++

.. hlist::
  :columns: 2

  * :ref:`anonymousLoginAllowed <property_OpcUaServerSecurity_anonymousLoginAllowed>`
  * :ref:`certificateFile <property_OpcUaServerSecurity_certificateFile>`
  * :ref:`issuerListFiles <property_OpcUaServerSecurity_issuerListFiles>`
  * :ref:`nonDiscoveryAccessRequiresEncryption <property_OpcUaServerSecurity_nonDiscoveryAccessRequiresEncryption>`
  * :ref:`policies <property_OpcUaServerSecurity_policies>`
  * :ref:`privateKeyFile <property_OpcUaServerSecurity_privateKeyFile>`
  * :ref:`revocationListFiles <property_OpcUaServerSecurity_revocationListFiles>`
  * :ref:`trustListFiles <property_OpcUaServerSecurity_trustListFiles>`
  * :ref:`userLoginRequiresEncryption <property_OpcUaServerSecurity_userLoginRequiresEncryption>`
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

  * :ref:`Object.completed() <signal_Object_completed>`

Enumerations
++++++++++++

.. hlist::
  :columns: 1

  * :ref:`Policies <enum_OpcUaServerSecurity_Policies>`



Properties
**********


.. _property_OpcUaServerSecurity_anonymousLoginAllowed:

.. _signal_OpcUaServerSecurity_anonymousLoginAllowedChanged:

.. index::
   single: anonymousLoginAllowed

anonymousLoginAllowed
+++++++++++++++++++++

This property holds whether to allow anonymous logins, i.e. without username and password.

:**› Type**: Boolean
:**› Default**: ``true``
:**› Signal**: anonymousLoginAllowedChanged()
:**› Attributes**: Writable


.. _property_OpcUaServerSecurity_certificateFile:

.. _signal_OpcUaServerSecurity_certificateFileChanged:

.. index::
   single: certificateFile

certificateFile
+++++++++++++++

This property holds the path to the certificate file used for security policies other than :ref:`OpcUaServerSecurity.PolicyNone <enumitem_OpcUaServerSecurity_PolicyNone>`.

:**› Type**: String
:**› Signal**: certificateFileChanged()
:**› Attributes**: Writable


.. _property_OpcUaServerSecurity_issuerListFiles:

.. _signal_OpcUaServerSecurity_issuerListFilesChanged:

.. index::
   single: issuerListFiles

issuerListFiles
+++++++++++++++

This property holds paths to one or multiple issuer list file used for security policies other than :ref:`OpcUaServerSecurity.PolicyNone <enumitem_OpcUaServerSecurity_PolicyNone>`.

:**› Type**: StringList
:**› Signal**: issuerListFilesChanged()
:**› Attributes**: Writable


.. _property_OpcUaServerSecurity_nonDiscoveryAccessRequiresEncryption:

.. _signal_OpcUaServerSecurity_nonDiscoveryAccessRequiresEncryptionChanged:

.. index::
   single: nonDiscoveryAccessRequiresEncryption

nonDiscoveryAccessRequiresEncryption
++++++++++++++++++++++++++++++++++++

This property holds whether the access to services other than the discovery service requires a security policy other than :ref:`OpcUaServerSecurity.PolicyNone <enumitem_OpcUaServerSecurity_PolicyNone>`.

:**› Type**: Boolean
:**› Default**: ``false``
:**› Signal**: nonDiscoveryAccessRequiresEncryptionChanged()
:**› Attributes**: Writable


.. _property_OpcUaServerSecurity_policies:

.. _signal_OpcUaServerSecurity_policiesChanged:

.. index::
   single: policies

policies
++++++++

This property holds the security policies to enable.

:**› Type**: :ref:`Policies <enum_OpcUaServerSecurity_Policies>`
:**› Default**: :ref:`OpcUaServerSecurity.PolicyNone <enumitem_OpcUaServerSecurity_PolicyNone>`
:**› Signal**: policiesChanged()
:**› Attributes**: Writable


.. _property_OpcUaServerSecurity_privateKeyFile:

.. _signal_OpcUaServerSecurity_privateKeyFileChanged:

.. index::
   single: privateKeyFile

privateKeyFile
++++++++++++++

This property holds the path to the private key file used for security policies other than :ref:`OpcUaServerSecurity.PolicyNone <enumitem_OpcUaServerSecurity_PolicyNone>`.

:**› Type**: String
:**› Signal**: privateKeyFileChanged()
:**› Attributes**: Writable


.. _property_OpcUaServerSecurity_revocationListFiles:

.. _signal_OpcUaServerSecurity_revocationListFilesChanged:

.. index::
   single: revocationListFiles

revocationListFiles
+++++++++++++++++++

This property holds paths to one or multiple revocation list file used for security policies other than :ref:`OpcUaServerSecurity.PolicyNone <enumitem_OpcUaServerSecurity_PolicyNone>`.

:**› Type**: StringList
:**› Signal**: revocationListFilesChanged()
:**› Attributes**: Writable


.. _property_OpcUaServerSecurity_trustListFiles:

.. _signal_OpcUaServerSecurity_trustListFilesChanged:

.. index::
   single: trustListFiles

trustListFiles
++++++++++++++

This property holds paths to one or multiple trust list file used for security policies other than :ref:`OpcUaServerSecurity.PolicyNone <enumitem_OpcUaServerSecurity_PolicyNone>`.

:**› Type**: StringList
:**› Signal**: trustListFilesChanged()
:**› Attributes**: Writable


.. _property_OpcUaServerSecurity_userLoginRequiresEncryption:

.. _signal_OpcUaServerSecurity_userLoginRequiresEncryptionChanged:

.. index::
   single: userLoginRequiresEncryption

userLoginRequiresEncryption
+++++++++++++++++++++++++++

This property holds whether to allow user logins for unencrypted connections, i.e. clients connecting with :ref:`OpcUaServerSecurity.PolicyNone <enumitem_OpcUaServerSecurity_PolicyNone>`.

:**› Type**: Boolean
:**› Default**: ``true``
:**› Signal**: userLoginRequiresEncryptionChanged()
:**› Attributes**: Writable

Enumerations
************


.. _enum_OpcUaServerSecurity_Policies:

.. index::
   single: Policies

Policies
++++++++



.. index::
   single: OpcUaServerSecurity.PolicyNone
.. index::
   single: OpcUaServerSecurity.PolicyBasic256Sha256
.. index::
   single: OpcUaServerSecurity.PolicyAes128Sha256RsaOaep
.. list-table::
  :widths: auto
  :header-rows: 1

  * - Name
    - Value
    - Description

      .. _enumitem_OpcUaServerSecurity_PolicyNone:
  * - ``OpcUaServerSecurity.PolicyNone``
    - ``1``
    - 

      .. _enumitem_OpcUaServerSecurity_PolicyBasic256Sha256:
  * - ``OpcUaServerSecurity.PolicyBasic256Sha256``
    - ``2``
    - 

      .. _enumitem_OpcUaServerSecurity_PolicyAes128Sha256RsaOaep:
  * - ``OpcUaServerSecurity.PolicyAes128Sha256RsaOaep``
    - ``4``
    - 

Example
*******
See :ref:`OpcUaServer example <example_OpcUaServer>` on how to use OpcUaServerSecurity.
