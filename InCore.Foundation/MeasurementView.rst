
.. _object_MeasurementView:


:index:`MeasurementView`
------------------------

Description
***********

The MeasurementView object is a specialized version of :ref:`DataObjectView <object_DataObjectView>` with additional properties for :ref:`Measurement <object_Measurement>` objects.

:**› Inherits**: :ref:`DataObjectView <object_DataObjectView>`

Overview
********

Properties
++++++++++

.. hlist::
  :columns: 3

  * :ref:`maximumValue <property_MeasurementView_maximumValue>`
  * :ref:`minimumValue <property_MeasurementView_minimumValue>`
  * :ref:`DataObjectView.color <property_DataObjectView_color>`
  * :ref:`DataObjectView.decimals <property_DataObjectView_decimals>`
  * :ref:`DataObjectView.disabled <property_DataObjectView_disabled>`
  * :ref:`DataObjectView.hidden <property_DataObjectView_hidden>`
  * :ref:`DataObjectView.orderIndex <property_DataObjectView_orderIndex>`
  * :ref:`DataObjectView.placeholder <property_DataObjectView_placeholder>`
  * :ref:`DataObjectView.range <property_DataObjectView_range>`
  * :ref:`DataObjectView.readOnly <property_DataObjectView_readOnly>`
  * :ref:`DataObjectView.stepSize <property_DataObjectView_stepSize>`
  * :ref:`DataObjectView.toolTip <property_DataObjectView_toolTip>`
  * :ref:`DataObjectView.widget <property_DataObjectView_widget>`
  * :ref:`DataObjectView.widgetData <property_DataObjectView_widgetData>`
  * :ref:`DataObjectView.widgetDataMap <property_DataObjectView_widgetDataMap>`
  * :ref:`DataObjectView.widgetWidth <property_DataObjectView_widgetWidth>`
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

  * :ref:`DataObjectView.Widget <enum_DataObjectView_Widget>`



Properties
**********


.. _property_MeasurementView_maximumValue:

.. _signal_MeasurementView_maximumValueChanged:

.. index::
   single: maximumValue

maximumValue
++++++++++++

This property holds the maximum value to use for parametrizing the widget displaying a measurement, e.g. a gauge or plot.

:**› Type**: Double
:**› Default**: ``0``
:**› Signal**: maximumValueChanged()
:**› Attributes**: Writable


.. _property_MeasurementView_minimumValue:

.. _signal_MeasurementView_minimumValueChanged:

.. index::
   single: minimumValue

minimumValue
++++++++++++

This property holds the minimum value to use for parametrizing the widget displaying a measurement, e.g. a gauge or plot.

:**› Type**: Double
:**› Default**: ``0``
:**› Signal**: minimumValueChanged()
:**› Attributes**: Writable

