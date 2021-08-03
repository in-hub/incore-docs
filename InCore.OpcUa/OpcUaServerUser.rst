
.. _object_OpcUaServerUser:


:index:`OpcUaServerUser`
------------------------

Description
***********



This object was introduced in InCore 2.3.

:**› Inherits**: :ref:`Object <object_Object>`

Overview
********

Properties
++++++++++

.. hlist::
  :columns: 1

  * :ref:`name <property_OpcUaServerUser_name>`
  * :ref:`password <property_OpcUaServerUser_password>`
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



Properties
**********


.. _property_OpcUaServerUser_name:

.. _signal_OpcUaServerUser_nameChanged:

.. index::
   single: name

name
++++

This property holds the name of the OPC UA server user.

:**› Type**: String
:**› Signal**: nameChanged()
:**› Attributes**: Writable


.. _property_OpcUaServerUser_password:

.. _signal_OpcUaServerUser_passwordChanged:

.. index::
   single: password

password
++++++++

This property holds the password of the OPC UA server user.

:**› Type**: String
:**› Signal**: passwordChanged()
:**› Attributes**: Writable

