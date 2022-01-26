
.. _object_MailAddress:


:index:`MailAddress`
--------------------

Description
***********

The MailAddress object holds properties for representing a well-formed e-mail address made up of a :ref:`name <property_MailAddress_name>` and an :ref:`address <property_MailAddress_address>`.

:**› Inherits**: :ref:`Object <object_Object>`

Overview
********

Properties
++++++++++

.. hlist::
  :columns: 1

  * :ref:`address <property_MailAddress_address>`
  * :ref:`name <property_MailAddress_name>`
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


.. _property_MailAddress_address:

.. _signal_MailAddress_addressChanged:

.. index::
   single: address

address
+++++++

This property holds the address used as sender or recipient. If the property :ref:`name <property_MailAddress_name>` is not empty it will be concatenated to *:ref:`name <property_MailAddress_name>` <:ref:`address <property_MailAddress_address>`>*.

:**› Type**: String
:**› Signal**: addressChanged()
:**› Attributes**: Writable


.. _property_MailAddress_name:

.. _signal_MailAddress_nameChanged:

.. index::
   single: name

name
++++

This property holds the name of the address. This usually contains the full name or a nick name.

:**› Type**: String
:**› Signal**: nameChanged()
:**› Attributes**: Writable, Optional

Example
*******
See :ref:`Mail example <example_Mail>` on how to use MailAddress.
