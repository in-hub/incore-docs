
.. _object_HttpAuthentication:


:index:`HttpAuthentication`
---------------------------

Description
***********

The HttpAuthentication object a helper class to encupsulate user credentials for authentication of a :ref:`HttpResponse <object_HttpResponse>`.

This object was introduced in InCore 2.7.

:**› Inherits**: :ref:`Object <object_Object>`

Overview
********

Properties
++++++++++

.. hlist::
  :columns: 1

  * :ref:`password <property_HttpAuthentication_password>`
  * :ref:`realm <property_HttpAuthentication_realm>`
  * :ref:`user <property_HttpAuthentication_user>`
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


.. _property_HttpAuthentication_password:

.. _signal_HttpAuthentication_passwordChanged:

.. index::
   single: password

password
++++++++

This property holds the username to use for authentication.

This property was introduced in InCore 2.7.

:**› Type**: String
:**› Signal**: passwordChanged()
:**› Attributes**: Writable


.. _property_HttpAuthentication_realm:

.. _signal_HttpAuthentication_realmChanged:

.. index::
   single: realm

realm
+++++

This property holds the realm requiring authentication.

This property was introduced in InCore 2.7.

:**› Type**: String
:**› Signal**: realmChanged()
:**› Attributes**: Readonly


.. _property_HttpAuthentication_user:

.. _signal_HttpAuthentication_userChanged:

.. index::
   single: user

user
++++

This property holds the password to use for authentication.

This property was introduced in InCore 2.7.

:**› Type**: String
:**› Signal**: userChanged()
:**› Attributes**: Writable

