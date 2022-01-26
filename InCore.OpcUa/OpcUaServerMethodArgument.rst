
.. _object_OpcUaServerMethodArgument:


:index:`OpcUaServerMethodArgument`
----------------------------------

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

  * :ref:`description <property_OpcUaServerMethodArgument_description>`
  * :ref:`name <property_OpcUaServerMethodArgument_name>`
  * :ref:`type <property_OpcUaServerMethodArgument_type>`
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


.. _property_OpcUaServerMethodArgument_description:

.. _signal_OpcUaServerMethodArgument_descriptionChanged:

.. index::
   single: description

description
+++++++++++



:**› Type**: :ref:`OpcUaLocalizedText <object_OpcUaLocalizedText>`
:**› Signal**: descriptionChanged()
:**› Attributes**: Readonly


.. _property_OpcUaServerMethodArgument_name:

.. _signal_OpcUaServerMethodArgument_nameChanged:

.. index::
   single: name

name
++++



:**› Type**: String
:**› Signal**: nameChanged()
:**› Attributes**: Writable


.. _property_OpcUaServerMethodArgument_type:

.. _signal_OpcUaServerMethodArgument_typeChanged:

.. index::
   single: type

type
++++



:**› Type**: :ref:`OpcUaType.Type <enum_OpcUaType_Type>`
:**› Default**: :ref:`OpcUaType.Undefined <enumitem_OpcUaType_Undefined>`
:**› Signal**: typeChanged()
:**› Attributes**: Writable

Example
*******
See :ref:`OpcUaServer example <example_OpcUaServer>` on how to use OpcUaServerMethodArgument.
