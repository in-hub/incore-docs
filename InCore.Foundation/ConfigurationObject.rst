
.. _object_ConfigurationObject:


:index:`ConfigurationObject`
----------------------------

Description
***********

The ConfigurationObject object contains the middle layer of the configuration hierarchy. It encapsulates :ref:`ConfigurationItem <object_ConfigurationItem>` objects which represent the actual settings.

:**› Inherits**: :ref:`Object <object_Object>`
:**› Inherited by**: :ref:`GeneralApplicationSettings <object_GeneralApplicationSettings>`, :ref:`GeneralSystemSettings <object_GeneralSystemSettings>`, :ref:`NetworkInterface <object_NetworkInterface>`

Overview
********

Properties
++++++++++

.. hlist::
  :columns: 1

  * :ref:`items <property_ConfigurationObject_items>`
  * :ref:`name <property_ConfigurationObject_name>`
  * :ref:`nameItem <property_ConfigurationObject_nameItem>`
  * :ref:`Object.objectId <property_Object_objectId>`
  * :ref:`Object.parent <property_Object_parent>`

Methods
+++++++

.. hlist::
  :columns: 1

  * :ref:`Object.fromJson() <method_Object_fromJson>`
  * :ref:`Object.toJson() <method_Object_toJson>`

Signals
+++++++

.. hlist::
  :columns: 1

  * :ref:`itemsDataChanged() <signal_ConfigurationObject_itemsDataChanged>`
  * :ref:`Object.completed() <signal_Object_completed>`



Properties
**********


.. _property_ConfigurationObject_items:

.. _signal_ConfigurationObject_itemsChanged:

.. index::
   single: items

items
+++++

This property holds a list of :ref:`ConfigurationItem <object_ConfigurationItem>` objects which represent the actual settings.

:**› Type**: :ref:`List <object_List>`\<:ref:`ConfigurationItem <object_ConfigurationItem>`>
:**› Signal**: itemsChanged()
:**› Attributes**: Readonly


.. _property_ConfigurationObject_name:

.. _signal_ConfigurationObject_nameChanged:

.. index::
   single: name

name
++++

This property holds the name of this configuration subgroup. It is printed as headline in Fluentum.

:**› Type**: String
:**› Signal**: nameChanged()
:**› Attributes**: Writable


.. _property_ConfigurationObject_nameItem:

.. index::
   single: nameItem

nameItem
++++++++

This property holds an internal :ref:`ConfigurationItem <object_ConfigurationItem>` instance for the :ref:`name <property_ConfigurationObject_name>` property.

:**› Type**: :ref:`ConfigurationItem <object_ConfigurationItem>`
:**› Attributes**: Readonly

Signals
*******


.. _signal_ConfigurationObject_itemsDataChanged:

.. index::
   single: itemsDataChanged

itemsDataChanged(SignedInteger index)
+++++++++++++++++++++++++++++++++++++

This signal is emitted whenever the :ref:`List.dataChanged() <signal_List_dataChanged>` signal is emitted, i.e. the item at ``index`` in the :ref:`items <property_ConfigurationObject_items>` list itself emitted the dataChanged() signal.


