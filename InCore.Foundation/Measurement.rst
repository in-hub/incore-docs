
.. _object_Measurement:


:index:`Measurement`
--------------------

Description
***********

The Measurement object represents a measurement of a sensor with :ref:`unit <property_Measurement_unit>` and :ref:`decimals <property_Measurement_decimals>` digits after the decimal point. Additional properties allow for measurement and measurement system specific value conversions.

:**› Inherits**: :ref:`DataObject <object_DataObject>`
:**› Inherited by**: :ref:`Current <object_Current>`, :ref:`Temperature <object_Temperature>`

Overview
********

Properties
++++++++++

.. hlist::
  :columns: 3

  * :ref:`decimals <property_Measurement_decimals>`
  * :ref:`displayString <property_Measurement_displayString>`
  * :ref:`displayValue <property_Measurement_displayValue>`
  * :ref:`siPrefix <property_Measurement_siPrefix>`
  * :ref:`siPrefixFactor <property_Measurement_siPrefixFactor>`
  * :ref:`siPrefixName <property_Measurement_siPrefixName>`
  * :ref:`system <property_Measurement_system>`
  * :ref:`unit <property_Measurement_unit>`
  * :ref:`view <property_Measurement_view>`
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

  * :ref:`SiPrefix <enum_Measurement_SiPrefix>`
  * :ref:`System <enum_Measurement_System>`
  * :ref:`DataObject.DataType <enum_DataObject_DataType>`



Properties
**********


.. _property_Measurement_decimals:

.. _signal_Measurement_decimalsChanged:

.. index::
   single: decimals

decimals
++++++++

This property holds the number of digits after the decimal point. This value is used to format the measurement value in the :ref:`displayString <property_Measurement_displayString>`.

:**› Type**: SignedInteger
:**› Default**: ``0``
:**› Signal**: decimalsChanged()
:**› Attributes**: Writable


.. _property_Measurement_displayString:

.. _signal_Measurement_displayStringChanged:

.. index::
   single: displayString

displayString
+++++++++++++

This property holds the converted, scaled and formatted measurement value including SI prefix and unit.

:**› Type**: String
:**› Signal**: displayStringChanged()
:**› Attributes**: Readonly


.. _property_Measurement_displayValue:

.. _signal_Measurement_displayValueChanged:

.. index::
   single: displayValue

displayValue
++++++++++++

This property holds an expression which is used to calculate the display value based on the current :ref:`value <property_DataObject_data>`, :ref:`SI prefix factor <property_Measurement_siPrefixFactor>` and :ref:`measurement system <property_Measurement_system>`.

This property was introduced in InCore 2.0.

:**› Type**: <QML expression>
:**› Signal**: displayValueChanged()
:**› Attributes**: Writable


.. _property_Measurement_siPrefix:

.. _signal_Measurement_siPrefixChanged:

.. index::
   single: siPrefix

siPrefix
++++++++

This property holds the SI prefix for the measurement. It is included in the formatted string provided in the :ref:`displayString <property_Measurement_displayString>` property if appropriate. The measurement value is scaled according to the selected SI prefix when formatting the string. The SI prefix may be ignored for certain absolute physical quantities such as the :ref:`Temperature <object_Temperature>`.

:**› Type**: :ref:`SiPrefix <enum_Measurement_SiPrefix>`
:**› Default**: :ref:`Measurement.NoSiPrefix <enumitem_Measurement_NoSiPrefix>`
:**› Signal**: siPrefixChanged()
:**› Attributes**: Writable


.. _property_Measurement_siPrefixFactor:

.. _signal_Measurement_siPrefixFactorChanged:

.. index::
   single: siPrefixFactor

siPrefixFactor
++++++++++++++

This property holds an expression which evaluates to the SI prefix factor based on the :ref:`siPrefix <property_Measurement_siPrefix>`. If unset or set to ``undefined`` sensible default values (e.g. ``1000`` for :ref:`Measurement.Kilo <enumitem_Measurement_Kilo>`) will be used.

This property was introduced in InCore 2.0.

:**› Type**: <QML expression>
:**› Signal**: siPrefixFactorChanged()
:**› Attributes**: Writable


.. _property_Measurement_siPrefixName:

.. _signal_Measurement_siPrefixNameChanged:

.. index::
   single: siPrefixName

siPrefixName
++++++++++++

This property holds an expression which evaluates to the SI prefix name based on the :ref:`siPrefix <property_Measurement_siPrefix>`. If unset or set to ``undefined`` sensible default values (e.g. ``µ`` for :ref:`Measurement.Micro <enumitem_Measurement_Micro>`) will be used.

This property was introduced in InCore 2.0.

:**› Type**: <QML expression>
:**› Signal**: siPrefixNameChanged()
:**› Attributes**: Writable


.. _property_Measurement_system:

.. _signal_Measurement_systemChanged:

.. index::
   single: system

system
++++++

This property holds the measurement system to use for calculating and formatting the content of the :ref:`displayString <property_Measurement_displayString>` property. It is identical to :ref:`Application.measurementSystem <property_Application_measurementSystem>` and provided for convenience only.

This property was introduced in InCore 2.0.

:**› Type**: :ref:`System <enum_Measurement_System>`
:**› Default**: :ref:`Measurement.MetricSystem <enumitem_Measurement_MetricSystem>`
:**› Signal**: systemChanged()
:**› Attributes**: Readonly


.. _property_Measurement_unit:

.. _signal_Measurement_unitChanged:

.. index::
   single: unit

unit
++++

This property holds the unit for the measurement. It is included in the formatted string provided in the :ref:`displayString <property_Measurement_displayString>` property. It's set automatically by the individual objects for specific physical quantities such as :ref:`Temperature <object_Temperature>`.

:**› Type**: String
:**› Signal**: unitChanged()
:**› Attributes**: Writable


.. _property_Measurement_view:

.. _signal_Measurement_viewChanged:

.. index::
   single: view

view
++++

This property holds the view attached to a specific measurement object. See the documentation for the :ref:`MeasurementView <object_MeasurementView>` object for details on how to use it.

:**› Type**: :ref:`MeasurementView <object_MeasurementView>`
:**› Signal**: viewChanged()
:**› Attributes**: Writable, Optional

Enumerations
************


.. _enum_Measurement_SiPrefix:

.. index::
   single: SiPrefix

SiPrefix
++++++++

This enumeration describes prefixes for the International System of Units (SI).

.. index::
   single: Measurement.NoSiPrefix
.. index::
   single: Measurement.Giga
.. index::
   single: Measurement.Mega
.. index::
   single: Measurement.Kilo
.. index::
   single: Measurement.Hecto
.. index::
   single: Measurement.Deca
.. index::
   single: Measurement.Deci
.. index::
   single: Measurement.Centi
.. index::
   single: Measurement.Milli
.. index::
   single: Measurement.Micro
.. index::
   single: Measurement.Nano
.. index::
   single: Measurement.Pico
.. list-table::
  :widths: auto
  :header-rows: 1

  * - Name
    - Value
    - Description

      .. _enumitem_Measurement_NoSiPrefix:
  * - ``Measurement.NoSiPrefix``
    - ``0``
    - 10\ :superscript:`0`\  (no prefix).

      .. _enumitem_Measurement_Giga:
  * - ``Measurement.Giga``
    - ``1``
    - 10\ :superscript:`9`\ .

      .. _enumitem_Measurement_Mega:
  * - ``Measurement.Mega``
    - ``2``
    - 10\ :superscript:`6`\ .

      .. _enumitem_Measurement_Kilo:
  * - ``Measurement.Kilo``
    - ``3``
    - 10\ :superscript:`3`\ .

      .. _enumitem_Measurement_Hecto:
  * - ``Measurement.Hecto``
    - ``4``
    - 10\ :superscript:`2`\ .

      .. _enumitem_Measurement_Deca:
  * - ``Measurement.Deca``
    - ``5``
    - 10\ :superscript:`1`\ .

      .. _enumitem_Measurement_Deci:
  * - ``Measurement.Deci``
    - ``6``
    - 10\ :superscript:`-1`\ .

      .. _enumitem_Measurement_Centi:
  * - ``Measurement.Centi``
    - ``7``
    - 10\ :superscript:`-2`\ .

      .. _enumitem_Measurement_Milli:
  * - ``Measurement.Milli``
    - ``8``
    - 10\ :superscript:`-3`\ .

      .. _enumitem_Measurement_Micro:
  * - ``Measurement.Micro``
    - ``9``
    - 10\ :superscript:`-6`\ .

      .. _enumitem_Measurement_Nano:
  * - ``Measurement.Nano``
    - ``10``
    - 10\ :superscript:`-9`\ .

      .. _enumitem_Measurement_Pico:
  * - ``Measurement.Pico``
    - ``11``
    - 10\ :superscript:`-12`\ .


.. _enum_Measurement_System:

.. index::
   single: System

System
++++++

This enumeration describes supported measurement systems. The measurement system is configured through the :ref:`Application.measurementSystem <property_Application_measurementSystem>` property.

.. index::
   single: Measurement.MetricSystem
.. index::
   single: Measurement.ImperialUSSystem
.. index::
   single: Measurement.ImperialUKSystem
.. list-table::
  :widths: auto
  :header-rows: 1

  * - Name
    - Value
    - Description

      .. _enumitem_Measurement_MetricSystem:
  * - ``Measurement.MetricSystem``
    - ``0``
    - This value indicates metric units, such as meters, centimeters and millimeters.

      .. _enumitem_Measurement_ImperialUSSystem:
  * - ``Measurement.ImperialUSSystem``
    - ``1``
    - This value indicates imperial units, such as inches and miles as they are used in the United States.

      .. _enumitem_Measurement_ImperialUKSystem:
  * - ``Measurement.ImperialUKSystem``
    - ``2``
    - This value indicates imperial units, such as inches and miles as they are used in the United Kingdom.

