
.. _object_ConfigurationItem:


:index:`ConfigurationItem`
--------------------------

Description
***********

The ConfigurationItem object contains one setting. :ref:`DataObject.name <property_DataObject_name>` will be printed as description. :ref:`DataObject.dataType <property_DataObject_dataType>` defines how the data is treated. :ref:`DataObject.view <property_DataObject_view>` contains additional properties to control for example if the element is hidden.

:**› Inherits**: :ref:`DataObject <object_DataObject>`

Overview
********

Properties
++++++++++

.. hlist::
  :columns: 2

  * :ref:`serializationDisabled <property_ConfigurationItem_serializationDisabled>`
  * :ref:`DataObject.data <property_DataObject_data>`
  * :ref:`DataObject.dataType <property_DataObject_dataType>`
  * :ref:`DataObject.description <property_DataObject_description>`
  * :ref:`DataObject.name <property_DataObject_name>`
  * :ref:`DataObject.timestamp <property_DataObject_timestamp>`
  * :ref:`DataObject.uuid <property_DataObject_uuid>`
  * :ref:`DataObject.view <property_DataObject_view>`
  * :ref:`Object.objectId <property_Object_objectId>`
  * :ref:`Object.parent <property_Object_parent>`

Methods
+++++++

.. hlist::
  :columns: 1

  * :ref:`DataObject.touch() <method_DataObject_touch>`
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

  * :ref:`DataObject.DataType <enum_DataObject_DataType>`



Properties
**********


.. _property_ConfigurationItem_serializationDisabled:

.. _signal_ConfigurationItem_serializationDisabledChanged:

.. index::
   single: serializationDisabled

serializationDisabled
+++++++++++++++++++++

This property holds whether the item is excluded from data serialization and deserialization. This can be used to override predefined configuration properties to be controlled programmatically instead of a user interface (view).

:**› Type**: Boolean
:**› Default**: ``false``
:**› Signal**: serializationDisabledChanged()
:**› Attributes**: Writable

