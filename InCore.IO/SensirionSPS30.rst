
.. _object_SensirionSPS30:


:index:`SensirionSPS30`
-----------------------

Description
***********

The SensirionSPS30 object provides an interface for the Sensirion SPS30 particle sensor and allows reading measured masss concentrations, number concentrations and the typical particle size. Additionally operations such as cleaning the fan can configured to be performed automatically or triggered manually.

:**› Inherits**: :ref:`SensirionHDLC <object_SensirionHDLC>`

Overview
********

Properties
++++++++++

.. hlist::
  :columns: 3

  * :ref:`autoCleaningInterval <property_SensirionSPS30_autoCleaningInterval>`
  * :ref:`enabled <property_SensirionSPS30_enabled>`
  * :ref:`massPM10 <property_SensirionSPS30_massPM10>`
  * :ref:`massPM1_0 <property_SensirionSPS30_massPM1_0>`
  * :ref:`massPM2_5 <property_SensirionSPS30_massPM2_5>`
  * :ref:`massPM4_0 <property_SensirionSPS30_massPM4_0>`
  * :ref:`numberPM0_5 <property_SensirionSPS30_numberPM0_5>`
  * :ref:`numberPM10 <property_SensirionSPS30_numberPM10>`
  * :ref:`numberPM1_0 <property_SensirionSPS30_numberPM1_0>`
  * :ref:`numberPM2_5 <property_SensirionSPS30_numberPM2_5>`
  * :ref:`numberPM4_0 <property_SensirionSPS30_numberPM4_0>`
  * :ref:`typicalSize <property_SensirionSPS30_typicalSize>`
  * :ref:`values <property_SensirionSPS30_values>`
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
  :columns: 2

  * :ref:`pollValues() <method_SensirionSPS30_pollValues>`
  * :ref:`startFanCleaning() <method_SensirionSPS30_startFanCleaning>`
  * :ref:`SensirionHDLC.reset() <method_SensirionHDLC_reset>`
  * :ref:`SensirionHDLC.sendCommand() <method_SensirionHDLC_sendCommand>`
  * :ref:`Object.deserializeProperties() <method_Object_deserializeProperties>`
  * :ref:`Object.fromJson() <method_Object_fromJson>`
  * :ref:`Object.serializeProperties() <method_Object_serializeProperties>`
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

  * :ref:`SensirionHDLC.Error <enum_SensirionHDLC_Error>`



Properties
**********


.. _property_SensirionSPS30_autoCleaningInterval:

.. _signal_SensirionSPS30_autoCleaningIntervalChanged:

.. index::
   single: autoCleaningInterval

autoCleaningInterval
++++++++++++++++++++

This property holds the interval [ms] of the periodic fan-cleaning. When the module is in measurement mode an automatic fan-cleaning procedure will be triggered periodically following a defined cleaning interval. This will accelerate the fan to maximum speed for 10 seconds in order to blow out the dust accumulated inside the fan. While cleaning measurement values are not updated. Set to ``0`` to disable. Default interval is ``604800000`` milliseconds (1 week). If the sensor is switched off, the time counter is reset to ``0``. Make sure to trigger a cleaning cycle at least every week if the sensor is switched off and on periodically (e.g., once per day).

:**› Type**: SignedInteger
:**› Default**: ``604800000``
:**› Signal**: autoCleaningIntervalChanged()
:**› Attributes**: Writable


.. _property_SensirionSPS30_enabled:

.. _signal_SensirionSPS30_enabledChanged:

.. index::
   single: enabled

enabled
+++++++

This property holds whether the sensor is enabled. After power up, the module is in Idle-Mode. Before any measurement values can be read, the sensor needs to be enabled. If enabling was successful the fan starts running.

:**› Type**: Boolean
:**› Default**: ``true``
:**› Signal**: enabledChanged()
:**› Attributes**: Writable


.. _property_SensirionSPS30_massPM10:

.. _signal_SensirionSPS30_massPM10Changed:

.. index::
   single: massPM10

massPM10
++++++++

This property holds the mass concentration *PM10* in *μg/m³*.

:**› Type**: Float
:**› Default**: ``0``
:**› Signal**: massPM10Changed()
:**› Attributes**: Readonly


.. _property_SensirionSPS30_massPM1_0:

.. _signal_SensirionSPS30_massPM1_0Changed:

.. index::
   single: massPM1_0

massPM1_0
+++++++++

This property holds the mass concentration *PM1.0* in *μg/m³*.

:**› Type**: Float
:**› Default**: ``0``
:**› Signal**: massPM1_0Changed()
:**› Attributes**: Readonly


.. _property_SensirionSPS30_massPM2_5:

.. _signal_SensirionSPS30_massPM2_5Changed:

.. index::
   single: massPM2_5

massPM2_5
+++++++++

This property holds the mass concentration *PM2.5* in *μg/m³*.

:**› Type**: Float
:**› Default**: ``0``
:**› Signal**: massPM2_5Changed()
:**› Attributes**: Readonly


.. _property_SensirionSPS30_massPM4_0:

.. _signal_SensirionSPS30_massPM4_0Changed:

.. index::
   single: massPM4_0

massPM4_0
+++++++++

This property holds the mass concentration *PM4.0* in *μg/m³*.

:**› Type**: Float
:**› Default**: ``0``
:**› Signal**: massPM4_0Changed()
:**› Attributes**: Readonly


.. _property_SensirionSPS30_numberPM0_5:

.. _signal_SensirionSPS30_numberPM0_5Changed:

.. index::
   single: numberPM0_5

numberPM0_5
+++++++++++

This property holds the number concentration *PM0.5* in *#/cm³*.

:**› Type**: Float
:**› Default**: ``0``
:**› Signal**: numberPM0_5Changed()
:**› Attributes**: Readonly


.. _property_SensirionSPS30_numberPM10:

.. _signal_SensirionSPS30_numberPM10Changed:

.. index::
   single: numberPM10

numberPM10
++++++++++

This property holds the number concentration *PM10* in *#/cm³*.

:**› Type**: Float
:**› Default**: ``0``
:**› Signal**: numberPM10Changed()
:**› Attributes**: Readonly


.. _property_SensirionSPS30_numberPM1_0:

.. _signal_SensirionSPS30_numberPM1_0Changed:

.. index::
   single: numberPM1_0

numberPM1_0
+++++++++++

This property holds the number concentration *PM1.0* in *#/cm³*.

:**› Type**: Float
:**› Default**: ``0``
:**› Signal**: numberPM1_0Changed()
:**› Attributes**: Readonly


.. _property_SensirionSPS30_numberPM2_5:

.. _signal_SensirionSPS30_numberPM2_5Changed:

.. index::
   single: numberPM2_5

numberPM2_5
+++++++++++

This property holds the number concentration *PM2.5* in *#/cm³*.

:**› Type**: Float
:**› Default**: ``0``
:**› Signal**: numberPM2_5Changed()
:**› Attributes**: Readonly


.. _property_SensirionSPS30_numberPM4_0:

.. _signal_SensirionSPS30_numberPM4_0Changed:

.. index::
   single: numberPM4_0

numberPM4_0
+++++++++++

This property holds the number concentration *PM4.0* in *#/cm³*.

:**› Type**: Float
:**› Default**: ``0``
:**› Signal**: numberPM4_0Changed()
:**› Attributes**: Readonly


.. _property_SensirionSPS30_typicalSize:

.. _signal_SensirionSPS30_typicalSizeChanged:

.. index::
   single: typicalSize

typicalSize
+++++++++++

This property holds the typical particle size in *μm*.

:**› Type**: Float
:**› Default**: ``1``
:**› Signal**: typicalSizeChanged()
:**› Attributes**: Readonly


.. _property_SensirionSPS30_values:

.. _signal_SensirionSPS30_valuesChanged:

.. index::
   single: values

values
++++++

This property holds all available values provided for convenience in the following order:

* Mass concentration *PM1.0*: :ref:`massPM1_0 <property_SensirionSPS30_massPM1_0>`
* Mass concentration *PM2.5*: :ref:`massPM2_5 <property_SensirionSPS30_massPM2_5>`
* Mass concentration *PM4.0*: :ref:`massPM4_0 <property_SensirionSPS30_massPM4_0>`
* Mass concentration *PM10*: :ref:`massPM10 <property_SensirionSPS30_massPM10>`
* Number concentration *PM0.5*: :ref:`numberPM0_5 <property_SensirionSPS30_numberPM0_5>`
* Number concentration *PM1.0*: :ref:`numberPM1_0 <property_SensirionSPS30_numberPM1_0>`
* Number concentration *PM2.5*: :ref:`numberPM2_5 <property_SensirionSPS30_numberPM2_5>`
* Number concentration *PM4.0*: :ref:`numberPM4_0 <property_SensirionSPS30_numberPM4_0>`
* Number concentration *PM10*: :ref:`numberPM10 <property_SensirionSPS30_numberPM10>`
* Typical particle size: :ref:`typicalSize <property_SensirionSPS30_typicalSize>`


:**› Type**: List
:**› Signal**: valuesChanged()
:**› Attributes**: Readonly, Requires :ref:`Polling <object_Polling>`

Methods
*******


.. _method_SensirionSPS30_pollValues:

.. index::
   single: pollValues

pollValues()
++++++++++++

This method polls the :ref:`values <property_SensirionSPS30_values>` property. It is called automatically when using a :ref:`Polling <object_Polling>` property modifier on this property and usually does not have to be called manually.



.. _method_SensirionSPS30_startFanCleaning:

.. index::
   single: startFanCleaning

startFanCleaning()
++++++++++++++++++

This method starts the fan-cleaning manually. For more details, see :ref:`autoCleaningInterval <property_SensirionSPS30_autoCleaningInterval>`



.. _example_SensirionSPS30:


Example
*******

.. code-block:: qml

    import InCore.Foundation 2.5
    import InCore.IO 2.5
    
    Application {
    
        SensirionSPS30 {
            serialPort: SerialPort { portName: "ttyUSB0" }
            autoCleaningInterval: 10 * 60 * 1000
            onErrorChanged: console.log( errorString )
            Polling on values { interval: 2000 }
            onValuesChanged: console.log( values )
        }
    }
    