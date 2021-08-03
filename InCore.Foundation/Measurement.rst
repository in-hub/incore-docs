
.. _object_Measurement:


:index:`Measurement`
--------------------

Description
***********

The Measurement object represents a measurement of a sensor with :ref:`unit <property_Measurement_unit>` and :ref:`decimals <property_Measurement_decimals>` digits after the decimal point. Additional properties allow for measurement and measurement system specific value conversions.

:**› Inherits**: :ref:`DataObject <object_DataObject>`

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
  * :ref:`Object.deserializeProperties() <method_Object_deserializeProperties>`
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
  * :ref:`Unit <enum_Measurement_Unit>`
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

This property holds the SI prefix for the measurement. It is included in the formatted string provided in the :ref:`displayString <property_Measurement_displayString>` property if appropriate. The measurement value is scaled according to the selected SI prefix when formatting the string. The SI prefix may be ignored for certain absolute physical quantities such as temperature objects.

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

This property holds the unit for the measurement. This can either be one of the :ref:`Measurement.Unit <enum_Measurement_Unit>` enumerations or a custom string. It is included in the formatted string provided in the :ref:`displayString <property_Measurement_displayString>` property.

:**› Type**: Variant
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
    - 10\ :superscript:`0`\  (no prefix)

      .. _enumitem_Measurement_Giga:
  * - ``Measurement.Giga``
    - ``1``
    - 10\ :superscript:`9`\ 

      .. _enumitem_Measurement_Mega:
  * - ``Measurement.Mega``
    - ``2``
    - 10\ :superscript:`6`\ 

      .. _enumitem_Measurement_Kilo:
  * - ``Measurement.Kilo``
    - ``3``
    - 10\ :superscript:`3`\ 

      .. _enumitem_Measurement_Hecto:
  * - ``Measurement.Hecto``
    - ``4``
    - 10\ :superscript:`2`\ 

      .. _enumitem_Measurement_Deca:
  * - ``Measurement.Deca``
    - ``5``
    - 10\ :superscript:`1`\ 

      .. _enumitem_Measurement_Deci:
  * - ``Measurement.Deci``
    - ``6``
    - 10\ :superscript:`-1`\ 

      .. _enumitem_Measurement_Centi:
  * - ``Measurement.Centi``
    - ``7``
    - 10\ :superscript:`-2`\ 

      .. _enumitem_Measurement_Milli:
  * - ``Measurement.Milli``
    - ``8``
    - 10\ :superscript:`-3`\ 

      .. _enumitem_Measurement_Micro:
  * - ``Measurement.Micro``
    - ``9``
    - 10\ :superscript:`-6`\ 

      .. _enumitem_Measurement_Nano:
  * - ``Measurement.Nano``
    - ``10``
    - 10\ :superscript:`-9`\ 

      .. _enumitem_Measurement_Pico:
  * - ``Measurement.Pico``
    - ``11``
    - 10\ :superscript:`-12`\ 


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


.. _enum_Measurement_Unit:

.. index::
   single: Unit

Unit
++++

This enumeration describes all supported units of measure as specified by the `UN ECE/CEFACT codes <https://unece.org/trade/cefact/UNLOCODE-Download>`_.

This enumeration was introduced in InCore 2.4.

.. index::
   single: Measurement.NoUnit
.. index::
   single: Measurement.Radian
.. index::
   single: Measurement.Milliradian
.. index::
   single: Measurement.Microradian
.. index::
   single: Measurement.DegreeUnitOfAngle
.. index::
   single: Measurement.MinuteUnitOfAngle
.. index::
   single: Measurement.SecondUnitOfAngle
.. index::
   single: Measurement.Gon
.. index::
   single: Measurement.Mil
.. index::
   single: Measurement.Revolution
.. index::
   single: Measurement.Steradian
.. index::
   single: Measurement.InchPerTwoPiRadiant
.. index::
   single: Measurement.Metre
.. index::
   single: Measurement.DegreePerSecond
.. index::
   single: Measurement.DegreePerMetre
.. index::
   single: Measurement.MetrePerRadiant
.. index::
   single: Measurement.Decimetre
.. index::
   single: Measurement.Centimetre
.. index::
   single: Measurement.MicrometreMicron
.. index::
   single: Measurement.Millimetre
.. index::
   single: Measurement.Hectometre
.. index::
   single: Measurement.Kilometre
.. index::
   single: Measurement.Nanometre
.. index::
   single: Measurement.Picometre
.. index::
   single: Measurement.Femtometre
.. index::
   single: Measurement.Decametre
.. index::
   single: Measurement.NauticalMile
.. index::
   single: Measurement.Angstrom
.. index::
   single: Measurement.AstronomicalUnit
.. index::
   single: Measurement.Parsec
.. index::
   single: Measurement.MetrePerKelvin
.. index::
   single: Measurement.MicrometrePerKelvin
.. index::
   single: Measurement.CentimetrePerKelvin
.. index::
   single: Measurement.MillimetrePerBar
.. index::
   single: Measurement.GramMillimetre
.. index::
   single: Measurement.CentimetrePerBar
.. index::
   single: Measurement.MetrePerBar
.. index::
   single: Measurement.FrenchGauge
.. index::
   single: Measurement.Fathom
.. index::
   single: Measurement.GuntersChain
.. index::
   single: Measurement.Inch
.. index::
   single: Measurement.Microinch
.. index::
   single: Measurement.Foot
.. index::
   single: Measurement.Yard
.. index::
   single: Measurement.MileStatuteMile
.. index::
   single: Measurement.Milliinch
.. index::
   single: Measurement.LightYear
.. index::
   single: Measurement.RodUnitOfDistance
.. index::
   single: Measurement.Megametre
.. index::
   single: Measurement.FootPerDegreeFahrenheit
.. index::
   single: Measurement.FootPerPsi
.. index::
   single: Measurement.InchPerDegreeFahrenheit
.. index::
   single: Measurement.InchPerPsi
.. index::
   single: Measurement.YardPerDegreeFahrenheit
.. index::
   single: Measurement.YardPerPsi
.. index::
   single: Measurement.ChainBasedOnUSSurveyFoot
.. index::
   single: Measurement.Furlong
.. index::
   single: Measurement.FootUSSurvey
.. index::
   single: Measurement.MileBasedOnUSSurveyFoot
.. index::
   single: Measurement.MetrePerPascal
.. index::
   single: Measurement.SquareMetre
.. index::
   single: Measurement.SquareKilometre
.. index::
   single: Measurement.SquareMicrometreSquareMicron
.. index::
   single: Measurement.SquareMetrePerNewton
.. index::
   single: Measurement.Decare
.. index::
   single: Measurement.SquareCentimetre
.. index::
   single: Measurement.SquareDecimetre
.. index::
   single: Measurement.SquareDecametre
.. index::
   single: Measurement.SquareHectometre
.. index::
   single: Measurement.SquareMillimetre
.. index::
   single: Measurement.SquareInch
.. index::
   single: Measurement.SquareFoot
.. index::
   single: Measurement.SquareYard
.. index::
   single: Measurement.SquareMileStatuteMile
.. index::
   single: Measurement.SquareMileBasedOnUSSurveyFoot
.. index::
   single: Measurement.Acre
.. index::
   single: Measurement.CircularMil
.. index::
   single: Measurement.CubicMetre
.. index::
   single: Measurement.Megalitre
.. index::
   single: Measurement.Litre
.. index::
   single: Measurement.CubicMillimetre
.. index::
   single: Measurement.CubicCentimetre
.. index::
   single: Measurement.CubicDecimetre
.. index::
   single: Measurement.Millilitre
.. index::
   single: Measurement.Hectolitre
.. index::
   single: Measurement.Centilitre
.. index::
   single: Measurement.CubicDecametre
.. index::
   single: Measurement.CubicHectometre
.. index::
   single: Measurement.CubicKilometre
.. index::
   single: Measurement.CubicMetrePerPascal
.. index::
   single: Measurement.Decilitre
.. index::
   single: Measurement.Microlitre
.. index::
   single: Measurement.Kilolitre
.. index::
   single: Measurement.Decalitre
.. index::
   single: Measurement.CubicCentimetrePerBar
.. index::
   single: Measurement.LitrePerBar
.. index::
   single: Measurement.CubicMetrePerBar
.. index::
   single: Measurement.MillilitrePerBar
.. index::
   single: Measurement.CubicInch
.. index::
   single: Measurement.CubicFoot
.. index::
   single: Measurement.CubicYard
.. index::
   single: Measurement.GallonUK
.. index::
   single: Measurement.GallonUS
.. index::
   single: Measurement.PintUK
.. index::
   single: Measurement.QuartUK
.. index::
   single: Measurement.LiquidPintUS
.. index::
   single: Measurement.LiquidQuartUS
.. index::
   single: Measurement.DryPintUS
.. index::
   single: Measurement.FluidOunceUK
.. index::
   single: Measurement.BarrelUKPetroleum
.. index::
   single: Measurement.CubicFootPerDegreeFahrenheit
.. index::
   single: Measurement.CubicFootPerPsi
.. index::
   single: Measurement.PeckUK
.. index::
   single: Measurement.TonUKShipping
.. index::
   single: Measurement.TonUSShipping
.. index::
   single: Measurement.CubicYardPerDegreeFahrenheit
.. index::
   single: Measurement.CubicYardPerPsi
.. index::
   single: Measurement.FluidOunceUS
.. index::
   single: Measurement.BushelUK
.. index::
   single: Measurement.BushelUS
.. index::
   single: Measurement.BarrelUS
.. index::
   single: Measurement.DryBarrelUS
.. index::
   single: Measurement.DryGallonUS
.. index::
   single: Measurement.DryQuartUS
.. index::
   single: Measurement.Stere
.. index::
   single: Measurement.CupUnitOfVolume
.. index::
   single: Measurement.TablespoonUS
.. index::
   single: Measurement.TeaspoonUS
.. index::
   single: Measurement.Peck
.. index::
   single: Measurement.AcrefootBasedOnUSSurveyFoot
.. index::
   single: Measurement.CordFt
.. index::
   single: Measurement.CubicMileUKStatute
.. index::
   single: Measurement.TonRegister
.. index::
   single: Measurement.CubicCentimetrePerKelvin
.. index::
   single: Measurement.CubicMetrePerKelvin
.. index::
   single: Measurement.LitrePerKelvin
.. index::
   single: Measurement.MillilitrePerKelvin
.. index::
   single: Measurement.MicrolitrePerLitre
.. index::
   single: Measurement.CubicCentimetrePerCubicMetre
.. index::
   single: Measurement.CubicDecimetrePerCubicMetre
.. index::
   single: Measurement.LitrePerLitre
.. index::
   single: Measurement.MillilitrePerLitre
.. index::
   single: Measurement.CubicMillimetrePerCubicMetre
.. index::
   single: Measurement.SecondUnitOfTime
.. index::
   single: Measurement.MinuteUnitOfTime
.. index::
   single: Measurement.Hour
.. index::
   single: Measurement.Day
.. index::
   single: Measurement.Kilosecond
.. index::
   single: Measurement.Millisecond
.. index::
   single: Measurement.Picosecond
.. index::
   single: Measurement.Microsecond
.. index::
   single: Measurement.Nanosecond
.. index::
   single: Measurement.Week
.. index::
   single: Measurement.Month
.. index::
   single: Measurement.Year
.. index::
   single: Measurement.TropicalYear
.. index::
   single: Measurement.CommonYear
.. index::
   single: Measurement.SiderealYear
.. index::
   single: Measurement.Shake
.. index::
   single: Measurement.RadianPerSecond
.. index::
   single: Measurement.RevolutionPerMinute
.. index::
   single: Measurement.RadianPerSecondSquared
.. index::
   single: Measurement.DegreeUnitOfAnglePerSecondSquared
.. index::
   single: Measurement.MetrePerSecond
.. index::
   single: Measurement.Knot
.. index::
   single: Measurement.KilometrePerHour
.. index::
   single: Measurement.MillimetrePerSecond
.. index::
   single: Measurement.CentimetrePerSecond
.. index::
   single: Measurement.CentimetrePerHour
.. index::
   single: Measurement.MillimetrePerMinute
.. index::
   single: Measurement.MetrePerMinute
.. index::
   single: Measurement.MetrePerSecondPascal
.. index::
   single: Measurement.MillimetrePerYear
.. index::
   single: Measurement.MillimetrePerHour
.. index::
   single: Measurement.FootPerMinute
.. index::
   single: Measurement.InchPerSecond
.. index::
   single: Measurement.FootPerSecond
.. index::
   single: Measurement.MilePerHourStatuteMile
.. index::
   single: Measurement.CentimetrePerSecondKelvin
.. index::
   single: Measurement.CentimetrePerSecondBar
.. index::
   single: Measurement.FootPerHour
.. index::
   single: Measurement.FootPerSecondDegreeFahrenheit
.. index::
   single: Measurement.FootPerSecondPsi
.. index::
   single: Measurement.InchPerSecondDegreeFahrenheit
.. index::
   single: Measurement.InchPerSecondPsi
.. index::
   single: Measurement.MetrePerSecondKelvin
.. index::
   single: Measurement.MetrePerSecondBar
.. index::
   single: Measurement.MillilitrePerSquareCentimetreMinute
.. index::
   single: Measurement.MilePerMinute
.. index::
   single: Measurement.MilePerSecond
.. index::
   single: Measurement.MetrePerHour
.. index::
   single: Measurement.InchPerYear
.. index::
   single: Measurement.KilometrePerSecond
.. index::
   single: Measurement.InchPerMinute
.. index::
   single: Measurement.YardPerSecond
.. index::
   single: Measurement.YardPerMinute
.. index::
   single: Measurement.YardPerHour
.. index::
   single: Measurement.MetrePerSecondSquared
.. index::
   single: Measurement.Gal
.. index::
   single: Measurement.Milligal
.. index::
   single: Measurement.KilometrePerSecondSquared
.. index::
   single: Measurement.CentimetrePerSecondSquared
.. index::
   single: Measurement.MillimetrePerSecondSquared
.. index::
   single: Measurement.FootPerSecondSquared
.. index::
   single: Measurement.InchPerSecondSquared
.. index::
   single: Measurement.StandardAccelerationOfFreeFall
.. index::
   single: Measurement.YardPerSecondSquared
.. index::
   single: Measurement.MileStatuteMilePerSecondSquared
.. index::
   single: Measurement.ReciprocalMetre
.. index::
   single: Measurement.Hertz
.. index::
   single: Measurement.Kilohertz
.. index::
   single: Measurement.Megahertz
.. index::
   single: Measurement.Terahertz
.. index::
   single: Measurement.Gigahertz
.. index::
   single: Measurement.ReciprocalHour
.. index::
   single: Measurement.ReciprocalMonth
.. index::
   single: Measurement.ReciprocalYear
.. index::
   single: Measurement.ReciprocalWeek
.. index::
   single: Measurement.ReciprocalSecond
.. index::
   single: Measurement.RevolutionsPerSecond
.. index::
   single: Measurement.RevolutionsPerMinute
.. index::
   single: Measurement.ReciprocalMinute
.. index::
   single: Measurement.Neper
.. index::
   single: Measurement.Decibel
.. index::
   single: Measurement.Bel
.. index::
   single: Measurement.NeperPerSecond
.. index::
   single: Measurement.Kilogram
.. index::
   single: Measurement.Microgram
.. index::
   single: Measurement.Decagram
.. index::
   single: Measurement.Decigram
.. index::
   single: Measurement.Gram
.. index::
   single: Measurement.Centigram
.. index::
   single: Measurement.TonneMetricTon
.. index::
   single: Measurement.Decitonne
.. index::
   single: Measurement.Milligram
.. index::
   single: Measurement.Hectogram
.. index::
   single: Measurement.Kilotonne
.. index::
   single: Measurement.Megagram
.. index::
   single: Measurement.Pound
.. index::
   single: Measurement.Grain
.. index::
   single: Measurement.OunceAvoirdupois
.. index::
   single: Measurement.HundredWeightUK
.. index::
   single: Measurement.HundredPoundCwtHundredWeightUS
.. index::
   single: Measurement.TonUKOrLongTonUS
.. index::
   single: Measurement.StoneUK
.. index::
   single: Measurement.TonUSOrShortTonUKUS
.. index::
   single: Measurement.TroyOunceOrApothecaryOunce
.. index::
   single: Measurement.Slug
.. index::
   single: Measurement.PoundAvoirdupoisPerDegreeFahrenheit
.. index::
   single: Measurement.TonnePerKelvin
.. index::
   single: Measurement.TonShortPerDegreeFahrenheit
.. index::
   single: Measurement.Pfund
.. index::
   single: Measurement.KilogramPerCubicMetre
.. index::
   single: Measurement.GramPerCubicCentimetre
.. index::
   single: Measurement.TonnePerCubicMetre
.. index::
   single: Measurement.GramPerMillilitre
.. index::
   single: Measurement.KilogramPerLitre
.. index::
   single: Measurement.GramPerLitre
.. index::
   single: Measurement.GramPerCubicMetre
.. index::
   single: Measurement.MilligramPerCubicMetre
.. index::
   single: Measurement.MegagramPerCubicMetre
.. index::
   single: Measurement.KilogramPerCubicDecimetre
.. index::
   single: Measurement.MilligramPerGram
.. index::
   single: Measurement.MicrogramPerLitre
.. index::
   single: Measurement.MilligramPerLitre
.. index::
   single: Measurement.MicrogramPerCubicMetre
.. index::
   single: Measurement.GramPerCubicCentimetreBar
.. index::
   single: Measurement.GramPerCubicCentimetreKelvin
.. index::
   single: Measurement.GramPerCubicDecimetre
.. index::
   single: Measurement.GramPerCubicDecimetreBar
.. index::
   single: Measurement.GramPerCubicDecimetreKelvin
.. index::
   single: Measurement.GramPerCubicMetreBar
.. index::
   single: Measurement.GramPerCubicMetreKelvin
.. index::
   single: Measurement.GramPerLitreBar
.. index::
   single: Measurement.GramPerLitreKelvin
.. index::
   single: Measurement.GramPerMillilitreBar
.. index::
   single: Measurement.GramPerMillilitreKelvin
.. index::
   single: Measurement.KilogramPerCubicCentimetre
.. index::
   single: Measurement.KilogramPerCubicCentimetreBar
.. index::
   single: Measurement.KilogramPerCubicCentimetreKelvin
.. index::
   single: Measurement.KilogramPerCubicMetreBar
.. index::
   single: Measurement.KilogramPerCubicMetreKelvin
.. index::
   single: Measurement.KilogramPerCubicDecimetreKelvin
.. index::
   single: Measurement.KilogramPerCubicDecimetreBar
.. index::
   single: Measurement.GramPerKelvin
.. index::
   single: Measurement.KilogramPerKelvin
.. index::
   single: Measurement.KilogramPerKilomol
.. index::
   single: Measurement.KilogramPerLitreBar
.. index::
   single: Measurement.KilogramPerLitreKelvin
.. index::
   single: Measurement.KilogramPerBar
.. index::
   single: Measurement.KilogramSquareCentimetre
.. index::
   single: Measurement.KilogramSquareMillimetre
.. index::
   single: Measurement.GramPerBar
.. index::
   single: Measurement.MilligramPerBar
.. index::
   single: Measurement.MilligramPerKelvin
.. index::
   single: Measurement.KilogramPerCubicMetrePascal
.. index::
   single: Measurement.PoundPerCubicFoot
.. index::
   single: Measurement.PoundPerGallonUS
.. index::
   single: Measurement.PoundPerCubicInch
.. index::
   single: Measurement.OunceAvoirdupoisPerCubicYard
.. index::
   single: Measurement.MicrogramPerCubicMetreKelvin
.. index::
   single: Measurement.MicrogramPerCubicMetreBar
.. index::
   single: Measurement.GrainPerGallonUS
.. index::
   single: Measurement.PoundAvoirdupoisPerCubicFootDegreeFahrenheit
.. index::
   single: Measurement.PoundAvoirdupoisPerCubicFootPsi
.. index::
   single: Measurement.PoundAvoirdupoisPerGallonUK
.. index::
   single: Measurement.PoundAvoirdupoisPerCubicInchDegreeFahrenheit
.. index::
   single: Measurement.PoundAvoirdupoisPerCubicInchPsi
.. index::
   single: Measurement.PoundPerCubicYard
.. index::
   single: Measurement.MilligramPerCubicMetreKelvin
.. index::
   single: Measurement.MilligramPerCubicMetreBar
.. index::
   single: Measurement.OunceAvoirdupoisPerGallonUK
.. index::
   single: Measurement.OunceAvoirdupoisPerGallonUS
.. index::
   single: Measurement.OunceAvoirdupoisPerCubicInch
.. index::
   single: Measurement.SlugPerCubicFoot
.. index::
   single: Measurement.TonnePerCubicMetreKelvin
.. index::
   single: Measurement.TonnePerCubicMetreBar
.. index::
   single: Measurement.TonUKLongPerCubicYard
.. index::
   single: Measurement.TonUSShortPerCubicYard
.. index::
   single: Measurement.PoundAvoirdupoisPerPsi
.. index::
   single: Measurement.TonnePerBar
.. index::
   single: Measurement.TonShortPerPsi
.. index::
   single: Measurement.KilogramPerPascal
.. index::
   single: Measurement.One
.. index::
   single: Measurement.CubicMetrePerKilogram
.. index::
   single: Measurement.DecilitrePerGram
.. index::
   single: Measurement.MillilitrePerCubicMetre
.. index::
   single: Measurement.LitrePerKilogram
.. index::
   single: Measurement.MillilitrePerKilogram
.. index::
   single: Measurement.SquareCentimetrePerGram
.. index::
   single: Measurement.CubicDecimetrePerKilogram
.. index::
   single: Measurement.CubicFootPerPound
.. index::
   single: Measurement.CubicInchPerPound
.. index::
   single: Measurement.KilogramPerMetre
.. index::
   single: Measurement.GramPerMetreGramPerCentimetres
.. index::
   single: Measurement.GramPerMillimetre
.. index::
   single: Measurement.KilogramPerMillimetre
.. index::
   single: Measurement.MilligramPerMetre
.. index::
   single: Measurement.KilogramPerKilometre
.. index::
   single: Measurement.PoundPerFoot
.. index::
   single: Measurement.PoundPerInchOfLength
.. index::
   single: Measurement.Denier
.. index::
   single: Measurement.PoundPerYard
.. index::
   single: Measurement.MilligramPerSquareMetre
.. index::
   single: Measurement.GramPerSquareCentimetre
.. index::
   single: Measurement.MilligramPerSquareCentimetre
.. index::
   single: Measurement.GramPerSquareMetre
.. index::
   single: Measurement.KilogramPerSquareMetre
.. index::
   single: Measurement.KilogramPerSquareCentimetre
.. index::
   single: Measurement.OuncePerSquareYard
.. index::
   single: Measurement.OuncePerSquareFoot
.. index::
   single: Measurement.KilogramMetrePerSecond
.. index::
   single: Measurement.KilogramCentimetrePerSecond
.. index::
   single: Measurement.GramCentimetrePerSecond
.. index::
   single: Measurement.PoundFootPerSecond
.. index::
   single: Measurement.PoundInchPerSecond
.. index::
   single: Measurement.KilogramMetreSquaredPerSecond
.. index::
   single: Measurement.KilogramMetreSquared
.. index::
   single: Measurement.PoundInchSquared
.. index::
   single: Measurement.PoundAvoirdupoisSquareFoot
.. index::
   single: Measurement.Newton
.. index::
   single: Measurement.Meganewton
.. index::
   single: Measurement.Kilonewton
.. index::
   single: Measurement.Millinewton
.. index::
   single: Measurement.Micronewton
.. index::
   single: Measurement.Poundforce
.. index::
   single: Measurement.OunceAvoirdupoisforce
.. index::
   single: Measurement.TonforceUSShort
.. index::
   single: Measurement.Kilopoundforce
.. index::
   single: Measurement.Poundal
.. index::
   single: Measurement.KilogramMetrePerSecondSquared
.. index::
   single: Measurement.Pond
.. index::
   single: Measurement.PoundforcePerFoot
.. index::
   single: Measurement.PoundforcePerInch
.. index::
   single: Measurement.NewtonMetreSquaredPerKilogramSquared
.. index::
   single: Measurement.NewtonMetre
.. index::
   single: Measurement.NewtonPerAmpere
.. index::
   single: Measurement.MeganewtonMetre
.. index::
   single: Measurement.KilonewtonMetre
.. index::
   single: Measurement.MillinewtonMetre
.. index::
   single: Measurement.MicronewtonMetre
.. index::
   single: Measurement.DecinewtonMetre
.. index::
   single: Measurement.CentinewtonMetre
.. index::
   single: Measurement.KilogramMetre
.. index::
   single: Measurement.NewtonCentimetre
.. index::
   single: Measurement.NewtonMetrePerAmpere
.. index::
   single: Measurement.NewtonMetrePerDegree
.. index::
   single: Measurement.NewtonMetrePerKilogram
.. index::
   single: Measurement.NewtonPerMillimetre
.. index::
   single: Measurement.NewtonMetrePerRadian
.. index::
   single: Measurement.NewtonMetreWattToThePowerMinus
.. index::
   single: Measurement.InchPoundPoundInch
.. index::
   single: Measurement.OunceInch
.. index::
   single: Measurement.OunceFoot
.. index::
   single: Measurement.PoundforceFootPerAmpere
.. index::
   single: Measurement.PoundforceInch
.. index::
   single: Measurement.PoundforceFootPerPound
.. index::
   single: Measurement.OunceAvoirdupoisforceInch
.. index::
   single: Measurement.PoundforceFoot
.. index::
   single: Measurement.PoundalFoot
.. index::
   single: Measurement.PoundalInch
.. index::
   single: Measurement.DyneMetre
.. index::
   single: Measurement.NewtonSecond
.. index::
   single: Measurement.NewtonMetreSecond
.. index::
   single: Measurement.Millipascal
.. index::
   single: Measurement.Megapascal
.. index::
   single: Measurement.Pascal
.. index::
   single: Measurement.Kilopascal
.. index::
   single: Measurement.BarUnitOfPressure
.. index::
   single: Measurement.Hectobar
.. index::
   single: Measurement.Millibar
.. index::
   single: Measurement.Kilobar
.. index::
   single: Measurement.StandardAtmosphere
.. index::
   single: Measurement.Gigapascal
.. index::
   single: Measurement.Micropascal
.. index::
   single: Measurement.Hectopascal
.. index::
   single: Measurement.Decapascal
.. index::
   single: Measurement.Microbar
.. index::
   single: Measurement.NewtonPerSquareMetre
.. index::
   single: Measurement.NewtonPerSquareMillimetre
.. index::
   single: Measurement.PascalSecondPerBar
.. index::
   single: Measurement.HectopascalCubicMetrePerSecond
.. index::
   single: Measurement.HectopascalLitrePerSecond
.. index::
   single: Measurement.HectopascalPerKelvin
.. index::
   single: Measurement.KilopascalPerKelvin
.. index::
   single: Measurement.MegapascalCubicMetrePerSecond
.. index::
   single: Measurement.MegapascalLitrePerSecond
.. index::
   single: Measurement.MegapascalPerKelvin
.. index::
   single: Measurement.MillibarCubicMetrePerSecond
.. index::
   single: Measurement.MillibarLitrePerSecond
.. index::
   single: Measurement.MillibarPerKelvin
.. index::
   single: Measurement.PascalCubicMetrePerSecond
.. index::
   single: Measurement.PascalLitrePerSecond
.. index::
   single: Measurement.PascalSecondPerKelvin
.. index::
   single: Measurement.NewtonPerSquareCentimetre
.. index::
   single: Measurement.PoundPerSquareFoot
.. index::
   single: Measurement.PoundforcePerSquareInch
.. index::
   single: Measurement.PoundPerSquareInchAbsolute
.. index::
   single: Measurement.InchOfMercury
.. index::
   single: Measurement.InchOfWater
.. index::
   single: Measurement.GramforcePerSquareCentimetre
.. index::
   single: Measurement.KilogramforcePerSquareCentimetre
.. index::
   single: Measurement.KilogramforcePerSquareMillimetre
.. index::
   single: Measurement.PoundforcePerSquareFoot
.. index::
   single: Measurement.PoundforcePerSquareInchDegreeFahrenheit
.. index::
   single: Measurement.CentimetreOfMercuryDegC
.. index::
   single: Measurement.CentimetreOfWaterDegC
.. index::
   single: Measurement.FootOfWaterDegF
.. index::
   single: Measurement.InchOfMercury32DegF
.. index::
   single: Measurement.InchOfMercury60DegF
.. index::
   single: Measurement.InchOfWater39DegF
.. index::
   single: Measurement.InchOfWater60DegF
.. index::
   single: Measurement.KipPerSquareInch
.. index::
   single: Measurement.PoundalPerSquareFoot
.. index::
   single: Measurement.OunceAvoirdupoisPerSquareInch
.. index::
   single: Measurement.ConventionalMetreOfWater
.. index::
   single: Measurement.GramPerSquareMillimetre
.. index::
   single: Measurement.PoundPerSquareYard
.. index::
   single: Measurement.PoundalPerSquareInch
.. index::
   single: Measurement.HectopascalPerBar
.. index::
   single: Measurement.MegapascalPerBar
.. index::
   single: Measurement.MillibarPerBar
.. index::
   single: Measurement.PascalPerBar
.. index::
   single: Measurement.KilopascalPerBar
.. index::
   single: Measurement.PsiPerPsi
.. index::
   single: Measurement.BarPerBar
.. index::
   single: Measurement.ReciprocalPascalOrPascalToThePowerMinusOne
.. index::
   single: Measurement.ReciprocalBar
.. index::
   single: Measurement.MetreToTheFourthPower
.. index::
   single: Measurement.MillimetreToTheFourthPower
.. index::
   single: Measurement.InchToTheFourthPower
.. index::
   single: Measurement.FootToTheFourthPower
.. index::
   single: Measurement.PascalSecond
.. index::
   single: Measurement.KilogramPerMetreSecond
.. index::
   single: Measurement.KilogramPerMetreMinute
.. index::
   single: Measurement.MillipascalSecond
.. index::
   single: Measurement.NewtonSecondPerSquareMetre
.. index::
   single: Measurement.KilogramPerMetreDay
.. index::
   single: Measurement.KilogramPerMetreHour
.. index::
   single: Measurement.GramPerCentimetreSecond
.. index::
   single: Measurement.Poise
.. index::
   single: Measurement.Centipoise
.. index::
   single: Measurement.PoisePerBar
.. index::
   single: Measurement.PoisePerKelvin
.. index::
   single: Measurement.Micropoise
.. index::
   single: Measurement.CentipoisePerKelvin
.. index::
   single: Measurement.CentipoisePerBar
.. index::
   single: Measurement.PoundPerFootHour
.. index::
   single: Measurement.PoundPerFootSecond
.. index::
   single: Measurement.PoundforceSecondPerSquareFoot
.. index::
   single: Measurement.PoundforceSecondPerSquareInch
.. index::
   single: Measurement.MillipascalSecondPerKelvin
.. index::
   single: Measurement.MillipascalSecondPerBar
.. index::
   single: Measurement.SlugPerFootSecond
.. index::
   single: Measurement.PoundalSecondPerSquareFoot
.. index::
   single: Measurement.PoisePerPascal
.. index::
   single: Measurement.PoundalSecondPerSquareInch
.. index::
   single: Measurement.PoundPerFootMinute
.. index::
   single: Measurement.PoundPerFootDay
.. index::
   single: Measurement.SquareMetrePerSecond
.. index::
   single: Measurement.SquareMetrePerSecondPascal
.. index::
   single: Measurement.MillimetreSquaredPerSecond
.. index::
   single: Measurement.SquareMetrePerSecondBar
.. index::
   single: Measurement.SquareMetrePerSecondKelvin
.. index::
   single: Measurement.Stokes
.. index::
   single: Measurement.Centistokes
.. index::
   single: Measurement.StokesPerBar
.. index::
   single: Measurement.StokesPerKelvin
.. index::
   single: Measurement.SquareFootPerSecond
.. index::
   single: Measurement.SquareInchPerSecond
.. index::
   single: Measurement.SquareFootPerHour
.. index::
   single: Measurement.StokesPerPascal
.. index::
   single: Measurement.SquareCentimetrePerSecond
.. index::
   single: Measurement.NewtonPerMetre
.. index::
   single: Measurement.MillinewtonPerMetre
.. index::
   single: Measurement.NewtonPerCentimetre
.. index::
   single: Measurement.KilonewtonPerMetre
.. index::
   single: Measurement.PoundalPerInch
.. index::
   single: Measurement.PoundforcePerYard
.. index::
   single: Measurement.NewtonMetrePerSquareMetre
.. index::
   single: Measurement.Joule
.. index::
   single: Measurement.Kilojoule
.. index::
   single: Measurement.Exajoule
.. index::
   single: Measurement.Petajoule
.. index::
   single: Measurement.Terajoule
.. index::
   single: Measurement.Gigajoule
.. index::
   single: Measurement.Megajoule
.. index::
   single: Measurement.Millijoule
.. index::
   single: Measurement.Femtojoule
.. index::
   single: Measurement.Attojoule
.. index::
   single: Measurement.WattHour
.. index::
   single: Measurement.MegawattHourKWh
.. index::
   single: Measurement.KilowattHour
.. index::
   single: Measurement.GigawattHour
.. index::
   single: Measurement.TerawattHour
.. index::
   single: Measurement.Electronvolt
.. index::
   single: Measurement.Megaelectronvolt
.. index::
   single: Measurement.Gigaelectronvolt
.. index::
   single: Measurement.Kiloelectronvolt
.. index::
   single: Measurement.FootPoundforce
.. index::
   single: Measurement.FootPoundal
.. index::
   single: Measurement.InchPoundal
.. index::
   single: Measurement.Watt
.. index::
   single: Measurement.Kilowatt
.. index::
   single: Measurement.Megawatt
.. index::
   single: Measurement.Gigawatt
.. index::
   single: Measurement.Milliwatt
.. index::
   single: Measurement.Microwatt
.. index::
   single: Measurement.FootPoundforcePerSecond
.. index::
   single: Measurement.BrakeHorsePower
.. index::
   single: Measurement.FootPoundforcePerHour
.. index::
   single: Measurement.FootPoundforcePerMinute
.. index::
   single: Measurement.HorsepowerBoiler
.. index::
   single: Measurement.Pferdestaerke
.. index::
   single: Measurement.KilogramPerSecond
.. index::
   single: Measurement.KilogramPerSquareMetreSecond
.. index::
   single: Measurement.KilogramPerSecondPascal
.. index::
   single: Measurement.MilligramPerHour
.. index::
   single: Measurement.GramPerDay
.. index::
   single: Measurement.GramPerDayBar
.. index::
   single: Measurement.GramPerDayKelvin
.. index::
   single: Measurement.GramPerHour
.. index::
   single: Measurement.GramPerHourBar
.. index::
   single: Measurement.GramPerHourKelvin
.. index::
   single: Measurement.GramPerMinute
.. index::
   single: Measurement.GramPerMinuteBar
.. index::
   single: Measurement.GramPerMinuteKelvin
.. index::
   single: Measurement.GramPerSecond
.. index::
   single: Measurement.GramPerSecondBar
.. index::
   single: Measurement.GramPerSecondKelvin
.. index::
   single: Measurement.KilogramPerDay
.. index::
   single: Measurement.KilogramPerDayBar
.. index::
   single: Measurement.KilogramPerDayKelvin
.. index::
   single: Measurement.KilogramPerHour
.. index::
   single: Measurement.KilogramPerHourBar
.. index::
   single: Measurement.KilogramPerHourKelvin
.. index::
   single: Measurement.KilogramPerMinute
.. index::
   single: Measurement.KilogramPerMinuteBar
.. index::
   single: Measurement.KilogramPerMinuteKelvin
.. index::
   single: Measurement.KilogramPerSecondBar
.. index::
   single: Measurement.KilogramPerSecondKelvin
.. index::
   single: Measurement.MilligramPerDay
.. index::
   single: Measurement.MilligramPerDayBar
.. index::
   single: Measurement.MilligramPerDayKelvin
.. index::
   single: Measurement.MilligramPerHourBar
.. index::
   single: Measurement.MilligramPerHourKelvin
.. index::
   single: Measurement.MilligramPerMinute
.. index::
   single: Measurement.MilligramPerMinuteBar
.. index::
   single: Measurement.MilligramPerMinuteKelvin
.. index::
   single: Measurement.MilligramPerSecond
.. index::
   single: Measurement.MilligramPerSecondBar
.. index::
   single: Measurement.MilligramPerSecondKelvin
.. index::
   single: Measurement.GramPerHertz
.. index::
   single: Measurement.TonUSPerHour
.. index::
   single: Measurement.PoundPerHour
.. index::
   single: Measurement.PoundAvoirdupoisPerDay
.. index::
   single: Measurement.PoundAvoirdupoisPerHourDegreeFahrenheit
.. index::
   single: Measurement.PoundAvoirdupoisPerHourPsi
.. index::
   single: Measurement.PoundAvoirdupoisPerMinute
.. index::
   single: Measurement.PoundAvoirdupoisPerMinuteDegreeFahrenheit
.. index::
   single: Measurement.PoundAvoirdupoisPerMinutePsi
.. index::
   single: Measurement.PoundAvoirdupoisPerSecond
.. index::
   single: Measurement.PoundAvoirdupoisPerSecondDegreeFahrenheit
.. index::
   single: Measurement.PoundAvoirdupoisPerSecondPsi
.. index::
   single: Measurement.OunceAvoirdupoisPerDay
.. index::
   single: Measurement.OunceAvoirdupoisPerHour
.. index::
   single: Measurement.OunceAvoirdupoisPerMinute
.. index::
   single: Measurement.OunceAvoirdupoisPerSecond
.. index::
   single: Measurement.SlugPerDay
.. index::
   single: Measurement.SlugPerHour
.. index::
   single: Measurement.SlugPerMinute
.. index::
   single: Measurement.SlugPerSecond
.. index::
   single: Measurement.TonnePerDay
.. index::
   single: Measurement.TonnePerDayKelvin
.. index::
   single: Measurement.TonnePerDayBar
.. index::
   single: Measurement.TonnePerHour
.. index::
   single: Measurement.TonnePerHourKelvin
.. index::
   single: Measurement.TonnePerHourBar
.. index::
   single: Measurement.TonnePerMinute
.. index::
   single: Measurement.TonnePerMinuteKelvin
.. index::
   single: Measurement.TonnePerMinuteBar
.. index::
   single: Measurement.TonnePerSecond
.. index::
   single: Measurement.TonnePerSecondKelvin
.. index::
   single: Measurement.TonnePerSecondBar
.. index::
   single: Measurement.TonLongPerDay
.. index::
   single: Measurement.TonShortPerDay
.. index::
   single: Measurement.TonShortPerHourDegreeFahrenheit
.. index::
   single: Measurement.TonShortPerHourPsi
.. index::
   single: Measurement.TonnePerMonth
.. index::
   single: Measurement.TonnePerYear
.. index::
   single: Measurement.KilopoundPerHour
.. index::
   single: Measurement.MicrogramPerKilogram
.. index::
   single: Measurement.NanogramPerKilogram
.. index::
   single: Measurement.MilligramPerKilogram
.. index::
   single: Measurement.KilogramPerKilogram
.. index::
   single: Measurement.PoundPerPound
.. index::
   single: Measurement.CubicMetrePerSecond
.. index::
   single: Measurement.CubicMetrePerHour
.. index::
   single: Measurement.MillilitrePerSecond
.. index::
   single: Measurement.MillilitrePerMinute
.. index::
   single: Measurement.LitrePerDay
.. index::
   single: Measurement.CubicCentimetrePerSecond
.. index::
   single: Measurement.KilolitrePerHour
.. index::
   single: Measurement.LitrePerMinute
.. index::
   single: Measurement.CubicCentimetrePerDay
.. index::
   single: Measurement.CubicCentimetrePerDayBar
.. index::
   single: Measurement.CubicCentimetrePerDayKelvin
.. index::
   single: Measurement.CubicCentimetrePerHour
.. index::
   single: Measurement.CubicCentimetrePerHourBar
.. index::
   single: Measurement.CubicCentimetrePerHourKelvin
.. index::
   single: Measurement.CubicCentimetrePerMinute
.. index::
   single: Measurement.CubicCentimetrePerMinuteBar
.. index::
   single: Measurement.CubicCentimetrePerMinuteKelvin
.. index::
   single: Measurement.CubicCentimetrePerSecondBar
.. index::
   single: Measurement.CubicCentimetrePerSecondKelvin
.. index::
   single: Measurement.CubicDecimetrePerHour
.. index::
   single: Measurement.CubicMetrePerDay
.. index::
   single: Measurement.CubicMetrePerDayBar
.. index::
   single: Measurement.CubicMetrePerDayKelvin
.. index::
   single: Measurement.CubicMetrePerHourBar
.. index::
   single: Measurement.CubicMetrePerHourKelvin
.. index::
   single: Measurement.CubicMetrePerMinute
.. index::
   single: Measurement.CubicMetrePerMinuteBar
.. index::
   single: Measurement.CubicMetrePerMinuteKelvin
.. index::
   single: Measurement.CubicMetrePerSecondBar
.. index::
   single: Measurement.CubicMetrePerSecondKelvin
.. index::
   single: Measurement.LitrePerDayBar
.. index::
   single: Measurement.LitrePerDayKelvin
.. index::
   single: Measurement.LitrePerHourBar
.. index::
   single: Measurement.LitrePerHourKelvin
.. index::
   single: Measurement.LitrePerMinuteBar
.. index::
   single: Measurement.LitrePerMinuteKelvin
.. index::
   single: Measurement.LitrePerSecond
.. index::
   single: Measurement.LitrePerSecondBar
.. index::
   single: Measurement.LitrePerSecondKelvin
.. index::
   single: Measurement.MillilitrePerDay
.. index::
   single: Measurement.MillilitrePerDayBar
.. index::
   single: Measurement.MillilitrePerDayKelvin
.. index::
   single: Measurement.MillilitrePerHour
.. index::
   single: Measurement.MillilitrePerHourBar
.. index::
   single: Measurement.MillilitrePerHourKelvin
.. index::
   single: Measurement.MillilitrePerMinuteBar
.. index::
   single: Measurement.MillilitrePerMinuteKelvin
.. index::
   single: Measurement.MillilitrePerSecondBar
.. index::
   single: Measurement.MillilitrePerSecondKelvin
.. index::
   single: Measurement.CubicFootPerHour
.. index::
   single: Measurement.CubicFootPerMinute
.. index::
   single: Measurement.BarrelUSPerMinute
.. index::
   single: Measurement.USGallonPerMinute
.. index::
   single: Measurement.ImperialGallonPerMinute
.. index::
   single: Measurement.CubicInchPerHour
.. index::
   single: Measurement.CubicInchPerMinute
.. index::
   single: Measurement.CubicInchPerSecond
.. index::
   single: Measurement.GallonUSPerHour
.. index::
   single: Measurement.BarrelUKPetroleumPerMinute
.. index::
   single: Measurement.BarrelUKPetroleumPerDay
.. index::
   single: Measurement.BarrelUKPetroleumPerHour
.. index::
   single: Measurement.BarrelUKPetroleumPerSecond
.. index::
   single: Measurement.BarrelUSPetroleumPerHour
.. index::
   single: Measurement.BarrelUSPetroleumPerSecond
.. index::
   single: Measurement.BushelUKPerDay
.. index::
   single: Measurement.BushelUKPerHour
.. index::
   single: Measurement.BushelUKPerMinute
.. index::
   single: Measurement.BushelUKPerSecond
.. index::
   single: Measurement.BushelUSDryPerDay
.. index::
   single: Measurement.BushelUSDryPerHour
.. index::
   single: Measurement.BushelUSDryPerMinute
.. index::
   single: Measurement.BushelUSDryPerSecond
.. index::
   single: Measurement.CubicDecimetrePerDay
.. index::
   single: Measurement.CubicDecimetrePerMinute
.. index::
   single: Measurement.CubicDecimetrePerSecond
.. index::
   single: Measurement.CubicMetrePerSecondPascal
.. index::
   single: Measurement.OunceUKFluidPerDay
.. index::
   single: Measurement.OunceUKFluidPerHour
.. index::
   single: Measurement.OunceUKFluidPerMinute
.. index::
   single: Measurement.OunceUKFluidPerSecond
.. index::
   single: Measurement.OunceUSFluidPerDay
.. index::
   single: Measurement.OunceUSFluidPerHour
.. index::
   single: Measurement.OunceUSFluidPerMinute
.. index::
   single: Measurement.OunceUSFluidPerSecond
.. index::
   single: Measurement.CubicFootPerDay
.. index::
   single: Measurement.GallonUKPerDay
.. index::
   single: Measurement.GallonUKPerHour
.. index::
   single: Measurement.GallonUKPerSecond
.. index::
   single: Measurement.GallonUSLiquidPerSecond
.. index::
   single: Measurement.GillUKPerDay
.. index::
   single: Measurement.GillUKPerHour
.. index::
   single: Measurement.GillUKPerMinute
.. index::
   single: Measurement.GillUKPerSecond
.. index::
   single: Measurement.GillUSPerDay
.. index::
   single: Measurement.GillUSPerHour
.. index::
   single: Measurement.GillUSPerMinute
.. index::
   single: Measurement.GillUSPerSecond
.. index::
   single: Measurement.QuartUKLiquidPerDay
.. index::
   single: Measurement.QuartUKLiquidPerHour
.. index::
   single: Measurement.QuartUKLiquidPerMinute
.. index::
   single: Measurement.QuartUKLiquidPerSecond
.. index::
   single: Measurement.QuartUSLiquidPerDay
.. index::
   single: Measurement.QuartUSLiquidPerHour
.. index::
   single: Measurement.QuartUSLiquidPerMinute
.. index::
   single: Measurement.QuartUSLiquidPerSecond
.. index::
   single: Measurement.PeckUKPerDay
.. index::
   single: Measurement.PeckUKPerHour
.. index::
   single: Measurement.PeckUKPerMinute
.. index::
   single: Measurement.PeckUKPerSecond
.. index::
   single: Measurement.PeckUSDryPerDay
.. index::
   single: Measurement.PeckUSDryPerHour
.. index::
   single: Measurement.PeckUSDryPerMinute
.. index::
   single: Measurement.PeckUSDryPerSecond
.. index::
   single: Measurement.PintUKPerDay
.. index::
   single: Measurement.PintUKPerHour
.. index::
   single: Measurement.PintUKPerMinute
.. index::
   single: Measurement.PintUKPerSecond
.. index::
   single: Measurement.PintUSLiquidPerDay
.. index::
   single: Measurement.PintUSLiquidPerHour
.. index::
   single: Measurement.PintUSLiquidPerMinute
.. index::
   single: Measurement.PintUSLiquidPerSecond
.. index::
   single: Measurement.CubicYardPerDay
.. index::
   single: Measurement.CubicYardPerHour
.. index::
   single: Measurement.CubicYardPerMinute
.. index::
   single: Measurement.CubicYardPerSecond
.. index::
   single: Measurement.CubicMetrePerCubicMetre
.. index::
   single: Measurement.BarCubicMetrePerSecond
.. index::
   single: Measurement.BarLitrePerSecond
.. index::
   single: Measurement.PsiCubicInchPerSecond
.. index::
   single: Measurement.PsiLitrePerSecond
.. index::
   single: Measurement.PsiCubicMetrePerSecond
.. index::
   single: Measurement.PsiCubicYardPerSecond
.. index::
   single: Measurement.Kelvin
.. index::
   single: Measurement.DegreeCelsius
.. index::
   single: Measurement.DegreeCelsiusPerHour
.. index::
   single: Measurement.DegreeCelsiusPerBar
.. index::
   single: Measurement.DegreeCelsiusPerKelvin
.. index::
   single: Measurement.DegreeCelsiusPerMinute
.. index::
   single: Measurement.DegreeCelsiusPerSecond
.. index::
   single: Measurement.KelvinPerBar
.. index::
   single: Measurement.KelvinPerHour
.. index::
   single: Measurement.KelvinPerKelvin
.. index::
   single: Measurement.KelvinPerMinute
.. index::
   single: Measurement.KelvinPerSecond
.. index::
   single: Measurement.KelvinPerPascal
.. index::
   single: Measurement.DegreeFahrenheitPerKelvin
.. index::
   single: Measurement.DegreeFahrenheitPerBar
.. index::
   single: Measurement.ReciprocalDegreeFahrenheit
.. index::
   single: Measurement.DegreeRankine
.. index::
   single: Measurement.DegreeFahrenheit
.. index::
   single: Measurement.DegreeFahrenheitPerHour
.. index::
   single: Measurement.DegreeFahrenheitPerMinute
.. index::
   single: Measurement.DegreeFahrenheitPerSecond
.. index::
   single: Measurement.DegreeRankinePerHour
.. index::
   single: Measurement.DegreeRankinePerMinute
.. index::
   single: Measurement.DegreeRankinePerSecond
.. index::
   single: Measurement.ReciprocalKelvinOrKelvinToThePowerMinusOne
.. index::
   single: Measurement.ReciprocalMegakelvinOrMegakelvinToThePowerMinusOne
.. index::
   single: Measurement.PascalPerKelvin
.. index::
   single: Measurement.BarPerKelvin
.. index::
   single: Measurement.WattSecond
.. index::
   single: Measurement.BritishThermalUnitInternationalTable
.. index::
   single: Measurement.BritishThermalUnitMean
.. index::
   single: Measurement.CalorieMean
.. index::
   single: Measurement.KilocalorieMean
.. index::
   single: Measurement.KilocalorieInternationalTable
.. index::
   single: Measurement.KilocalorieThermochemical
.. index::
   single: Measurement.BritishThermalUnit39DegF
.. index::
   single: Measurement.BritishThermalUnit59DegF
.. index::
   single: Measurement.BritishThermalUnit60DegF
.. index::
   single: Measurement.CalorieDegC
.. index::
   single: Measurement.QuadBtuIT
.. index::
   single: Measurement.ThermEC
.. index::
   single: Measurement.ThermUS
.. index::
   single: Measurement.BritishThermalUnitInternationalTablePerHour
.. index::
   single: Measurement.BritishThermalUnitInternationalTablePerMinute
.. index::
   single: Measurement.BritishThermalUnitInternationalTablePerSecond
.. index::
   single: Measurement.BritishThermalUnitThermochemicalPerHour
.. index::
   single: Measurement.BritishThermalUnitThermochemicalPerMinute
.. index::
   single: Measurement.BritishThermalUnitThermochemicalPerSecond
.. index::
   single: Measurement.CalorieThermochemicalPerMinute
.. index::
   single: Measurement.CalorieThermochemicalPerSecond
.. index::
   single: Measurement.KilocalorieThermochemicalPerHour
.. index::
   single: Measurement.KilocalorieThermochemicalPerMinute
.. index::
   single: Measurement.KilocalorieThermochemicalPerSecond
.. index::
   single: Measurement.WattPerSquareMetre
.. index::
   single: Measurement.WattPerSquareCentimetre
.. index::
   single: Measurement.WattPerSquareInch
.. index::
   single: Measurement.BritishThermalUnitInternationalTablePerSquareFootHour
.. index::
   single: Measurement.BritishThermalUnitThermochemicalPerSquareFootHour
.. index::
   single: Measurement.BritishThermalUnitThermochemicalPerSquareFootMinute
.. index::
   single: Measurement.BritishThermalUnitInternationalTablePerSquareFootSecond
.. index::
   single: Measurement.BritishThermalUnitThermochemicalPerSquareFootSecond
.. index::
   single: Measurement.BritishThermalUnitInternationalTablePerSquareInchSecond
.. index::
   single: Measurement.CalorieThermochemicalPerSquareCentimetreMinute
.. index::
   single: Measurement.CalorieThermochemicalPerSquareCentimetreSecond
.. index::
   single: Measurement.WattPerMetreKelvin
.. index::
   single: Measurement.WattPerMetreDegreeCelsius
.. index::
   single: Measurement.KilowattPerMetreKelvin
.. index::
   single: Measurement.KilowattPerMetreDegreeCelsius
.. index::
   single: Measurement.BritishThermalUnitInternationalTablePerSecondFootDegreeRankine
.. index::
   single: Measurement.BritishThermalUnitInternationalTableFootPerHourSquareFootDegreeFahrenheit
.. index::
   single: Measurement.BritishThermalUnitInternationalTableInchPerHourSquareFootDegreeFahrenheit
.. index::
   single: Measurement.BritishThermalUnitInternationalTableInchPerSecondSquareFootDegreeFahrenheit
.. index::
   single: Measurement.BritishThermalUnitThermochemicalFootPerHourSquareFootDegreeFahrenheit
.. index::
   single: Measurement.BritishThermalUnitThermochemicalInchPerHourSquareFootDegreeFahrenheit
.. index::
   single: Measurement.BritishThermalUnitThermochemicalInchPerSecondSquareFootDegreeFahrenheit
.. index::
   single: Measurement.CalorieThermochemicalPerCentimetreSecondDegreeCelsius
.. index::
   single: Measurement.KilocalorieInternationalTablePerHourMetreDegreeCelsius
.. index::
   single: Measurement.WattPerSquareMetreKelvin
.. index::
   single: Measurement.KilowattPerSquareMetreKelvin
.. index::
   single: Measurement.BritishThermalUnitInternationalTablePerSecondSquareFootDegreeRankine
.. index::
   single: Measurement.BritishThermalUnitInternationalTablePerHourSquareFootDegreeRankine
.. index::
   single: Measurement.BritishThermalUnitInternationalTablePerHourSquareFootDegreeFahrenheit
.. index::
   single: Measurement.BritishThermalUnitThermochemicalPerHourSquareFootDegreeFahrenheit
.. index::
   single: Measurement.BritishThermalUnitInternationalTablePerSecondSquareFootDegreeFahrenheit
.. index::
   single: Measurement.BritishThermalUnitThermochemicalPerSecondSquareFootDegreeFahrenheit
.. index::
   single: Measurement.SquareMetreKelvinPerWatt
.. index::
   single: Measurement.DegreeFahrenheitHourSquareFootPerBritishThermalUnitThermochemical
.. index::
   single: Measurement.DegreeFahrenheitHourSquareFootPerBritishThermalUnitInternationalTable
.. index::
   single: Measurement.Clo
.. index::
   single: Measurement.SquareMetreHourDegreeCelsiusPerKilocalorieInternationalTable
.. index::
   single: Measurement.KelvinPerWatt
.. index::
   single: Measurement.KelvinMetrePerWatt
.. index::
   single: Measurement.DegreeFahrenheitHourPerBritishThermalUnitInternationalTable
.. index::
   single: Measurement.DegreeFahrenheitHourPerBritishThermalUnitThermochemical
.. index::
   single: Measurement.DegreeFahrenheitSecondPerBritishThermalUnitInternationalTable
.. index::
   single: Measurement.DegreeFahrenheitSecondPerBritishThermalUnitThermochemical
.. index::
   single: Measurement.DegreeFahrenheitHourSquareFootPerBritishThermalUnitInternationalTableInch
.. index::
   single: Measurement.DegreeFahrenheitHourSquareFootPerBritishThermalUnitThermochemicalInch
.. index::
   single: Measurement.WattPerKelvin
.. index::
   single: Measurement.MillimetrePerDegreeCelciusMetre
.. index::
   single: Measurement.MillimetrePerKelvin
.. index::
   single: Measurement.MetrePerDegreeCelciusMetre
.. index::
   single: Measurement.JoulePerKelvin
.. index::
   single: Measurement.KilojoulePerKelvin
.. index::
   single: Measurement.BritishThermalUnitInternationalTablePerPoundDegreeFahrenheit
.. index::
   single: Measurement.BritishThermalUnitThermochemicalPerPoundDegreeFahrenheit
.. index::
   single: Measurement.CalorieInternationalTablePerGramDegreeCelsius
.. index::
   single: Measurement.CalorieThermochemicalPerGramDegreeCelsius
.. index::
   single: Measurement.BritishThermalUnitInternationalTablePerDegreeFahrenheit
.. index::
   single: Measurement.BritishThermalUnitThermochemicalPerDegreeFahrenheit
.. index::
   single: Measurement.BritishThermalUnitInternationalTablePerDegreeRankine
.. index::
   single: Measurement.BritishThermalUnitThermochemicalPerDegreeRankine
.. index::
   single: Measurement.BritishThermalUnitThermochemicalPerPoundDegreeRankine
.. index::
   single: Measurement.KilocalorieInternationalTablePerGramKelvin
.. index::
   single: Measurement.JoulePerKilogramKelvin
.. index::
   single: Measurement.KilojoulePerKilogramKelvin
.. index::
   single: Measurement.BritishThermalUnitInternationalTablePerPoundDegreeRankine
.. index::
   single: Measurement.JoulePerKilogram
.. index::
   single: Measurement.JoulePerGram
.. index::
   single: Measurement.MegajoulePerKilogram
.. index::
   single: Measurement.KilojoulePerKilogram
.. index::
   single: Measurement.BritishThermalUnitInternationalTablePerPound
.. index::
   single: Measurement.BritishThermalUnitThermochemicalPerPound
.. index::
   single: Measurement.BritishThermalUnitInternationalTablePerCubicFoot
.. index::
   single: Measurement.BritishThermalUnitThermochemicalPerCubicFoot
.. index::
   single: Measurement.Ampere
.. index::
   single: Measurement.Kiloampere
.. index::
   single: Measurement.Megaampere
.. index::
   single: Measurement.Milliampere
.. index::
   single: Measurement.Microampere
.. index::
   single: Measurement.Nanoampere
.. index::
   single: Measurement.Picoampere
.. index::
   single: Measurement.Biot
.. index::
   single: Measurement.Gilbert
.. index::
   single: Measurement.Coulomb
.. index::
   single: Measurement.AmpereSecond
.. index::
   single: Measurement.AmpereSquaredSecond
.. index::
   single: Measurement.AmpereHour
.. index::
   single: Measurement.KiloampereHourThousandAmpereHour
.. index::
   single: Measurement.Megacoulomb
.. index::
   single: Measurement.Millicoulomb
.. index::
   single: Measurement.Kilocoulomb
.. index::
   single: Measurement.Microcoulomb
.. index::
   single: Measurement.Nanocoulomb
.. index::
   single: Measurement.Picocoulomb
.. index::
   single: Measurement.MilliampereHour
.. index::
   single: Measurement.AmpereMinute
.. index::
   single: Measurement.Franklin
.. index::
   single: Measurement.CoulombPerCubicMetre
.. index::
   single: Measurement.GigacoulombPerCubicMetre
.. index::
   single: Measurement.CoulombPerCubicMillimetre
.. index::
   single: Measurement.MegacoulombPerCubicMetre
.. index::
   single: Measurement.CoulombPerCubicCentimetre
.. index::
   single: Measurement.KilocoulombPerCubicMetre
.. index::
   single: Measurement.MillicoulombPerCubicMetre
.. index::
   single: Measurement.MicrocoulombPerCubicMetre
.. index::
   single: Measurement.CoulombPerSquareMetre
.. index::
   single: Measurement.MegacoulombPerSquareMetre
.. index::
   single: Measurement.CoulombPerSquareMillimetre
.. index::
   single: Measurement.CoulombPerSquareCentimetre
.. index::
   single: Measurement.KilocoulombPerSquareMetre
.. index::
   single: Measurement.MillicoulombPerSquareMetre
.. index::
   single: Measurement.MicrocoulombPerSquareMetre
.. index::
   single: Measurement.VoltPerMetre
.. index::
   single: Measurement.VoltSecondPerMetre
.. index::
   single: Measurement.VoltSquaredPerKelvinSquared
.. index::
   single: Measurement.VoltPerMillimetre
.. index::
   single: Measurement.VoltPerMicrosecond
.. index::
   single: Measurement.MillivoltPerMinute
.. index::
   single: Measurement.VoltPerSecond
.. index::
   single: Measurement.MegavoltPerMetre
.. index::
   single: Measurement.KilovoltPerMetre
.. index::
   single: Measurement.VoltPerCentimetre
.. index::
   single: Measurement.MillivoltPerMetre
.. index::
   single: Measurement.MicrovoltPerMetre
.. index::
   single: Measurement.VoltPerBar
.. index::
   single: Measurement.VoltPerPascal
.. index::
   single: Measurement.VoltPerLitreMinute
.. index::
   single: Measurement.VoltSquareInchPerPoundforce
.. index::
   single: Measurement.VoltPerInch
.. index::
   single: Measurement.Volt
.. index::
   single: Measurement.Megavolt
.. index::
   single: Measurement.Kilovolt
.. index::
   single: Measurement.Millivolt
.. index::
   single: Measurement.Microvolt
.. index::
   single: Measurement.Picovolt
.. index::
   single: Measurement.Farad
.. index::
   single: Measurement.Attofarad
.. index::
   single: Measurement.Millifarad
.. index::
   single: Measurement.Microfarad
.. index::
   single: Measurement.Nanofarad
.. index::
   single: Measurement.Picofarad
.. index::
   single: Measurement.Kilofarad
.. index::
   single: Measurement.FaradPerMetre
.. index::
   single: Measurement.MicrofaradPerKilometre
.. index::
   single: Measurement.FaradPerKilometre
.. index::
   single: Measurement.MicrofaradPerMetre
.. index::
   single: Measurement.NanofaradPerMetre
.. index::
   single: Measurement.PicofaradPerMetre
.. index::
   single: Measurement.CoulombMetre
.. index::
   single: Measurement.AmperePerSquareMetre
.. index::
   single: Measurement.AmperePerKilogram
.. index::
   single: Measurement.MegaamperePerSquareMetre
.. index::
   single: Measurement.AmperePerSquareMillimetre
.. index::
   single: Measurement.AmperePerSquareCentimetre
.. index::
   single: Measurement.KiloamperePerSquareMetre
.. index::
   single: Measurement.MilliamperePerLitreMinute
.. index::
   single: Measurement.AmperePerPascal
.. index::
   single: Measurement.MilliamperePerPoundforcePerSquareInch
.. index::
   single: Measurement.MilliamperePerBar
.. index::
   single: Measurement.AmperePerMetre
.. index::
   single: Measurement.KiloamperePerMetre
.. index::
   single: Measurement.AmperePerMillimetre
.. index::
   single: Measurement.AmperePerCentimetre
.. index::
   single: Measurement.MilliamperePerMillimetre
.. index::
   single: Measurement.MilliamperePerInch
.. index::
   single: Measurement.CoulombPerMetre
.. index::
   single: Measurement.Tesla
.. index::
   single: Measurement.Millitesla
.. index::
   single: Measurement.Microtesla
.. index::
   single: Measurement.Nanotesla
.. index::
   single: Measurement.Kilotesla
.. index::
   single: Measurement.Gamma
.. index::
   single: Measurement.Weber
.. index::
   single: Measurement.Milliweber
.. index::
   single: Measurement.Kiloweber
.. index::
   single: Measurement.WeberPerMetre
.. index::
   single: Measurement.KiloweberPerMetre
.. index::
   single: Measurement.WeberPerMillimetre
.. index::
   single: Measurement.Henry
.. index::
   single: Measurement.Millihenry
.. index::
   single: Measurement.Microhenry
.. index::
   single: Measurement.Nanohenry
.. index::
   single: Measurement.Picohenry
.. index::
   single: Measurement.HenryPerKiloohm
.. index::
   single: Measurement.HenryPerOhm
.. index::
   single: Measurement.MicrohenryPerKiloohm
.. index::
   single: Measurement.MicrohenryPerOhm
.. index::
   single: Measurement.MillihenryPerKiloohm
.. index::
   single: Measurement.MillihenryPerOhm
.. index::
   single: Measurement.Kilohenry
.. index::
   single: Measurement.HenryPerMetre
.. index::
   single: Measurement.MicrohenryPerMetre
.. index::
   single: Measurement.NanohenryPerMetre
.. index::
   single: Measurement.AmpereSquareMetre
.. index::
   single: Measurement.JoulePerCubicMetre
.. index::
   single: Measurement.Ohm
.. index::
   single: Measurement.Gigaohm
.. index::
   single: Measurement.Megaohm
.. index::
   single: Measurement.Teraohm
.. index::
   single: Measurement.Kiloohm
.. index::
   single: Measurement.Milliohm
.. index::
   single: Measurement.Microohm
.. index::
   single: Measurement.Nanoohm
.. index::
   single: Measurement.GigaohmPerMetre
.. index::
   single: Measurement.Siemens
.. index::
   single: Measurement.Kilosiemens
.. index::
   single: Measurement.Millisiemens
.. index::
   single: Measurement.Microsiemens
.. index::
   single: Measurement.MicrosiemensPerCentimetre
.. index::
   single: Measurement.MicrosiemensPerMetre
.. index::
   single: Measurement.Picosiemens
.. index::
   single: Measurement.OhmMetre
.. index::
   single: Measurement.GigaohmMetre
.. index::
   single: Measurement.MegaohmMetre
.. index::
   single: Measurement.MegaohmKilometre
.. index::
   single: Measurement.KiloohmMetre
.. index::
   single: Measurement.OhmCentimetre
.. index::
   single: Measurement.MilliohmMetre
.. index::
   single: Measurement.MicroohmMetre
.. index::
   single: Measurement.NanoohmMetre
.. index::
   single: Measurement.OhmKilometre
.. index::
   single: Measurement.OhmCircularmilPerFoot
.. index::
   single: Measurement.OhmPerKilometre
.. index::
   single: Measurement.OhmPerMetre
.. index::
   single: Measurement.MegaohmPerMetre
.. index::
   single: Measurement.MilliohmPerMetre
.. index::
   single: Measurement.MegaohmPerKilometre
.. index::
   single: Measurement.OhmPerMileStatuteMile
.. index::
   single: Measurement.SiemensPerMetre
.. index::
   single: Measurement.SiemensPerCentimetre
.. index::
   single: Measurement.MillisiemensPerCentimetre
.. index::
   single: Measurement.MegasiemensPerMetre
.. index::
   single: Measurement.KilosiemensPerMetre
.. index::
   single: Measurement.NanosiemensPerMetre
.. index::
   single: Measurement.NanosiemensPerCentimetre
.. index::
   single: Measurement.PicosiemensPerMetre
.. index::
   single: Measurement.ReciprocalHenry
.. index::
   single: Measurement.JoulePerSecond
.. index::
   single: Measurement.Terawatt
.. index::
   single: Measurement.JoulePerMinute
.. index::
   single: Measurement.JoulePerHour
.. index::
   single: Measurement.JoulePerDay
.. index::
   single: Measurement.KilojoulePerSecond
.. index::
   single: Measurement.KilojoulePerMinute
.. index::
   single: Measurement.KilojoulePerHour
.. index::
   single: Measurement.KilojoulePerDay
.. index::
   single: Measurement.HorsepowerElectric
.. index::
   single: Measurement.Nanowatt
.. index::
   single: Measurement.Picowatt
.. index::
   single: Measurement.VoltAmpere
.. index::
   single: Measurement.MegavoltAmpere
.. index::
   single: Measurement.KilovoltAmpere
.. index::
   single: Measurement.MillivoltAmpere
.. index::
   single: Measurement.Var
.. index::
   single: Measurement.Kilovar
.. index::
   single: Measurement.Megavar
.. index::
   single: Measurement.ReciprocalJoule
.. index::
   single: Measurement.ReciprocalVoltAmpereReciprocalSecond
.. index::
   single: Measurement.KilohertzMetre
.. index::
   single: Measurement.GigahertzMetre
.. index::
   single: Measurement.MegahertzMetre
.. index::
   single: Measurement.ReciprocalKilovoltAmpereReciprocalHour
.. index::
   single: Measurement.HertzMetre
.. index::
   single: Measurement.MegahertzKilometre
.. index::
   single: Measurement.RadianPerMetre
.. index::
   single: Measurement.MegajoulePerCubicMetre
.. index::
   single: Measurement.JoulePerMetreToTheFourthPower
.. index::
   single: Measurement.JoulePerSquareMetre
.. index::
   single: Measurement.ReciprocalSecondPerSteradian
.. index::
   single: Measurement.ReciprocalSecondPerSteradianMetreSquared
.. index::
   single: Measurement.ReciprocalSecondPerMetreSquared
.. index::
   single: Measurement.ReciprocalSquareMetre
.. index::
   single: Measurement.WattPerCubicMetre
.. index::
   single: Measurement.WattPerMetre
.. index::
   single: Measurement.JoulePerSquareCentimetre
.. index::
   single: Measurement.BritishThermalUnitInternationalTablePerSquareFoot
.. index::
   single: Measurement.BritishThermalUnitThermochemicalPerSquareFoot
.. index::
   single: Measurement.CalorieThermochemicalPerSquareCentimetre
.. index::
   single: Measurement.Langley
.. index::
   single: Measurement.WattPerSteradian
.. index::
   single: Measurement.WattPerSteradianSquareMetre
.. index::
   single: Measurement.WattPerSquareMetreKelvinToTheFourthPower
.. index::
   single: Measurement.MetreKelvin
.. index::
   single: Measurement.Candela
.. index::
   single: Measurement.Kilocandela
.. index::
   single: Measurement.Millicandela
.. index::
   single: Measurement.HefnerKerze
.. index::
   single: Measurement.InternationalCandle
.. index::
   single: Measurement.Lumen
.. index::
   single: Measurement.LumenSecond
.. index::
   single: Measurement.LumenHour
.. index::
   single: Measurement.CandelaPerSquareMetre
.. index::
   single: Measurement.CandelaPerSquareInch
.. index::
   single: Measurement.Footlambert
.. index::
   single: Measurement.Lambert
.. index::
   single: Measurement.Stilb
.. index::
   single: Measurement.CandelaPerSquareFoot
.. index::
   single: Measurement.LumenPerSquareMetre
.. index::
   single: Measurement.Lux
.. index::
   single: Measurement.Kilolux
.. index::
   single: Measurement.LumenPerSquareFoot
.. index::
   single: Measurement.Phot
.. index::
   single: Measurement.Footcandle
.. index::
   single: Measurement.LuxSecond
.. index::
   single: Measurement.LuxHour
.. index::
   single: Measurement.LumenPerWatt
.. index::
   single: Measurement.SquareMetrePerMole
.. index::
   single: Measurement.MilliwattPerSquareMetre
.. index::
   single: Measurement.MicrowattPerSquareMetre
.. index::
   single: Measurement.PicowattPerSquareMetre
.. index::
   single: Measurement.PascalSecondPerMetre
.. index::
   single: Measurement.PascalSecondPerCubicMetre
.. index::
   single: Measurement.PascalSecondPerLitre
.. index::
   single: Measurement.NewtonSecondPerMetre
.. index::
   single: Measurement.BelPerMetre
.. index::
   single: Measurement.DecibelPerKilometre
.. index::
   single: Measurement.DecibelPerMetre
.. index::
   single: Measurement.PascalSquaredSecond
.. index::
   single: Measurement.DecadeLogarithmic
.. index::
   single: Measurement.Mole
.. index::
   single: Measurement.Kilomole
.. index::
   single: Measurement.Millimole
.. index::
   single: Measurement.Micromole
.. index::
   single: Measurement.PoundMole
.. index::
   single: Measurement.ReciprocalMole
.. index::
   single: Measurement.KilogramPerMole
.. index::
   single: Measurement.GramPerMole
.. index::
   single: Measurement.CubicMetrePerMole
.. index::
   single: Measurement.CubicDecimetrePerMole
.. index::
   single: Measurement.CubicCentimetrePerMole
.. index::
   single: Measurement.LitrePerMole
.. index::
   single: Measurement.JoulePerMole
.. index::
   single: Measurement.KilojoulePerMole
.. index::
   single: Measurement.JoulePerMoleKelvin
.. index::
   single: Measurement.ReciprocalCubicMetre
.. index::
   single: Measurement.ReciprocalCubicCentimetre
.. index::
   single: Measurement.ReciprocalCubicMillimetre
.. index::
   single: Measurement.ReciprocalCubicFoot
.. index::
   single: Measurement.ReciprocalCubicInch
.. index::
   single: Measurement.ReciprocalLitre
.. index::
   single: Measurement.ReciprocalCubicYard
.. index::
   single: Measurement.MolePerCubicMetre
.. index::
   single: Measurement.MolePerLitre
.. index::
   single: Measurement.MolePerCubicDecimetre
.. index::
   single: Measurement.KilomolePerCubicMetre
.. index::
   single: Measurement.MolePerSecond
.. index::
   single: Measurement.MillimolePerLitre
.. index::
   single: Measurement.MolPerKilogramPascal
.. index::
   single: Measurement.MolPerCubicMetrePascal
.. index::
   single: Measurement.KilomolePerCubicMetreKelvin
.. index::
   single: Measurement.KilomolePerCubicMetreBar
.. index::
   single: Measurement.ReciprocalPsi
.. index::
   single: Measurement.MolePerKilogramKelvin
.. index::
   single: Measurement.MolePerKilogramBar
.. index::
   single: Measurement.MolePerLitreKelvin
.. index::
   single: Measurement.MolePerLitreBar
.. index::
   single: Measurement.MolePerCubicMetreKelvin
.. index::
   single: Measurement.MolePerCubicMetreBar
.. index::
   single: Measurement.MolePerKilogram
.. index::
   single: Measurement.SecondPerCubicMetre
.. index::
   single: Measurement.MillimolePerKilogram
.. index::
   single: Measurement.MillimolePerGram
.. index::
   single: Measurement.KilomolePerKilogram
.. index::
   single: Measurement.PoundMolePerPound
.. index::
   single: Measurement.Katal
.. index::
   single: Measurement.KilomolePerSecond
.. index::
   single: Measurement.PoundMolePerSecond
.. index::
   single: Measurement.PoundMolePerMinute
.. index::
   single: Measurement.UnifiedAtomicMassUnit
.. index::
   single: Measurement.CoulombMetreSquaredPerVolt
.. index::
   single: Measurement.CoulombPerMole
.. index::
   single: Measurement.SiemensSquareMetrePerMole
.. index::
   single: Measurement.KilomolePerHour
.. index::
   single: Measurement.KilomolePerMinute
.. index::
   single: Measurement.MolePerHour
.. index::
   single: Measurement.MolePerMinute
.. index::
   single: Measurement.RadianSquareMetrePerMole
.. index::
   single: Measurement.RadianSquareMetrePerKilogram
.. index::
   single: Measurement.NewtonSquareMetrePerAmpere
.. index::
   single: Measurement.WeberMetre
.. index::
   single: Measurement.JouleSecond
.. index::
   single: Measurement.AmpereSquareMetrePerJouleSecond
.. index::
   single: Measurement.Curie
.. index::
   single: Measurement.Millicurie
.. index::
   single: Measurement.Microcurie
.. index::
   single: Measurement.Kilocurie
.. index::
   single: Measurement.Becquerel
.. index::
   single: Measurement.Gigabecquerel
.. index::
   single: Measurement.Kilobecquerel
.. index::
   single: Measurement.Megabecquerel
.. index::
   single: Measurement.Microbecquerel
.. index::
   single: Measurement.CuriePerKilogram
.. index::
   single: Measurement.BecquerelPerKilogram
.. index::
   single: Measurement.MegabecquerelPerKilogram
.. index::
   single: Measurement.KilobecquerelPerKilogram
.. index::
   single: Measurement.BecquerelPerCubicMetre
.. index::
   single: Measurement.Barn
.. index::
   single: Measurement.SquareMetrePerSteradian
.. index::
   single: Measurement.BarnPerSteradian
.. index::
   single: Measurement.SquareMetrePerJoule
.. index::
   single: Measurement.BarnPerElectronvolt
.. index::
   single: Measurement.SquareCentimetrePerErg
.. index::
   single: Measurement.SquareMetrePerSteradianJoule
.. index::
   single: Measurement.BarnPerSteradianElectronvolt
.. index::
   single: Measurement.SquareCentimetrePerSteradianErg
.. index::
   single: Measurement.ReciprocalMetreSquaredReciprocalSecond
.. index::
   single: Measurement.SquareMetrePerKilogram
.. index::
   single: Measurement.JoulePerMetre
.. index::
   single: Measurement.ElectronvoltPerMetre
.. index::
   single: Measurement.JouleSquareMetre
.. index::
   single: Measurement.ElectronvoltSquareMetre
.. index::
   single: Measurement.JouleSquareMetrePerKilogram
.. index::
   single: Measurement.ElectronvoltSquareMetrePerKilogram
.. index::
   single: Measurement.SquareMetrePerVoltSecond
.. index::
   single: Measurement.MetrePerVoltSecond
.. index::
   single: Measurement.ReciprocalCubicMetrePerSecond
.. index::
   single: Measurement.Gray
.. index::
   single: Measurement.Milligray
.. index::
   single: Measurement.Rad
.. index::
   single: Measurement.Sievert
.. index::
   single: Measurement.Millisievert
.. index::
   single: Measurement.Rem
.. index::
   single: Measurement.MilliroentgenAequivalentMen
.. index::
   single: Measurement.GrayPerSecond
.. index::
   single: Measurement.CoulombPerKilogram
.. index::
   single: Measurement.MillicoulombPerKilogram
.. index::
   single: Measurement.Roentgen
.. index::
   single: Measurement.Milliroentgen
.. index::
   single: Measurement.CoulombSquareMetrePerKilogram
.. index::
   single: Measurement.Kiloroentgen
.. index::
   single: Measurement.CoulombPerKilogramSecond
.. index::
   single: Measurement.RoentgenPerSecond
.. index::
   single: Measurement.MilligrayPerSecond
.. index::
   single: Measurement.MicrograyPerSecond
.. index::
   single: Measurement.NanograyPerSecond
.. index::
   single: Measurement.GrayPerMinute
.. index::
   single: Measurement.MilligrayPerMinute
.. index::
   single: Measurement.MicrograyPerMinute
.. index::
   single: Measurement.NanograyPerMinute
.. index::
   single: Measurement.GrayPerHour
.. index::
   single: Measurement.MilligrayPerHour
.. index::
   single: Measurement.MicrograyPerHour
.. index::
   single: Measurement.NanograyPerHour
.. index::
   single: Measurement.SievertPerSecond
.. index::
   single: Measurement.MillisievertPerSecond
.. index::
   single: Measurement.MicrosievertPerSecond
.. index::
   single: Measurement.NanosievertPerSecond
.. index::
   single: Measurement.RemPerSecond
.. index::
   single: Measurement.SievertPerHour
.. index::
   single: Measurement.MillisievertPerHour
.. index::
   single: Measurement.MicrosievertPerHour
.. index::
   single: Measurement.NanosievertPerHour
.. index::
   single: Measurement.SievertPerMinute
.. index::
   single: Measurement.MillisievertPerMinute
.. index::
   single: Measurement.MicrosievertPerMinute
.. index::
   single: Measurement.NanosievertPerMinute
.. index::
   single: Measurement.ReciprocalSquareInch
.. index::
   single: Measurement.UnitPole
.. index::
   single: Measurement.ReciprocalAngstrom
.. index::
   single: Measurement.SecondPerCubicMetreRadian
.. index::
   single: Measurement.ReciprocalJoulePerCubicMetre
.. index::
   single: Measurement.ReciprocalElectronVoltPerCubicMetre
.. index::
   single: Measurement.CubicMetrePerCoulomb
.. index::
   single: Measurement.VoltPerKelvin
.. index::
   single: Measurement.MillivoltPerKelvin
.. index::
   single: Measurement.AmperePerSquareMetreKelvinSquared
.. index::
   single: Measurement.KilopascalSquareMetrePerGram
.. index::
   single: Measurement.PascalSquareMetrePerKilogram
.. index::
   single: Measurement.KilopascalPerMillimetre
.. index::
   single: Measurement.PascalPerMetre
.. index::
   single: Measurement.PicopascalPerKilometre
.. index::
   single: Measurement.MillipascalPerMetre
.. index::
   single: Measurement.KilopascalPerMetre
.. index::
   single: Measurement.HectopascalPerMetre
.. index::
   single: Measurement.StandardAtmospherePerMetre
.. index::
   single: Measurement.TechnicalAtmospherePerMetre
.. index::
   single: Measurement.TorrPerMetre
.. index::
   single: Measurement.PsiPerInch
.. index::
   single: Measurement.MillilitrePerSquareCentimetreSecond
.. index::
   single: Measurement.CubicMetrePerSecondSquareMetre
.. list-table::
  :widths: auto
  :header-rows: 1

  * - Name
    - Value
    - Description

      .. _enumitem_Measurement_NoUnit:
  * - ``Measurement.NoUnit``
    - ``0``
    -  

      .. _enumitem_Measurement_Radian:
  * - ``Measurement.Radian``
    - ``1``
    - rad

      .. _enumitem_Measurement_Milliradian:
  * - ``Measurement.Milliradian``
    - ``2``
    - mrad

      .. _enumitem_Measurement_Microradian:
  * - ``Measurement.Microradian``
    - ``3``
    - µrad

      .. _enumitem_Measurement_DegreeUnitOfAngle:
  * - ``Measurement.DegreeUnitOfAngle``
    - ``4``
    - °

      .. _enumitem_Measurement_MinuteUnitOfAngle:
  * - ``Measurement.MinuteUnitOfAngle``
    - ``5``
    - '

      .. _enumitem_Measurement_SecondUnitOfAngle:
  * - ``Measurement.SecondUnitOfAngle``
    - ``6``
    - "

      .. _enumitem_Measurement_Gon:
  * - ``Measurement.Gon``
    - ``7``
    - gon

      .. _enumitem_Measurement_Mil:
  * - ``Measurement.Mil``
    - ``8``
    - mil

      .. _enumitem_Measurement_Revolution:
  * - ``Measurement.Revolution``
    - ``9``
    - rev

      .. _enumitem_Measurement_Steradian:
  * - ``Measurement.Steradian``
    - ``10``
    - sr

      .. _enumitem_Measurement_InchPerTwoPiRadiant:
  * - ``Measurement.InchPerTwoPiRadiant``
    - ``11``
    - in/revolution

      .. _enumitem_Measurement_Metre:
  * - ``Measurement.Metre``
    - ``12``
    - m

      .. _enumitem_Measurement_DegreePerSecond:
  * - ``Measurement.DegreePerSecond``
    - ``13``
    - °/s

      .. _enumitem_Measurement_DegreePerMetre:
  * - ``Measurement.DegreePerMetre``
    - ``14``
    - °/m

      .. _enumitem_Measurement_MetrePerRadiant:
  * - ``Measurement.MetrePerRadiant``
    - ``15``
    - m/rad

      .. _enumitem_Measurement_Decimetre:
  * - ``Measurement.Decimetre``
    - ``16``
    - dm

      .. _enumitem_Measurement_Centimetre:
  * - ``Measurement.Centimetre``
    - ``17``
    - cm

      .. _enumitem_Measurement_MicrometreMicron:
  * - ``Measurement.MicrometreMicron``
    - ``18``
    - µm

      .. _enumitem_Measurement_Millimetre:
  * - ``Measurement.Millimetre``
    - ``19``
    - mm

      .. _enumitem_Measurement_Hectometre:
  * - ``Measurement.Hectometre``
    - ``20``
    - hm

      .. _enumitem_Measurement_Kilometre:
  * - ``Measurement.Kilometre``
    - ``21``
    - km

      .. _enumitem_Measurement_Nanometre:
  * - ``Measurement.Nanometre``
    - ``22``
    - nm

      .. _enumitem_Measurement_Picometre:
  * - ``Measurement.Picometre``
    - ``23``
    - pm

      .. _enumitem_Measurement_Femtometre:
  * - ``Measurement.Femtometre``
    - ``24``
    - fm

      .. _enumitem_Measurement_Decametre:
  * - ``Measurement.Decametre``
    - ``25``
    - dam

      .. _enumitem_Measurement_NauticalMile:
  * - ``Measurement.NauticalMile``
    - ``26``
    - n mile

      .. _enumitem_Measurement_Angstrom:
  * - ``Measurement.Angstrom``
    - ``27``
    - Å

      .. _enumitem_Measurement_AstronomicalUnit:
  * - ``Measurement.AstronomicalUnit``
    - ``28``
    - ua

      .. _enumitem_Measurement_Parsec:
  * - ``Measurement.Parsec``
    - ``29``
    - pc

      .. _enumitem_Measurement_MetrePerKelvin:
  * - ``Measurement.MetrePerKelvin``
    - ``30``
    - m/K

      .. _enumitem_Measurement_MicrometrePerKelvin:
  * - ``Measurement.MicrometrePerKelvin``
    - ``31``
    - µm/K

      .. _enumitem_Measurement_CentimetrePerKelvin:
  * - ``Measurement.CentimetrePerKelvin``
    - ``32``
    - cm/K

      .. _enumitem_Measurement_MillimetrePerBar:
  * - ``Measurement.MillimetrePerBar``
    - ``33``
    - mm/bar

      .. _enumitem_Measurement_GramMillimetre:
  * - ``Measurement.GramMillimetre``
    - ``34``
    - g·mm

      .. _enumitem_Measurement_CentimetrePerBar:
  * - ``Measurement.CentimetrePerBar``
    - ``35``
    - cm/bar

      .. _enumitem_Measurement_MetrePerBar:
  * - ``Measurement.MetrePerBar``
    - ``36``
    - m/bar

      .. _enumitem_Measurement_FrenchGauge:
  * - ``Measurement.FrenchGauge``
    - ``37``
    - Fg

      .. _enumitem_Measurement_Fathom:
  * - ``Measurement.Fathom``
    - ``38``
    - fth

      .. _enumitem_Measurement_GuntersChain:
  * - ``Measurement.GuntersChain``
    - ``39``
    - ch (UK)

      .. _enumitem_Measurement_Inch:
  * - ``Measurement.Inch``
    - ``40``
    - in

      .. _enumitem_Measurement_Microinch:
  * - ``Measurement.Microinch``
    - ``41``
    - µin

      .. _enumitem_Measurement_Foot:
  * - ``Measurement.Foot``
    - ``42``
    - ft

      .. _enumitem_Measurement_Yard:
  * - ``Measurement.Yard``
    - ``43``
    - yd

      .. _enumitem_Measurement_MileStatuteMile:
  * - ``Measurement.MileStatuteMile``
    - ``44``
    - mile

      .. _enumitem_Measurement_Milliinch:
  * - ``Measurement.Milliinch``
    - ``45``
    - mil

      .. _enumitem_Measurement_LightYear:
  * - ``Measurement.LightYear``
    - ``46``
    - ly

      .. _enumitem_Measurement_RodUnitOfDistance:
  * - ``Measurement.RodUnitOfDistance``
    - ``47``
    - rd (US)

      .. _enumitem_Measurement_Megametre:
  * - ``Measurement.Megametre``
    - ``48``
    - Mm

      .. _enumitem_Measurement_FootPerDegreeFahrenheit:
  * - ``Measurement.FootPerDegreeFahrenheit``
    - ``49``
    - ft/°F

      .. _enumitem_Measurement_FootPerPsi:
  * - ``Measurement.FootPerPsi``
    - ``50``
    - ft/psi

      .. _enumitem_Measurement_InchPerDegreeFahrenheit:
  * - ``Measurement.InchPerDegreeFahrenheit``
    - ``51``
    - in/°F

      .. _enumitem_Measurement_InchPerPsi:
  * - ``Measurement.InchPerPsi``
    - ``52``
    - in/psi

      .. _enumitem_Measurement_YardPerDegreeFahrenheit:
  * - ``Measurement.YardPerDegreeFahrenheit``
    - ``53``
    - yd/°F

      .. _enumitem_Measurement_YardPerPsi:
  * - ``Measurement.YardPerPsi``
    - ``54``
    - yd/psi

      .. _enumitem_Measurement_ChainBasedOnUSSurveyFoot:
  * - ``Measurement.ChainBasedOnUSSurveyFoot``
    - ``55``
    - ch (US survey) 

      .. _enumitem_Measurement_Furlong:
  * - ``Measurement.Furlong``
    - ``56``
    - fur

      .. _enumitem_Measurement_FootUSSurvey:
  * - ``Measurement.FootUSSurvey``
    - ``57``
    - ft (US survey) 

      .. _enumitem_Measurement_MileBasedOnUSSurveyFoot:
  * - ``Measurement.MileBasedOnUSSurveyFoot``
    - ``58``
    - mi (US survey) 

      .. _enumitem_Measurement_MetrePerPascal:
  * - ``Measurement.MetrePerPascal``
    - ``59``
    - m/Pa

      .. _enumitem_Measurement_SquareMetre:
  * - ``Measurement.SquareMetre``
    - ``60``
    - m²

      .. _enumitem_Measurement_SquareKilometre:
  * - ``Measurement.SquareKilometre``
    - ``61``
    - km²

      .. _enumitem_Measurement_SquareMicrometreSquareMicron:
  * - ``Measurement.SquareMicrometreSquareMicron``
    - ``62``
    - µm²

      .. _enumitem_Measurement_SquareMetrePerNewton:
  * - ``Measurement.SquareMetrePerNewton``
    - ``63``
    - m²/N

      .. _enumitem_Measurement_Decare:
  * - ``Measurement.Decare``
    - ``64``
    - daa

      .. _enumitem_Measurement_SquareCentimetre:
  * - ``Measurement.SquareCentimetre``
    - ``65``
    - cm²

      .. _enumitem_Measurement_SquareDecimetre:
  * - ``Measurement.SquareDecimetre``
    - ``66``
    - dm²

      .. _enumitem_Measurement_SquareDecametre:
  * - ``Measurement.SquareDecametre``
    - ``67``
    - dam²

      .. _enumitem_Measurement_SquareHectometre:
  * - ``Measurement.SquareHectometre``
    - ``68``
    - hm²

      .. _enumitem_Measurement_SquareMillimetre:
  * - ``Measurement.SquareMillimetre``
    - ``69``
    - mm²

      .. _enumitem_Measurement_SquareInch:
  * - ``Measurement.SquareInch``
    - ``70``
    - in²

      .. _enumitem_Measurement_SquareFoot:
  * - ``Measurement.SquareFoot``
    - ``71``
    - ft²

      .. _enumitem_Measurement_SquareYard:
  * - ``Measurement.SquareYard``
    - ``72``
    - yd²

      .. _enumitem_Measurement_SquareMileStatuteMile:
  * - ``Measurement.SquareMileStatuteMile``
    - ``73``
    - mi²

      .. _enumitem_Measurement_SquareMileBasedOnUSSurveyFoot:
  * - ``Measurement.SquareMileBasedOnUSSurveyFoot``
    - ``74``
    - mi² (US survey)

      .. _enumitem_Measurement_Acre:
  * - ``Measurement.Acre``
    - ``75``
    - acre

      .. _enumitem_Measurement_CircularMil:
  * - ``Measurement.CircularMil``
    - ``76``
    - cmil

      .. _enumitem_Measurement_CubicMetre:
  * - ``Measurement.CubicMetre``
    - ``77``
    - m³

      .. _enumitem_Measurement_Megalitre:
  * - ``Measurement.Megalitre``
    - ``78``
    - Ml

      .. _enumitem_Measurement_Litre:
  * - ``Measurement.Litre``
    - ``79``
    - l

      .. _enumitem_Measurement_CubicMillimetre:
  * - ``Measurement.CubicMillimetre``
    - ``80``
    - mm³

      .. _enumitem_Measurement_CubicCentimetre:
  * - ``Measurement.CubicCentimetre``
    - ``81``
    - cm³

      .. _enumitem_Measurement_CubicDecimetre:
  * - ``Measurement.CubicDecimetre``
    - ``82``
    - dm³

      .. _enumitem_Measurement_Millilitre:
  * - ``Measurement.Millilitre``
    - ``83``
    - ml

      .. _enumitem_Measurement_Hectolitre:
  * - ``Measurement.Hectolitre``
    - ``84``
    - hl

      .. _enumitem_Measurement_Centilitre:
  * - ``Measurement.Centilitre``
    - ``85``
    - cl

      .. _enumitem_Measurement_CubicDecametre:
  * - ``Measurement.CubicDecametre``
    - ``86``
    - dam³

      .. _enumitem_Measurement_CubicHectometre:
  * - ``Measurement.CubicHectometre``
    - ``87``
    - hm³

      .. _enumitem_Measurement_CubicKilometre:
  * - ``Measurement.CubicKilometre``
    - ``88``
    - km³

      .. _enumitem_Measurement_CubicMetrePerPascal:
  * - ``Measurement.CubicMetrePerPascal``
    - ``89``
    - m³/Pa

      .. _enumitem_Measurement_Decilitre:
  * - ``Measurement.Decilitre``
    - ``90``
    - dl

      .. _enumitem_Measurement_Microlitre:
  * - ``Measurement.Microlitre``
    - ``91``
    - µl

      .. _enumitem_Measurement_Kilolitre:
  * - ``Measurement.Kilolitre``
    - ``92``
    - kl

      .. _enumitem_Measurement_Decalitre:
  * - ``Measurement.Decalitre``
    - ``93``
    - dal

      .. _enumitem_Measurement_CubicCentimetrePerBar:
  * - ``Measurement.CubicCentimetrePerBar``
    - ``94``
    - cm³/bar

      .. _enumitem_Measurement_LitrePerBar:
  * - ``Measurement.LitrePerBar``
    - ``95``
    - l/bar

      .. _enumitem_Measurement_CubicMetrePerBar:
  * - ``Measurement.CubicMetrePerBar``
    - ``96``
    - m³/bar

      .. _enumitem_Measurement_MillilitrePerBar:
  * - ``Measurement.MillilitrePerBar``
    - ``97``
    - ml/bar

      .. _enumitem_Measurement_CubicInch:
  * - ``Measurement.CubicInch``
    - ``98``
    - in³

      .. _enumitem_Measurement_CubicFoot:
  * - ``Measurement.CubicFoot``
    - ``99``
    - ft³

      .. _enumitem_Measurement_CubicYard:
  * - ``Measurement.CubicYard``
    - ``100``
    - yd³

      .. _enumitem_Measurement_GallonUK:
  * - ``Measurement.GallonUK``
    - ``101``
    - gal (UK)

      .. _enumitem_Measurement_GallonUS:
  * - ``Measurement.GallonUS``
    - ``102``
    - gal (US)

      .. _enumitem_Measurement_PintUK:
  * - ``Measurement.PintUK``
    - ``103``
    - pt (UK)

      .. _enumitem_Measurement_QuartUK:
  * - ``Measurement.QuartUK``
    - ``104``
    - qt (UK)

      .. _enumitem_Measurement_LiquidPintUS:
  * - ``Measurement.LiquidPintUS``
    - ``105``
    - liq pt (US)

      .. _enumitem_Measurement_LiquidQuartUS:
  * - ``Measurement.LiquidQuartUS``
    - ``106``
    - liq qt (US)

      .. _enumitem_Measurement_DryPintUS:
  * - ``Measurement.DryPintUS``
    - ``107``
    - dry pt (US)

      .. _enumitem_Measurement_FluidOunceUK:
  * - ``Measurement.FluidOunceUK``
    - ``108``
    - fl oz (UK)

      .. _enumitem_Measurement_BarrelUKPetroleum:
  * - ``Measurement.BarrelUKPetroleum``
    - ``109``
    - bbl (UK liq.)

      .. _enumitem_Measurement_CubicFootPerDegreeFahrenheit:
  * - ``Measurement.CubicFootPerDegreeFahrenheit``
    - ``110``
    - ft³/°F

      .. _enumitem_Measurement_CubicFootPerPsi:
  * - ``Measurement.CubicFootPerPsi``
    - ``111``
    - ft³/psi

      .. _enumitem_Measurement_PeckUK:
  * - ``Measurement.PeckUK``
    - ``112``
    - pk (UK)

      .. _enumitem_Measurement_TonUKShipping:
  * - ``Measurement.TonUKShipping``
    - ``113``
    - British shipping ton

      .. _enumitem_Measurement_TonUSShipping:
  * - ``Measurement.TonUSShipping``
    - ``114``
    - (US) shipping ton

      .. _enumitem_Measurement_CubicYardPerDegreeFahrenheit:
  * - ``Measurement.CubicYardPerDegreeFahrenheit``
    - ``115``
    - yd³/°F

      .. _enumitem_Measurement_CubicYardPerPsi:
  * - ``Measurement.CubicYardPerPsi``
    - ``116``
    - yd³/psi

      .. _enumitem_Measurement_FluidOunceUS:
  * - ``Measurement.FluidOunceUS``
    - ``117``
    - fl oz (US)

      .. _enumitem_Measurement_BushelUK:
  * - ``Measurement.BushelUK``
    - ``118``
    - bushel (UK)

      .. _enumitem_Measurement_BushelUS:
  * - ``Measurement.BushelUS``
    - ``119``
    - bu (US)

      .. _enumitem_Measurement_BarrelUS:
  * - ``Measurement.BarrelUS``
    - ``120``
    - barrel (US)

      .. _enumitem_Measurement_DryBarrelUS:
  * - ``Measurement.DryBarrelUS``
    - ``121``
    - bbl (US)

      .. _enumitem_Measurement_DryGallonUS:
  * - ``Measurement.DryGallonUS``
    - ``122``
    - dry gal (US)

      .. _enumitem_Measurement_DryQuartUS:
  * - ``Measurement.DryQuartUS``
    - ``123``
    - dry qt (US)

      .. _enumitem_Measurement_Stere:
  * - ``Measurement.Stere``
    - ``124``
    - st

      .. _enumitem_Measurement_CupUnitOfVolume:
  * - ``Measurement.CupUnitOfVolume``
    - ``125``
    - cup (US)

      .. _enumitem_Measurement_TablespoonUS:
  * - ``Measurement.TablespoonUS``
    - ``126``
    - tablespoon (US)

      .. _enumitem_Measurement_TeaspoonUS:
  * - ``Measurement.TeaspoonUS``
    - ``127``
    - teaspoon (US)

      .. _enumitem_Measurement_Peck:
  * - ``Measurement.Peck``
    - ``128``
    - pk (US)

      .. _enumitem_Measurement_AcrefootBasedOnUSSurveyFoot:
  * - ``Measurement.AcrefootBasedOnUSSurveyFoot``
    - ``129``
    - acre-ft (US survey)

      .. _enumitem_Measurement_CordFt:
  * - ``Measurement.CordFt``
    - ``130``
    - cord

      .. _enumitem_Measurement_CubicMileUKStatute:
  * - ``Measurement.CubicMileUKStatute``
    - ``131``
    - mi³

      .. _enumitem_Measurement_TonRegister:
  * - ``Measurement.TonRegister``
    - ``132``
    - RT

      .. _enumitem_Measurement_CubicCentimetrePerKelvin:
  * - ``Measurement.CubicCentimetrePerKelvin``
    - ``133``
    - cm³/K

      .. _enumitem_Measurement_CubicMetrePerKelvin:
  * - ``Measurement.CubicMetrePerKelvin``
    - ``134``
    - m³/K

      .. _enumitem_Measurement_LitrePerKelvin:
  * - ``Measurement.LitrePerKelvin``
    - ``135``
    - l/K

      .. _enumitem_Measurement_MillilitrePerKelvin:
  * - ``Measurement.MillilitrePerKelvin``
    - ``136``
    - ml/K

      .. _enumitem_Measurement_MicrolitrePerLitre:
  * - ``Measurement.MicrolitrePerLitre``
    - ``137``
    - µl/l

      .. _enumitem_Measurement_CubicCentimetrePerCubicMetre:
  * - ``Measurement.CubicCentimetrePerCubicMetre``
    - ``138``
    - cm³/m³

      .. _enumitem_Measurement_CubicDecimetrePerCubicMetre:
  * - ``Measurement.CubicDecimetrePerCubicMetre``
    - ``139``
    - dm³/m³

      .. _enumitem_Measurement_LitrePerLitre:
  * - ``Measurement.LitrePerLitre``
    - ``140``
    - l/l

      .. _enumitem_Measurement_MillilitrePerLitre:
  * - ``Measurement.MillilitrePerLitre``
    - ``141``
    - ml/l

      .. _enumitem_Measurement_CubicMillimetrePerCubicMetre:
  * - ``Measurement.CubicMillimetrePerCubicMetre``
    - ``142``
    - mm³/m³

      .. _enumitem_Measurement_SecondUnitOfTime:
  * - ``Measurement.SecondUnitOfTime``
    - ``143``
    - s

      .. _enumitem_Measurement_MinuteUnitOfTime:
  * - ``Measurement.MinuteUnitOfTime``
    - ``144``
    - min

      .. _enumitem_Measurement_Hour:
  * - ``Measurement.Hour``
    - ``145``
    - h

      .. _enumitem_Measurement_Day:
  * - ``Measurement.Day``
    - ``146``
    - d

      .. _enumitem_Measurement_Kilosecond:
  * - ``Measurement.Kilosecond``
    - ``147``
    - ks

      .. _enumitem_Measurement_Millisecond:
  * - ``Measurement.Millisecond``
    - ``148``
    - ms

      .. _enumitem_Measurement_Picosecond:
  * - ``Measurement.Picosecond``
    - ``149``
    - ps

      .. _enumitem_Measurement_Microsecond:
  * - ``Measurement.Microsecond``
    - ``150``
    - µs

      .. _enumitem_Measurement_Nanosecond:
  * - ``Measurement.Nanosecond``
    - ``151``
    - ns

      .. _enumitem_Measurement_Week:
  * - ``Measurement.Week``
    - ``152``
    - wk

      .. _enumitem_Measurement_Month:
  * - ``Measurement.Month``
    - ``153``
    - mo

      .. _enumitem_Measurement_Year:
  * - ``Measurement.Year``
    - ``154``
    - y

      .. _enumitem_Measurement_TropicalYear:
  * - ``Measurement.TropicalYear``
    - ``155``
    - y (tropical)

      .. _enumitem_Measurement_CommonYear:
  * - ``Measurement.CommonYear``
    - ``156``
    - y (365 days)

      .. _enumitem_Measurement_SiderealYear:
  * - ``Measurement.SiderealYear``
    - ``157``
    - y (sidereal)

      .. _enumitem_Measurement_Shake:
  * - ``Measurement.Shake``
    - ``158``
    - shake

      .. _enumitem_Measurement_RadianPerSecond:
  * - ``Measurement.RadianPerSecond``
    - ``159``
    - rad/s

      .. _enumitem_Measurement_RevolutionPerMinute:
  * - ``Measurement.RevolutionPerMinute``
    - ``160``
    - r/min

      .. _enumitem_Measurement_RadianPerSecondSquared:
  * - ``Measurement.RadianPerSecondSquared``
    - ``161``
    - rad/s²

      .. _enumitem_Measurement_DegreeUnitOfAnglePerSecondSquared:
  * - ``Measurement.DegreeUnitOfAnglePerSecondSquared``
    - ``162``
    - °/s²

      .. _enumitem_Measurement_MetrePerSecond:
  * - ``Measurement.MetrePerSecond``
    - ``163``
    - m/s

      .. _enumitem_Measurement_Knot:
  * - ``Measurement.Knot``
    - ``164``
    - kn

      .. _enumitem_Measurement_KilometrePerHour:
  * - ``Measurement.KilometrePerHour``
    - ``165``
    - km/h

      .. _enumitem_Measurement_MillimetrePerSecond:
  * - ``Measurement.MillimetrePerSecond``
    - ``166``
    - mm/s

      .. _enumitem_Measurement_CentimetrePerSecond:
  * - ``Measurement.CentimetrePerSecond``
    - ``167``
    - cm/s

      .. _enumitem_Measurement_CentimetrePerHour:
  * - ``Measurement.CentimetrePerHour``
    - ``168``
    - cm/h

      .. _enumitem_Measurement_MillimetrePerMinute:
  * - ``Measurement.MillimetrePerMinute``
    - ``169``
    - mm/min

      .. _enumitem_Measurement_MetrePerMinute:
  * - ``Measurement.MetrePerMinute``
    - ``170``
    - m/min

      .. _enumitem_Measurement_MetrePerSecondPascal:
  * - ``Measurement.MetrePerSecondPascal``
    - ``171``
    - (m/s)/Pa

      .. _enumitem_Measurement_MillimetrePerYear:
  * - ``Measurement.MillimetrePerYear``
    - ``172``
    - mm/y

      .. _enumitem_Measurement_MillimetrePerHour:
  * - ``Measurement.MillimetrePerHour``
    - ``173``
    - mm/h

      .. _enumitem_Measurement_FootPerMinute:
  * - ``Measurement.FootPerMinute``
    - ``174``
    - ft/min

      .. _enumitem_Measurement_InchPerSecond:
  * - ``Measurement.InchPerSecond``
    - ``175``
    - in/s

      .. _enumitem_Measurement_FootPerSecond:
  * - ``Measurement.FootPerSecond``
    - ``176``
    - ft/s

      .. _enumitem_Measurement_MilePerHourStatuteMile:
  * - ``Measurement.MilePerHourStatuteMile``
    - ``177``
    - mile/h

      .. _enumitem_Measurement_CentimetrePerSecondKelvin:
  * - ``Measurement.CentimetrePerSecondKelvin``
    - ``178``
    - (cm/s)/K

      .. _enumitem_Measurement_CentimetrePerSecondBar:
  * - ``Measurement.CentimetrePerSecondBar``
    - ``179``
    - (cm/s)/bar

      .. _enumitem_Measurement_FootPerHour:
  * - ``Measurement.FootPerHour``
    - ``180``
    - ft/h

      .. _enumitem_Measurement_FootPerSecondDegreeFahrenheit:
  * - ``Measurement.FootPerSecondDegreeFahrenheit``
    - ``181``
    - (ft/s)/°F

      .. _enumitem_Measurement_FootPerSecondPsi:
  * - ``Measurement.FootPerSecondPsi``
    - ``182``
    - (ft/s)/psi

      .. _enumitem_Measurement_InchPerSecondDegreeFahrenheit:
  * - ``Measurement.InchPerSecondDegreeFahrenheit``
    - ``183``
    - (in/s)/°F

      .. _enumitem_Measurement_InchPerSecondPsi:
  * - ``Measurement.InchPerSecondPsi``
    - ``184``
    - (in/s)/psi

      .. _enumitem_Measurement_MetrePerSecondKelvin:
  * - ``Measurement.MetrePerSecondKelvin``
    - ``185``
    - (m/s)/K

      .. _enumitem_Measurement_MetrePerSecondBar:
  * - ``Measurement.MetrePerSecondBar``
    - ``186``
    - (m/s)/bar

      .. _enumitem_Measurement_MillilitrePerSquareCentimetreMinute:
  * - ``Measurement.MillilitrePerSquareCentimetreMinute``
    - ``187``
    - (ml/min)/cm²

      .. _enumitem_Measurement_MilePerMinute:
  * - ``Measurement.MilePerMinute``
    - ``188``
    - mi/min

      .. _enumitem_Measurement_MilePerSecond:
  * - ``Measurement.MilePerSecond``
    - ``189``
    - mi/s

      .. _enumitem_Measurement_MetrePerHour:
  * - ``Measurement.MetrePerHour``
    - ``190``
    - m/h

      .. _enumitem_Measurement_InchPerYear:
  * - ``Measurement.InchPerYear``
    - ``191``
    - in/y

      .. _enumitem_Measurement_KilometrePerSecond:
  * - ``Measurement.KilometrePerSecond``
    - ``192``
    - km/s

      .. _enumitem_Measurement_InchPerMinute:
  * - ``Measurement.InchPerMinute``
    - ``193``
    - in/min

      .. _enumitem_Measurement_YardPerSecond:
  * - ``Measurement.YardPerSecond``
    - ``194``
    - yd/s

      .. _enumitem_Measurement_YardPerMinute:
  * - ``Measurement.YardPerMinute``
    - ``195``
    - yd/min

      .. _enumitem_Measurement_YardPerHour:
  * - ``Measurement.YardPerHour``
    - ``196``
    - yd/h

      .. _enumitem_Measurement_MetrePerSecondSquared:
  * - ``Measurement.MetrePerSecondSquared``
    - ``197``
    - m/s²

      .. _enumitem_Measurement_Gal:
  * - ``Measurement.Gal``
    - ``198``
    - Gal

      .. _enumitem_Measurement_Milligal:
  * - ``Measurement.Milligal``
    - ``199``
    - mGal

      .. _enumitem_Measurement_KilometrePerSecondSquared:
  * - ``Measurement.KilometrePerSecondSquared``
    - ``200``
    - km/s²

      .. _enumitem_Measurement_CentimetrePerSecondSquared:
  * - ``Measurement.CentimetrePerSecondSquared``
    - ``201``
    - cm/s²

      .. _enumitem_Measurement_MillimetrePerSecondSquared:
  * - ``Measurement.MillimetrePerSecondSquared``
    - ``202``
    - mm/s²

      .. _enumitem_Measurement_FootPerSecondSquared:
  * - ``Measurement.FootPerSecondSquared``
    - ``203``
    - ft/s²

      .. _enumitem_Measurement_InchPerSecondSquared:
  * - ``Measurement.InchPerSecondSquared``
    - ``204``
    - in/s²

      .. _enumitem_Measurement_StandardAccelerationOfFreeFall:
  * - ``Measurement.StandardAccelerationOfFreeFall``
    - ``205``
    - gn

      .. _enumitem_Measurement_YardPerSecondSquared:
  * - ``Measurement.YardPerSecondSquared``
    - ``206``
    - yd/s²

      .. _enumitem_Measurement_MileStatuteMilePerSecondSquared:
  * - ``Measurement.MileStatuteMilePerSecondSquared``
    - ``207``
    - mi/s²

      .. _enumitem_Measurement_ReciprocalMetre:
  * - ``Measurement.ReciprocalMetre``
    - ``208``
    - m⁻¹

      .. _enumitem_Measurement_Hertz:
  * - ``Measurement.Hertz``
    - ``209``
    - Hz

      .. _enumitem_Measurement_Kilohertz:
  * - ``Measurement.Kilohertz``
    - ``210``
    - kHz

      .. _enumitem_Measurement_Megahertz:
  * - ``Measurement.Megahertz``
    - ``211``
    - MHz

      .. _enumitem_Measurement_Terahertz:
  * - ``Measurement.Terahertz``
    - ``212``
    - THz

      .. _enumitem_Measurement_Gigahertz:
  * - ``Measurement.Gigahertz``
    - ``213``
    - GHz

      .. _enumitem_Measurement_ReciprocalHour:
  * - ``Measurement.ReciprocalHour``
    - ``214``
    - 1/h

      .. _enumitem_Measurement_ReciprocalMonth:
  * - ``Measurement.ReciprocalMonth``
    - ``215``
    - 1/mo

      .. _enumitem_Measurement_ReciprocalYear:
  * - ``Measurement.ReciprocalYear``
    - ``216``
    - 1/y

      .. _enumitem_Measurement_ReciprocalWeek:
  * - ``Measurement.ReciprocalWeek``
    - ``217``
    - 1/wk

      .. _enumitem_Measurement_ReciprocalSecond:
  * - ``Measurement.ReciprocalSecond``
    - ``218``
    - s⁻¹

      .. _enumitem_Measurement_RevolutionsPerSecond:
  * - ``Measurement.RevolutionsPerSecond``
    - ``219``
    - r/s

      .. _enumitem_Measurement_RevolutionsPerMinute:
  * - ``Measurement.RevolutionsPerMinute``
    - ``220``
    - r/min

      .. _enumitem_Measurement_ReciprocalMinute:
  * - ``Measurement.ReciprocalMinute``
    - ``221``
    - min⁻¹

      .. _enumitem_Measurement_Neper:
  * - ``Measurement.Neper``
    - ``222``
    - Np

      .. _enumitem_Measurement_Decibel:
  * - ``Measurement.Decibel``
    - ``223``
    - dB

      .. _enumitem_Measurement_Bel:
  * - ``Measurement.Bel``
    - ``224``
    - B

      .. _enumitem_Measurement_NeperPerSecond:
  * - ``Measurement.NeperPerSecond``
    - ``225``
    - Np/s

      .. _enumitem_Measurement_Kilogram:
  * - ``Measurement.Kilogram``
    - ``226``
    - kg

      .. _enumitem_Measurement_Microgram:
  * - ``Measurement.Microgram``
    - ``227``
    - µg

      .. _enumitem_Measurement_Decagram:
  * - ``Measurement.Decagram``
    - ``228``
    - dag

      .. _enumitem_Measurement_Decigram:
  * - ``Measurement.Decigram``
    - ``229``
    - dg

      .. _enumitem_Measurement_Gram:
  * - ``Measurement.Gram``
    - ``230``
    - g

      .. _enumitem_Measurement_Centigram:
  * - ``Measurement.Centigram``
    - ``231``
    - cg

      .. _enumitem_Measurement_TonneMetricTon:
  * - ``Measurement.TonneMetricTon``
    - ``232``
    - t

      .. _enumitem_Measurement_Decitonne:
  * - ``Measurement.Decitonne``
    - ``233``
    - dt or dtn

      .. _enumitem_Measurement_Milligram:
  * - ``Measurement.Milligram``
    - ``234``
    - mg

      .. _enumitem_Measurement_Hectogram:
  * - ``Measurement.Hectogram``
    - ``235``
    - hg

      .. _enumitem_Measurement_Kilotonne:
  * - ``Measurement.Kilotonne``
    - ``236``
    - kt

      .. _enumitem_Measurement_Megagram:
  * - ``Measurement.Megagram``
    - ``237``
    - Mg

      .. _enumitem_Measurement_Pound:
  * - ``Measurement.Pound``
    - ``238``
    - lb

      .. _enumitem_Measurement_Grain:
  * - ``Measurement.Grain``
    - ``239``
    - gr

      .. _enumitem_Measurement_OunceAvoirdupois:
  * - ``Measurement.OunceAvoirdupois``
    - ``240``
    - oz

      .. _enumitem_Measurement_HundredWeightUK:
  * - ``Measurement.HundredWeightUK``
    - ``241``
    - cwt (UK)

      .. _enumitem_Measurement_HundredPoundCwtHundredWeightUS:
  * - ``Measurement.HundredPoundCwtHundredWeightUS``
    - ``242``
    - cwt (US)

      .. _enumitem_Measurement_TonUKOrLongTonUS:
  * - ``Measurement.TonUKOrLongTonUS``
    - ``243``
    - ton (UK)

      .. _enumitem_Measurement_StoneUK:
  * - ``Measurement.StoneUK``
    - ``244``
    - st

      .. _enumitem_Measurement_TonUSOrShortTonUKUS:
  * - ``Measurement.TonUSOrShortTonUKUS``
    - ``245``
    - ton (US)

      .. _enumitem_Measurement_TroyOunceOrApothecaryOunce:
  * - ``Measurement.TroyOunceOrApothecaryOunce``
    - ``246``
    - tr oz

      .. _enumitem_Measurement_Slug:
  * - ``Measurement.Slug``
    - ``247``
    - slug

      .. _enumitem_Measurement_PoundAvoirdupoisPerDegreeFahrenheit:
  * - ``Measurement.PoundAvoirdupoisPerDegreeFahrenheit``
    - ``248``
    - lb/°F

      .. _enumitem_Measurement_TonnePerKelvin:
  * - ``Measurement.TonnePerKelvin``
    - ``249``
    - t/K

      .. _enumitem_Measurement_TonShortPerDegreeFahrenheit:
  * - ``Measurement.TonShortPerDegreeFahrenheit``
    - ``250``
    - ton (US)/°F

      .. _enumitem_Measurement_Pfund:
  * - ``Measurement.Pfund``
    - ``251``
    - pfd

      .. _enumitem_Measurement_KilogramPerCubicMetre:
  * - ``Measurement.KilogramPerCubicMetre``
    - ``252``
    - kg/m³

      .. _enumitem_Measurement_GramPerCubicCentimetre:
  * - ``Measurement.GramPerCubicCentimetre``
    - ``253``
    - g/cm³

      .. _enumitem_Measurement_TonnePerCubicMetre:
  * - ``Measurement.TonnePerCubicMetre``
    - ``254``
    - t/m³

      .. _enumitem_Measurement_GramPerMillilitre:
  * - ``Measurement.GramPerMillilitre``
    - ``255``
    - g/ml

      .. _enumitem_Measurement_KilogramPerLitre:
  * - ``Measurement.KilogramPerLitre``
    - ``256``
    - kg/l or kg/L

      .. _enumitem_Measurement_GramPerLitre:
  * - ``Measurement.GramPerLitre``
    - ``257``
    - g/l

      .. _enumitem_Measurement_GramPerCubicMetre:
  * - ``Measurement.GramPerCubicMetre``
    - ``258``
    - g/m³

      .. _enumitem_Measurement_MilligramPerCubicMetre:
  * - ``Measurement.MilligramPerCubicMetre``
    - ``259``
    - mg/m³

      .. _enumitem_Measurement_MegagramPerCubicMetre:
  * - ``Measurement.MegagramPerCubicMetre``
    - ``260``
    - Mg/m³

      .. _enumitem_Measurement_KilogramPerCubicDecimetre:
  * - ``Measurement.KilogramPerCubicDecimetre``
    - ``261``
    - kg/dm³

      .. _enumitem_Measurement_MilligramPerGram:
  * - ``Measurement.MilligramPerGram``
    - ``262``
    - mg/g

      .. _enumitem_Measurement_MicrogramPerLitre:
  * - ``Measurement.MicrogramPerLitre``
    - ``263``
    - µg/l

      .. _enumitem_Measurement_MilligramPerLitre:
  * - ``Measurement.MilligramPerLitre``
    - ``264``
    - mg/l

      .. _enumitem_Measurement_MicrogramPerCubicMetre:
  * - ``Measurement.MicrogramPerCubicMetre``
    - ``265``
    - µg/m³

      .. _enumitem_Measurement_GramPerCubicCentimetreBar:
  * - ``Measurement.GramPerCubicCentimetreBar``
    - ``266``
    - g/(cm³·bar)

      .. _enumitem_Measurement_GramPerCubicCentimetreKelvin:
  * - ``Measurement.GramPerCubicCentimetreKelvin``
    - ``267``
    - g/(cm³·K)

      .. _enumitem_Measurement_GramPerCubicDecimetre:
  * - ``Measurement.GramPerCubicDecimetre``
    - ``268``
    - g/dm³

      .. _enumitem_Measurement_GramPerCubicDecimetreBar:
  * - ``Measurement.GramPerCubicDecimetreBar``
    - ``269``
    - g/(dm³·bar)

      .. _enumitem_Measurement_GramPerCubicDecimetreKelvin:
  * - ``Measurement.GramPerCubicDecimetreKelvin``
    - ``270``
    - g/(dm³·K)

      .. _enumitem_Measurement_GramPerCubicMetreBar:
  * - ``Measurement.GramPerCubicMetreBar``
    - ``271``
    - g/(m³·bar)

      .. _enumitem_Measurement_GramPerCubicMetreKelvin:
  * - ``Measurement.GramPerCubicMetreKelvin``
    - ``272``
    - g/(m³·K)

      .. _enumitem_Measurement_GramPerLitreBar:
  * - ``Measurement.GramPerLitreBar``
    - ``273``
    - g/(l·bar)

      .. _enumitem_Measurement_GramPerLitreKelvin:
  * - ``Measurement.GramPerLitreKelvin``
    - ``274``
    - g/(l·K)

      .. _enumitem_Measurement_GramPerMillilitreBar:
  * - ``Measurement.GramPerMillilitreBar``
    - ``275``
    - g/(ml·bar)

      .. _enumitem_Measurement_GramPerMillilitreKelvin:
  * - ``Measurement.GramPerMillilitreKelvin``
    - ``276``
    - g/(ml·K)

      .. _enumitem_Measurement_KilogramPerCubicCentimetre:
  * - ``Measurement.KilogramPerCubicCentimetre``
    - ``277``
    - kg/cm³

      .. _enumitem_Measurement_KilogramPerCubicCentimetreBar:
  * - ``Measurement.KilogramPerCubicCentimetreBar``
    - ``278``
    - kg/(cm³·bar)

      .. _enumitem_Measurement_KilogramPerCubicCentimetreKelvin:
  * - ``Measurement.KilogramPerCubicCentimetreKelvin``
    - ``279``
    - kg/(cm³·K)

      .. _enumitem_Measurement_KilogramPerCubicMetreBar:
  * - ``Measurement.KilogramPerCubicMetreBar``
    - ``280``
    - kg/(m³·bar)

      .. _enumitem_Measurement_KilogramPerCubicMetreKelvin:
  * - ``Measurement.KilogramPerCubicMetreKelvin``
    - ``281``
    - kg/(m³·K)

      .. _enumitem_Measurement_KilogramPerCubicDecimetreKelvin:
  * - ``Measurement.KilogramPerCubicDecimetreKelvin``
    - ``282``
    - (kg/dm³)/K

      .. _enumitem_Measurement_KilogramPerCubicDecimetreBar:
  * - ``Measurement.KilogramPerCubicDecimetreBar``
    - ``283``
    - (kg/dm³)/bar

      .. _enumitem_Measurement_GramPerKelvin:
  * - ``Measurement.GramPerKelvin``
    - ``284``
    - g/K

      .. _enumitem_Measurement_KilogramPerKelvin:
  * - ``Measurement.KilogramPerKelvin``
    - ``285``
    - kg/K

      .. _enumitem_Measurement_KilogramPerKilomol:
  * - ``Measurement.KilogramPerKilomol``
    - ``286``
    - kg/kmol

      .. _enumitem_Measurement_KilogramPerLitreBar:
  * - ``Measurement.KilogramPerLitreBar``
    - ``287``
    - kg/(l·bar)

      .. _enumitem_Measurement_KilogramPerLitreKelvin:
  * - ``Measurement.KilogramPerLitreKelvin``
    - ``288``
    - kg/(l·K)

      .. _enumitem_Measurement_KilogramPerBar:
  * - ``Measurement.KilogramPerBar``
    - ``289``
    - kg/bar

      .. _enumitem_Measurement_KilogramSquareCentimetre:
  * - ``Measurement.KilogramSquareCentimetre``
    - ``290``
    - kg·cm²

      .. _enumitem_Measurement_KilogramSquareMillimetre:
  * - ``Measurement.KilogramSquareMillimetre``
    - ``291``
    - kg·mm²

      .. _enumitem_Measurement_GramPerBar:
  * - ``Measurement.GramPerBar``
    - ``292``
    - g/bar

      .. _enumitem_Measurement_MilligramPerBar:
  * - ``Measurement.MilligramPerBar``
    - ``293``
    - mg/bar

      .. _enumitem_Measurement_MilligramPerKelvin:
  * - ``Measurement.MilligramPerKelvin``
    - ``294``
    - mg/K

      .. _enumitem_Measurement_KilogramPerCubicMetrePascal:
  * - ``Measurement.KilogramPerCubicMetrePascal``
    - ``295``
    - (kg/m³)/Pa

      .. _enumitem_Measurement_PoundPerCubicFoot:
  * - ``Measurement.PoundPerCubicFoot``
    - ``296``
    - lb/ft³

      .. _enumitem_Measurement_PoundPerGallonUS:
  * - ``Measurement.PoundPerGallonUS``
    - ``297``
    - lb/gal (US)

      .. _enumitem_Measurement_PoundPerCubicInch:
  * - ``Measurement.PoundPerCubicInch``
    - ``298``
    - lb/in³

      .. _enumitem_Measurement_OunceAvoirdupoisPerCubicYard:
  * - ``Measurement.OunceAvoirdupoisPerCubicYard``
    - ``299``
    - oz/yd³

      .. _enumitem_Measurement_MicrogramPerCubicMetreKelvin:
  * - ``Measurement.MicrogramPerCubicMetreKelvin``
    - ``300``
    - (µg/m³)/K

      .. _enumitem_Measurement_MicrogramPerCubicMetreBar:
  * - ``Measurement.MicrogramPerCubicMetreBar``
    - ``301``
    - (µg/m³)/bar

      .. _enumitem_Measurement_GrainPerGallonUS:
  * - ``Measurement.GrainPerGallonUS``
    - ``302``
    - gr/gal (US)

      .. _enumitem_Measurement_PoundAvoirdupoisPerCubicFootDegreeFahrenheit:
  * - ``Measurement.PoundAvoirdupoisPerCubicFootDegreeFahrenheit``
    - ``303``
    - (lb/ft³)/°F

      .. _enumitem_Measurement_PoundAvoirdupoisPerCubicFootPsi:
  * - ``Measurement.PoundAvoirdupoisPerCubicFootPsi``
    - ``304``
    - (lb/ft³)/psi

      .. _enumitem_Measurement_PoundAvoirdupoisPerGallonUK:
  * - ``Measurement.PoundAvoirdupoisPerGallonUK``
    - ``305``
    - lb/gal (UK)

      .. _enumitem_Measurement_PoundAvoirdupoisPerCubicInchDegreeFahrenheit:
  * - ``Measurement.PoundAvoirdupoisPerCubicInchDegreeFahrenheit``
    - ``306``
    - (lb/in³)/°F

      .. _enumitem_Measurement_PoundAvoirdupoisPerCubicInchPsi:
  * - ``Measurement.PoundAvoirdupoisPerCubicInchPsi``
    - ``307``
    - (lb/in³)/psi

      .. _enumitem_Measurement_PoundPerCubicYard:
  * - ``Measurement.PoundPerCubicYard``
    - ``308``
    - lb/yd³

      .. _enumitem_Measurement_MilligramPerCubicMetreKelvin:
  * - ``Measurement.MilligramPerCubicMetreKelvin``
    - ``309``
    - (mg/m³)/K

      .. _enumitem_Measurement_MilligramPerCubicMetreBar:
  * - ``Measurement.MilligramPerCubicMetreBar``
    - ``310``
    - (mg/m³)/bar

      .. _enumitem_Measurement_OunceAvoirdupoisPerGallonUK:
  * - ``Measurement.OunceAvoirdupoisPerGallonUK``
    - ``311``
    - oz/gal (UK)

      .. _enumitem_Measurement_OunceAvoirdupoisPerGallonUS:
  * - ``Measurement.OunceAvoirdupoisPerGallonUS``
    - ``312``
    - oz/gal (US)

      .. _enumitem_Measurement_OunceAvoirdupoisPerCubicInch:
  * - ``Measurement.OunceAvoirdupoisPerCubicInch``
    - ``313``
    - oz/in³

      .. _enumitem_Measurement_SlugPerCubicFoot:
  * - ``Measurement.SlugPerCubicFoot``
    - ``314``
    - slug/ft³

      .. _enumitem_Measurement_TonnePerCubicMetreKelvin:
  * - ``Measurement.TonnePerCubicMetreKelvin``
    - ``315``
    - (t/m³)/K

      .. _enumitem_Measurement_TonnePerCubicMetreBar:
  * - ``Measurement.TonnePerCubicMetreBar``
    - ``316``
    - (t/m³)/bar

      .. _enumitem_Measurement_TonUKLongPerCubicYard:
  * - ``Measurement.TonUKLongPerCubicYard``
    - ``317``
    - ton.l/yd³ (UK)

      .. _enumitem_Measurement_TonUSShortPerCubicYard:
  * - ``Measurement.TonUSShortPerCubicYard``
    - ``318``
    - ton.s/yd³ (US)

      .. _enumitem_Measurement_PoundAvoirdupoisPerPsi:
  * - ``Measurement.PoundAvoirdupoisPerPsi``
    - ``319``
    - lb/psi

      .. _enumitem_Measurement_TonnePerBar:
  * - ``Measurement.TonnePerBar``
    - ``320``
    - t/bar

      .. _enumitem_Measurement_TonShortPerPsi:
  * - ``Measurement.TonShortPerPsi``
    - ``321``
    - ton (US)/psi

      .. _enumitem_Measurement_KilogramPerPascal:
  * - ``Measurement.KilogramPerPascal``
    - ``322``
    - kg/Pa

      .. _enumitem_Measurement_One:
  * - ``Measurement.One``
    - ``323``
    - 1

      .. _enumitem_Measurement_CubicMetrePerKilogram:
  * - ``Measurement.CubicMetrePerKilogram``
    - ``324``
    - m³/kg

      .. _enumitem_Measurement_DecilitrePerGram:
  * - ``Measurement.DecilitrePerGram``
    - ``325``
    - dl/g

      .. _enumitem_Measurement_MillilitrePerCubicMetre:
  * - ``Measurement.MillilitrePerCubicMetre``
    - ``326``
    - ml/m³

      .. _enumitem_Measurement_LitrePerKilogram:
  * - ``Measurement.LitrePerKilogram``
    - ``327``
    - l/kg

      .. _enumitem_Measurement_MillilitrePerKilogram:
  * - ``Measurement.MillilitrePerKilogram``
    - ``328``
    - ml/kg

      .. _enumitem_Measurement_SquareCentimetrePerGram:
  * - ``Measurement.SquareCentimetrePerGram``
    - ``329``
    - cm²/g

      .. _enumitem_Measurement_CubicDecimetrePerKilogram:
  * - ``Measurement.CubicDecimetrePerKilogram``
    - ``330``
    - dm³/kg

      .. _enumitem_Measurement_CubicFootPerPound:
  * - ``Measurement.CubicFootPerPound``
    - ``331``
    - ft³/lb

      .. _enumitem_Measurement_CubicInchPerPound:
  * - ``Measurement.CubicInchPerPound``
    - ``332``
    - in³/lb

      .. _enumitem_Measurement_KilogramPerMetre:
  * - ``Measurement.KilogramPerMetre``
    - ``333``
    - kg/m

      .. _enumitem_Measurement_GramPerMetreGramPerCentimetres:
  * - ``Measurement.GramPerMetreGramPerCentimetres``
    - ``334``
    - g/m

      .. _enumitem_Measurement_GramPerMillimetre:
  * - ``Measurement.GramPerMillimetre``
    - ``335``
    - g/mm

      .. _enumitem_Measurement_KilogramPerMillimetre:
  * - ``Measurement.KilogramPerMillimetre``
    - ``336``
    - kg/mm

      .. _enumitem_Measurement_MilligramPerMetre:
  * - ``Measurement.MilligramPerMetre``
    - ``337``
    - mg/m

      .. _enumitem_Measurement_KilogramPerKilometre:
  * - ``Measurement.KilogramPerKilometre``
    - ``338``
    - kg/km

      .. _enumitem_Measurement_PoundPerFoot:
  * - ``Measurement.PoundPerFoot``
    - ``339``
    - lb/ft

      .. _enumitem_Measurement_PoundPerInchOfLength:
  * - ``Measurement.PoundPerInchOfLength``
    - ``340``
    - lb/in

      .. _enumitem_Measurement_Denier:
  * - ``Measurement.Denier``
    - ``341``
    - den

      .. _enumitem_Measurement_PoundPerYard:
  * - ``Measurement.PoundPerYard``
    - ``342``
    - lb/yd

      .. _enumitem_Measurement_MilligramPerSquareMetre:
  * - ``Measurement.MilligramPerSquareMetre``
    - ``343``
    - mg/m²

      .. _enumitem_Measurement_GramPerSquareCentimetre:
  * - ``Measurement.GramPerSquareCentimetre``
    - ``344``
    - g/cm²

      .. _enumitem_Measurement_MilligramPerSquareCentimetre:
  * - ``Measurement.MilligramPerSquareCentimetre``
    - ``345``
    - mg/cm²

      .. _enumitem_Measurement_GramPerSquareMetre:
  * - ``Measurement.GramPerSquareMetre``
    - ``346``
    - g/m²

      .. _enumitem_Measurement_KilogramPerSquareMetre:
  * - ``Measurement.KilogramPerSquareMetre``
    - ``347``
    - kg/m²

      .. _enumitem_Measurement_KilogramPerSquareCentimetre:
  * - ``Measurement.KilogramPerSquareCentimetre``
    - ``348``
    - kg/cm²

      .. _enumitem_Measurement_OuncePerSquareYard:
  * - ``Measurement.OuncePerSquareYard``
    - ``349``
    - oz/yd²

      .. _enumitem_Measurement_OuncePerSquareFoot:
  * - ``Measurement.OuncePerSquareFoot``
    - ``350``
    - oz/ft²

      .. _enumitem_Measurement_KilogramMetrePerSecond:
  * - ``Measurement.KilogramMetrePerSecond``
    - ``351``
    - kg·m/s

      .. _enumitem_Measurement_KilogramCentimetrePerSecond:
  * - ``Measurement.KilogramCentimetrePerSecond``
    - ``352``
    - kg·(cm/s)

      .. _enumitem_Measurement_GramCentimetrePerSecond:
  * - ``Measurement.GramCentimetrePerSecond``
    - ``353``
    - g·(cm/s)

      .. _enumitem_Measurement_PoundFootPerSecond:
  * - ``Measurement.PoundFootPerSecond``
    - ``354``
    - lb·(ft/s)

      .. _enumitem_Measurement_PoundInchPerSecond:
  * - ``Measurement.PoundInchPerSecond``
    - ``355``
    - lb·(in/s)

      .. _enumitem_Measurement_KilogramMetreSquaredPerSecond:
  * - ``Measurement.KilogramMetreSquaredPerSecond``
    - ``356``
    - kg·m²/s

      .. _enumitem_Measurement_KilogramMetreSquared:
  * - ``Measurement.KilogramMetreSquared``
    - ``357``
    - kg·m²

      .. _enumitem_Measurement_PoundInchSquared:
  * - ``Measurement.PoundInchSquared``
    - ``358``
    - lb·in²

      .. _enumitem_Measurement_PoundAvoirdupoisSquareFoot:
  * - ``Measurement.PoundAvoirdupoisSquareFoot``
    - ``359``
    - lb·ft²

      .. _enumitem_Measurement_Newton:
  * - ``Measurement.Newton``
    - ``360``
    - N

      .. _enumitem_Measurement_Meganewton:
  * - ``Measurement.Meganewton``
    - ``361``
    - MN

      .. _enumitem_Measurement_Kilonewton:
  * - ``Measurement.Kilonewton``
    - ``362``
    - kN

      .. _enumitem_Measurement_Millinewton:
  * - ``Measurement.Millinewton``
    - ``363``
    - mN

      .. _enumitem_Measurement_Micronewton:
  * - ``Measurement.Micronewton``
    - ``364``
    - µN

      .. _enumitem_Measurement_Poundforce:
  * - ``Measurement.Poundforce``
    - ``365``
    - lbf

      .. _enumitem_Measurement_OunceAvoirdupoisforce:
  * - ``Measurement.OunceAvoirdupoisforce``
    - ``366``
    - ozf

      .. _enumitem_Measurement_TonforceUSShort:
  * - ``Measurement.TonforceUSShort``
    - ``367``
    - ton.sh-force

      .. _enumitem_Measurement_Kilopoundforce:
  * - ``Measurement.Kilopoundforce``
    - ``368``
    - kip

      .. _enumitem_Measurement_Poundal:
  * - ``Measurement.Poundal``
    - ``369``
    - pdl

      .. _enumitem_Measurement_KilogramMetrePerSecondSquared:
  * - ``Measurement.KilogramMetrePerSecondSquared``
    - ``370``
    - kg·m/s²

      .. _enumitem_Measurement_Pond:
  * - ``Measurement.Pond``
    - ``371``
    - p

      .. _enumitem_Measurement_PoundforcePerFoot:
  * - ``Measurement.PoundforcePerFoot``
    - ``372``
    - lbf/ft

      .. _enumitem_Measurement_PoundforcePerInch:
  * - ``Measurement.PoundforcePerInch``
    - ``373``
    - lbf/in

      .. _enumitem_Measurement_NewtonMetreSquaredPerKilogramSquared:
  * - ``Measurement.NewtonMetreSquaredPerKilogramSquared``
    - ``374``
    - N·m²/kg²

      .. _enumitem_Measurement_NewtonMetre:
  * - ``Measurement.NewtonMetre``
    - ``375``
    - N·m

      .. _enumitem_Measurement_NewtonPerAmpere:
  * - ``Measurement.NewtonPerAmpere``
    - ``376``
    - N/A

      .. _enumitem_Measurement_MeganewtonMetre:
  * - ``Measurement.MeganewtonMetre``
    - ``377``
    - MN·m

      .. _enumitem_Measurement_KilonewtonMetre:
  * - ``Measurement.KilonewtonMetre``
    - ``378``
    - kN·m

      .. _enumitem_Measurement_MillinewtonMetre:
  * - ``Measurement.MillinewtonMetre``
    - ``379``
    - mN·m

      .. _enumitem_Measurement_MicronewtonMetre:
  * - ``Measurement.MicronewtonMetre``
    - ``380``
    - µN·m

      .. _enumitem_Measurement_DecinewtonMetre:
  * - ``Measurement.DecinewtonMetre``
    - ``381``
    - dN·m

      .. _enumitem_Measurement_CentinewtonMetre:
  * - ``Measurement.CentinewtonMetre``
    - ``382``
    - cN·m

      .. _enumitem_Measurement_KilogramMetre:
  * - ``Measurement.KilogramMetre``
    - ``383``
    - kg·m

      .. _enumitem_Measurement_NewtonCentimetre:
  * - ``Measurement.NewtonCentimetre``
    - ``384``
    - N·cm

      .. _enumitem_Measurement_NewtonMetrePerAmpere:
  * - ``Measurement.NewtonMetrePerAmpere``
    - ``385``
    - N·m/A

      .. _enumitem_Measurement_NewtonMetrePerDegree:
  * - ``Measurement.NewtonMetrePerDegree``
    - ``386``
    - Nm/°

      .. _enumitem_Measurement_NewtonMetrePerKilogram:
  * - ``Measurement.NewtonMetrePerKilogram``
    - ``387``
    - N·m/kg

      .. _enumitem_Measurement_NewtonPerMillimetre:
  * - ``Measurement.NewtonPerMillimetre``
    - ``388``
    - N/mm

      .. _enumitem_Measurement_NewtonMetrePerRadian:
  * - ``Measurement.NewtonMetrePerRadian``
    - ``389``
    - N·m/rad

      .. _enumitem_Measurement_NewtonMetreWattToThePowerMinus:
  * - ``Measurement.NewtonMetreWattToThePowerMinus``
    - ``390``
    - N·m·W⁻⁰‧⁵

      .. _enumitem_Measurement_InchPoundPoundInch:
  * - ``Measurement.InchPoundPoundInch``
    - ``391``
    - in·lb

      .. _enumitem_Measurement_OunceInch:
  * - ``Measurement.OunceInch``
    - ``392``
    - oz·in

      .. _enumitem_Measurement_OunceFoot:
  * - ``Measurement.OunceFoot``
    - ``393``
    - oz·ft

      .. _enumitem_Measurement_PoundforceFootPerAmpere:
  * - ``Measurement.PoundforceFootPerAmpere``
    - ``394``
    - lbf·ft/A

      .. _enumitem_Measurement_PoundforceInch:
  * - ``Measurement.PoundforceInch``
    - ``395``
    - lbf·in

      .. _enumitem_Measurement_PoundforceFootPerPound:
  * - ``Measurement.PoundforceFootPerPound``
    - ``396``
    - lbf·ft/lb

      .. _enumitem_Measurement_OunceAvoirdupoisforceInch:
  * - ``Measurement.OunceAvoirdupoisforceInch``
    - ``397``
    - ozf·in

      .. _enumitem_Measurement_PoundforceFoot:
  * - ``Measurement.PoundforceFoot``
    - ``398``
    - lbf·ft

      .. _enumitem_Measurement_PoundalFoot:
  * - ``Measurement.PoundalFoot``
    - ``399``
    - pdl·ft

      .. _enumitem_Measurement_PoundalInch:
  * - ``Measurement.PoundalInch``
    - ``400``
    - pdl·in

      .. _enumitem_Measurement_DyneMetre:
  * - ``Measurement.DyneMetre``
    - ``401``
    - dyn·m

      .. _enumitem_Measurement_NewtonSecond:
  * - ``Measurement.NewtonSecond``
    - ``402``
    - N·s

      .. _enumitem_Measurement_NewtonMetreSecond:
  * - ``Measurement.NewtonMetreSecond``
    - ``403``
    - N·m·s

      .. _enumitem_Measurement_Millipascal:
  * - ``Measurement.Millipascal``
    - ``404``
    - mPa

      .. _enumitem_Measurement_Megapascal:
  * - ``Measurement.Megapascal``
    - ``405``
    - MPa

      .. _enumitem_Measurement_Pascal:
  * - ``Measurement.Pascal``
    - ``406``
    - Pa

      .. _enumitem_Measurement_Kilopascal:
  * - ``Measurement.Kilopascal``
    - ``407``
    - kPa

      .. _enumitem_Measurement_BarUnitOfPressure:
  * - ``Measurement.BarUnitOfPressure``
    - ``408``
    - bar

      .. _enumitem_Measurement_Hectobar:
  * - ``Measurement.Hectobar``
    - ``409``
    - hbar

      .. _enumitem_Measurement_Millibar:
  * - ``Measurement.Millibar``
    - ``410``
    - mbar

      .. _enumitem_Measurement_Kilobar:
  * - ``Measurement.Kilobar``
    - ``411``
    - kbar

      .. _enumitem_Measurement_StandardAtmosphere:
  * - ``Measurement.StandardAtmosphere``
    - ``412``
    - atm

      .. _enumitem_Measurement_Gigapascal:
  * - ``Measurement.Gigapascal``
    - ``413``
    - GPa

      .. _enumitem_Measurement_Micropascal:
  * - ``Measurement.Micropascal``
    - ``414``
    - µPa

      .. _enumitem_Measurement_Hectopascal:
  * - ``Measurement.Hectopascal``
    - ``415``
    - hPa

      .. _enumitem_Measurement_Decapascal:
  * - ``Measurement.Decapascal``
    - ``416``
    - daPa

      .. _enumitem_Measurement_Microbar:
  * - ``Measurement.Microbar``
    - ``417``
    - µbar

      .. _enumitem_Measurement_NewtonPerSquareMetre:
  * - ``Measurement.NewtonPerSquareMetre``
    - ``418``
    - N/m²

      .. _enumitem_Measurement_NewtonPerSquareMillimetre:
  * - ``Measurement.NewtonPerSquareMillimetre``
    - ``419``
    - N/mm²

      .. _enumitem_Measurement_PascalSecondPerBar:
  * - ``Measurement.PascalSecondPerBar``
    - ``420``
    - Pa·s/bar

      .. _enumitem_Measurement_HectopascalCubicMetrePerSecond:
  * - ``Measurement.HectopascalCubicMetrePerSecond``
    - ``421``
    - hPa·m³/s

      .. _enumitem_Measurement_HectopascalLitrePerSecond:
  * - ``Measurement.HectopascalLitrePerSecond``
    - ``422``
    - hPa·l/s

      .. _enumitem_Measurement_HectopascalPerKelvin:
  * - ``Measurement.HectopascalPerKelvin``
    - ``423``
    - hPa/K

      .. _enumitem_Measurement_KilopascalPerKelvin:
  * - ``Measurement.KilopascalPerKelvin``
    - ``424``
    - kPa/K

      .. _enumitem_Measurement_MegapascalCubicMetrePerSecond:
  * - ``Measurement.MegapascalCubicMetrePerSecond``
    - ``425``
    - MPa·m³/s

      .. _enumitem_Measurement_MegapascalLitrePerSecond:
  * - ``Measurement.MegapascalLitrePerSecond``
    - ``426``
    - MPa·l/s

      .. _enumitem_Measurement_MegapascalPerKelvin:
  * - ``Measurement.MegapascalPerKelvin``
    - ``427``
    - MPa/K

      .. _enumitem_Measurement_MillibarCubicMetrePerSecond:
  * - ``Measurement.MillibarCubicMetrePerSecond``
    - ``428``
    - mbar·m³/s

      .. _enumitem_Measurement_MillibarLitrePerSecond:
  * - ``Measurement.MillibarLitrePerSecond``
    - ``429``
    - mbar·l/s

      .. _enumitem_Measurement_MillibarPerKelvin:
  * - ``Measurement.MillibarPerKelvin``
    - ``430``
    - mbar/K

      .. _enumitem_Measurement_PascalCubicMetrePerSecond:
  * - ``Measurement.PascalCubicMetrePerSecond``
    - ``431``
    - Pa·m³/s

      .. _enumitem_Measurement_PascalLitrePerSecond:
  * - ``Measurement.PascalLitrePerSecond``
    - ``432``
    - Pa·l/s

      .. _enumitem_Measurement_PascalSecondPerKelvin:
  * - ``Measurement.PascalSecondPerKelvin``
    - ``433``
    - Pa.s/K

      .. _enumitem_Measurement_NewtonPerSquareCentimetre:
  * - ``Measurement.NewtonPerSquareCentimetre``
    - ``434``
    - N/cm²

      .. _enumitem_Measurement_PoundPerSquareFoot:
  * - ``Measurement.PoundPerSquareFoot``
    - ``435``
    - lb/ft²

      .. _enumitem_Measurement_PoundforcePerSquareInch:
  * - ``Measurement.PoundforcePerSquareInch``
    - ``436``
    - lbf/in²

      .. _enumitem_Measurement_PoundPerSquareInchAbsolute:
  * - ``Measurement.PoundPerSquareInchAbsolute``
    - ``437``
    - lb/in²

      .. _enumitem_Measurement_InchOfMercury:
  * - ``Measurement.InchOfMercury``
    - ``438``
    - inHg

      .. _enumitem_Measurement_InchOfWater:
  * - ``Measurement.InchOfWater``
    - ``439``
    - inH₂O

      .. _enumitem_Measurement_GramforcePerSquareCentimetre:
  * - ``Measurement.GramforcePerSquareCentimetre``
    - ``440``
    - gf/cm²

      .. _enumitem_Measurement_KilogramforcePerSquareCentimetre:
  * - ``Measurement.KilogramforcePerSquareCentimetre``
    - ``441``
    - kgf/cm²

      .. _enumitem_Measurement_KilogramforcePerSquareMillimetre:
  * - ``Measurement.KilogramforcePerSquareMillimetre``
    - ``442``
    - kgf·m/cm²

      .. _enumitem_Measurement_PoundforcePerSquareFoot:
  * - ``Measurement.PoundforcePerSquareFoot``
    - ``443``
    - lbf/ft²

      .. _enumitem_Measurement_PoundforcePerSquareInchDegreeFahrenheit:
  * - ``Measurement.PoundforcePerSquareInchDegreeFahrenheit``
    - ``444``
    - psi/°F

      .. _enumitem_Measurement_CentimetreOfMercuryDegC:
  * - ``Measurement.CentimetreOfMercuryDegC``
    - ``445``
    - cmHg (0 ºC)

      .. _enumitem_Measurement_CentimetreOfWaterDegC:
  * - ``Measurement.CentimetreOfWaterDegC``
    - ``446``
    - cmH₂O (4 °C)

      .. _enumitem_Measurement_FootOfWaterDegF:
  * - ``Measurement.FootOfWaterDegF``
    - ``447``
    - ftH₂O (39,2 ºF)

      .. _enumitem_Measurement_InchOfMercury32DegF:
  * - ``Measurement.InchOfMercury32DegF``
    - ``448``
    - inHG (32 ºF)

      .. _enumitem_Measurement_InchOfMercury60DegF:
  * - ``Measurement.InchOfMercury60DegF``
    - ``449``
    - inHg (60 ºF)

      .. _enumitem_Measurement_InchOfWater39DegF:
  * - ``Measurement.InchOfWater39DegF``
    - ``450``
    - inH₂O (39,2 ºF)

      .. _enumitem_Measurement_InchOfWater60DegF:
  * - ``Measurement.InchOfWater60DegF``
    - ``451``
    - inH₂O (60 ºF)

      .. _enumitem_Measurement_KipPerSquareInch:
  * - ``Measurement.KipPerSquareInch``
    - ``452``
    - ksi

      .. _enumitem_Measurement_PoundalPerSquareFoot:
  * - ``Measurement.PoundalPerSquareFoot``
    - ``453``
    - pdl/ft²

      .. _enumitem_Measurement_OunceAvoirdupoisPerSquareInch:
  * - ``Measurement.OunceAvoirdupoisPerSquareInch``
    - ``454``
    - oz/in²

      .. _enumitem_Measurement_ConventionalMetreOfWater:
  * - ``Measurement.ConventionalMetreOfWater``
    - ``455``
    - mH₂O

      .. _enumitem_Measurement_GramPerSquareMillimetre:
  * - ``Measurement.GramPerSquareMillimetre``
    - ``456``
    - g/mm²

      .. _enumitem_Measurement_PoundPerSquareYard:
  * - ``Measurement.PoundPerSquareYard``
    - ``457``
    - lb/yd²

      .. _enumitem_Measurement_PoundalPerSquareInch:
  * - ``Measurement.PoundalPerSquareInch``
    - ``458``
    - pdl/in²

      .. _enumitem_Measurement_HectopascalPerBar:
  * - ``Measurement.HectopascalPerBar``
    - ``459``
    - hPa/bar

      .. _enumitem_Measurement_MegapascalPerBar:
  * - ``Measurement.MegapascalPerBar``
    - ``460``
    - MPa/bar

      .. _enumitem_Measurement_MillibarPerBar:
  * - ``Measurement.MillibarPerBar``
    - ``461``
    - mbar/bar

      .. _enumitem_Measurement_PascalPerBar:
  * - ``Measurement.PascalPerBar``
    - ``462``
    - Pa/bar

      .. _enumitem_Measurement_KilopascalPerBar:
  * - ``Measurement.KilopascalPerBar``
    - ``463``
    - kPa/bar

      .. _enumitem_Measurement_PsiPerPsi:
  * - ``Measurement.PsiPerPsi``
    - ``464``
    - psi/psi

      .. _enumitem_Measurement_BarPerBar:
  * - ``Measurement.BarPerBar``
    - ``465``
    - bar/bar

      .. _enumitem_Measurement_ReciprocalPascalOrPascalToThePowerMinusOne:
  * - ``Measurement.ReciprocalPascalOrPascalToThePowerMinusOne``
    - ``466``
    - Pa⁻¹

      .. _enumitem_Measurement_ReciprocalBar:
  * - ``Measurement.ReciprocalBar``
    - ``467``
    - 1/bar

      .. _enumitem_Measurement_MetreToTheFourthPower:
  * - ``Measurement.MetreToTheFourthPower``
    - ``468``
    - m⁴

      .. _enumitem_Measurement_MillimetreToTheFourthPower:
  * - ``Measurement.MillimetreToTheFourthPower``
    - ``469``
    - mm⁴

      .. _enumitem_Measurement_InchToTheFourthPower:
  * - ``Measurement.InchToTheFourthPower``
    - ``470``
    - in⁴

      .. _enumitem_Measurement_FootToTheFourthPower:
  * - ``Measurement.FootToTheFourthPower``
    - ``471``
    - ft⁴

      .. _enumitem_Measurement_PascalSecond:
  * - ``Measurement.PascalSecond``
    - ``472``
    - Pa·s

      .. _enumitem_Measurement_KilogramPerMetreSecond:
  * - ``Measurement.KilogramPerMetreSecond``
    - ``473``
    - kg/(m·s)

      .. _enumitem_Measurement_KilogramPerMetreMinute:
  * - ``Measurement.KilogramPerMetreMinute``
    - ``474``
    - kg/(m·min)

      .. _enumitem_Measurement_MillipascalSecond:
  * - ``Measurement.MillipascalSecond``
    - ``475``
    - mPa·s

      .. _enumitem_Measurement_NewtonSecondPerSquareMetre:
  * - ``Measurement.NewtonSecondPerSquareMetre``
    - ``476``
    - (N/m²)·s

      .. _enumitem_Measurement_KilogramPerMetreDay:
  * - ``Measurement.KilogramPerMetreDay``
    - ``477``
    - kg/(m·d)

      .. _enumitem_Measurement_KilogramPerMetreHour:
  * - ``Measurement.KilogramPerMetreHour``
    - ``478``
    - kg/(m·h)

      .. _enumitem_Measurement_GramPerCentimetreSecond:
  * - ``Measurement.GramPerCentimetreSecond``
    - ``479``
    - g/(cm·s)

      .. _enumitem_Measurement_Poise:
  * - ``Measurement.Poise``
    - ``480``
    - P

      .. _enumitem_Measurement_Centipoise:
  * - ``Measurement.Centipoise``
    - ``481``
    - cP

      .. _enumitem_Measurement_PoisePerBar:
  * - ``Measurement.PoisePerBar``
    - ``482``
    - P/bar

      .. _enumitem_Measurement_PoisePerKelvin:
  * - ``Measurement.PoisePerKelvin``
    - ``483``
    - P/K

      .. _enumitem_Measurement_Micropoise:
  * - ``Measurement.Micropoise``
    - ``484``
    - µP

      .. _enumitem_Measurement_CentipoisePerKelvin:
  * - ``Measurement.CentipoisePerKelvin``
    - ``485``
    - cP/K

      .. _enumitem_Measurement_CentipoisePerBar:
  * - ``Measurement.CentipoisePerBar``
    - ``486``
    - cP/bar

      .. _enumitem_Measurement_PoundPerFootHour:
  * - ``Measurement.PoundPerFootHour``
    - ``487``
    - lb/(ft·h)

      .. _enumitem_Measurement_PoundPerFootSecond:
  * - ``Measurement.PoundPerFootSecond``
    - ``488``
    - lb/(ft·s)

      .. _enumitem_Measurement_PoundforceSecondPerSquareFoot:
  * - ``Measurement.PoundforceSecondPerSquareFoot``
    - ``489``
    - lbf·s/ft²

      .. _enumitem_Measurement_PoundforceSecondPerSquareInch:
  * - ``Measurement.PoundforceSecondPerSquareInch``
    - ``490``
    - lbf·s/in²

      .. _enumitem_Measurement_MillipascalSecondPerKelvin:
  * - ``Measurement.MillipascalSecondPerKelvin``
    - ``491``
    - mPa·s/K

      .. _enumitem_Measurement_MillipascalSecondPerBar:
  * - ``Measurement.MillipascalSecondPerBar``
    - ``492``
    - mPa·s/bar

      .. _enumitem_Measurement_SlugPerFootSecond:
  * - ``Measurement.SlugPerFootSecond``
    - ``493``
    - slug/(ft·s)

      .. _enumitem_Measurement_PoundalSecondPerSquareFoot:
  * - ``Measurement.PoundalSecondPerSquareFoot``
    - ``494``
    - (pdl/ft²)·s

      .. _enumitem_Measurement_PoisePerPascal:
  * - ``Measurement.PoisePerPascal``
    - ``495``
    - P/Pa

      .. _enumitem_Measurement_PoundalSecondPerSquareInch:
  * - ``Measurement.PoundalSecondPerSquareInch``
    - ``496``
    - (pdl/in²)·s

      .. _enumitem_Measurement_PoundPerFootMinute:
  * - ``Measurement.PoundPerFootMinute``
    - ``497``
    - lb/(ft·min)

      .. _enumitem_Measurement_PoundPerFootDay:
  * - ``Measurement.PoundPerFootDay``
    - ``498``
    - lb/(ft·d)

      .. _enumitem_Measurement_SquareMetrePerSecond:
  * - ``Measurement.SquareMetrePerSecond``
    - ``499``
    - m²/s

      .. _enumitem_Measurement_SquareMetrePerSecondPascal:
  * - ``Measurement.SquareMetrePerSecondPascal``
    - ``500``
    - (m²/s)/Pa

      .. _enumitem_Measurement_MillimetreSquaredPerSecond:
  * - ``Measurement.MillimetreSquaredPerSecond``
    - ``501``
    - mm²/s

      .. _enumitem_Measurement_SquareMetrePerSecondBar:
  * - ``Measurement.SquareMetrePerSecondBar``
    - ``502``
    - m²/(s·bar)

      .. _enumitem_Measurement_SquareMetrePerSecondKelvin:
  * - ``Measurement.SquareMetrePerSecondKelvin``
    - ``503``
    - m²/(s·K)

      .. _enumitem_Measurement_Stokes:
  * - ``Measurement.Stokes``
    - ``504``
    - St

      .. _enumitem_Measurement_Centistokes:
  * - ``Measurement.Centistokes``
    - ``505``
    - cSt

      .. _enumitem_Measurement_StokesPerBar:
  * - ``Measurement.StokesPerBar``
    - ``506``
    - St/bar

      .. _enumitem_Measurement_StokesPerKelvin:
  * - ``Measurement.StokesPerKelvin``
    - ``507``
    - St/K

      .. _enumitem_Measurement_SquareFootPerSecond:
  * - ``Measurement.SquareFootPerSecond``
    - ``508``
    - ft²/s

      .. _enumitem_Measurement_SquareInchPerSecond:
  * - ``Measurement.SquareInchPerSecond``
    - ``509``
    - in²/s

      .. _enumitem_Measurement_SquareFootPerHour:
  * - ``Measurement.SquareFootPerHour``
    - ``510``
    - ft²/h

      .. _enumitem_Measurement_StokesPerPascal:
  * - ``Measurement.StokesPerPascal``
    - ``511``
    - St/Pa

      .. _enumitem_Measurement_SquareCentimetrePerSecond:
  * - ``Measurement.SquareCentimetrePerSecond``
    - ``512``
    - cm²/s

      .. _enumitem_Measurement_NewtonPerMetre:
  * - ``Measurement.NewtonPerMetre``
    - ``513``
    - N/m

      .. _enumitem_Measurement_MillinewtonPerMetre:
  * - ``Measurement.MillinewtonPerMetre``
    - ``514``
    - mN/m

      .. _enumitem_Measurement_NewtonPerCentimetre:
  * - ``Measurement.NewtonPerCentimetre``
    - ``515``
    - N/cm

      .. _enumitem_Measurement_KilonewtonPerMetre:
  * - ``Measurement.KilonewtonPerMetre``
    - ``516``
    - kN/m

      .. _enumitem_Measurement_PoundalPerInch:
  * - ``Measurement.PoundalPerInch``
    - ``517``
    - pdl/in

      .. _enumitem_Measurement_PoundforcePerYard:
  * - ``Measurement.PoundforcePerYard``
    - ``518``
    - lbf/yd

      .. _enumitem_Measurement_NewtonMetrePerSquareMetre:
  * - ``Measurement.NewtonMetrePerSquareMetre``
    - ``519``
    - N·m/m²

      .. _enumitem_Measurement_Joule:
  * - ``Measurement.Joule``
    - ``520``
    - J

      .. _enumitem_Measurement_Kilojoule:
  * - ``Measurement.Kilojoule``
    - ``521``
    - kJ

      .. _enumitem_Measurement_Exajoule:
  * - ``Measurement.Exajoule``
    - ``522``
    - EJ

      .. _enumitem_Measurement_Petajoule:
  * - ``Measurement.Petajoule``
    - ``523``
    - PJ

      .. _enumitem_Measurement_Terajoule:
  * - ``Measurement.Terajoule``
    - ``524``
    - TJ

      .. _enumitem_Measurement_Gigajoule:
  * - ``Measurement.Gigajoule``
    - ``525``
    - GJ

      .. _enumitem_Measurement_Megajoule:
  * - ``Measurement.Megajoule``
    - ``526``
    - MJ

      .. _enumitem_Measurement_Millijoule:
  * - ``Measurement.Millijoule``
    - ``527``
    - mJ

      .. _enumitem_Measurement_Femtojoule:
  * - ``Measurement.Femtojoule``
    - ``528``
    - fJ

      .. _enumitem_Measurement_Attojoule:
  * - ``Measurement.Attojoule``
    - ``529``
    - aJ

      .. _enumitem_Measurement_WattHour:
  * - ``Measurement.WattHour``
    - ``530``
    - W·h

      .. _enumitem_Measurement_MegawattHourKWh:
  * - ``Measurement.MegawattHourKWh``
    - ``531``
    - MW·h

      .. _enumitem_Measurement_KilowattHour:
  * - ``Measurement.KilowattHour``
    - ``532``
    - kW·h

      .. _enumitem_Measurement_GigawattHour:
  * - ``Measurement.GigawattHour``
    - ``533``
    - GW·h

      .. _enumitem_Measurement_TerawattHour:
  * - ``Measurement.TerawattHour``
    - ``534``
    - TW·h

      .. _enumitem_Measurement_Electronvolt:
  * - ``Measurement.Electronvolt``
    - ``535``
    - eV

      .. _enumitem_Measurement_Megaelectronvolt:
  * - ``Measurement.Megaelectronvolt``
    - ``536``
    - MeV

      .. _enumitem_Measurement_Gigaelectronvolt:
  * - ``Measurement.Gigaelectronvolt``
    - ``537``
    - GeV

      .. _enumitem_Measurement_Kiloelectronvolt:
  * - ``Measurement.Kiloelectronvolt``
    - ``538``
    - keV

      .. _enumitem_Measurement_FootPoundforce:
  * - ``Measurement.FootPoundforce``
    - ``539``
    - ft·lbf

      .. _enumitem_Measurement_FootPoundal:
  * - ``Measurement.FootPoundal``
    - ``540``
    - ft·pdl

      .. _enumitem_Measurement_InchPoundal:
  * - ``Measurement.InchPoundal``
    - ``541``
    - in·pdl

      .. _enumitem_Measurement_Watt:
  * - ``Measurement.Watt``
    - ``542``
    - W

      .. _enumitem_Measurement_Kilowatt:
  * - ``Measurement.Kilowatt``
    - ``543``
    - kW

      .. _enumitem_Measurement_Megawatt:
  * - ``Measurement.Megawatt``
    - ``544``
    - MW

      .. _enumitem_Measurement_Gigawatt:
  * - ``Measurement.Gigawatt``
    - ``545``
    - GW

      .. _enumitem_Measurement_Milliwatt:
  * - ``Measurement.Milliwatt``
    - ``546``
    - mW

      .. _enumitem_Measurement_Microwatt:
  * - ``Measurement.Microwatt``
    - ``547``
    - µW

      .. _enumitem_Measurement_FootPoundforcePerSecond:
  * - ``Measurement.FootPoundforcePerSecond``
    - ``548``
    - ft·lbf/s

      .. _enumitem_Measurement_BrakeHorsePower:
  * - ``Measurement.BrakeHorsePower``
    - ``549``
    - BHP

      .. _enumitem_Measurement_FootPoundforcePerHour:
  * - ``Measurement.FootPoundforcePerHour``
    - ``550``
    - ft·lbf/h

      .. _enumitem_Measurement_FootPoundforcePerMinute:
  * - ``Measurement.FootPoundforcePerMinute``
    - ``551``
    - ft·lbf/min

      .. _enumitem_Measurement_HorsepowerBoiler:
  * - ``Measurement.HorsepowerBoiler``
    - ``552``
    - boiler hp

      .. _enumitem_Measurement_Pferdestaerke:
  * - ``Measurement.Pferdestaerke``
    - ``553``
    - PS

      .. _enumitem_Measurement_KilogramPerSecond:
  * - ``Measurement.KilogramPerSecond``
    - ``554``
    - kg/s

      .. _enumitem_Measurement_KilogramPerSquareMetreSecond:
  * - ``Measurement.KilogramPerSquareMetreSecond``
    - ``555``
    - kg/(m²·s)

      .. _enumitem_Measurement_KilogramPerSecondPascal:
  * - ``Measurement.KilogramPerSecondPascal``
    - ``556``
    - (kg/s)/Pa

      .. _enumitem_Measurement_MilligramPerHour:
  * - ``Measurement.MilligramPerHour``
    - ``557``
    - mg/h

      .. _enumitem_Measurement_GramPerDay:
  * - ``Measurement.GramPerDay``
    - ``558``
    - g/d

      .. _enumitem_Measurement_GramPerDayBar:
  * - ``Measurement.GramPerDayBar``
    - ``559``
    - g/(d·bar)

      .. _enumitem_Measurement_GramPerDayKelvin:
  * - ``Measurement.GramPerDayKelvin``
    - ``560``
    - g/(d·K)

      .. _enumitem_Measurement_GramPerHour:
  * - ``Measurement.GramPerHour``
    - ``561``
    - g/h

      .. _enumitem_Measurement_GramPerHourBar:
  * - ``Measurement.GramPerHourBar``
    - ``562``
    - g/(h·bar)

      .. _enumitem_Measurement_GramPerHourKelvin:
  * - ``Measurement.GramPerHourKelvin``
    - ``563``
    - g/(h·K)

      .. _enumitem_Measurement_GramPerMinute:
  * - ``Measurement.GramPerMinute``
    - ``564``
    - g/min

      .. _enumitem_Measurement_GramPerMinuteBar:
  * - ``Measurement.GramPerMinuteBar``
    - ``565``
    - g/(min·bar)

      .. _enumitem_Measurement_GramPerMinuteKelvin:
  * - ``Measurement.GramPerMinuteKelvin``
    - ``566``
    - g/(min·K)

      .. _enumitem_Measurement_GramPerSecond:
  * - ``Measurement.GramPerSecond``
    - ``567``
    - g/s

      .. _enumitem_Measurement_GramPerSecondBar:
  * - ``Measurement.GramPerSecondBar``
    - ``568``
    - g/(s·bar)

      .. _enumitem_Measurement_GramPerSecondKelvin:
  * - ``Measurement.GramPerSecondKelvin``
    - ``569``
    - g/(s·K)

      .. _enumitem_Measurement_KilogramPerDay:
  * - ``Measurement.KilogramPerDay``
    - ``570``
    - kg/d

      .. _enumitem_Measurement_KilogramPerDayBar:
  * - ``Measurement.KilogramPerDayBar``
    - ``571``
    - kg/(d·bar)

      .. _enumitem_Measurement_KilogramPerDayKelvin:
  * - ``Measurement.KilogramPerDayKelvin``
    - ``572``
    - kg/(d·K)

      .. _enumitem_Measurement_KilogramPerHour:
  * - ``Measurement.KilogramPerHour``
    - ``573``
    - kg/h

      .. _enumitem_Measurement_KilogramPerHourBar:
  * - ``Measurement.KilogramPerHourBar``
    - ``574``
    - kg/(h·bar)

      .. _enumitem_Measurement_KilogramPerHourKelvin:
  * - ``Measurement.KilogramPerHourKelvin``
    - ``575``
    - kg/(h·K)

      .. _enumitem_Measurement_KilogramPerMinute:
  * - ``Measurement.KilogramPerMinute``
    - ``576``
    - kg/min

      .. _enumitem_Measurement_KilogramPerMinuteBar:
  * - ``Measurement.KilogramPerMinuteBar``
    - ``577``
    - kg/(min·bar)

      .. _enumitem_Measurement_KilogramPerMinuteKelvin:
  * - ``Measurement.KilogramPerMinuteKelvin``
    - ``578``
    - kg/(min·K)

      .. _enumitem_Measurement_KilogramPerSecondBar:
  * - ``Measurement.KilogramPerSecondBar``
    - ``579``
    - kg/(s·bar)

      .. _enumitem_Measurement_KilogramPerSecondKelvin:
  * - ``Measurement.KilogramPerSecondKelvin``
    - ``580``
    - kg/(s·K)

      .. _enumitem_Measurement_MilligramPerDay:
  * - ``Measurement.MilligramPerDay``
    - ``581``
    - mg/d

      .. _enumitem_Measurement_MilligramPerDayBar:
  * - ``Measurement.MilligramPerDayBar``
    - ``582``
    - mg/(d·bar)

      .. _enumitem_Measurement_MilligramPerDayKelvin:
  * - ``Measurement.MilligramPerDayKelvin``
    - ``583``
    - mg/(d·K)

      .. _enumitem_Measurement_MilligramPerHourBar:
  * - ``Measurement.MilligramPerHourBar``
    - ``584``
    - mg/(h·bar)

      .. _enumitem_Measurement_MilligramPerHourKelvin:
  * - ``Measurement.MilligramPerHourKelvin``
    - ``585``
    - mg/(h·K)

      .. _enumitem_Measurement_MilligramPerMinute:
  * - ``Measurement.MilligramPerMinute``
    - ``586``
    - mg/min

      .. _enumitem_Measurement_MilligramPerMinuteBar:
  * - ``Measurement.MilligramPerMinuteBar``
    - ``587``
    - mg/(min·bar)

      .. _enumitem_Measurement_MilligramPerMinuteKelvin:
  * - ``Measurement.MilligramPerMinuteKelvin``
    - ``588``
    - mg/(min·K)

      .. _enumitem_Measurement_MilligramPerSecond:
  * - ``Measurement.MilligramPerSecond``
    - ``589``
    - mg/s

      .. _enumitem_Measurement_MilligramPerSecondBar:
  * - ``Measurement.MilligramPerSecondBar``
    - ``590``
    - mg/(s·bar)

      .. _enumitem_Measurement_MilligramPerSecondKelvin:
  * - ``Measurement.MilligramPerSecondKelvin``
    - ``591``
    - mg/(s·K)

      .. _enumitem_Measurement_GramPerHertz:
  * - ``Measurement.GramPerHertz``
    - ``592``
    - g/Hz

      .. _enumitem_Measurement_TonUSPerHour:
  * - ``Measurement.TonUSPerHour``
    - ``593``
    - ton (US) /h

      .. _enumitem_Measurement_PoundPerHour:
  * - ``Measurement.PoundPerHour``
    - ``594``
    - lb/h

      .. _enumitem_Measurement_PoundAvoirdupoisPerDay:
  * - ``Measurement.PoundAvoirdupoisPerDay``
    - ``595``
    - lb/d

      .. _enumitem_Measurement_PoundAvoirdupoisPerHourDegreeFahrenheit:
  * - ``Measurement.PoundAvoirdupoisPerHourDegreeFahrenheit``
    - ``596``
    - (lb/h)/°F

      .. _enumitem_Measurement_PoundAvoirdupoisPerHourPsi:
  * - ``Measurement.PoundAvoirdupoisPerHourPsi``
    - ``597``
    - (lb/h)/psi

      .. _enumitem_Measurement_PoundAvoirdupoisPerMinute:
  * - ``Measurement.PoundAvoirdupoisPerMinute``
    - ``598``
    - lb/min

      .. _enumitem_Measurement_PoundAvoirdupoisPerMinuteDegreeFahrenheit:
  * - ``Measurement.PoundAvoirdupoisPerMinuteDegreeFahrenheit``
    - ``599``
    - lb/(min·°F)

      .. _enumitem_Measurement_PoundAvoirdupoisPerMinutePsi:
  * - ``Measurement.PoundAvoirdupoisPerMinutePsi``
    - ``600``
    - (lb/min)/psi

      .. _enumitem_Measurement_PoundAvoirdupoisPerSecond:
  * - ``Measurement.PoundAvoirdupoisPerSecond``
    - ``601``
    - lb/s

      .. _enumitem_Measurement_PoundAvoirdupoisPerSecondDegreeFahrenheit:
  * - ``Measurement.PoundAvoirdupoisPerSecondDegreeFahrenheit``
    - ``602``
    - (lb/s)/°F

      .. _enumitem_Measurement_PoundAvoirdupoisPerSecondPsi:
  * - ``Measurement.PoundAvoirdupoisPerSecondPsi``
    - ``603``
    - (lb/s)/psi

      .. _enumitem_Measurement_OunceAvoirdupoisPerDay:
  * - ``Measurement.OunceAvoirdupoisPerDay``
    - ``604``
    - oz/d

      .. _enumitem_Measurement_OunceAvoirdupoisPerHour:
  * - ``Measurement.OunceAvoirdupoisPerHour``
    - ``605``
    - oz/h

      .. _enumitem_Measurement_OunceAvoirdupoisPerMinute:
  * - ``Measurement.OunceAvoirdupoisPerMinute``
    - ``606``
    - oz/min

      .. _enumitem_Measurement_OunceAvoirdupoisPerSecond:
  * - ``Measurement.OunceAvoirdupoisPerSecond``
    - ``607``
    - oz/s

      .. _enumitem_Measurement_SlugPerDay:
  * - ``Measurement.SlugPerDay``
    - ``608``
    - slug/d

      .. _enumitem_Measurement_SlugPerHour:
  * - ``Measurement.SlugPerHour``
    - ``609``
    - slug/h

      .. _enumitem_Measurement_SlugPerMinute:
  * - ``Measurement.SlugPerMinute``
    - ``610``
    - slug/min

      .. _enumitem_Measurement_SlugPerSecond:
  * - ``Measurement.SlugPerSecond``
    - ``611``
    - slug/s

      .. _enumitem_Measurement_TonnePerDay:
  * - ``Measurement.TonnePerDay``
    - ``612``
    - t/d

      .. _enumitem_Measurement_TonnePerDayKelvin:
  * - ``Measurement.TonnePerDayKelvin``
    - ``613``
    - (t/d)/K

      .. _enumitem_Measurement_TonnePerDayBar:
  * - ``Measurement.TonnePerDayBar``
    - ``614``
    - (t/d)/bar

      .. _enumitem_Measurement_TonnePerHour:
  * - ``Measurement.TonnePerHour``
    - ``615``
    - t/h

      .. _enumitem_Measurement_TonnePerHourKelvin:
  * - ``Measurement.TonnePerHourKelvin``
    - ``616``
    - (t/h)/K

      .. _enumitem_Measurement_TonnePerHourBar:
  * - ``Measurement.TonnePerHourBar``
    - ``617``
    - (t/h)/bar

      .. _enumitem_Measurement_TonnePerMinute:
  * - ``Measurement.TonnePerMinute``
    - ``618``
    - t/min

      .. _enumitem_Measurement_TonnePerMinuteKelvin:
  * - ``Measurement.TonnePerMinuteKelvin``
    - ``619``
    - (t/min)/K

      .. _enumitem_Measurement_TonnePerMinuteBar:
  * - ``Measurement.TonnePerMinuteBar``
    - ``620``
    - (t/min)/bar

      .. _enumitem_Measurement_TonnePerSecond:
  * - ``Measurement.TonnePerSecond``
    - ``621``
    - t/s

      .. _enumitem_Measurement_TonnePerSecondKelvin:
  * - ``Measurement.TonnePerSecondKelvin``
    - ``622``
    - (t/s)/K

      .. _enumitem_Measurement_TonnePerSecondBar:
  * - ``Measurement.TonnePerSecondBar``
    - ``623``
    - (t/s)/bar

      .. _enumitem_Measurement_TonLongPerDay:
  * - ``Measurement.TonLongPerDay``
    - ``624``
    - ton (UK)/d

      .. _enumitem_Measurement_TonShortPerDay:
  * - ``Measurement.TonShortPerDay``
    - ``625``
    - ton (US)/d

      .. _enumitem_Measurement_TonShortPerHourDegreeFahrenheit:
  * - ``Measurement.TonShortPerHourDegreeFahrenheit``
    - ``626``
    - ton (US)/(h·°F)

      .. _enumitem_Measurement_TonShortPerHourPsi:
  * - ``Measurement.TonShortPerHourPsi``
    - ``627``
    - (ton (US)/h)/psi

      .. _enumitem_Measurement_TonnePerMonth:
  * - ``Measurement.TonnePerMonth``
    - ``628``
    - t/mo

      .. _enumitem_Measurement_TonnePerYear:
  * - ``Measurement.TonnePerYear``
    - ``629``
    - t/y

      .. _enumitem_Measurement_KilopoundPerHour:
  * - ``Measurement.KilopoundPerHour``
    - ``630``
    - klb/h

      .. _enumitem_Measurement_MicrogramPerKilogram:
  * - ``Measurement.MicrogramPerKilogram``
    - ``631``
    - µg/kg

      .. _enumitem_Measurement_NanogramPerKilogram:
  * - ``Measurement.NanogramPerKilogram``
    - ``632``
    - ng/kg

      .. _enumitem_Measurement_MilligramPerKilogram:
  * - ``Measurement.MilligramPerKilogram``
    - ``633``
    - mg/kg

      .. _enumitem_Measurement_KilogramPerKilogram:
  * - ``Measurement.KilogramPerKilogram``
    - ``634``
    - kg/kg

      .. _enumitem_Measurement_PoundPerPound:
  * - ``Measurement.PoundPerPound``
    - ``635``
    - lb/lb

      .. _enumitem_Measurement_CubicMetrePerSecond:
  * - ``Measurement.CubicMetrePerSecond``
    - ``636``
    - m³/s

      .. _enumitem_Measurement_CubicMetrePerHour:
  * - ``Measurement.CubicMetrePerHour``
    - ``637``
    - m³/h

      .. _enumitem_Measurement_MillilitrePerSecond:
  * - ``Measurement.MillilitrePerSecond``
    - ``638``
    - ml/s

      .. _enumitem_Measurement_MillilitrePerMinute:
  * - ``Measurement.MillilitrePerMinute``
    - ``639``
    - ml/min

      .. _enumitem_Measurement_LitrePerDay:
  * - ``Measurement.LitrePerDay``
    - ``640``
    - l/d

      .. _enumitem_Measurement_CubicCentimetrePerSecond:
  * - ``Measurement.CubicCentimetrePerSecond``
    - ``641``
    - cm³/s

      .. _enumitem_Measurement_KilolitrePerHour:
  * - ``Measurement.KilolitrePerHour``
    - ``642``
    - kl/h

      .. _enumitem_Measurement_LitrePerMinute:
  * - ``Measurement.LitrePerMinute``
    - ``643``
    - l/min

      .. _enumitem_Measurement_CubicCentimetrePerDay:
  * - ``Measurement.CubicCentimetrePerDay``
    - ``644``
    - cm³/d

      .. _enumitem_Measurement_CubicCentimetrePerDayBar:
  * - ``Measurement.CubicCentimetrePerDayBar``
    - ``645``
    - cm³/(d·bar)

      .. _enumitem_Measurement_CubicCentimetrePerDayKelvin:
  * - ``Measurement.CubicCentimetrePerDayKelvin``
    - ``646``
    - cm³/(d·K)

      .. _enumitem_Measurement_CubicCentimetrePerHour:
  * - ``Measurement.CubicCentimetrePerHour``
    - ``647``
    - cm³/h

      .. _enumitem_Measurement_CubicCentimetrePerHourBar:
  * - ``Measurement.CubicCentimetrePerHourBar``
    - ``648``
    - cm³/(h·bar)

      .. _enumitem_Measurement_CubicCentimetrePerHourKelvin:
  * - ``Measurement.CubicCentimetrePerHourKelvin``
    - ``649``
    - cm³/(h·K)

      .. _enumitem_Measurement_CubicCentimetrePerMinute:
  * - ``Measurement.CubicCentimetrePerMinute``
    - ``650``
    - cm³/min

      .. _enumitem_Measurement_CubicCentimetrePerMinuteBar:
  * - ``Measurement.CubicCentimetrePerMinuteBar``
    - ``651``
    - cm³/(min·bar)

      .. _enumitem_Measurement_CubicCentimetrePerMinuteKelvin:
  * - ``Measurement.CubicCentimetrePerMinuteKelvin``
    - ``652``
    - cm³/(min·K)

      .. _enumitem_Measurement_CubicCentimetrePerSecondBar:
  * - ``Measurement.CubicCentimetrePerSecondBar``
    - ``653``
    - cm³/(s·bar)

      .. _enumitem_Measurement_CubicCentimetrePerSecondKelvin:
  * - ``Measurement.CubicCentimetrePerSecondKelvin``
    - ``654``
    - cm³/(s·K)

      .. _enumitem_Measurement_CubicDecimetrePerHour:
  * - ``Measurement.CubicDecimetrePerHour``
    - ``655``
    - dm³/h

      .. _enumitem_Measurement_CubicMetrePerDay:
  * - ``Measurement.CubicMetrePerDay``
    - ``656``
    - m³/d

      .. _enumitem_Measurement_CubicMetrePerDayBar:
  * - ``Measurement.CubicMetrePerDayBar``
    - ``657``
    - m³/(d·bar)

      .. _enumitem_Measurement_CubicMetrePerDayKelvin:
  * - ``Measurement.CubicMetrePerDayKelvin``
    - ``658``
    - m³/(d·K)

      .. _enumitem_Measurement_CubicMetrePerHourBar:
  * - ``Measurement.CubicMetrePerHourBar``
    - ``659``
    - m³/(h·bar)

      .. _enumitem_Measurement_CubicMetrePerHourKelvin:
  * - ``Measurement.CubicMetrePerHourKelvin``
    - ``660``
    - m³/(h·K)

      .. _enumitem_Measurement_CubicMetrePerMinute:
  * - ``Measurement.CubicMetrePerMinute``
    - ``661``
    - m³/min

      .. _enumitem_Measurement_CubicMetrePerMinuteBar:
  * - ``Measurement.CubicMetrePerMinuteBar``
    - ``662``
    - m³/(min·bar)

      .. _enumitem_Measurement_CubicMetrePerMinuteKelvin:
  * - ``Measurement.CubicMetrePerMinuteKelvin``
    - ``663``
    - m³/(min·K)

      .. _enumitem_Measurement_CubicMetrePerSecondBar:
  * - ``Measurement.CubicMetrePerSecondBar``
    - ``664``
    - m³/(s·bar)

      .. _enumitem_Measurement_CubicMetrePerSecondKelvin:
  * - ``Measurement.CubicMetrePerSecondKelvin``
    - ``665``
    - m³/(s·K)

      .. _enumitem_Measurement_LitrePerDayBar:
  * - ``Measurement.LitrePerDayBar``
    - ``666``
    - l/(d·bar)

      .. _enumitem_Measurement_LitrePerDayKelvin:
  * - ``Measurement.LitrePerDayKelvin``
    - ``667``
    - l/(d·K)

      .. _enumitem_Measurement_LitrePerHourBar:
  * - ``Measurement.LitrePerHourBar``
    - ``668``
    - l/(h·bar)

      .. _enumitem_Measurement_LitrePerHourKelvin:
  * - ``Measurement.LitrePerHourKelvin``
    - ``669``
    - l/(h·K)

      .. _enumitem_Measurement_LitrePerMinuteBar:
  * - ``Measurement.LitrePerMinuteBar``
    - ``670``
    - l/(min·bar)

      .. _enumitem_Measurement_LitrePerMinuteKelvin:
  * - ``Measurement.LitrePerMinuteKelvin``
    - ``671``
    - l/(min·K)

      .. _enumitem_Measurement_LitrePerSecond:
  * - ``Measurement.LitrePerSecond``
    - ``672``
    - l/s

      .. _enumitem_Measurement_LitrePerSecondBar:
  * - ``Measurement.LitrePerSecondBar``
    - ``673``
    - l/(s·bar)

      .. _enumitem_Measurement_LitrePerSecondKelvin:
  * - ``Measurement.LitrePerSecondKelvin``
    - ``674``
    - l/(s·K)

      .. _enumitem_Measurement_MillilitrePerDay:
  * - ``Measurement.MillilitrePerDay``
    - ``675``
    - ml/d

      .. _enumitem_Measurement_MillilitrePerDayBar:
  * - ``Measurement.MillilitrePerDayBar``
    - ``676``
    - ml/(d·bar)

      .. _enumitem_Measurement_MillilitrePerDayKelvin:
  * - ``Measurement.MillilitrePerDayKelvin``
    - ``677``
    - ml/(d·K)

      .. _enumitem_Measurement_MillilitrePerHour:
  * - ``Measurement.MillilitrePerHour``
    - ``678``
    - ml/h

      .. _enumitem_Measurement_MillilitrePerHourBar:
  * - ``Measurement.MillilitrePerHourBar``
    - ``679``
    - ml/(h·bar)

      .. _enumitem_Measurement_MillilitrePerHourKelvin:
  * - ``Measurement.MillilitrePerHourKelvin``
    - ``680``
    - ml/(h·K)

      .. _enumitem_Measurement_MillilitrePerMinuteBar:
  * - ``Measurement.MillilitrePerMinuteBar``
    - ``681``
    - ml/(min·bar)

      .. _enumitem_Measurement_MillilitrePerMinuteKelvin:
  * - ``Measurement.MillilitrePerMinuteKelvin``
    - ``682``
    - ml/(min·K)

      .. _enumitem_Measurement_MillilitrePerSecondBar:
  * - ``Measurement.MillilitrePerSecondBar``
    - ``683``
    - ml/(s·bar)

      .. _enumitem_Measurement_MillilitrePerSecondKelvin:
  * - ``Measurement.MillilitrePerSecondKelvin``
    - ``684``
    - ml/(s·K)

      .. _enumitem_Measurement_CubicFootPerHour:
  * - ``Measurement.CubicFootPerHour``
    - ``685``
    - ft³/h

      .. _enumitem_Measurement_CubicFootPerMinute:
  * - ``Measurement.CubicFootPerMinute``
    - ``686``
    - ft³/min

      .. _enumitem_Measurement_BarrelUSPerMinute:
  * - ``Measurement.BarrelUSPerMinute``
    - ``687``
    - barrel (US)/min

      .. _enumitem_Measurement_USGallonPerMinute:
  * - ``Measurement.USGallonPerMinute``
    - ``688``
    - gal (US) /min

      .. _enumitem_Measurement_ImperialGallonPerMinute:
  * - ``Measurement.ImperialGallonPerMinute``
    - ``689``
    - gal (UK) /min

      .. _enumitem_Measurement_CubicInchPerHour:
  * - ``Measurement.CubicInchPerHour``
    - ``690``
    - in³/h

      .. _enumitem_Measurement_CubicInchPerMinute:
  * - ``Measurement.CubicInchPerMinute``
    - ``691``
    - in³/min

      .. _enumitem_Measurement_CubicInchPerSecond:
  * - ``Measurement.CubicInchPerSecond``
    - ``692``
    - in³/s

      .. _enumitem_Measurement_GallonUSPerHour:
  * - ``Measurement.GallonUSPerHour``
    - ``693``
    - gal/h

      .. _enumitem_Measurement_BarrelUKPetroleumPerMinute:
  * - ``Measurement.BarrelUKPetroleumPerMinute``
    - ``694``
    - bbl (UK liq.)/min

      .. _enumitem_Measurement_BarrelUKPetroleumPerDay:
  * - ``Measurement.BarrelUKPetroleumPerDay``
    - ``695``
    - bbl (UK liq.)/d

      .. _enumitem_Measurement_BarrelUKPetroleumPerHour:
  * - ``Measurement.BarrelUKPetroleumPerHour``
    - ``696``
    - bbl (UK liq.)/h

      .. _enumitem_Measurement_BarrelUKPetroleumPerSecond:
  * - ``Measurement.BarrelUKPetroleumPerSecond``
    - ``697``
    - bbl (UK liq.)/s

      .. _enumitem_Measurement_BarrelUSPetroleumPerHour:
  * - ``Measurement.BarrelUSPetroleumPerHour``
    - ``698``
    - bbl (US)/h

      .. _enumitem_Measurement_BarrelUSPetroleumPerSecond:
  * - ``Measurement.BarrelUSPetroleumPerSecond``
    - ``699``
    - bbl (US)/s

      .. _enumitem_Measurement_BushelUKPerDay:
  * - ``Measurement.BushelUKPerDay``
    - ``700``
    - bu (UK)/d

      .. _enumitem_Measurement_BushelUKPerHour:
  * - ``Measurement.BushelUKPerHour``
    - ``701``
    - bu (UK)/h

      .. _enumitem_Measurement_BushelUKPerMinute:
  * - ``Measurement.BushelUKPerMinute``
    - ``702``
    - bu (UK)/min

      .. _enumitem_Measurement_BushelUKPerSecond:
  * - ``Measurement.BushelUKPerSecond``
    - ``703``
    - bu (UK)/s

      .. _enumitem_Measurement_BushelUSDryPerDay:
  * - ``Measurement.BushelUSDryPerDay``
    - ``704``
    - bu (US dry)/d

      .. _enumitem_Measurement_BushelUSDryPerHour:
  * - ``Measurement.BushelUSDryPerHour``
    - ``705``
    - bu (US dry)/h

      .. _enumitem_Measurement_BushelUSDryPerMinute:
  * - ``Measurement.BushelUSDryPerMinute``
    - ``706``
    - bu (US dry)/min

      .. _enumitem_Measurement_BushelUSDryPerSecond:
  * - ``Measurement.BushelUSDryPerSecond``
    - ``707``
    - bu (US dry)/s

      .. _enumitem_Measurement_CubicDecimetrePerDay:
  * - ``Measurement.CubicDecimetrePerDay``
    - ``708``
    - dm³/d

      .. _enumitem_Measurement_CubicDecimetrePerMinute:
  * - ``Measurement.CubicDecimetrePerMinute``
    - ``709``
    - dm³/min

      .. _enumitem_Measurement_CubicDecimetrePerSecond:
  * - ``Measurement.CubicDecimetrePerSecond``
    - ``710``
    - dm³/s

      .. _enumitem_Measurement_CubicMetrePerSecondPascal:
  * - ``Measurement.CubicMetrePerSecondPascal``
    - ``711``
    - (m³/s)/Pa

      .. _enumitem_Measurement_OunceUKFluidPerDay:
  * - ``Measurement.OunceUKFluidPerDay``
    - ``712``
    - fl oz (UK)/d

      .. _enumitem_Measurement_OunceUKFluidPerHour:
  * - ``Measurement.OunceUKFluidPerHour``
    - ``713``
    - fl oz (UK)/h

      .. _enumitem_Measurement_OunceUKFluidPerMinute:
  * - ``Measurement.OunceUKFluidPerMinute``
    - ``714``
    - fl oz (UK)/min

      .. _enumitem_Measurement_OunceUKFluidPerSecond:
  * - ``Measurement.OunceUKFluidPerSecond``
    - ``715``
    - fl oz (UK)/s

      .. _enumitem_Measurement_OunceUSFluidPerDay:
  * - ``Measurement.OunceUSFluidPerDay``
    - ``716``
    - fl oz (US)/d

      .. _enumitem_Measurement_OunceUSFluidPerHour:
  * - ``Measurement.OunceUSFluidPerHour``
    - ``717``
    - fl oz (US)/h

      .. _enumitem_Measurement_OunceUSFluidPerMinute:
  * - ``Measurement.OunceUSFluidPerMinute``
    - ``718``
    - fl oz (US)/min

      .. _enumitem_Measurement_OunceUSFluidPerSecond:
  * - ``Measurement.OunceUSFluidPerSecond``
    - ``719``
    - fl oz (US)/s

      .. _enumitem_Measurement_CubicFootPerDay:
  * - ``Measurement.CubicFootPerDay``
    - ``720``
    - ft³/d

      .. _enumitem_Measurement_GallonUKPerDay:
  * - ``Measurement.GallonUKPerDay``
    - ``721``
    - gal (UK)/d

      .. _enumitem_Measurement_GallonUKPerHour:
  * - ``Measurement.GallonUKPerHour``
    - ``722``
    - gal (UK)/h

      .. _enumitem_Measurement_GallonUKPerSecond:
  * - ``Measurement.GallonUKPerSecond``
    - ``723``
    - gal (UK)/s

      .. _enumitem_Measurement_GallonUSLiquidPerSecond:
  * - ``Measurement.GallonUSLiquidPerSecond``
    - ``724``
    - gal (US liq.)/s

      .. _enumitem_Measurement_GillUKPerDay:
  * - ``Measurement.GillUKPerDay``
    - ``725``
    - gi (UK)/d

      .. _enumitem_Measurement_GillUKPerHour:
  * - ``Measurement.GillUKPerHour``
    - ``726``
    - gi (UK)/h

      .. _enumitem_Measurement_GillUKPerMinute:
  * - ``Measurement.GillUKPerMinute``
    - ``727``
    - gi (UK)/min

      .. _enumitem_Measurement_GillUKPerSecond:
  * - ``Measurement.GillUKPerSecond``
    - ``728``
    - gi (UK)/s

      .. _enumitem_Measurement_GillUSPerDay:
  * - ``Measurement.GillUSPerDay``
    - ``729``
    - gi (US)/d

      .. _enumitem_Measurement_GillUSPerHour:
  * - ``Measurement.GillUSPerHour``
    - ``730``
    - gi (US)/h

      .. _enumitem_Measurement_GillUSPerMinute:
  * - ``Measurement.GillUSPerMinute``
    - ``731``
    - gi (US)/min

      .. _enumitem_Measurement_GillUSPerSecond:
  * - ``Measurement.GillUSPerSecond``
    - ``732``
    - gi (US)/s

      .. _enumitem_Measurement_QuartUKLiquidPerDay:
  * - ``Measurement.QuartUKLiquidPerDay``
    - ``733``
    - qt (UK liq.)/d

      .. _enumitem_Measurement_QuartUKLiquidPerHour:
  * - ``Measurement.QuartUKLiquidPerHour``
    - ``734``
    - qt (UK liq.)/h

      .. _enumitem_Measurement_QuartUKLiquidPerMinute:
  * - ``Measurement.QuartUKLiquidPerMinute``
    - ``735``
    - qt (UK liq.)/min

      .. _enumitem_Measurement_QuartUKLiquidPerSecond:
  * - ``Measurement.QuartUKLiquidPerSecond``
    - ``736``
    - qt (UK liq.)/s

      .. _enumitem_Measurement_QuartUSLiquidPerDay:
  * - ``Measurement.QuartUSLiquidPerDay``
    - ``737``
    - qt (US liq.)/d

      .. _enumitem_Measurement_QuartUSLiquidPerHour:
  * - ``Measurement.QuartUSLiquidPerHour``
    - ``738``
    - qt (US liq.)/h

      .. _enumitem_Measurement_QuartUSLiquidPerMinute:
  * - ``Measurement.QuartUSLiquidPerMinute``
    - ``739``
    - qt (US liq.)/min

      .. _enumitem_Measurement_QuartUSLiquidPerSecond:
  * - ``Measurement.QuartUSLiquidPerSecond``
    - ``740``
    - qt (US liq.)/s

      .. _enumitem_Measurement_PeckUKPerDay:
  * - ``Measurement.PeckUKPerDay``
    - ``741``
    - pk (UK)/d

      .. _enumitem_Measurement_PeckUKPerHour:
  * - ``Measurement.PeckUKPerHour``
    - ``742``
    - pk (UK)/h

      .. _enumitem_Measurement_PeckUKPerMinute:
  * - ``Measurement.PeckUKPerMinute``
    - ``743``
    - pk (UK)/min

      .. _enumitem_Measurement_PeckUKPerSecond:
  * - ``Measurement.PeckUKPerSecond``
    - ``744``
    - pk (UK)/s

      .. _enumitem_Measurement_PeckUSDryPerDay:
  * - ``Measurement.PeckUSDryPerDay``
    - ``745``
    - pk (US dry)/d

      .. _enumitem_Measurement_PeckUSDryPerHour:
  * - ``Measurement.PeckUSDryPerHour``
    - ``746``
    - pk (US dry)/h

      .. _enumitem_Measurement_PeckUSDryPerMinute:
  * - ``Measurement.PeckUSDryPerMinute``
    - ``747``
    - pk (US dry)/min

      .. _enumitem_Measurement_PeckUSDryPerSecond:
  * - ``Measurement.PeckUSDryPerSecond``
    - ``748``
    - pk (US dry)/s

      .. _enumitem_Measurement_PintUKPerDay:
  * - ``Measurement.PintUKPerDay``
    - ``749``
    - pt (UK)/d

      .. _enumitem_Measurement_PintUKPerHour:
  * - ``Measurement.PintUKPerHour``
    - ``750``
    - pt (UK)/h

      .. _enumitem_Measurement_PintUKPerMinute:
  * - ``Measurement.PintUKPerMinute``
    - ``751``
    - pt (UK)/min

      .. _enumitem_Measurement_PintUKPerSecond:
  * - ``Measurement.PintUKPerSecond``
    - ``752``
    - pt (UK)/s

      .. _enumitem_Measurement_PintUSLiquidPerDay:
  * - ``Measurement.PintUSLiquidPerDay``
    - ``753``
    - pt (US liq.)/d

      .. _enumitem_Measurement_PintUSLiquidPerHour:
  * - ``Measurement.PintUSLiquidPerHour``
    - ``754``
    - pt (US liq.)/h

      .. _enumitem_Measurement_PintUSLiquidPerMinute:
  * - ``Measurement.PintUSLiquidPerMinute``
    - ``755``
    - pt (US liq.)/min

      .. _enumitem_Measurement_PintUSLiquidPerSecond:
  * - ``Measurement.PintUSLiquidPerSecond``
    - ``756``
    - pt (US liq.)/s

      .. _enumitem_Measurement_CubicYardPerDay:
  * - ``Measurement.CubicYardPerDay``
    - ``757``
    - yd³/d

      .. _enumitem_Measurement_CubicYardPerHour:
  * - ``Measurement.CubicYardPerHour``
    - ``758``
    - yd³/h

      .. _enumitem_Measurement_CubicYardPerMinute:
  * - ``Measurement.CubicYardPerMinute``
    - ``759``
    - yd³/min

      .. _enumitem_Measurement_CubicYardPerSecond:
  * - ``Measurement.CubicYardPerSecond``
    - ``760``
    - yd³/s

      .. _enumitem_Measurement_CubicMetrePerCubicMetre:
  * - ``Measurement.CubicMetrePerCubicMetre``
    - ``761``
    - m³/m³

      .. _enumitem_Measurement_BarCubicMetrePerSecond:
  * - ``Measurement.BarCubicMetrePerSecond``
    - ``762``
    - bar·m³/s

      .. _enumitem_Measurement_BarLitrePerSecond:
  * - ``Measurement.BarLitrePerSecond``
    - ``763``
    - bar·l/s

      .. _enumitem_Measurement_PsiCubicInchPerSecond:
  * - ``Measurement.PsiCubicInchPerSecond``
    - ``764``
    - psi·in³/s

      .. _enumitem_Measurement_PsiLitrePerSecond:
  * - ``Measurement.PsiLitrePerSecond``
    - ``765``
    - psi·l/s

      .. _enumitem_Measurement_PsiCubicMetrePerSecond:
  * - ``Measurement.PsiCubicMetrePerSecond``
    - ``766``
    - psi·m³/s

      .. _enumitem_Measurement_PsiCubicYardPerSecond:
  * - ``Measurement.PsiCubicYardPerSecond``
    - ``767``
    - psi·yd³/s

      .. _enumitem_Measurement_Kelvin:
  * - ``Measurement.Kelvin``
    - ``768``
    - K

      .. _enumitem_Measurement_DegreeCelsius:
  * - ``Measurement.DegreeCelsius``
    - ``769``
    - °C

      .. _enumitem_Measurement_DegreeCelsiusPerHour:
  * - ``Measurement.DegreeCelsiusPerHour``
    - ``770``
    - °C/h

      .. _enumitem_Measurement_DegreeCelsiusPerBar:
  * - ``Measurement.DegreeCelsiusPerBar``
    - ``771``
    - °C/bar

      .. _enumitem_Measurement_DegreeCelsiusPerKelvin:
  * - ``Measurement.DegreeCelsiusPerKelvin``
    - ``772``
    - °C/K

      .. _enumitem_Measurement_DegreeCelsiusPerMinute:
  * - ``Measurement.DegreeCelsiusPerMinute``
    - ``773``
    - °C/min

      .. _enumitem_Measurement_DegreeCelsiusPerSecond:
  * - ``Measurement.DegreeCelsiusPerSecond``
    - ``774``
    - °C/s

      .. _enumitem_Measurement_KelvinPerBar:
  * - ``Measurement.KelvinPerBar``
    - ``775``
    - K/bar

      .. _enumitem_Measurement_KelvinPerHour:
  * - ``Measurement.KelvinPerHour``
    - ``776``
    - K/h

      .. _enumitem_Measurement_KelvinPerKelvin:
  * - ``Measurement.KelvinPerKelvin``
    - ``777``
    - K/K

      .. _enumitem_Measurement_KelvinPerMinute:
  * - ``Measurement.KelvinPerMinute``
    - ``778``
    - K/min

      .. _enumitem_Measurement_KelvinPerSecond:
  * - ``Measurement.KelvinPerSecond``
    - ``779``
    - K/s

      .. _enumitem_Measurement_KelvinPerPascal:
  * - ``Measurement.KelvinPerPascal``
    - ``780``
    - K/Pa

      .. _enumitem_Measurement_DegreeFahrenheitPerKelvin:
  * - ``Measurement.DegreeFahrenheitPerKelvin``
    - ``781``
    - °F/K

      .. _enumitem_Measurement_DegreeFahrenheitPerBar:
  * - ``Measurement.DegreeFahrenheitPerBar``
    - ``782``
    - °F/bar

      .. _enumitem_Measurement_ReciprocalDegreeFahrenheit:
  * - ``Measurement.ReciprocalDegreeFahrenheit``
    - ``783``
    - 1/°F

      .. _enumitem_Measurement_DegreeRankine:
  * - ``Measurement.DegreeRankine``
    - ``784``
    - °R

      .. _enumitem_Measurement_DegreeFahrenheit:
  * - ``Measurement.DegreeFahrenheit``
    - ``785``
    - °F

      .. _enumitem_Measurement_DegreeFahrenheitPerHour:
  * - ``Measurement.DegreeFahrenheitPerHour``
    - ``786``
    - °F/h

      .. _enumitem_Measurement_DegreeFahrenheitPerMinute:
  * - ``Measurement.DegreeFahrenheitPerMinute``
    - ``787``
    - °F/min

      .. _enumitem_Measurement_DegreeFahrenheitPerSecond:
  * - ``Measurement.DegreeFahrenheitPerSecond``
    - ``788``
    - °F/s

      .. _enumitem_Measurement_DegreeRankinePerHour:
  * - ``Measurement.DegreeRankinePerHour``
    - ``789``
    - °R/h

      .. _enumitem_Measurement_DegreeRankinePerMinute:
  * - ``Measurement.DegreeRankinePerMinute``
    - ``790``
    - °R/min

      .. _enumitem_Measurement_DegreeRankinePerSecond:
  * - ``Measurement.DegreeRankinePerSecond``
    - ``791``
    - °R/s

      .. _enumitem_Measurement_ReciprocalKelvinOrKelvinToThePowerMinusOne:
  * - ``Measurement.ReciprocalKelvinOrKelvinToThePowerMinusOne``
    - ``792``
    - K⁻¹

      .. _enumitem_Measurement_ReciprocalMegakelvinOrMegakelvinToThePowerMinusOne:
  * - ``Measurement.ReciprocalMegakelvinOrMegakelvinToThePowerMinusOne``
    - ``793``
    - 1/MK

      .. _enumitem_Measurement_PascalPerKelvin:
  * - ``Measurement.PascalPerKelvin``
    - ``794``
    - Pa/K

      .. _enumitem_Measurement_BarPerKelvin:
  * - ``Measurement.BarPerKelvin``
    - ``795``
    - bar/K

      .. _enumitem_Measurement_WattSecond:
  * - ``Measurement.WattSecond``
    - ``796``
    - W·s

      .. _enumitem_Measurement_BritishThermalUnitInternationalTable:
  * - ``Measurement.BritishThermalUnitInternationalTable``
    - ``797``
    - BtuIT

      .. _enumitem_Measurement_BritishThermalUnitMean:
  * - ``Measurement.BritishThermalUnitMean``
    - ``798``
    - Btu

      .. _enumitem_Measurement_CalorieMean:
  * - ``Measurement.CalorieMean``
    - ``799``
    - cal

      .. _enumitem_Measurement_KilocalorieMean:
  * - ``Measurement.KilocalorieMean``
    - ``800``
    - kcal

      .. _enumitem_Measurement_KilocalorieInternationalTable:
  * - ``Measurement.KilocalorieInternationalTable``
    - ``801``
    - kcalIT

      .. _enumitem_Measurement_KilocalorieThermochemical:
  * - ``Measurement.KilocalorieThermochemical``
    - ``802``
    - kcalth

      .. _enumitem_Measurement_BritishThermalUnit39DegF:
  * - ``Measurement.BritishThermalUnit39DegF``
    - ``803``
    - Btu (39 ºF) 

      .. _enumitem_Measurement_BritishThermalUnit59DegF:
  * - ``Measurement.BritishThermalUnit59DegF``
    - ``804``
    - Btu (59 ºF)

      .. _enumitem_Measurement_BritishThermalUnit60DegF:
  * - ``Measurement.BritishThermalUnit60DegF``
    - ``805``
    - Btu (60 ºF) 

      .. _enumitem_Measurement_CalorieDegC:
  * - ``Measurement.CalorieDegC``
    - ``806``
    - cal₂₀

      .. _enumitem_Measurement_QuadBtuIT:
  * - ``Measurement.QuadBtuIT``
    - ``807``
    - quad

      .. _enumitem_Measurement_ThermEC:
  * - ``Measurement.ThermEC``
    - ``808``
    - thm (EC)

      .. _enumitem_Measurement_ThermUS:
  * - ``Measurement.ThermUS``
    - ``809``
    - thm (US)

      .. _enumitem_Measurement_BritishThermalUnitInternationalTablePerHour:
  * - ``Measurement.BritishThermalUnitInternationalTablePerHour``
    - ``810``
    - BtuIT/h

      .. _enumitem_Measurement_BritishThermalUnitInternationalTablePerMinute:
  * - ``Measurement.BritishThermalUnitInternationalTablePerMinute``
    - ``811``
    - BtuIT/min

      .. _enumitem_Measurement_BritishThermalUnitInternationalTablePerSecond:
  * - ``Measurement.BritishThermalUnitInternationalTablePerSecond``
    - ``812``
    - BtuIT/s

      .. _enumitem_Measurement_BritishThermalUnitThermochemicalPerHour:
  * - ``Measurement.BritishThermalUnitThermochemicalPerHour``
    - ``813``
    - Btuth/h

      .. _enumitem_Measurement_BritishThermalUnitThermochemicalPerMinute:
  * - ``Measurement.BritishThermalUnitThermochemicalPerMinute``
    - ``814``
    - Btuth/min

      .. _enumitem_Measurement_BritishThermalUnitThermochemicalPerSecond:
  * - ``Measurement.BritishThermalUnitThermochemicalPerSecond``
    - ``815``
    - Btuth/s

      .. _enumitem_Measurement_CalorieThermochemicalPerMinute:
  * - ``Measurement.CalorieThermochemicalPerMinute``
    - ``816``
    - calth/min

      .. _enumitem_Measurement_CalorieThermochemicalPerSecond:
  * - ``Measurement.CalorieThermochemicalPerSecond``
    - ``817``
    - calth/s

      .. _enumitem_Measurement_KilocalorieThermochemicalPerHour:
  * - ``Measurement.KilocalorieThermochemicalPerHour``
    - ``818``
    - kcalth/h

      .. _enumitem_Measurement_KilocalorieThermochemicalPerMinute:
  * - ``Measurement.KilocalorieThermochemicalPerMinute``
    - ``819``
    - kcalth/min

      .. _enumitem_Measurement_KilocalorieThermochemicalPerSecond:
  * - ``Measurement.KilocalorieThermochemicalPerSecond``
    - ``820``
    - kcalth/s

      .. _enumitem_Measurement_WattPerSquareMetre:
  * - ``Measurement.WattPerSquareMetre``
    - ``821``
    - W/m²

      .. _enumitem_Measurement_WattPerSquareCentimetre:
  * - ``Measurement.WattPerSquareCentimetre``
    - ``822``
    - W/cm²

      .. _enumitem_Measurement_WattPerSquareInch:
  * - ``Measurement.WattPerSquareInch``
    - ``823``
    - W/in²

      .. _enumitem_Measurement_BritishThermalUnitInternationalTablePerSquareFootHour:
  * - ``Measurement.BritishThermalUnitInternationalTablePerSquareFootHour``
    - ``824``
    - BtuIT/(ft²·h)

      .. _enumitem_Measurement_BritishThermalUnitThermochemicalPerSquareFootHour:
  * - ``Measurement.BritishThermalUnitThermochemicalPerSquareFootHour``
    - ``825``
    - Btuth/(ft²·h)

      .. _enumitem_Measurement_BritishThermalUnitThermochemicalPerSquareFootMinute:
  * - ``Measurement.BritishThermalUnitThermochemicalPerSquareFootMinute``
    - ``826``
    - Btuth/(ft²·min) 

      .. _enumitem_Measurement_BritishThermalUnitInternationalTablePerSquareFootSecond:
  * - ``Measurement.BritishThermalUnitInternationalTablePerSquareFootSecond``
    - ``827``
    - BtuIT/(ft²·s)

      .. _enumitem_Measurement_BritishThermalUnitThermochemicalPerSquareFootSecond:
  * - ``Measurement.BritishThermalUnitThermochemicalPerSquareFootSecond``
    - ``828``
    - Btuth/(ft²·s)

      .. _enumitem_Measurement_BritishThermalUnitInternationalTablePerSquareInchSecond:
  * - ``Measurement.BritishThermalUnitInternationalTablePerSquareInchSecond``
    - ``829``
    - BtuIT/(in²·s)

      .. _enumitem_Measurement_CalorieThermochemicalPerSquareCentimetreMinute:
  * - ``Measurement.CalorieThermochemicalPerSquareCentimetreMinute``
    - ``830``
    - calth/(cm²·min)

      .. _enumitem_Measurement_CalorieThermochemicalPerSquareCentimetreSecond:
  * - ``Measurement.CalorieThermochemicalPerSquareCentimetreSecond``
    - ``831``
    - calth/(cm²·s)

      .. _enumitem_Measurement_WattPerMetreKelvin:
  * - ``Measurement.WattPerMetreKelvin``
    - ``832``
    - W/(m·K)

      .. _enumitem_Measurement_WattPerMetreDegreeCelsius:
  * - ``Measurement.WattPerMetreDegreeCelsius``
    - ``833``
    - W/(m·°C)

      .. _enumitem_Measurement_KilowattPerMetreKelvin:
  * - ``Measurement.KilowattPerMetreKelvin``
    - ``834``
    - kW/(m·K)

      .. _enumitem_Measurement_KilowattPerMetreDegreeCelsius:
  * - ``Measurement.KilowattPerMetreDegreeCelsius``
    - ``835``
    - kW/(m·°C)

      .. _enumitem_Measurement_BritishThermalUnitInternationalTablePerSecondFootDegreeRankine:
  * - ``Measurement.BritishThermalUnitInternationalTablePerSecondFootDegreeRankine``
    - ``836``
    - BtuIT/(s·ft·°R)

      .. _enumitem_Measurement_BritishThermalUnitInternationalTableFootPerHourSquareFootDegreeFahrenheit:
  * - ``Measurement.BritishThermalUnitInternationalTableFootPerHourSquareFootDegreeFahrenheit``
    - ``837``
    - BtuIT·ft/(h·ft²·°F)

      .. _enumitem_Measurement_BritishThermalUnitInternationalTableInchPerHourSquareFootDegreeFahrenheit:
  * - ``Measurement.BritishThermalUnitInternationalTableInchPerHourSquareFootDegreeFahrenheit``
    - ``838``
    - BtuIT·in/(h·ft²·°F)

      .. _enumitem_Measurement_BritishThermalUnitInternationalTableInchPerSecondSquareFootDegreeFahrenheit:
  * - ``Measurement.BritishThermalUnitInternationalTableInchPerSecondSquareFootDegreeFahrenheit``
    - ``839``
    - BtuIT·in/(s·ft²·°F)

      .. _enumitem_Measurement_BritishThermalUnitThermochemicalFootPerHourSquareFootDegreeFahrenheit:
  * - ``Measurement.BritishThermalUnitThermochemicalFootPerHourSquareFootDegreeFahrenheit``
    - ``840``
    - Btuth·ft/(h·ft²·°F)

      .. _enumitem_Measurement_BritishThermalUnitThermochemicalInchPerHourSquareFootDegreeFahrenheit:
  * - ``Measurement.BritishThermalUnitThermochemicalInchPerHourSquareFootDegreeFahrenheit``
    - ``841``
    - Btuth·in/(h·ft²·°F)

      .. _enumitem_Measurement_BritishThermalUnitThermochemicalInchPerSecondSquareFootDegreeFahrenheit:
  * - ``Measurement.BritishThermalUnitThermochemicalInchPerSecondSquareFootDegreeFahrenheit``
    - ``842``
    - Btuth·in/(s·ft²·°F)

      .. _enumitem_Measurement_CalorieThermochemicalPerCentimetreSecondDegreeCelsius:
  * - ``Measurement.CalorieThermochemicalPerCentimetreSecondDegreeCelsius``
    - ``843``
    - calth/(cm·s·°C)

      .. _enumitem_Measurement_KilocalorieInternationalTablePerHourMetreDegreeCelsius:
  * - ``Measurement.KilocalorieInternationalTablePerHourMetreDegreeCelsius``
    - ``844``
    - kcal/(m·h·°C)

      .. _enumitem_Measurement_WattPerSquareMetreKelvin:
  * - ``Measurement.WattPerSquareMetreKelvin``
    - ``845``
    - W/(m²·K)

      .. _enumitem_Measurement_KilowattPerSquareMetreKelvin:
  * - ``Measurement.KilowattPerSquareMetreKelvin``
    - ``846``
    - kW/(m²·K)

      .. _enumitem_Measurement_BritishThermalUnitInternationalTablePerSecondSquareFootDegreeRankine:
  * - ``Measurement.BritishThermalUnitInternationalTablePerSecondSquareFootDegreeRankine``
    - ``847``
    - BtuIT/(s·ft²·°R)

      .. _enumitem_Measurement_BritishThermalUnitInternationalTablePerHourSquareFootDegreeRankine:
  * - ``Measurement.BritishThermalUnitInternationalTablePerHourSquareFootDegreeRankine``
    - ``848``
    - BtuIT/(h·ft²·°R)

      .. _enumitem_Measurement_BritishThermalUnitInternationalTablePerHourSquareFootDegreeFahrenheit:
  * - ``Measurement.BritishThermalUnitInternationalTablePerHourSquareFootDegreeFahrenheit``
    - ``849``
    - BtuIT/(h·ft²·ºF)

      .. _enumitem_Measurement_BritishThermalUnitThermochemicalPerHourSquareFootDegreeFahrenheit:
  * - ``Measurement.BritishThermalUnitThermochemicalPerHourSquareFootDegreeFahrenheit``
    - ``850``
    - Btuth/(h·ft²·ºF)

      .. _enumitem_Measurement_BritishThermalUnitInternationalTablePerSecondSquareFootDegreeFahrenheit:
  * - ``Measurement.BritishThermalUnitInternationalTablePerSecondSquareFootDegreeFahrenheit``
    - ``851``
    - BtuIT/(s·ft²·ºF)

      .. _enumitem_Measurement_BritishThermalUnitThermochemicalPerSecondSquareFootDegreeFahrenheit:
  * - ``Measurement.BritishThermalUnitThermochemicalPerSecondSquareFootDegreeFahrenheit``
    - ``852``
    - Btuth/(s·ft²·ºF) 

      .. _enumitem_Measurement_SquareMetreKelvinPerWatt:
  * - ``Measurement.SquareMetreKelvinPerWatt``
    - ``853``
    - m²·K/W

      .. _enumitem_Measurement_DegreeFahrenheitHourSquareFootPerBritishThermalUnitThermochemical:
  * - ``Measurement.DegreeFahrenheitHourSquareFootPerBritishThermalUnitThermochemical``
    - ``854``
    - °F·h·ft²/Btuth

      .. _enumitem_Measurement_DegreeFahrenheitHourSquareFootPerBritishThermalUnitInternationalTable:
  * - ``Measurement.DegreeFahrenheitHourSquareFootPerBritishThermalUnitInternationalTable``
    - ``855``
    - °F·h·ft²/BtuIT

      .. _enumitem_Measurement_Clo:
  * - ``Measurement.Clo``
    - ``856``
    - clo

      .. _enumitem_Measurement_SquareMetreHourDegreeCelsiusPerKilocalorieInternationalTable:
  * - ``Measurement.SquareMetreHourDegreeCelsiusPerKilocalorieInternationalTable``
    - ``857``
    - m²·h·°C/kcal

      .. _enumitem_Measurement_KelvinPerWatt:
  * - ``Measurement.KelvinPerWatt``
    - ``858``
    - K/W

      .. _enumitem_Measurement_KelvinMetrePerWatt:
  * - ``Measurement.KelvinMetrePerWatt``
    - ``859``
    - K·m/W

      .. _enumitem_Measurement_DegreeFahrenheitHourPerBritishThermalUnitInternationalTable:
  * - ``Measurement.DegreeFahrenheitHourPerBritishThermalUnitInternationalTable``
    - ``860``
    - ºF/(BtuIT/h)

      .. _enumitem_Measurement_DegreeFahrenheitHourPerBritishThermalUnitThermochemical:
  * - ``Measurement.DegreeFahrenheitHourPerBritishThermalUnitThermochemical``
    - ``861``
    - ºF/(Btuth/h)

      .. _enumitem_Measurement_DegreeFahrenheitSecondPerBritishThermalUnitInternationalTable:
  * - ``Measurement.DegreeFahrenheitSecondPerBritishThermalUnitInternationalTable``
    - ``862``
    - ºF/(BtuIT/s)

      .. _enumitem_Measurement_DegreeFahrenheitSecondPerBritishThermalUnitThermochemical:
  * - ``Measurement.DegreeFahrenheitSecondPerBritishThermalUnitThermochemical``
    - ``863``
    - ºF/(Btuth/s)

      .. _enumitem_Measurement_DegreeFahrenheitHourSquareFootPerBritishThermalUnitInternationalTableInch:
  * - ``Measurement.DegreeFahrenheitHourSquareFootPerBritishThermalUnitInternationalTableInch``
    - ``864``
    - ºF·h·ft²/(BtuIT·in)

      .. _enumitem_Measurement_DegreeFahrenheitHourSquareFootPerBritishThermalUnitThermochemicalInch:
  * - ``Measurement.DegreeFahrenheitHourSquareFootPerBritishThermalUnitThermochemicalInch``
    - ``865``
    - ºF·h·ft²/(Btuth·in)

      .. _enumitem_Measurement_WattPerKelvin:
  * - ``Measurement.WattPerKelvin``
    - ``866``
    - W/K

      .. _enumitem_Measurement_MillimetrePerDegreeCelciusMetre:
  * - ``Measurement.MillimetrePerDegreeCelciusMetre``
    - ``867``
    - mm/(°C·m)

      .. _enumitem_Measurement_MillimetrePerKelvin:
  * - ``Measurement.MillimetrePerKelvin``
    - ``868``
    - mm/K

      .. _enumitem_Measurement_MetrePerDegreeCelciusMetre:
  * - ``Measurement.MetrePerDegreeCelciusMetre``
    - ``869``
    - m/(°C·m)

      .. _enumitem_Measurement_JoulePerKelvin:
  * - ``Measurement.JoulePerKelvin``
    - ``870``
    - J/K

      .. _enumitem_Measurement_KilojoulePerKelvin:
  * - ``Measurement.KilojoulePerKelvin``
    - ``871``
    - kJ/K

      .. _enumitem_Measurement_BritishThermalUnitInternationalTablePerPoundDegreeFahrenheit:
  * - ``Measurement.BritishThermalUnitInternationalTablePerPoundDegreeFahrenheit``
    - ``872``
    - BtuIT/(lb·°F)

      .. _enumitem_Measurement_BritishThermalUnitThermochemicalPerPoundDegreeFahrenheit:
  * - ``Measurement.BritishThermalUnitThermochemicalPerPoundDegreeFahrenheit``
    - ``873``
    - Btuth/(lb·°F)

      .. _enumitem_Measurement_CalorieInternationalTablePerGramDegreeCelsius:
  * - ``Measurement.CalorieInternationalTablePerGramDegreeCelsius``
    - ``874``
    - calIT/(g·°C)

      .. _enumitem_Measurement_CalorieThermochemicalPerGramDegreeCelsius:
  * - ``Measurement.CalorieThermochemicalPerGramDegreeCelsius``
    - ``875``
    - calth/(g·°C)

      .. _enumitem_Measurement_BritishThermalUnitInternationalTablePerDegreeFahrenheit:
  * - ``Measurement.BritishThermalUnitInternationalTablePerDegreeFahrenheit``
    - ``876``
    - BtuIT/ºF

      .. _enumitem_Measurement_BritishThermalUnitThermochemicalPerDegreeFahrenheit:
  * - ``Measurement.BritishThermalUnitThermochemicalPerDegreeFahrenheit``
    - ``877``
    - Btuth/ºF

      .. _enumitem_Measurement_BritishThermalUnitInternationalTablePerDegreeRankine:
  * - ``Measurement.BritishThermalUnitInternationalTablePerDegreeRankine``
    - ``878``
    - BtuIT/ºR

      .. _enumitem_Measurement_BritishThermalUnitThermochemicalPerDegreeRankine:
  * - ``Measurement.BritishThermalUnitThermochemicalPerDegreeRankine``
    - ``879``
    - Btuth/ºR

      .. _enumitem_Measurement_BritishThermalUnitThermochemicalPerPoundDegreeRankine:
  * - ``Measurement.BritishThermalUnitThermochemicalPerPoundDegreeRankine``
    - ``880``
    - (Btuth/°R)/lb

      .. _enumitem_Measurement_KilocalorieInternationalTablePerGramKelvin:
  * - ``Measurement.KilocalorieInternationalTablePerGramKelvin``
    - ``881``
    - (kcalIT/K)/g

      .. _enumitem_Measurement_JoulePerKilogramKelvin:
  * - ``Measurement.JoulePerKilogramKelvin``
    - ``882``
    - J/(kg·K)

      .. _enumitem_Measurement_KilojoulePerKilogramKelvin:
  * - ``Measurement.KilojoulePerKilogramKelvin``
    - ``883``
    - kJ/(kg·K)

      .. _enumitem_Measurement_BritishThermalUnitInternationalTablePerPoundDegreeRankine:
  * - ``Measurement.BritishThermalUnitInternationalTablePerPoundDegreeRankine``
    - ``884``
    - Btu/IT(lb·°R)

      .. _enumitem_Measurement_JoulePerKilogram:
  * - ``Measurement.JoulePerKilogram``
    - ``885``
    - J/kg

      .. _enumitem_Measurement_JoulePerGram:
  * - ``Measurement.JoulePerGram``
    - ``886``
    - J/g

      .. _enumitem_Measurement_MegajoulePerKilogram:
  * - ``Measurement.MegajoulePerKilogram``
    - ``887``
    - MJ/kg

      .. _enumitem_Measurement_KilojoulePerKilogram:
  * - ``Measurement.KilojoulePerKilogram``
    - ``888``
    - kJ/kg

      .. _enumitem_Measurement_BritishThermalUnitInternationalTablePerPound:
  * - ``Measurement.BritishThermalUnitInternationalTablePerPound``
    - ``889``
    - BtuIT/lb

      .. _enumitem_Measurement_BritishThermalUnitThermochemicalPerPound:
  * - ``Measurement.BritishThermalUnitThermochemicalPerPound``
    - ``890``
    - Btuth/lb

      .. _enumitem_Measurement_BritishThermalUnitInternationalTablePerCubicFoot:
  * - ``Measurement.BritishThermalUnitInternationalTablePerCubicFoot``
    - ``891``
    - BtuIT/ft³

      .. _enumitem_Measurement_BritishThermalUnitThermochemicalPerCubicFoot:
  * - ``Measurement.BritishThermalUnitThermochemicalPerCubicFoot``
    - ``892``
    - Btuth/ft³

      .. _enumitem_Measurement_Ampere:
  * - ``Measurement.Ampere``
    - ``893``
    - A

      .. _enumitem_Measurement_Kiloampere:
  * - ``Measurement.Kiloampere``
    - ``894``
    - kA

      .. _enumitem_Measurement_Megaampere:
  * - ``Measurement.Megaampere``
    - ``895``
    - MA

      .. _enumitem_Measurement_Milliampere:
  * - ``Measurement.Milliampere``
    - ``896``
    - mA

      .. _enumitem_Measurement_Microampere:
  * - ``Measurement.Microampere``
    - ``897``
    - µA

      .. _enumitem_Measurement_Nanoampere:
  * - ``Measurement.Nanoampere``
    - ``898``
    - nA

      .. _enumitem_Measurement_Picoampere:
  * - ``Measurement.Picoampere``
    - ``899``
    - pA

      .. _enumitem_Measurement_Biot:
  * - ``Measurement.Biot``
    - ``900``
    - Bi

      .. _enumitem_Measurement_Gilbert:
  * - ``Measurement.Gilbert``
    - ``901``
    - Gi

      .. _enumitem_Measurement_Coulomb:
  * - ``Measurement.Coulomb``
    - ``902``
    - C

      .. _enumitem_Measurement_AmpereSecond:
  * - ``Measurement.AmpereSecond``
    - ``903``
    - A·s

      .. _enumitem_Measurement_AmpereSquaredSecond:
  * - ``Measurement.AmpereSquaredSecond``
    - ``904``
    - A²·s

      .. _enumitem_Measurement_AmpereHour:
  * - ``Measurement.AmpereHour``
    - ``905``
    - A·h

      .. _enumitem_Measurement_KiloampereHourThousandAmpereHour:
  * - ``Measurement.KiloampereHourThousandAmpereHour``
    - ``906``
    - kA·h

      .. _enumitem_Measurement_Megacoulomb:
  * - ``Measurement.Megacoulomb``
    - ``907``
    - MC

      .. _enumitem_Measurement_Millicoulomb:
  * - ``Measurement.Millicoulomb``
    - ``908``
    - mC

      .. _enumitem_Measurement_Kilocoulomb:
  * - ``Measurement.Kilocoulomb``
    - ``909``
    - kC

      .. _enumitem_Measurement_Microcoulomb:
  * - ``Measurement.Microcoulomb``
    - ``910``
    - µC

      .. _enumitem_Measurement_Nanocoulomb:
  * - ``Measurement.Nanocoulomb``
    - ``911``
    - nC

      .. _enumitem_Measurement_Picocoulomb:
  * - ``Measurement.Picocoulomb``
    - ``912``
    - pC

      .. _enumitem_Measurement_MilliampereHour:
  * - ``Measurement.MilliampereHour``
    - ``913``
    - mA·h

      .. _enumitem_Measurement_AmpereMinute:
  * - ``Measurement.AmpereMinute``
    - ``914``
    - A·min

      .. _enumitem_Measurement_Franklin:
  * - ``Measurement.Franklin``
    - ``915``
    - Fr

      .. _enumitem_Measurement_CoulombPerCubicMetre:
  * - ``Measurement.CoulombPerCubicMetre``
    - ``916``
    - C/m³

      .. _enumitem_Measurement_GigacoulombPerCubicMetre:
  * - ``Measurement.GigacoulombPerCubicMetre``
    - ``917``
    - GC/m³

      .. _enumitem_Measurement_CoulombPerCubicMillimetre:
  * - ``Measurement.CoulombPerCubicMillimetre``
    - ``918``
    - C/mm³

      .. _enumitem_Measurement_MegacoulombPerCubicMetre:
  * - ``Measurement.MegacoulombPerCubicMetre``
    - ``919``
    - MC/m³

      .. _enumitem_Measurement_CoulombPerCubicCentimetre:
  * - ``Measurement.CoulombPerCubicCentimetre``
    - ``920``
    - C/cm³

      .. _enumitem_Measurement_KilocoulombPerCubicMetre:
  * - ``Measurement.KilocoulombPerCubicMetre``
    - ``921``
    - kC/m³

      .. _enumitem_Measurement_MillicoulombPerCubicMetre:
  * - ``Measurement.MillicoulombPerCubicMetre``
    - ``922``
    - mC/m³

      .. _enumitem_Measurement_MicrocoulombPerCubicMetre:
  * - ``Measurement.MicrocoulombPerCubicMetre``
    - ``923``
    - µC/m³

      .. _enumitem_Measurement_CoulombPerSquareMetre:
  * - ``Measurement.CoulombPerSquareMetre``
    - ``924``
    - C/m²

      .. _enumitem_Measurement_MegacoulombPerSquareMetre:
  * - ``Measurement.MegacoulombPerSquareMetre``
    - ``925``
    - MC/m²

      .. _enumitem_Measurement_CoulombPerSquareMillimetre:
  * - ``Measurement.CoulombPerSquareMillimetre``
    - ``926``
    - C/mm²

      .. _enumitem_Measurement_CoulombPerSquareCentimetre:
  * - ``Measurement.CoulombPerSquareCentimetre``
    - ``927``
    - C/cm²

      .. _enumitem_Measurement_KilocoulombPerSquareMetre:
  * - ``Measurement.KilocoulombPerSquareMetre``
    - ``928``
    - kC/m²

      .. _enumitem_Measurement_MillicoulombPerSquareMetre:
  * - ``Measurement.MillicoulombPerSquareMetre``
    - ``929``
    - mC/m²

      .. _enumitem_Measurement_MicrocoulombPerSquareMetre:
  * - ``Measurement.MicrocoulombPerSquareMetre``
    - ``930``
    - µC/m²

      .. _enumitem_Measurement_VoltPerMetre:
  * - ``Measurement.VoltPerMetre``
    - ``931``
    - V/m

      .. _enumitem_Measurement_VoltSecondPerMetre:
  * - ``Measurement.VoltSecondPerMetre``
    - ``932``
    - V·s/m

      .. _enumitem_Measurement_VoltSquaredPerKelvinSquared:
  * - ``Measurement.VoltSquaredPerKelvinSquared``
    - ``933``
    - V²/K²

      .. _enumitem_Measurement_VoltPerMillimetre:
  * - ``Measurement.VoltPerMillimetre``
    - ``934``
    - V/mm

      .. _enumitem_Measurement_VoltPerMicrosecond:
  * - ``Measurement.VoltPerMicrosecond``
    - ``935``
    - V/µs

      .. _enumitem_Measurement_MillivoltPerMinute:
  * - ``Measurement.MillivoltPerMinute``
    - ``936``
    - mV/min

      .. _enumitem_Measurement_VoltPerSecond:
  * - ``Measurement.VoltPerSecond``
    - ``937``
    - V/s

      .. _enumitem_Measurement_MegavoltPerMetre:
  * - ``Measurement.MegavoltPerMetre``
    - ``938``
    - MV/m

      .. _enumitem_Measurement_KilovoltPerMetre:
  * - ``Measurement.KilovoltPerMetre``
    - ``939``
    - kV/m

      .. _enumitem_Measurement_VoltPerCentimetre:
  * - ``Measurement.VoltPerCentimetre``
    - ``940``
    - V/cm

      .. _enumitem_Measurement_MillivoltPerMetre:
  * - ``Measurement.MillivoltPerMetre``
    - ``941``
    - mV/m

      .. _enumitem_Measurement_MicrovoltPerMetre:
  * - ``Measurement.MicrovoltPerMetre``
    - ``942``
    - µV/m

      .. _enumitem_Measurement_VoltPerBar:
  * - ``Measurement.VoltPerBar``
    - ``943``
    - V/bar

      .. _enumitem_Measurement_VoltPerPascal:
  * - ``Measurement.VoltPerPascal``
    - ``944``
    - V/Pa

      .. _enumitem_Measurement_VoltPerLitreMinute:
  * - ``Measurement.VoltPerLitreMinute``
    - ``945``
    - V/(l·min)

      .. _enumitem_Measurement_VoltSquareInchPerPoundforce:
  * - ``Measurement.VoltSquareInchPerPoundforce``
    - ``946``
    - V/(lbf/in²)

      .. _enumitem_Measurement_VoltPerInch:
  * - ``Measurement.VoltPerInch``
    - ``947``
    - V/in

      .. _enumitem_Measurement_Volt:
  * - ``Measurement.Volt``
    - ``948``
    - V

      .. _enumitem_Measurement_Megavolt:
  * - ``Measurement.Megavolt``
    - ``949``
    - MV

      .. _enumitem_Measurement_Kilovolt:
  * - ``Measurement.Kilovolt``
    - ``950``
    - kV

      .. _enumitem_Measurement_Millivolt:
  * - ``Measurement.Millivolt``
    - ``951``
    - mV

      .. _enumitem_Measurement_Microvolt:
  * - ``Measurement.Microvolt``
    - ``952``
    - µV

      .. _enumitem_Measurement_Picovolt:
  * - ``Measurement.Picovolt``
    - ``953``
    - pV

      .. _enumitem_Measurement_Farad:
  * - ``Measurement.Farad``
    - ``954``
    - F

      .. _enumitem_Measurement_Attofarad:
  * - ``Measurement.Attofarad``
    - ``955``
    - aF

      .. _enumitem_Measurement_Millifarad:
  * - ``Measurement.Millifarad``
    - ``956``
    - mF

      .. _enumitem_Measurement_Microfarad:
  * - ``Measurement.Microfarad``
    - ``957``
    - µF

      .. _enumitem_Measurement_Nanofarad:
  * - ``Measurement.Nanofarad``
    - ``958``
    - nF

      .. _enumitem_Measurement_Picofarad:
  * - ``Measurement.Picofarad``
    - ``959``
    - pF

      .. _enumitem_Measurement_Kilofarad:
  * - ``Measurement.Kilofarad``
    - ``960``
    - kF

      .. _enumitem_Measurement_FaradPerMetre:
  * - ``Measurement.FaradPerMetre``
    - ``961``
    - F/m

      .. _enumitem_Measurement_MicrofaradPerKilometre:
  * - ``Measurement.MicrofaradPerKilometre``
    - ``962``
    - µF/km

      .. _enumitem_Measurement_FaradPerKilometre:
  * - ``Measurement.FaradPerKilometre``
    - ``963``
    - F/km

      .. _enumitem_Measurement_MicrofaradPerMetre:
  * - ``Measurement.MicrofaradPerMetre``
    - ``964``
    - µF/m

      .. _enumitem_Measurement_NanofaradPerMetre:
  * - ``Measurement.NanofaradPerMetre``
    - ``965``
    - nF/m

      .. _enumitem_Measurement_PicofaradPerMetre:
  * - ``Measurement.PicofaradPerMetre``
    - ``966``
    - pF/m

      .. _enumitem_Measurement_CoulombMetre:
  * - ``Measurement.CoulombMetre``
    - ``967``
    - C·m

      .. _enumitem_Measurement_AmperePerSquareMetre:
  * - ``Measurement.AmperePerSquareMetre``
    - ``968``
    - A/m²

      .. _enumitem_Measurement_AmperePerKilogram:
  * - ``Measurement.AmperePerKilogram``
    - ``969``
    - A/kg

      .. _enumitem_Measurement_MegaamperePerSquareMetre:
  * - ``Measurement.MegaamperePerSquareMetre``
    - ``970``
    - MA/m²

      .. _enumitem_Measurement_AmperePerSquareMillimetre:
  * - ``Measurement.AmperePerSquareMillimetre``
    - ``971``
    - A/mm²

      .. _enumitem_Measurement_AmperePerSquareCentimetre:
  * - ``Measurement.AmperePerSquareCentimetre``
    - ``972``
    - A/cm²

      .. _enumitem_Measurement_KiloamperePerSquareMetre:
  * - ``Measurement.KiloamperePerSquareMetre``
    - ``973``
    - kA/m²

      .. _enumitem_Measurement_MilliamperePerLitreMinute:
  * - ``Measurement.MilliamperePerLitreMinute``
    - ``974``
    - mA/(l·min)

      .. _enumitem_Measurement_AmperePerPascal:
  * - ``Measurement.AmperePerPascal``
    - ``975``
    - A/Pa

      .. _enumitem_Measurement_MilliamperePerPoundforcePerSquareInch:
  * - ``Measurement.MilliamperePerPoundforcePerSquareInch``
    - ``976``
    - mA/(lbf/in²)

      .. _enumitem_Measurement_MilliamperePerBar:
  * - ``Measurement.MilliamperePerBar``
    - ``977``
    - mA/bar

      .. _enumitem_Measurement_AmperePerMetre:
  * - ``Measurement.AmperePerMetre``
    - ``978``
    - A/m

      .. _enumitem_Measurement_KiloamperePerMetre:
  * - ``Measurement.KiloamperePerMetre``
    - ``979``
    - kA/m

      .. _enumitem_Measurement_AmperePerMillimetre:
  * - ``Measurement.AmperePerMillimetre``
    - ``980``
    - A/mm

      .. _enumitem_Measurement_AmperePerCentimetre:
  * - ``Measurement.AmperePerCentimetre``
    - ``981``
    - A/cm

      .. _enumitem_Measurement_MilliamperePerMillimetre:
  * - ``Measurement.MilliamperePerMillimetre``
    - ``982``
    - mA/mm

      .. _enumitem_Measurement_MilliamperePerInch:
  * - ``Measurement.MilliamperePerInch``
    - ``983``
    - mA/in

      .. _enumitem_Measurement_CoulombPerMetre:
  * - ``Measurement.CoulombPerMetre``
    - ``984``
    - C/m

      .. _enumitem_Measurement_Tesla:
  * - ``Measurement.Tesla``
    - ``985``
    - T

      .. _enumitem_Measurement_Millitesla:
  * - ``Measurement.Millitesla``
    - ``986``
    - mT

      .. _enumitem_Measurement_Microtesla:
  * - ``Measurement.Microtesla``
    - ``987``
    - µT

      .. _enumitem_Measurement_Nanotesla:
  * - ``Measurement.Nanotesla``
    - ``988``
    - nT

      .. _enumitem_Measurement_Kilotesla:
  * - ``Measurement.Kilotesla``
    - ``989``
    - kT

      .. _enumitem_Measurement_Gamma:
  * - ``Measurement.Gamma``
    - ``990``
    - γ

      .. _enumitem_Measurement_Weber:
  * - ``Measurement.Weber``
    - ``991``
    - Wb

      .. _enumitem_Measurement_Milliweber:
  * - ``Measurement.Milliweber``
    - ``992``
    - mWb

      .. _enumitem_Measurement_Kiloweber:
  * - ``Measurement.Kiloweber``
    - ``993``
    - kWb

      .. _enumitem_Measurement_WeberPerMetre:
  * - ``Measurement.WeberPerMetre``
    - ``994``
    - Wb/m

      .. _enumitem_Measurement_KiloweberPerMetre:
  * - ``Measurement.KiloweberPerMetre``
    - ``995``
    - kWb/m

      .. _enumitem_Measurement_WeberPerMillimetre:
  * - ``Measurement.WeberPerMillimetre``
    - ``996``
    - Wb/mm

      .. _enumitem_Measurement_Henry:
  * - ``Measurement.Henry``
    - ``997``
    - H

      .. _enumitem_Measurement_Millihenry:
  * - ``Measurement.Millihenry``
    - ``998``
    - mH

      .. _enumitem_Measurement_Microhenry:
  * - ``Measurement.Microhenry``
    - ``999``
    - µH

      .. _enumitem_Measurement_Nanohenry:
  * - ``Measurement.Nanohenry``
    - ``1000``
    - nH

      .. _enumitem_Measurement_Picohenry:
  * - ``Measurement.Picohenry``
    - ``1001``
    - pH

      .. _enumitem_Measurement_HenryPerKiloohm:
  * - ``Measurement.HenryPerKiloohm``
    - ``1002``
    - H/kΩ

      .. _enumitem_Measurement_HenryPerOhm:
  * - ``Measurement.HenryPerOhm``
    - ``1003``
    - H/Ω

      .. _enumitem_Measurement_MicrohenryPerKiloohm:
  * - ``Measurement.MicrohenryPerKiloohm``
    - ``1004``
    - µH/kΩ

      .. _enumitem_Measurement_MicrohenryPerOhm:
  * - ``Measurement.MicrohenryPerOhm``
    - ``1005``
    - µH/Ω

      .. _enumitem_Measurement_MillihenryPerKiloohm:
  * - ``Measurement.MillihenryPerKiloohm``
    - ``1006``
    - mH/kΩ

      .. _enumitem_Measurement_MillihenryPerOhm:
  * - ``Measurement.MillihenryPerOhm``
    - ``1007``
    - mH/Ω

      .. _enumitem_Measurement_Kilohenry:
  * - ``Measurement.Kilohenry``
    - ``1008``
    - kH

      .. _enumitem_Measurement_HenryPerMetre:
  * - ``Measurement.HenryPerMetre``
    - ``1009``
    - H/m

      .. _enumitem_Measurement_MicrohenryPerMetre:
  * - ``Measurement.MicrohenryPerMetre``
    - ``1010``
    - µH/m

      .. _enumitem_Measurement_NanohenryPerMetre:
  * - ``Measurement.NanohenryPerMetre``
    - ``1011``
    - nH/m

      .. _enumitem_Measurement_AmpereSquareMetre:
  * - ``Measurement.AmpereSquareMetre``
    - ``1012``
    - A·m²

      .. _enumitem_Measurement_JoulePerCubicMetre:
  * - ``Measurement.JoulePerCubicMetre``
    - ``1013``
    - J/m³

      .. _enumitem_Measurement_Ohm:
  * - ``Measurement.Ohm``
    - ``1014``
    - Ω

      .. _enumitem_Measurement_Gigaohm:
  * - ``Measurement.Gigaohm``
    - ``1015``
    - GΩ

      .. _enumitem_Measurement_Megaohm:
  * - ``Measurement.Megaohm``
    - ``1016``
    - MΩ

      .. _enumitem_Measurement_Teraohm:
  * - ``Measurement.Teraohm``
    - ``1017``
    - TΩ

      .. _enumitem_Measurement_Kiloohm:
  * - ``Measurement.Kiloohm``
    - ``1018``
    - kΩ

      .. _enumitem_Measurement_Milliohm:
  * - ``Measurement.Milliohm``
    - ``1019``
    - mΩ

      .. _enumitem_Measurement_Microohm:
  * - ``Measurement.Microohm``
    - ``1020``
    - µΩ

      .. _enumitem_Measurement_Nanoohm:
  * - ``Measurement.Nanoohm``
    - ``1021``
    - nΩ

      .. _enumitem_Measurement_GigaohmPerMetre:
  * - ``Measurement.GigaohmPerMetre``
    - ``1022``
    - GΩ/m

      .. _enumitem_Measurement_Siemens:
  * - ``Measurement.Siemens``
    - ``1023``
    - S

      .. _enumitem_Measurement_Kilosiemens:
  * - ``Measurement.Kilosiemens``
    - ``1024``
    - kS

      .. _enumitem_Measurement_Millisiemens:
  * - ``Measurement.Millisiemens``
    - ``1025``
    - mS

      .. _enumitem_Measurement_Microsiemens:
  * - ``Measurement.Microsiemens``
    - ``1026``
    - µS

      .. _enumitem_Measurement_MicrosiemensPerCentimetre:
  * - ``Measurement.MicrosiemensPerCentimetre``
    - ``1027``
    - µS/cm

      .. _enumitem_Measurement_MicrosiemensPerMetre:
  * - ``Measurement.MicrosiemensPerMetre``
    - ``1028``
    - µS/m

      .. _enumitem_Measurement_Picosiemens:
  * - ``Measurement.Picosiemens``
    - ``1029``
    - pS

      .. _enumitem_Measurement_OhmMetre:
  * - ``Measurement.OhmMetre``
    - ``1030``
    - Ω·m

      .. _enumitem_Measurement_GigaohmMetre:
  * - ``Measurement.GigaohmMetre``
    - ``1031``
    - GΩ·m

      .. _enumitem_Measurement_MegaohmMetre:
  * - ``Measurement.MegaohmMetre``
    - ``1032``
    - MΩ·m

      .. _enumitem_Measurement_MegaohmKilometre:
  * - ``Measurement.MegaohmKilometre``
    - ``1033``
    - MΩ·km

      .. _enumitem_Measurement_KiloohmMetre:
  * - ``Measurement.KiloohmMetre``
    - ``1034``
    - kΩ·m

      .. _enumitem_Measurement_OhmCentimetre:
  * - ``Measurement.OhmCentimetre``
    - ``1035``
    - Ω·cm

      .. _enumitem_Measurement_MilliohmMetre:
  * - ``Measurement.MilliohmMetre``
    - ``1036``
    - mΩ·m

      .. _enumitem_Measurement_MicroohmMetre:
  * - ``Measurement.MicroohmMetre``
    - ``1037``
    - µΩ·m

      .. _enumitem_Measurement_NanoohmMetre:
  * - ``Measurement.NanoohmMetre``
    - ``1038``
    - nΩ·m

      .. _enumitem_Measurement_OhmKilometre:
  * - ``Measurement.OhmKilometre``
    - ``1039``
    - Ω·km

      .. _enumitem_Measurement_OhmCircularmilPerFoot:
  * - ``Measurement.OhmCircularmilPerFoot``
    - ``1040``
    - Ω·cmil/ft 

      .. _enumitem_Measurement_OhmPerKilometre:
  * - ``Measurement.OhmPerKilometre``
    - ``1041``
    - Ω/km

      .. _enumitem_Measurement_OhmPerMetre:
  * - ``Measurement.OhmPerMetre``
    - ``1042``
    - Ω/m

      .. _enumitem_Measurement_MegaohmPerMetre:
  * - ``Measurement.MegaohmPerMetre``
    - ``1043``
    - MΩ/m

      .. _enumitem_Measurement_MilliohmPerMetre:
  * - ``Measurement.MilliohmPerMetre``
    - ``1044``
    - mΩ/m

      .. _enumitem_Measurement_MegaohmPerKilometre:
  * - ``Measurement.MegaohmPerKilometre``
    - ``1045``
    - MΩ/km

      .. _enumitem_Measurement_OhmPerMileStatuteMile:
  * - ``Measurement.OhmPerMileStatuteMile``
    - ``1046``
    - Ω/mi

      .. _enumitem_Measurement_SiemensPerMetre:
  * - ``Measurement.SiemensPerMetre``
    - ``1047``
    - S/m

      .. _enumitem_Measurement_SiemensPerCentimetre:
  * - ``Measurement.SiemensPerCentimetre``
    - ``1048``
    - S/cm

      .. _enumitem_Measurement_MillisiemensPerCentimetre:
  * - ``Measurement.MillisiemensPerCentimetre``
    - ``1049``
    - mS/cm

      .. _enumitem_Measurement_MegasiemensPerMetre:
  * - ``Measurement.MegasiemensPerMetre``
    - ``1050``
    - MS/m

      .. _enumitem_Measurement_KilosiemensPerMetre:
  * - ``Measurement.KilosiemensPerMetre``
    - ``1051``
    - kS/m

      .. _enumitem_Measurement_NanosiemensPerMetre:
  * - ``Measurement.NanosiemensPerMetre``
    - ``1052``
    - nS/m

      .. _enumitem_Measurement_NanosiemensPerCentimetre:
  * - ``Measurement.NanosiemensPerCentimetre``
    - ``1053``
    - nS/cm

      .. _enumitem_Measurement_PicosiemensPerMetre:
  * - ``Measurement.PicosiemensPerMetre``
    - ``1054``
    - pS/m

      .. _enumitem_Measurement_ReciprocalHenry:
  * - ``Measurement.ReciprocalHenry``
    - ``1055``
    - H⁻¹

      .. _enumitem_Measurement_JoulePerSecond:
  * - ``Measurement.JoulePerSecond``
    - ``1056``
    - J/s

      .. _enumitem_Measurement_Terawatt:
  * - ``Measurement.Terawatt``
    - ``1057``
    - TW

      .. _enumitem_Measurement_JoulePerMinute:
  * - ``Measurement.JoulePerMinute``
    - ``1058``
    - J/min

      .. _enumitem_Measurement_JoulePerHour:
  * - ``Measurement.JoulePerHour``
    - ``1059``
    - J/h

      .. _enumitem_Measurement_JoulePerDay:
  * - ``Measurement.JoulePerDay``
    - ``1060``
    - J/d

      .. _enumitem_Measurement_KilojoulePerSecond:
  * - ``Measurement.KilojoulePerSecond``
    - ``1061``
    - kJ/s

      .. _enumitem_Measurement_KilojoulePerMinute:
  * - ``Measurement.KilojoulePerMinute``
    - ``1062``
    - kJ/min

      .. _enumitem_Measurement_KilojoulePerHour:
  * - ``Measurement.KilojoulePerHour``
    - ``1063``
    - kJ/h

      .. _enumitem_Measurement_KilojoulePerDay:
  * - ``Measurement.KilojoulePerDay``
    - ``1064``
    - kJ/d

      .. _enumitem_Measurement_HorsepowerElectric:
  * - ``Measurement.HorsepowerElectric``
    - ``1065``
    - electric hp

      .. _enumitem_Measurement_Nanowatt:
  * - ``Measurement.Nanowatt``
    - ``1066``
    - nW

      .. _enumitem_Measurement_Picowatt:
  * - ``Measurement.Picowatt``
    - ``1067``
    - pW

      .. _enumitem_Measurement_VoltAmpere:
  * - ``Measurement.VoltAmpere``
    - ``1068``
    - V·A

      .. _enumitem_Measurement_MegavoltAmpere:
  * - ``Measurement.MegavoltAmpere``
    - ``1069``
    - MV·A

      .. _enumitem_Measurement_KilovoltAmpere:
  * - ``Measurement.KilovoltAmpere``
    - ``1070``
    - kV·A

      .. _enumitem_Measurement_MillivoltAmpere:
  * - ``Measurement.MillivoltAmpere``
    - ``1071``
    - mV·A

      .. _enumitem_Measurement_Var:
  * - ``Measurement.Var``
    - ``1072``
    - var

      .. _enumitem_Measurement_Kilovar:
  * - ``Measurement.Kilovar``
    - ``1073``
    - kvar

      .. _enumitem_Measurement_Megavar:
  * - ``Measurement.Megavar``
    - ``1074``
    - kvar

      .. _enumitem_Measurement_ReciprocalJoule:
  * - ``Measurement.ReciprocalJoule``
    - ``1075``
    - 1/J

      .. _enumitem_Measurement_ReciprocalVoltAmpereReciprocalSecond:
  * - ``Measurement.ReciprocalVoltAmpereReciprocalSecond``
    - ``1076``
    - 1/(V·A·s)

      .. _enumitem_Measurement_KilohertzMetre:
  * - ``Measurement.KilohertzMetre``
    - ``1077``
    - kHz·m

      .. _enumitem_Measurement_GigahertzMetre:
  * - ``Measurement.GigahertzMetre``
    - ``1078``
    - GHz·m

      .. _enumitem_Measurement_MegahertzMetre:
  * - ``Measurement.MegahertzMetre``
    - ``1079``
    - MHz·m

      .. _enumitem_Measurement_ReciprocalKilovoltAmpereReciprocalHour:
  * - ``Measurement.ReciprocalKilovoltAmpereReciprocalHour``
    - ``1080``
    - 1/kVAh

      .. _enumitem_Measurement_HertzMetre:
  * - ``Measurement.HertzMetre``
    - ``1081``
    - Hz·m

      .. _enumitem_Measurement_MegahertzKilometre:
  * - ``Measurement.MegahertzKilometre``
    - ``1082``
    - MHz·km

      .. _enumitem_Measurement_RadianPerMetre:
  * - ``Measurement.RadianPerMetre``
    - ``1083``
    - rad/m

      .. _enumitem_Measurement_MegajoulePerCubicMetre:
  * - ``Measurement.MegajoulePerCubicMetre``
    - ``1084``
    - MJ/m³

      .. _enumitem_Measurement_JoulePerMetreToTheFourthPower:
  * - ``Measurement.JoulePerMetreToTheFourthPower``
    - ``1085``
    - J/m⁴

      .. _enumitem_Measurement_JoulePerSquareMetre:
  * - ``Measurement.JoulePerSquareMetre``
    - ``1086``
    - J/m²

      .. _enumitem_Measurement_ReciprocalSecondPerSteradian:
  * - ``Measurement.ReciprocalSecondPerSteradian``
    - ``1087``
    - s⁻¹/sr

      .. _enumitem_Measurement_ReciprocalSecondPerSteradianMetreSquared:
  * - ``Measurement.ReciprocalSecondPerSteradianMetreSquared``
    - ``1088``
    - s⁻¹/(sr·m²)

      .. _enumitem_Measurement_ReciprocalSecondPerMetreSquared:
  * - ``Measurement.ReciprocalSecondPerMetreSquared``
    - ``1089``
    - s⁻¹/m²

      .. _enumitem_Measurement_ReciprocalSquareMetre:
  * - ``Measurement.ReciprocalSquareMetre``
    - ``1090``
    - m⁻²

      .. _enumitem_Measurement_WattPerCubicMetre:
  * - ``Measurement.WattPerCubicMetre``
    - ``1091``
    - W/m³

      .. _enumitem_Measurement_WattPerMetre:
  * - ``Measurement.WattPerMetre``
    - ``1092``
    - W/m

      .. _enumitem_Measurement_JoulePerSquareCentimetre:
  * - ``Measurement.JoulePerSquareCentimetre``
    - ``1093``
    - J/cm²

      .. _enumitem_Measurement_BritishThermalUnitInternationalTablePerSquareFoot:
  * - ``Measurement.BritishThermalUnitInternationalTablePerSquareFoot``
    - ``1094``
    - BtuIT/ft²

      .. _enumitem_Measurement_BritishThermalUnitThermochemicalPerSquareFoot:
  * - ``Measurement.BritishThermalUnitThermochemicalPerSquareFoot``
    - ``1095``
    - Btuth/ft²

      .. _enumitem_Measurement_CalorieThermochemicalPerSquareCentimetre:
  * - ``Measurement.CalorieThermochemicalPerSquareCentimetre``
    - ``1096``
    - calth/cm²

      .. _enumitem_Measurement_Langley:
  * - ``Measurement.Langley``
    - ``1097``
    - Ly

      .. _enumitem_Measurement_WattPerSteradian:
  * - ``Measurement.WattPerSteradian``
    - ``1098``
    - W/sr

      .. _enumitem_Measurement_WattPerSteradianSquareMetre:
  * - ``Measurement.WattPerSteradianSquareMetre``
    - ``1099``
    - W/(sr·m²)

      .. _enumitem_Measurement_WattPerSquareMetreKelvinToTheFourthPower:
  * - ``Measurement.WattPerSquareMetreKelvinToTheFourthPower``
    - ``1100``
    - W/(m²·K⁴)

      .. _enumitem_Measurement_MetreKelvin:
  * - ``Measurement.MetreKelvin``
    - ``1101``
    - m·K

      .. _enumitem_Measurement_Candela:
  * - ``Measurement.Candela``
    - ``1102``
    - cd

      .. _enumitem_Measurement_Kilocandela:
  * - ``Measurement.Kilocandela``
    - ``1103``
    - kcd

      .. _enumitem_Measurement_Millicandela:
  * - ``Measurement.Millicandela``
    - ``1104``
    - mcd

      .. _enumitem_Measurement_HefnerKerze:
  * - ``Measurement.HefnerKerze``
    - ``1105``
    - HK

      .. _enumitem_Measurement_InternationalCandle:
  * - ``Measurement.InternationalCandle``
    - ``1106``
    - IK

      .. _enumitem_Measurement_Lumen:
  * - ``Measurement.Lumen``
    - ``1107``
    - lm

      .. _enumitem_Measurement_LumenSecond:
  * - ``Measurement.LumenSecond``
    - ``1108``
    - lm·s

      .. _enumitem_Measurement_LumenHour:
  * - ``Measurement.LumenHour``
    - ``1109``
    - lm·h

      .. _enumitem_Measurement_CandelaPerSquareMetre:
  * - ``Measurement.CandelaPerSquareMetre``
    - ``1110``
    - cd/m²

      .. _enumitem_Measurement_CandelaPerSquareInch:
  * - ``Measurement.CandelaPerSquareInch``
    - ``1111``
    - cd/in²

      .. _enumitem_Measurement_Footlambert:
  * - ``Measurement.Footlambert``
    - ``1112``
    - ftL

      .. _enumitem_Measurement_Lambert:
  * - ``Measurement.Lambert``
    - ``1113``
    - Lb

      .. _enumitem_Measurement_Stilb:
  * - ``Measurement.Stilb``
    - ``1114``
    - sb

      .. _enumitem_Measurement_CandelaPerSquareFoot:
  * - ``Measurement.CandelaPerSquareFoot``
    - ``1115``
    - cd/ft²

      .. _enumitem_Measurement_LumenPerSquareMetre:
  * - ``Measurement.LumenPerSquareMetre``
    - ``1116``
    - lm/m²

      .. _enumitem_Measurement_Lux:
  * - ``Measurement.Lux``
    - ``1117``
    - lx

      .. _enumitem_Measurement_Kilolux:
  * - ``Measurement.Kilolux``
    - ``1118``
    - klx

      .. _enumitem_Measurement_LumenPerSquareFoot:
  * - ``Measurement.LumenPerSquareFoot``
    - ``1119``
    - lm/ft²

      .. _enumitem_Measurement_Phot:
  * - ``Measurement.Phot``
    - ``1120``
    - ph

      .. _enumitem_Measurement_Footcandle:
  * - ``Measurement.Footcandle``
    - ``1121``
    - ftc

      .. _enumitem_Measurement_LuxSecond:
  * - ``Measurement.LuxSecond``
    - ``1122``
    - lx·s

      .. _enumitem_Measurement_LuxHour:
  * - ``Measurement.LuxHour``
    - ``1123``
    - lx·h

      .. _enumitem_Measurement_LumenPerWatt:
  * - ``Measurement.LumenPerWatt``
    - ``1124``
    - lm/W

      .. _enumitem_Measurement_SquareMetrePerMole:
  * - ``Measurement.SquareMetrePerMole``
    - ``1125``
    - m²/mol

      .. _enumitem_Measurement_MilliwattPerSquareMetre:
  * - ``Measurement.MilliwattPerSquareMetre``
    - ``1126``
    - mW/m²

      .. _enumitem_Measurement_MicrowattPerSquareMetre:
  * - ``Measurement.MicrowattPerSquareMetre``
    - ``1127``
    - µW/m²

      .. _enumitem_Measurement_PicowattPerSquareMetre:
  * - ``Measurement.PicowattPerSquareMetre``
    - ``1128``
    - pW/m²

      .. _enumitem_Measurement_PascalSecondPerMetre:
  * - ``Measurement.PascalSecondPerMetre``
    - ``1129``
    - Pa· s/m

      .. _enumitem_Measurement_PascalSecondPerCubicMetre:
  * - ``Measurement.PascalSecondPerCubicMetre``
    - ``1130``
    - Pa·s/m³

      .. _enumitem_Measurement_PascalSecondPerLitre:
  * - ``Measurement.PascalSecondPerLitre``
    - ``1131``
    - Pa·s/l

      .. _enumitem_Measurement_NewtonSecondPerMetre:
  * - ``Measurement.NewtonSecondPerMetre``
    - ``1132``
    - N·s/m

      .. _enumitem_Measurement_BelPerMetre:
  * - ``Measurement.BelPerMetre``
    - ``1133``
    - B/m

      .. _enumitem_Measurement_DecibelPerKilometre:
  * - ``Measurement.DecibelPerKilometre``
    - ``1134``
    - dB/km

      .. _enumitem_Measurement_DecibelPerMetre:
  * - ``Measurement.DecibelPerMetre``
    - ``1135``
    - dB/m

      .. _enumitem_Measurement_PascalSquaredSecond:
  * - ``Measurement.PascalSquaredSecond``
    - ``1136``
    - Pa²·s

      .. _enumitem_Measurement_DecadeLogarithmic:
  * - ``Measurement.DecadeLogarithmic``
    - ``1137``
    - dec

      .. _enumitem_Measurement_Mole:
  * - ``Measurement.Mole``
    - ``1138``
    - mol

      .. _enumitem_Measurement_Kilomole:
  * - ``Measurement.Kilomole``
    - ``1139``
    - kmol

      .. _enumitem_Measurement_Millimole:
  * - ``Measurement.Millimole``
    - ``1140``
    - mmol

      .. _enumitem_Measurement_Micromole:
  * - ``Measurement.Micromole``
    - ``1141``
    - µmol

      .. _enumitem_Measurement_PoundMole:
  * - ``Measurement.PoundMole``
    - ``1142``
    - lbmol

      .. _enumitem_Measurement_ReciprocalMole:
  * - ``Measurement.ReciprocalMole``
    - ``1143``
    - mol⁻¹

      .. _enumitem_Measurement_KilogramPerMole:
  * - ``Measurement.KilogramPerMole``
    - ``1144``
    - kg/mol

      .. _enumitem_Measurement_GramPerMole:
  * - ``Measurement.GramPerMole``
    - ``1145``
    - g/mol

      .. _enumitem_Measurement_CubicMetrePerMole:
  * - ``Measurement.CubicMetrePerMole``
    - ``1146``
    - m³/mol

      .. _enumitem_Measurement_CubicDecimetrePerMole:
  * - ``Measurement.CubicDecimetrePerMole``
    - ``1147``
    - dm³/mol

      .. _enumitem_Measurement_CubicCentimetrePerMole:
  * - ``Measurement.CubicCentimetrePerMole``
    - ``1148``
    - cm³/mol

      .. _enumitem_Measurement_LitrePerMole:
  * - ``Measurement.LitrePerMole``
    - ``1149``
    - l/mol

      .. _enumitem_Measurement_JoulePerMole:
  * - ``Measurement.JoulePerMole``
    - ``1150``
    - J/mol

      .. _enumitem_Measurement_KilojoulePerMole:
  * - ``Measurement.KilojoulePerMole``
    - ``1151``
    - kJ/mol

      .. _enumitem_Measurement_JoulePerMoleKelvin:
  * - ``Measurement.JoulePerMoleKelvin``
    - ``1152``
    - J/(mol·K)

      .. _enumitem_Measurement_ReciprocalCubicMetre:
  * - ``Measurement.ReciprocalCubicMetre``
    - ``1153``
    - m⁻³

      .. _enumitem_Measurement_ReciprocalCubicCentimetre:
  * - ``Measurement.ReciprocalCubicCentimetre``
    - ``1154``
    - cm⁻³

      .. _enumitem_Measurement_ReciprocalCubicMillimetre:
  * - ``Measurement.ReciprocalCubicMillimetre``
    - ``1155``
    - 1/mm³

      .. _enumitem_Measurement_ReciprocalCubicFoot:
  * - ``Measurement.ReciprocalCubicFoot``
    - ``1156``
    - 1/ft³

      .. _enumitem_Measurement_ReciprocalCubicInch:
  * - ``Measurement.ReciprocalCubicInch``
    - ``1157``
    - 1/in³

      .. _enumitem_Measurement_ReciprocalLitre:
  * - ``Measurement.ReciprocalLitre``
    - ``1158``
    - 1/l

      .. _enumitem_Measurement_ReciprocalCubicYard:
  * - ``Measurement.ReciprocalCubicYard``
    - ``1159``
    - 1/yd³

      .. _enumitem_Measurement_MolePerCubicMetre:
  * - ``Measurement.MolePerCubicMetre``
    - ``1160``
    - mol/m³

      .. _enumitem_Measurement_MolePerLitre:
  * - ``Measurement.MolePerLitre``
    - ``1161``
    - mol/l

      .. _enumitem_Measurement_MolePerCubicDecimetre:
  * - ``Measurement.MolePerCubicDecimetre``
    - ``1162``
    - mol/dm³

      .. _enumitem_Measurement_KilomolePerCubicMetre:
  * - ``Measurement.KilomolePerCubicMetre``
    - ``1163``
    - kmol/m³

      .. _enumitem_Measurement_MolePerSecond:
  * - ``Measurement.MolePerSecond``
    - ``1164``
    - mol/s

      .. _enumitem_Measurement_MillimolePerLitre:
  * - ``Measurement.MillimolePerLitre``
    - ``1165``
    - mmol/l

      .. _enumitem_Measurement_MolPerKilogramPascal:
  * - ``Measurement.MolPerKilogramPascal``
    - ``1166``
    - (mol/kg)/Pa

      .. _enumitem_Measurement_MolPerCubicMetrePascal:
  * - ``Measurement.MolPerCubicMetrePascal``
    - ``1167``
    - (mol/m³)/Pa

      .. _enumitem_Measurement_KilomolePerCubicMetreKelvin:
  * - ``Measurement.KilomolePerCubicMetreKelvin``
    - ``1168``
    - (kmol/m³)/K

      .. _enumitem_Measurement_KilomolePerCubicMetreBar:
  * - ``Measurement.KilomolePerCubicMetreBar``
    - ``1169``
    - (kmol/m³)/bar

      .. _enumitem_Measurement_ReciprocalPsi:
  * - ``Measurement.ReciprocalPsi``
    - ``1170``
    - 1/psi

      .. _enumitem_Measurement_MolePerKilogramKelvin:
  * - ``Measurement.MolePerKilogramKelvin``
    - ``1171``
    - (mol/kg)/K

      .. _enumitem_Measurement_MolePerKilogramBar:
  * - ``Measurement.MolePerKilogramBar``
    - ``1172``
    - (mol/kg)/bar

      .. _enumitem_Measurement_MolePerLitreKelvin:
  * - ``Measurement.MolePerLitreKelvin``
    - ``1173``
    - (mol/l)/K

      .. _enumitem_Measurement_MolePerLitreBar:
  * - ``Measurement.MolePerLitreBar``
    - ``1174``
    - (mol/l)/bar

      .. _enumitem_Measurement_MolePerCubicMetreKelvin:
  * - ``Measurement.MolePerCubicMetreKelvin``
    - ``1175``
    - (mol/m³)/K

      .. _enumitem_Measurement_MolePerCubicMetreBar:
  * - ``Measurement.MolePerCubicMetreBar``
    - ``1176``
    - (mol/m³)/bar

      .. _enumitem_Measurement_MolePerKilogram:
  * - ``Measurement.MolePerKilogram``
    - ``1177``
    - mol/kg

      .. _enumitem_Measurement_SecondPerCubicMetre:
  * - ``Measurement.SecondPerCubicMetre``
    - ``1178``
    - s/m³

      .. _enumitem_Measurement_MillimolePerKilogram:
  * - ``Measurement.MillimolePerKilogram``
    - ``1179``
    - mmol/kg

      .. _enumitem_Measurement_MillimolePerGram:
  * - ``Measurement.MillimolePerGram``
    - ``1180``
    - mmol/g

      .. _enumitem_Measurement_KilomolePerKilogram:
  * - ``Measurement.KilomolePerKilogram``
    - ``1181``
    - kmol/kg

      .. _enumitem_Measurement_PoundMolePerPound:
  * - ``Measurement.PoundMolePerPound``
    - ``1182``
    - lbmol/lb

      .. _enumitem_Measurement_Katal:
  * - ``Measurement.Katal``
    - ``1183``
    - kat

      .. _enumitem_Measurement_KilomolePerSecond:
  * - ``Measurement.KilomolePerSecond``
    - ``1184``
    - kmol/s

      .. _enumitem_Measurement_PoundMolePerSecond:
  * - ``Measurement.PoundMolePerSecond``
    - ``1185``
    - lbmol/s

      .. _enumitem_Measurement_PoundMolePerMinute:
  * - ``Measurement.PoundMolePerMinute``
    - ``1186``
    - lbmol/h

      .. _enumitem_Measurement_UnifiedAtomicMassUnit:
  * - ``Measurement.UnifiedAtomicMassUnit``
    - ``1187``
    - u

      .. _enumitem_Measurement_CoulombMetreSquaredPerVolt:
  * - ``Measurement.CoulombMetreSquaredPerVolt``
    - ``1188``
    - C·m²/V

      .. _enumitem_Measurement_CoulombPerMole:
  * - ``Measurement.CoulombPerMole``
    - ``1189``
    - C/mol

      .. _enumitem_Measurement_SiemensSquareMetrePerMole:
  * - ``Measurement.SiemensSquareMetrePerMole``
    - ``1190``
    - S·m²/mol

      .. _enumitem_Measurement_KilomolePerHour:
  * - ``Measurement.KilomolePerHour``
    - ``1191``
    - kmol/h

      .. _enumitem_Measurement_KilomolePerMinute:
  * - ``Measurement.KilomolePerMinute``
    - ``1192``
    - kmol/min

      .. _enumitem_Measurement_MolePerHour:
  * - ``Measurement.MolePerHour``
    - ``1193``
    - mol/h

      .. _enumitem_Measurement_MolePerMinute:
  * - ``Measurement.MolePerMinute``
    - ``1194``
    - mol/min

      .. _enumitem_Measurement_RadianSquareMetrePerMole:
  * - ``Measurement.RadianSquareMetrePerMole``
    - ``1195``
    - rad·m²/mol

      .. _enumitem_Measurement_RadianSquareMetrePerKilogram:
  * - ``Measurement.RadianSquareMetrePerKilogram``
    - ``1196``
    - rad·m²/kg

      .. _enumitem_Measurement_NewtonSquareMetrePerAmpere:
  * - ``Measurement.NewtonSquareMetrePerAmpere``
    - ``1197``
    - N·m²/A

      .. _enumitem_Measurement_WeberMetre:
  * - ``Measurement.WeberMetre``
    - ``1198``
    - Wb·m

      .. _enumitem_Measurement_JouleSecond:
  * - ``Measurement.JouleSecond``
    - ``1199``
    - J·s

      .. _enumitem_Measurement_AmpereSquareMetrePerJouleSecond:
  * - ``Measurement.AmpereSquareMetrePerJouleSecond``
    - ``1200``
    - A·m²/(J·s)

      .. _enumitem_Measurement_Curie:
  * - ``Measurement.Curie``
    - ``1201``
    - Ci

      .. _enumitem_Measurement_Millicurie:
  * - ``Measurement.Millicurie``
    - ``1202``
    - mCi

      .. _enumitem_Measurement_Microcurie:
  * - ``Measurement.Microcurie``
    - ``1203``
    - µCi

      .. _enumitem_Measurement_Kilocurie:
  * - ``Measurement.Kilocurie``
    - ``1204``
    - kCi

      .. _enumitem_Measurement_Becquerel:
  * - ``Measurement.Becquerel``
    - ``1205``
    - Bq

      .. _enumitem_Measurement_Gigabecquerel:
  * - ``Measurement.Gigabecquerel``
    - ``1206``
    - GBq

      .. _enumitem_Measurement_Kilobecquerel:
  * - ``Measurement.Kilobecquerel``
    - ``1207``
    - kBq

      .. _enumitem_Measurement_Megabecquerel:
  * - ``Measurement.Megabecquerel``
    - ``1208``
    - MBq

      .. _enumitem_Measurement_Microbecquerel:
  * - ``Measurement.Microbecquerel``
    - ``1209``
    - µBq

      .. _enumitem_Measurement_CuriePerKilogram:
  * - ``Measurement.CuriePerKilogram``
    - ``1210``
    - Ci/kg

      .. _enumitem_Measurement_BecquerelPerKilogram:
  * - ``Measurement.BecquerelPerKilogram``
    - ``1211``
    - Bq/kg

      .. _enumitem_Measurement_MegabecquerelPerKilogram:
  * - ``Measurement.MegabecquerelPerKilogram``
    - ``1212``
    - MBq/kg

      .. _enumitem_Measurement_KilobecquerelPerKilogram:
  * - ``Measurement.KilobecquerelPerKilogram``
    - ``1213``
    - kBq/kg

      .. _enumitem_Measurement_BecquerelPerCubicMetre:
  * - ``Measurement.BecquerelPerCubicMetre``
    - ``1214``
    - Bq/m³

      .. _enumitem_Measurement_Barn:
  * - ``Measurement.Barn``
    - ``1215``
    - b

      .. _enumitem_Measurement_SquareMetrePerSteradian:
  * - ``Measurement.SquareMetrePerSteradian``
    - ``1216``
    - m²/sr

      .. _enumitem_Measurement_BarnPerSteradian:
  * - ``Measurement.BarnPerSteradian``
    - ``1217``
    - b/sr

      .. _enumitem_Measurement_SquareMetrePerJoule:
  * - ``Measurement.SquareMetrePerJoule``
    - ``1218``
    - m²/J

      .. _enumitem_Measurement_BarnPerElectronvolt:
  * - ``Measurement.BarnPerElectronvolt``
    - ``1219``
    - b/eV

      .. _enumitem_Measurement_SquareCentimetrePerErg:
  * - ``Measurement.SquareCentimetrePerErg``
    - ``1220``
    - cm²/erg

      .. _enumitem_Measurement_SquareMetrePerSteradianJoule:
  * - ``Measurement.SquareMetrePerSteradianJoule``
    - ``1221``
    - m²/(sr·J)

      .. _enumitem_Measurement_BarnPerSteradianElectronvolt:
  * - ``Measurement.BarnPerSteradianElectronvolt``
    - ``1222``
    - b/(sr·eV)

      .. _enumitem_Measurement_SquareCentimetrePerSteradianErg:
  * - ``Measurement.SquareCentimetrePerSteradianErg``
    - ``1223``
    - cm²/(sr·erg)

      .. _enumitem_Measurement_ReciprocalMetreSquaredReciprocalSecond:
  * - ``Measurement.ReciprocalMetreSquaredReciprocalSecond``
    - ``1224``
    - m⁻²/s

      .. _enumitem_Measurement_SquareMetrePerKilogram:
  * - ``Measurement.SquareMetrePerKilogram``
    - ``1225``
    - m²/kg

      .. _enumitem_Measurement_JoulePerMetre:
  * - ``Measurement.JoulePerMetre``
    - ``1226``
    - J/m

      .. _enumitem_Measurement_ElectronvoltPerMetre:
  * - ``Measurement.ElectronvoltPerMetre``
    - ``1227``
    - eV/m

      .. _enumitem_Measurement_JouleSquareMetre:
  * - ``Measurement.JouleSquareMetre``
    - ``1228``
    - J·m²

      .. _enumitem_Measurement_ElectronvoltSquareMetre:
  * - ``Measurement.ElectronvoltSquareMetre``
    - ``1229``
    - eV·m²

      .. _enumitem_Measurement_JouleSquareMetrePerKilogram:
  * - ``Measurement.JouleSquareMetrePerKilogram``
    - ``1230``
    - J·m²/kg

      .. _enumitem_Measurement_ElectronvoltSquareMetrePerKilogram:
  * - ``Measurement.ElectronvoltSquareMetrePerKilogram``
    - ``1231``
    - eV·m²/kg

      .. _enumitem_Measurement_SquareMetrePerVoltSecond:
  * - ``Measurement.SquareMetrePerVoltSecond``
    - ``1232``
    - m²/(V·s)

      .. _enumitem_Measurement_MetrePerVoltSecond:
  * - ``Measurement.MetrePerVoltSecond``
    - ``1233``
    - m/(V·s)

      .. _enumitem_Measurement_ReciprocalCubicMetrePerSecond:
  * - ``Measurement.ReciprocalCubicMetrePerSecond``
    - ``1234``
    - m⁻³/s

      .. _enumitem_Measurement_Gray:
  * - ``Measurement.Gray``
    - ``1235``
    - Gy

      .. _enumitem_Measurement_Milligray:
  * - ``Measurement.Milligray``
    - ``1236``
    - mGy

      .. _enumitem_Measurement_Rad:
  * - ``Measurement.Rad``
    - ``1237``
    - rad

      .. _enumitem_Measurement_Sievert:
  * - ``Measurement.Sievert``
    - ``1238``
    - Sv

      .. _enumitem_Measurement_Millisievert:
  * - ``Measurement.Millisievert``
    - ``1239``
    - mSv

      .. _enumitem_Measurement_Rem:
  * - ``Measurement.Rem``
    - ``1240``
    - rem

      .. _enumitem_Measurement_MilliroentgenAequivalentMen:
  * - ``Measurement.MilliroentgenAequivalentMen``
    - ``1241``
    - mrem

      .. _enumitem_Measurement_GrayPerSecond:
  * - ``Measurement.GrayPerSecond``
    - ``1242``
    - Gy/s

      .. _enumitem_Measurement_CoulombPerKilogram:
  * - ``Measurement.CoulombPerKilogram``
    - ``1243``
    - C/kg

      .. _enumitem_Measurement_MillicoulombPerKilogram:
  * - ``Measurement.MillicoulombPerKilogram``
    - ``1244``
    - mC/kg

      .. _enumitem_Measurement_Roentgen:
  * - ``Measurement.Roentgen``
    - ``1245``
    - R

      .. _enumitem_Measurement_Milliroentgen:
  * - ``Measurement.Milliroentgen``
    - ``1246``
    - mR

      .. _enumitem_Measurement_CoulombSquareMetrePerKilogram:
  * - ``Measurement.CoulombSquareMetrePerKilogram``
    - ``1247``
    - C·m²/kg

      .. _enumitem_Measurement_Kiloroentgen:
  * - ``Measurement.Kiloroentgen``
    - ``1248``
    - kR

      .. _enumitem_Measurement_CoulombPerKilogramSecond:
  * - ``Measurement.CoulombPerKilogramSecond``
    - ``1249``
    - C/(kg·s)

      .. _enumitem_Measurement_RoentgenPerSecond:
  * - ``Measurement.RoentgenPerSecond``
    - ``1250``
    - R/s

      .. _enumitem_Measurement_MilligrayPerSecond:
  * - ``Measurement.MilligrayPerSecond``
    - ``1251``
    - mGy/s

      .. _enumitem_Measurement_MicrograyPerSecond:
  * - ``Measurement.MicrograyPerSecond``
    - ``1252``
    - µGy/s

      .. _enumitem_Measurement_NanograyPerSecond:
  * - ``Measurement.NanograyPerSecond``
    - ``1253``
    - nGy/s

      .. _enumitem_Measurement_GrayPerMinute:
  * - ``Measurement.GrayPerMinute``
    - ``1254``
    - Gy/min

      .. _enumitem_Measurement_MilligrayPerMinute:
  * - ``Measurement.MilligrayPerMinute``
    - ``1255``
    - mGy/min

      .. _enumitem_Measurement_MicrograyPerMinute:
  * - ``Measurement.MicrograyPerMinute``
    - ``1256``
    - µGy/min

      .. _enumitem_Measurement_NanograyPerMinute:
  * - ``Measurement.NanograyPerMinute``
    - ``1257``
    - nGy/min

      .. _enumitem_Measurement_GrayPerHour:
  * - ``Measurement.GrayPerHour``
    - ``1258``
    - Gy/h

      .. _enumitem_Measurement_MilligrayPerHour:
  * - ``Measurement.MilligrayPerHour``
    - ``1259``
    - mGy/h

      .. _enumitem_Measurement_MicrograyPerHour:
  * - ``Measurement.MicrograyPerHour``
    - ``1260``
    - µGy/h

      .. _enumitem_Measurement_NanograyPerHour:
  * - ``Measurement.NanograyPerHour``
    - ``1261``
    - nGy/h

      .. _enumitem_Measurement_SievertPerSecond:
  * - ``Measurement.SievertPerSecond``
    - ``1262``
    - Sv/s

      .. _enumitem_Measurement_MillisievertPerSecond:
  * - ``Measurement.MillisievertPerSecond``
    - ``1263``
    - mSv/s

      .. _enumitem_Measurement_MicrosievertPerSecond:
  * - ``Measurement.MicrosievertPerSecond``
    - ``1264``
    - µSv/s

      .. _enumitem_Measurement_NanosievertPerSecond:
  * - ``Measurement.NanosievertPerSecond``
    - ``1265``
    - nSv/s

      .. _enumitem_Measurement_RemPerSecond:
  * - ``Measurement.RemPerSecond``
    - ``1266``
    - rem/s

      .. _enumitem_Measurement_SievertPerHour:
  * - ``Measurement.SievertPerHour``
    - ``1267``
    - Sv/h

      .. _enumitem_Measurement_MillisievertPerHour:
  * - ``Measurement.MillisievertPerHour``
    - ``1268``
    - mSv/h

      .. _enumitem_Measurement_MicrosievertPerHour:
  * - ``Measurement.MicrosievertPerHour``
    - ``1269``
    - µSv/h

      .. _enumitem_Measurement_NanosievertPerHour:
  * - ``Measurement.NanosievertPerHour``
    - ``1270``
    - nSv/h

      .. _enumitem_Measurement_SievertPerMinute:
  * - ``Measurement.SievertPerMinute``
    - ``1271``
    - Sv/min

      .. _enumitem_Measurement_MillisievertPerMinute:
  * - ``Measurement.MillisievertPerMinute``
    - ``1272``
    - mSv/min

      .. _enumitem_Measurement_MicrosievertPerMinute:
  * - ``Measurement.MicrosievertPerMinute``
    - ``1273``
    - µSv/min

      .. _enumitem_Measurement_NanosievertPerMinute:
  * - ``Measurement.NanosievertPerMinute``
    - ``1274``
    - nSv/min

      .. _enumitem_Measurement_ReciprocalSquareInch:
  * - ``Measurement.ReciprocalSquareInch``
    - ``1275``
    - 1/in²

      .. _enumitem_Measurement_UnitPole:
  * - ``Measurement.UnitPole``
    - ``1276``
    - unit pole 

      .. _enumitem_Measurement_ReciprocalAngstrom:
  * - ``Measurement.ReciprocalAngstrom``
    - ``1277``
    - Å⁻¹

      .. _enumitem_Measurement_SecondPerCubicMetreRadian:
  * - ``Measurement.SecondPerCubicMetreRadian``
    - ``1278``
    - s/(rad·m³)

      .. _enumitem_Measurement_ReciprocalJoulePerCubicMetre:
  * - ``Measurement.ReciprocalJoulePerCubicMetre``
    - ``1279``
    - J⁻¹/m³

      .. _enumitem_Measurement_ReciprocalElectronVoltPerCubicMetre:
  * - ``Measurement.ReciprocalElectronVoltPerCubicMetre``
    - ``1280``
    - eV⁻¹/m³

      .. _enumitem_Measurement_CubicMetrePerCoulomb:
  * - ``Measurement.CubicMetrePerCoulomb``
    - ``1281``
    - m³/C

      .. _enumitem_Measurement_VoltPerKelvin:
  * - ``Measurement.VoltPerKelvin``
    - ``1282``
    - V/K

      .. _enumitem_Measurement_MillivoltPerKelvin:
  * - ``Measurement.MillivoltPerKelvin``
    - ``1283``
    - mV/K

      .. _enumitem_Measurement_AmperePerSquareMetreKelvinSquared:
  * - ``Measurement.AmperePerSquareMetreKelvinSquared``
    - ``1284``
    - A/(m²·K²)

      .. _enumitem_Measurement_KilopascalSquareMetrePerGram:
  * - ``Measurement.KilopascalSquareMetrePerGram``
    - ``1285``
    - kPa·m²/g

      .. _enumitem_Measurement_PascalSquareMetrePerKilogram:
  * - ``Measurement.PascalSquareMetrePerKilogram``
    - ``1286``
    - Pa/(kg/m²)

      .. _enumitem_Measurement_KilopascalPerMillimetre:
  * - ``Measurement.KilopascalPerMillimetre``
    - ``1287``
    - kPa/mm

      .. _enumitem_Measurement_PascalPerMetre:
  * - ``Measurement.PascalPerMetre``
    - ``1288``
    - Pa/m

      .. _enumitem_Measurement_PicopascalPerKilometre:
  * - ``Measurement.PicopascalPerKilometre``
    - ``1289``
    - pPa/km

      .. _enumitem_Measurement_MillipascalPerMetre:
  * - ``Measurement.MillipascalPerMetre``
    - ``1290``
    - mPa/m

      .. _enumitem_Measurement_KilopascalPerMetre:
  * - ``Measurement.KilopascalPerMetre``
    - ``1291``
    - kPa/m

      .. _enumitem_Measurement_HectopascalPerMetre:
  * - ``Measurement.HectopascalPerMetre``
    - ``1292``
    - hPa/m

      .. _enumitem_Measurement_StandardAtmospherePerMetre:
  * - ``Measurement.StandardAtmospherePerMetre``
    - ``1293``
    - Atm/m

      .. _enumitem_Measurement_TechnicalAtmospherePerMetre:
  * - ``Measurement.TechnicalAtmospherePerMetre``
    - ``1294``
    - at/m

      .. _enumitem_Measurement_TorrPerMetre:
  * - ``Measurement.TorrPerMetre``
    - ``1295``
    - Torr/m

      .. _enumitem_Measurement_PsiPerInch:
  * - ``Measurement.PsiPerInch``
    - ``1296``
    - psi/in

      .. _enumitem_Measurement_MillilitrePerSquareCentimetreSecond:
  * - ``Measurement.MillilitrePerSquareCentimetreSecond``
    - ``1297``
    - ml/(cm²·s)

      .. _enumitem_Measurement_CubicMetrePerSecondSquareMetre:
  * - ``Measurement.CubicMetrePerSecondSquareMetre``
    - ``1298``
    - (m³/s)/m²


.. _example_Measurement:


Example
*******

.. code-block:: qml

    import InCore.Foundation 2.4
    
    Application {
        Measurement {
            unit: Measurement.SquareMetre
            data: 123.456
            onDisplayStringChanged: console.log(displayString)
        }
    }
    