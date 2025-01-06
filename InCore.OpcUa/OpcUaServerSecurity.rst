
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
  :columns: 3

  * :ref:`certificateFile <property_OpcUaServerSecurity_certificateFile>`
  * :ref:`nonDiscoveryAccessRequiresEncryption <property_OpcUaServerSecurity_nonDiscoveryAccessRequiresEncryption>`
  * :ref:`privateKeyFile <property_OpcUaServerSecurity_privateKeyFile>`
  * :ref:`secureChannelIssuerListFiles <property_OpcUaServerSecurity_secureChannelIssuerListFiles>`
  * :ref:`secureChannelRevocationListFiles <property_OpcUaServerSecurity_secureChannelRevocationListFiles>`
  * :ref:`secureChannelTrustListFiles <property_OpcUaServerSecurity_secureChannelTrustListFiles>`
  * :ref:`securityPolicies <property_OpcUaServerSecurity_securityPolicies>`
  * :ref:`sessionIssuerListFiles <property_OpcUaServerSecurity_sessionIssuerListFiles>`
  * :ref:`sessionRevocationListFiles <property_OpcUaServerSecurity_sessionRevocationListFiles>`
  * :ref:`sessionTrustListFiles <property_OpcUaServerSecurity_sessionTrustListFiles>`
  * :ref:`userLoginRequiresEncryption <property_OpcUaServerSecurity_userLoginRequiresEncryption>`
  * :ref:`userTokenPolicies <property_OpcUaServerSecurity_userTokenPolicies>`
  * :ref:`verifyApplicationUri <property_OpcUaServerSecurity_verifyApplicationUri>`
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

  * :ref:`SecurityPolicies <enum_OpcUaServerSecurity_SecurityPolicies>`
  * :ref:`UserTokenPolicies <enum_OpcUaServerSecurity_UserTokenPolicies>`



Properties
**********


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


.. _property_OpcUaServerSecurity_secureChannelIssuerListFiles:

.. _signal_OpcUaServerSecurity_secureChannelIssuerListFilesChanged:

.. index::
   single: secureChannelIssuerListFiles

secureChannelIssuerListFiles
++++++++++++++++++++++++++++

This property holds paths to one or multiple issuer list file used for security policies other than :ref:`OpcUaServerSecurity.PolicyNone <enumitem_OpcUaServerSecurity_PolicyNone>`.

:**› Type**: StringList
:**› Signal**: secureChannelIssuerListFilesChanged()
:**› Attributes**: Writable


.. _property_OpcUaServerSecurity_secureChannelRevocationListFiles:

.. _signal_OpcUaServerSecurity_secureChannelRevocationListFilesChanged:

.. index::
   single: secureChannelRevocationListFiles

secureChannelRevocationListFiles
++++++++++++++++++++++++++++++++

This property holds paths to one or multiple revocation list file used for security policies other than :ref:`OpcUaServerSecurity.PolicyNone <enumitem_OpcUaServerSecurity_PolicyNone>`.

:**› Type**: StringList
:**› Signal**: secureChannelRevocationListFilesChanged()
:**› Attributes**: Writable


.. _property_OpcUaServerSecurity_secureChannelTrustListFiles:

.. _signal_OpcUaServerSecurity_secureChannelTrustListFilesChanged:

.. index::
   single: secureChannelTrustListFiles

secureChannelTrustListFiles
+++++++++++++++++++++++++++

This property holds paths to one or multiple trust list file used for security policies other than :ref:`OpcUaServerSecurity.PolicyNone <enumitem_OpcUaServerSecurity_PolicyNone>`.

:**› Type**: StringList
:**› Signal**: secureChannelTrustListFilesChanged()
:**› Attributes**: Writable


.. _property_OpcUaServerSecurity_securityPolicies:

.. _signal_OpcUaServerSecurity_securityPoliciesChanged:

.. index::
   single: securityPolicies

securityPolicies
++++++++++++++++

This property holds the security policies to enable.

:**› Type**: :ref:`SecurityPolicies <enum_OpcUaServerSecurity_SecurityPolicies>`
:**› Default**: :ref:`OpcUaServerSecurity.SecurityPolicyNone <enumitem_OpcUaServerSecurity_SecurityPolicyNone>`
:**› Signal**: securityPoliciesChanged()
:**› Attributes**: Writable


.. _property_OpcUaServerSecurity_sessionIssuerListFiles:

.. _signal_OpcUaServerSecurity_sessionIssuerListFilesChanged:

.. index::
   single: sessionIssuerListFiles

sessionIssuerListFiles
++++++++++++++++++++++

This property holds paths to one or multiple issuer list file used for the user token policy :ref:`OpcUaServerSecurity.UserTokenPolicyCertificate <enumitem_OpcUaServerSecurity_UserTokenPolicyCertificate>`.

:**› Type**: StringList
:**› Signal**: sessionIssuerListFilesChanged()
:**› Attributes**: Writable


.. _property_OpcUaServerSecurity_sessionRevocationListFiles:

.. _signal_OpcUaServerSecurity_sessionRevocationListFilesChanged:

.. index::
   single: sessionRevocationListFiles

sessionRevocationListFiles
++++++++++++++++++++++++++

This property holds paths to one or multiple revocation list file used for the user token policy :ref:`OpcUaServerSecurity.UserTokenPolicyCertificate <enumitem_OpcUaServerSecurity_UserTokenPolicyCertificate>`.

:**› Type**: StringList
:**› Signal**: sessionRevocationListFilesChanged()
:**› Attributes**: Writable


.. _property_OpcUaServerSecurity_sessionTrustListFiles:

.. _signal_OpcUaServerSecurity_sessionTrustListFilesChanged:

.. index::
   single: sessionTrustListFiles

sessionTrustListFiles
+++++++++++++++++++++

This property holds paths to one or multiple trust list file used for the user token policy :ref:`OpcUaServerSecurity.UserTokenPolicyCertificate <enumitem_OpcUaServerSecurity_UserTokenPolicyCertificate>`.

:**› Type**: StringList
:**› Signal**: sessionTrustListFilesChanged()
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


.. _property_OpcUaServerSecurity_userTokenPolicies:

.. _signal_OpcUaServerSecurity_userTokenPoliciesChanged:

.. index::
   single: userTokenPolicies

userTokenPolicies
+++++++++++++++++

This property holds the user token policies to enable.

This property was introduced in InCore 2.8.

:**› Type**: :ref:`UserTokenPolicies <enum_OpcUaServerSecurity_UserTokenPolicies>`
:**› Default**: :ref:`OpcUaServerSecurity.UserTokenPolicyAnonymous <enumitem_OpcUaServerSecurity_UserTokenPolicyAnonymous>`
:**› Signal**: userTokenPoliciesChanged()
:**› Attributes**: Writable


.. _property_OpcUaServerSecurity_verifyApplicationUri:

.. _signal_OpcUaServerSecurity_verifyApplicationUriChanged:

.. index::
   single: verifyApplicationUri

verifyApplicationUri
++++++++++++++++++++

This property holds whether the the server should verify if the client's application URI has a corresponding URI entry in the client certificate's subject alternative name.

This property was introduced in InCore 2.8.

:**› Type**: Boolean
:**› Default**: ``true``
:**› Signal**: verifyApplicationUriChanged()
:**› Attributes**: Writable

Enumerations
************


.. _enum_OpcUaServerSecurity_SecurityPolicies:

.. index::
   single: SecurityPolicies

SecurityPolicies
++++++++++++++++



.. index::
   single: OpcUaServerSecurity.SecurityPolicyNone
.. index::
   single: OpcUaServerSecurity.SecurityPolicyBasic256Sha256
.. index::
   single: OpcUaServerSecurity.SecurityPolicyAes128Sha256RsaOaep
.. index::
   single: OpcUaServerSecurity.SecurityPolicyAes256Sha256RsaPss
.. list-table::
  :widths: auto
  :header-rows: 1

  * - Name
    - Value
    - Description

      .. _enumitem_OpcUaServerSecurity_SecurityPolicyNone:
  * - ``OpcUaServerSecurity.SecurityPolicyNone``
    - ``1``
    - 

      .. _enumitem_OpcUaServerSecurity_SecurityPolicyBasic256Sha256:
  * - ``OpcUaServerSecurity.SecurityPolicyBasic256Sha256``
    - ``2``
    - 

      .. _enumitem_OpcUaServerSecurity_SecurityPolicyAes128Sha256RsaOaep:
  * - ``OpcUaServerSecurity.SecurityPolicyAes128Sha256RsaOaep``
    - ``4``
    - 

      .. _enumitem_OpcUaServerSecurity_SecurityPolicyAes256Sha256RsaPss:
  * - ``OpcUaServerSecurity.SecurityPolicyAes256Sha256RsaPss``
    - ``8``
    - 


.. _enum_OpcUaServerSecurity_UserTokenPolicies:

.. index::
   single: UserTokenPolicies

UserTokenPolicies
+++++++++++++++++



.. index::
   single: OpcUaServerSecurity.UserTokenPolicyAnonymous
.. index::
   single: OpcUaServerSecurity.UserTokenPolicyUsername
.. index::
   single: OpcUaServerSecurity.UserTokenPolicyCertificate
.. list-table::
  :widths: auto
  :header-rows: 1

  * - Name
    - Value
    - Description

      .. _enumitem_OpcUaServerSecurity_UserTokenPolicyAnonymous:
  * - ``OpcUaServerSecurity.UserTokenPolicyAnonymous``
    - ``1``
    - 

      .. _enumitem_OpcUaServerSecurity_UserTokenPolicyUsername:
  * - ``OpcUaServerSecurity.UserTokenPolicyUsername``
    - ``2``
    - 

      .. _enumitem_OpcUaServerSecurity_UserTokenPolicyCertificate:
  * - ``OpcUaServerSecurity.UserTokenPolicyCertificate``
    - ``4``
    - 

Example
*******
See :ref:`OpcUaServer example <example_OpcUaServer>` on how to use OpcUaServerSecurity.
