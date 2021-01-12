
.. _object_DataObjectGroup:


:index:`DataObjectGroup`
------------------------

Description
***********

The DataObjectGroup object provides a container to group :ref:`DataObject <object_DataObject>` instances while providing the additional properties :ref:`name <property_DataObjectGroup_name>` and :ref:`description <property_DataObjectGroup_description>`. This can be useful to model and use :ref:`DataObject <object_DataObject>` hierarchies through :ref:`Repeater <object_Repeater>` and :ref:`Gather <object_Gather>`. When working with :ref:`Measurement <object_Measurement>` objects only, the specialized :ref:`MeasurementGroup <object_MeasurementGroup>` object can be used instead.

:**› Inherits**: :ref:`Object <object_Object>`
:**› Inherited by**: :ref:`MeasurementGroup <object_MeasurementGroup>`

Overview
********

Properties
++++++++++

.. hlist::
  :columns: 1

  * :ref:`description <property_DataObjectGroup_description>`
  * :ref:`name <property_DataObjectGroup_name>`
  * :ref:`objects <property_DataObjectGroup_objects>`
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

  * :ref:`objectsDataChanged() <signal_DataObjectGroup_objectsDataChanged>`
  * :ref:`Object.completed() <signal_Object_completed>`



Properties
**********


.. _property_DataObjectGroup_description:

.. _signal_DataObjectGroup_descriptionChanged:

.. index::
   single: description

description
+++++++++++

This property holds a user-defined description for the data object group.

:**› Type**: String
:**› Signal**: descriptionChanged()
:**› Attributes**: Writable


.. _property_DataObjectGroup_name:

.. _signal_DataObjectGroup_nameChanged:

.. index::
   single: name

name
++++

This property holds a user-defined name for the data object group.

:**› Type**: String
:**› Signal**: nameChanged()
:**› Attributes**: Writable


.. _property_DataObjectGroup_objects:

.. _signal_DataObjectGroup_objectsChanged:

.. index::
   single: objects

objects
+++++++

This property holds a list of :ref:`DataObject <object_DataObject>` (or subclass) objects to group.

:**› Type**: :ref:`List <object_List>`\<:ref:`DataObject <object_DataObject>`>
:**› Signal**: objectsChanged()
:**› Attributes**: Readonly

Signals
*******


.. _signal_DataObjectGroup_objectsDataChanged:

.. index::
   single: objectsDataChanged

objectsDataChanged(SignedInteger index)
+++++++++++++++++++++++++++++++++++++++

This signal is emitted whenever the :ref:`List.dataChanged() <signal_List_dataChanged>` signal is emitted, i.e. the item at ``index`` in the :ref:`objects <property_DataObjectGroup_objects>` list itself emitted the dataChanged() signal.


