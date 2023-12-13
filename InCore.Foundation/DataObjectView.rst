
.. _object_DataObjectView:


:index:`DataObjectView`
-----------------------

Description
***********

The DataObjectView object contains settings and data for representing and displaying a :ref:`DataObject <object_DataObject>` in a user-defined frontend. This allows modelling generic and dynamic user interfaces. None of the properties are evaluated or used by any InCore objects so that no restrictions apply. However some objects with :ref:`ConfigurationItem <object_ConfigurationItem>` properties may provide sensible and generic default values for some properties such as :ref:`widget <property_DataObjectView_widget>` and :ref:`widgetData <property_DataObjectView_widgetData>`.

:**› Inherits**: :ref:`Object <object_Object>`
:**› Inherited by**: :ref:`MeasurementView <object_MeasurementView>`

Overview
********

Properties
++++++++++

.. hlist::
  :columns: 3

  * :ref:`color <property_DataObjectView_color>`
  * :ref:`decimals <property_DataObjectView_decimals>`
  * :ref:`disabled <property_DataObjectView_disabled>`
  * :ref:`hidden <property_DataObjectView_hidden>`
  * :ref:`orderIndex <property_DataObjectView_orderIndex>`
  * :ref:`placeholder <property_DataObjectView_placeholder>`
  * :ref:`range <property_DataObjectView_range>`
  * :ref:`readOnly <property_DataObjectView_readOnly>`
  * :ref:`stepSize <property_DataObjectView_stepSize>`
  * :ref:`toolTip <property_DataObjectView_toolTip>`
  * :ref:`widget <property_DataObjectView_widget>`
  * :ref:`widgetData <property_DataObjectView_widgetData>`
  * :ref:`widgetDataMap <property_DataObjectView_widgetDataMap>`
  * :ref:`widgetWidth <property_DataObjectView_widgetWidth>`
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

  * :ref:`Widget <enum_DataObjectView_Widget>`



Properties
**********


.. _property_DataObjectView_color:

.. _signal_DataObjectView_colorChanged:

.. index::
   single: color

color
+++++

This property holds the color to use for visualizing the data, e.g. the measurement curve in a plot.

This property was introduced in InCore 2.4.

:**› Type**: String
:**› Signal**: colorChanged()
:**› Attributes**: Writable


.. _property_DataObjectView_decimals:

.. _signal_DataObjectView_decimalsChanged:

.. index::
   single: decimals

decimals
++++++++

This property holds the number of digits after the decimal point to show for :ref:`DataObject.Float <enumitem_DataObject_Float>` or :ref:`DataObject.Double <enumitem_DataObject_Double>` data in widgets such as spinboxes.

This property was introduced in InCore 2.4.

:**› Type**: SignedInteger
:**› Default**: ``0``
:**› Signal**: decimalsChanged()
:**› Attributes**: Writable


.. _property_DataObjectView_disabled:

.. _signal_DataObjectView_disabledChanged:

.. index::
   single: disabled

disabled
++++++++

This property holds whether the view/widget should be disabled.

:**› Type**: Boolean
:**› Default**: ``false``
:**› Signal**: disabledChanged()
:**› Attributes**: Writable


.. _property_DataObjectView_hidden:

.. _signal_DataObjectView_hiddenChanged:

.. index::
   single: hidden

hidden
++++++

This property holds whether the view/widget should be hidden.

:**› Type**: Boolean
:**› Default**: ``false``
:**› Signal**: hiddenChanged()
:**› Attributes**: Writable


.. _property_DataObjectView_orderIndex:

.. _signal_DataObjectView_orderIndexChanged:

.. index::
   single: orderIndex

orderIndex
++++++++++

This property holds an index which can be evaluated by a frontend do determine how to order views/widgets.

:**› Type**: SignedInteger
:**› Default**: ``0``
:**› Signal**: orderIndexChanged()
:**› Attributes**: Writable


.. _property_DataObjectView_placeholder:

.. _signal_DataObjectView_placeholderChanged:

.. index::
   single: placeholder

placeholder
+++++++++++

This property holds the placeholder for the input widget which usually is shown if no value has been entered yet.

:**› Type**: String
:**› Signal**: placeholderChanged()
:**› Attributes**: Writable


.. _property_DataObjectView_range:

.. _signal_DataObjectView_rangeChanged:

.. index::
   single: range

range
+++++

This property holds the range which to display or allow for input, usually a minimum and a maximum value.

This property was introduced in InCore 2.4.

:**› Type**: List
:**› Signal**: rangeChanged()
:**› Attributes**: Writable


.. _property_DataObjectView_readOnly:

.. _signal_DataObjectView_readOnlyChanged:

.. index::
   single: readOnly

readOnly
++++++++

This property holds whether the view/widget should be read-only. If set to ``true`` no changes should be allowed. This property is intended as an indication for the frontend only. This means even if set to ``true`` neither the :ref:`DataObject <object_DataObject>` nor the :ref:`DataObjectView <object_DataObjectView>` will prevent actual writes to the :ref:`DataObject.data <property_DataObject_data>` property.

:**› Type**: Boolean
:**› Default**: ``false``
:**› Signal**: readOnlyChanged()
:**› Attributes**: Writable


.. _property_DataObjectView_stepSize:

.. _signal_DataObjectView_stepSizeChanged:

.. index::
   single: stepSize

stepSize
++++++++

This property holds the step size for widgets such as spinboxes or sliders.

This property was introduced in InCore 2.4.

:**› Type**: Double
:**› Default**: ``1``
:**› Signal**: stepSizeChanged()
:**› Attributes**: Writable


.. _property_DataObjectView_toolTip:

.. _signal_DataObjectView_toolTipChanged:

.. index::
   single: toolTip

toolTip
+++++++

This property holds the tooltip for the widget which is shown when hovering with the mouse.

:**› Type**: String
:**› Signal**: toolTipChanged()
:**› Attributes**: Writable


.. _property_DataObjectView_widget:

.. _signal_DataObjectView_widgetChanged:

.. index::
   single: widget

widget
++++++

This property holds an enumeration value for the frontend indicating which kind of widget to use for the related :ref:`DataObject <object_DataObject>`. See the :ref:`Widget <enum_DataObjectView_Widget>` enumeration for details.

:**› Type**: :ref:`DataObjectView.Widget <enum_DataObjectView_Widget>`
:**› Default**: :ref:`DataObjectView.NoWidget <enumitem_DataObjectView_NoWidget>`
:**› Signal**: widgetChanged()
:**› Attributes**: Writable


.. _property_DataObjectView_widgetData:

.. _signal_DataObjectView_widgetDataChanged:

.. index::
   single: widgetData

widgetData
++++++++++

This property holds the data in any representation required for populating or operating the specified :ref:`widget <property_DataObjectView_widget>`. This is mainly used for widgets that allow the user to select one or more items. In such cases a list of items can be specified here. In either case the data and its format entirely depend on the frontend used and is not processed by any InCore objects.

:**› Type**: Variant
:**› Signal**: widgetDataChanged()
:**› Attributes**: Writable


.. _property_DataObjectView_widgetDataMap:

.. index::
   single: widgetDataMap

widgetDataMap
+++++++++++++

This property holds the :ref:`widget <property_DataObjectView_widget>`-specific data in a special map representation. This may be required for widgets such as comboboxes where keys are used internally and values displayed as choices to the user.

:**› Type**: Map
:**› Attributes**: Readonly


.. _property_DataObjectView_widgetWidth:

.. _signal_DataObjectView_widgetWidthChanged:

.. index::
   single: widgetWidth

widgetWidth
+++++++++++

This property holds the width of the widget which allows specifying relative widget sizes.

:**› Type**: SignedInteger
:**› Default**: ``100``
:**› Signal**: widgetWidthChanged()
:**› Attributes**: Writable

Enumerations
************


.. _enum_DataObjectView_Widget:

.. index::
   single: Widget

Widget
++++++

This enumeration describes predefined values for the :ref:`widget <property_DataObjectView_widget>` property.

.. index::
   single: DataObjectView.NoWidget
.. index::
   single: DataObjectView.Label
.. index::
   single: DataObjectView.TextInput
.. index::
   single: DataObjectView.Slider
.. index::
   single: DataObjectView.Switch
.. index::
   single: DataObjectView.Combobox
.. index::
   single: DataObjectView.Gauge
.. index::
   single: DataObjectView.Chart
.. index::
   single: DataObjectView.SpinBox
.. index::
   single: DataObjectView.EditableCombobox
.. index::
   single: DataObjectView.PasswordField
.. index::
   single: DataObjectView.TextFileField
.. index::
   single: DataObjectView.BinaryFilePicker
.. list-table::
  :widths: auto
  :header-rows: 1

  * - Name
    - Value
    - Description

      .. _enumitem_DataObjectView_NoWidget:
  * - ``DataObjectView.NoWidget``
    - ``0``
    - Use none of the predefined widgets.

      .. _enumitem_DataObjectView_Label:
  * - ``DataObjectView.Label``
    - ``1``
    - Use a simple text label for informational purposes.

      .. _enumitem_DataObjectView_TextInput:
  * - ``DataObjectView.TextInput``
    - ``2``
    - Use a text input widget allowing the user to enter text.

      .. _enumitem_DataObjectView_Slider:
  * - ``DataObjectView.Slider``
    - ``3``
    - Use a slider widget to quickly adjust a number value.

      .. _enumitem_DataObjectView_Switch:
  * - ``DataObjectView.Switch``
    - ``4``
    - Use a switch widget to toggle a boolean value.

      .. _enumitem_DataObjectView_Combobox:
  * - ``DataObjectView.Combobox``
    - ``5``
    - Use a combobox widget to select from a number of items.

      .. _enumitem_DataObjectView_Gauge:
  * - ``DataObjectView.Gauge``
    - ``6``
    - Display the data value in a gauge.

      .. _enumitem_DataObjectView_Chart:
  * - ``DataObjectView.Chart``
    - ``7``
    - Display the data value in a chart.

      .. _enumitem_DataObjectView_SpinBox:
  * - ``DataObjectView.SpinBox``
    - ``8``
    - Use a spinbox widget for number input.

      .. _enumitem_DataObjectView_EditableCombobox:
  * - ``DataObjectView.EditableCombobox``
    - ``9``
    - Use a combobox which allows editing the text.

      .. _enumitem_DataObjectView_PasswordField:
  * - ``DataObjectView.PasswordField``
    - ``10``
    - Use text field widget which shows asterisks instead of the actual input.

      .. _enumitem_DataObjectView_TextFileField:
  * - ``DataObjectView.TextFileField``
    - ``11``
    - a text field which also can be filled from a local text file.

      .. _enumitem_DataObjectView_BinaryFilePicker:
  * - ``DataObjectView.BinaryFilePicker``
    - ``12``
    - a widget allowing to select a file and use its content for the :ref:`DataObject <object_DataObject>`'s data in base64 representation.

Example
*******
See :ref:`DataObject example <example_DataObject>` on how to use DataObjectView.
