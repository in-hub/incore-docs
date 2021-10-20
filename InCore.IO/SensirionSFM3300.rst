
.. _object_SensirionSFM3300:


:index:`SensirionSFM3300`
-------------------------

Description
***********



This object was introduced in InCore 2.5.

:**› Inherits**: :ref:`SensirionHDLC <object_SensirionHDLC>`

Overview
********

Properties
++++++++++

.. hlist::
  :columns: 3

  * :ref:`baseUnit <property_SensirionSFM3300_baseUnit>`
  * :ref:`measureContinuously <property_SensirionSFM3300_measureContinuously>`
  * :ref:`sensorSerialNumber <property_SensirionSFM3300_sensorSerialNumber>`
  * :ref:`siPrefix <property_SensirionSFM3300_siPrefix>`
  * :ref:`timeBase <property_SensirionSFM3300_timeBase>`
  * :ref:`unit <property_SensirionSFM3300_unit>`
  * :ref:`value <property_SensirionSFM3300_value>`
  * :ref:`SensirionHDLC.articleCode <property_SensirionHDLC_articleCode>`
  * :ref:`SensirionHDLC.error <property_SensirionHDLC_error>`
  * :ref:`SensirionHDLC.errorString <property_SensirionHDLC_errorString>`
  * :ref:`SensirionHDLC.firmwareVersion <property_SensirionHDLC_firmwareVersion>`
  * :ref:`SensirionHDLC.hardwareVersion <property_SensirionHDLC_hardwareVersion>`
  * :ref:`SensirionHDLC.productName <property_SensirionHDLC_productName>`
  * :ref:`SensirionHDLC.serialNumber <property_SensirionHDLC_serialNumber>`
  * :ref:`SerialPortBusNode.bus <property_SerialPortBusNode_bus>`
  * :ref:`SerialPortBusNode.portName <property_SerialPortBusNode_portName>`
  * :ref:`SerialPortBusNode.responseTimeout <property_SerialPortBusNode_responseTimeout>`
  * :ref:`SerialPortBusNode.serialPort <property_SerialPortBusNode_serialPort>`
  * :ref:`Object.objectId <property_Object_objectId>`
  * :ref:`Object.parent <property_Object_parent>`

Methods
+++++++

.. hlist::
  :columns: 1

  * :ref:`pollValue() <method_SensirionSFM3300_pollValue>`
  * :ref:`SensirionHDLC.reset() <method_SensirionHDLC_reset>`
  * :ref:`SensirionHDLC.sendCommand() <method_SensirionHDLC_sendCommand>`
  * :ref:`Object.deserializeProperties() <method_Object_deserializeProperties>`
  * :ref:`Object.fromJson() <method_Object_fromJson>`
  * :ref:`Object.toJson() <method_Object_toJson>`

Signals
+++++++

.. hlist::
  :columns: 1

  * :ref:`SensirionHDLC.errorOccurred() <signal_SensirionHDLC_errorOccurred>`
  * :ref:`SensirionHDLC.responseReceived() <signal_SensirionHDLC_responseReceived>`
  * :ref:`Object.completed() <signal_Object_completed>`

Enumerations
++++++++++++

.. hlist::
  :columns: 1

  * :ref:`BaseUnit <enum_SensirionSFM3300_BaseUnit>`
  * :ref:`SensirionHDLC.Error <enum_SensirionHDLC_Error>`



Properties
**********


.. _property_SensirionSFM3300_baseUnit:

.. _signal_SensirionSFM3300_baseUnitChanged:

.. index::
   single: baseUnit

baseUnit
++++++++

This property holds the base unit for temperature or pressure measurements.

:**› Type**: :ref:`BaseUnit <enum_SensirionSFM3300_BaseUnit>`
:**› Signal**: baseUnitChanged()
:**› Attributes**: Readonly


.. _property_SensirionSFM3300_measureContinuously:

.. _signal_SensirionSFM3300_measureContinuouslyChanged:

.. index::
   single: measureContinuously

measureContinuously
+++++++++++++++++++

This property holds whether to configure the sensor such that it measures continuously.

:**› Type**: Boolean
:**› Default**: ``true``
:**› Signal**: measureContinuouslyChanged()
:**› Attributes**: Writable


.. _property_SensirionSFM3300_sensorSerialNumber:

.. _signal_SensirionSFM3300_sensorSerialNumberChanged:

.. index::
   single: sensorSerialNumber

sensorSerialNumber
++++++++++++++++++

This property holds the serial number of the attached sensor.

:**› Type**: UnsignedInteger
:**› Signal**: sensorSerialNumberChanged()
:**› Attributes**: Readonly


.. _property_SensirionSFM3300_siPrefix:

.. _signal_SensirionSFM3300_siPrefixChanged:

.. index::
   single: siPrefix

siPrefix
++++++++

This property holds the SI prefix for measurements.

:**› Type**: :ref:`Measurement.SiPrefix <enum_Measurement_SiPrefix>`
:**› Signal**: siPrefixChanged()
:**› Attributes**: Readonly


.. _property_SensirionSFM3300_timeBase:

.. _signal_SensirionSFM3300_timeBaseChanged:

.. index::
   single: timeBase

timeBase
++++++++

This property holds the time base unit for measurements.

:**› Type**: :ref:`Measurement.Unit <enum_Measurement_Unit>`
:**› Signal**: timeBaseChanged()
:**› Attributes**: Readonly


.. _property_SensirionSFM3300_unit:

.. _signal_SensirionSFM3300_unitChanged:

.. index::
   single: unit

unit
++++

This property holds the full unit string based on :ref:`siPrefix <property_SensirionSFM3300_siPrefix>`, :ref:`baseUnit <property_SensirionSFM3300_baseUnit>` and :ref:`timeBase <property_SensirionSFM3300_timeBase>`.

:**› Type**: String
:**› Signal**: unitChanged()
:**› Attributes**: Readonly


.. _property_SensirionSFM3300_value:

.. _signal_SensirionSFM3300_valueChanged:

.. index::
   single: value

value
+++++

This property holds the most recently measured value from the sensor.

:**› Type**: Float
:**› Signal**: valueChanged()
:**› Attributes**: Readonly, Requires :ref:`Polling <object_Polling>`

Methods
*******


.. _method_SensirionSFM3300_pollValue:

.. index::
   single: pollValue

pollValue()
+++++++++++

This method polls the :ref:`value <property_SensirionSFM3300_value>` property. It is called automatically when using a :ref:`Polling <object_Polling>` property modifier on this property and usually does not have to be called manually.


Enumerations
************


.. _enum_SensirionSFM3300_BaseUnit:

.. index::
   single: BaseUnit

BaseUnit
++++++++



.. index::
   single: SensirionSFM3300.NoBaseUnit
.. index::
   single: SensirionSFM3300.NormLiter
.. index::
   single: SensirionSFM3300.StandardLiter
.. index::
   single: SensirionSFM3300.Liter
.. index::
   single: SensirionSFM3300.Gram
.. index::
   single: SensirionSFM3300.Pascal
.. index::
   single: SensirionSFM3300.Bar
.. index::
   single: SensirionSFM3300.MeterOfWater
.. index::
   single: SensirionSFM3300.InchOfWater
.. list-table::
  :widths: auto
  :header-rows: 1

  * - Name
    - Value
    - Description

      .. _enumitem_SensirionSFM3300_NoBaseUnit:
  * - ``SensirionSFM3300.NoBaseUnit``
    - ``0``
    - 

      .. _enumitem_SensirionSFM3300_NormLiter:
  * - ``SensirionSFM3300.NormLiter``
    - ``1``
    - 

      .. _enumitem_SensirionSFM3300_StandardLiter:
  * - ``SensirionSFM3300.StandardLiter``
    - ``2``
    - 

      .. _enumitem_SensirionSFM3300_Liter:
  * - ``SensirionSFM3300.Liter``
    - ``3``
    - 

      .. _enumitem_SensirionSFM3300_Gram:
  * - ``SensirionSFM3300.Gram``
    - ``4``
    - 

      .. _enumitem_SensirionSFM3300_Pascal:
  * - ``SensirionSFM3300.Pascal``
    - ``5``
    - 

      .. _enumitem_SensirionSFM3300_Bar:
  * - ``SensirionSFM3300.Bar``
    - ``6``
    - 

      .. _enumitem_SensirionSFM3300_MeterOfWater:
  * - ``SensirionSFM3300.MeterOfWater``
    - ``7``
    - 

      .. _enumitem_SensirionSFM3300_InchOfWater:
  * - ``SensirionSFM3300.InchOfWater``
    - ``8``
    - 


.. _example_SensirionSFM3300:


Example
*******

.. code-block:: qml

    import InCore.Foundation 2.5
    import InCore.IO 2.5
    
    Application {
    
        SensirionSFM3300 {
            property real volume: 0
            portName: "ttyUSB0"
            Polling on value { interval: 25 }
            onValueChanged: {
                // integrate volume flow to get the total exhaled volume
                if( value > 0.5 )
                {
                    if(timer.msecsElapsed > 0)
                    {
                        volume += value * timer.msecsElapsed / 60000;
                    }
                    timer.restart()
                }
                else if( value < -0.5 && timer.running )
                {
                    console.log("Exhaled volume", volume)
                    volume = 0
                    timer.stop()
                }
            }
        }
    
        Timer { id: timer }
    }
    