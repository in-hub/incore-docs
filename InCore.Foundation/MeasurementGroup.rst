
.. _object_MeasurementGroup:


:index:`MeasurementGroup`
-------------------------

Description
***********

The MeasurementGroup object provides a container to group :ref:`Measurement <object_Measurement>` objects while providing the additional :ref:`enabled <property_MeasurementGroup_enabled>` and :ref:`view <property_MeasurementGroup_view>` properties. This can be useful to model and use :ref:`Measurement <object_Measurement>` hierarchies through :ref:`Repeater <object_Repeater>` and :ref:`Gather <object_Gather>`.

:**› Inherits**: :ref:`DataObjectGroup <object_DataObjectGroup>`

Overview
********

Properties
++++++++++

.. hlist::
  :columns: 1

  * :ref:`enabled <property_MeasurementGroup_enabled>`
  * :ref:`view <property_MeasurementGroup_view>`
  * :ref:`DataObjectGroup.description <property_DataObjectGroup_description>`
  * :ref:`DataObjectGroup.name <property_DataObjectGroup_name>`
  * :ref:`DataObjectGroup.objects <property_DataObjectGroup_objects>`
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

  * :ref:`DataObjectGroup.objectsDataChanged() <signal_DataObjectGroup_objectsDataChanged>`
  * :ref:`Object.completed() <signal_Object_completed>`



Properties
**********


.. _property_MeasurementGroup_enabled:

.. _signal_MeasurementGroup_enabledChanged:

.. index::
   single: enabled

enabled
+++++++

This property holds whether the measurement group is enabled, i.e. the measurements in this group are valid and/or should be displayed/processed.

This property was introduced in InCore 1.1.

:**› Type**: Boolean
:**› Default**: ``true``
:**› Signal**: enabledChanged()
:**› Attributes**: Writable


.. _property_MeasurementGroup_view:

.. _signal_MeasurementGroup_viewChanged:

.. index::
   single: view

view
++++

This property holds a :ref:`MeasurementView <object_MeasurementView>` with common :ref:`view <property_DataObject_view>`-related properties for all grouped measurements.

:**› Type**: :ref:`MeasurementView <object_MeasurementView>`
:**› Signal**: viewChanged()
:**› Attributes**: Writable

