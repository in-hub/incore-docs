
.. _object_AnalogInput:


:index:`AnalogInput`
--------------------

Description
***********

The AnalogInput object allows measuring voltages or currents. The underlying hardware works with a 12 bit ADC so measured values are always in the range [0..4095].

:**› Inherits**: :ref:`Object <object_Object>`

Overview
********

Properties
++++++++++

.. hlist::
  :columns: 2

  * :ref:`analogFault <property_AnalogInput_analogFault>`
  * :ref:`current <property_AnalogInput_current>`
  * :ref:`error <property_AnalogInput_error>`
  * :ref:`errorString <property_AnalogInput_errorString>`
  * :ref:`index <property_AnalogInput_index>`
  * :ref:`mode <property_AnalogInput_mode>`
  * :ref:`value <property_AnalogInput_value>`
  * :ref:`voltage <property_AnalogInput_voltage>`
  * :ref:`Object.objectId <property_Object_objectId>`
  * :ref:`Object.parent <property_Object_parent>`

Methods
+++++++

.. hlist::
  :columns: 1

  * :ref:`pollAnalogFault() <method_AnalogInput_pollAnalogFault>`
  * :ref:`pollValue() <method_AnalogInput_pollValue>`
  * :ref:`Object.deserializeProperties() <method_Object_deserializeProperties>`
  * :ref:`Object.fromJson() <method_Object_fromJson>`
  * :ref:`Object.serializeProperties() <method_Object_serializeProperties>`
  * :ref:`Object.toJson() <method_Object_toJson>`

Signals
+++++++

.. hlist::
  :columns: 1

  * :ref:`errorOccurred() <signal_AnalogInput_errorOccurred>`
  * :ref:`Object.completed() <signal_Object_completed>`

Enumerations
++++++++++++

.. hlist::
  :columns: 1

  * :ref:`Error <enum_AnalogInput_Error>`
  * :ref:`Index <enum_AnalogInput_Index>`
  * :ref:`Mode <enum_AnalogInput_Mode>`



Properties
**********


.. _property_AnalogInput_analogFault:

.. _signal_AnalogInput_analogFaultChanged:

.. index::
   single: analogFault

analogFault
+++++++++++

This property holds the current state of the Analog Fault pin (HUB-GM200 only).

This property was introduced in InCore 2.1.

:**› Type**: Boolean
:**› Signal**: analogFaultChanged()
:**› Attributes**: Readonly, Requires :ref:`Polling <object_Polling>`


.. _property_AnalogInput_current:

.. _signal_AnalogInput_currentChanged:

.. index::
   single: current

current
+++++++

This property holds the current calculated from :ref:`value <property_AnalogInput_value>` if :ref:`mode <property_AnalogInput_mode>` is set to :ref:`AnalogInput.Mode20mA <enumitem_AnalogInput_Mode20mA>`. Otherwise ``0`` will be returned. The current is be updated whenver the :ref:`valueChanged() <signal_AnalogInput_valueChanged>` signal is emitted, so you have to poll :ref:`value <property_AnalogInput_value>` to read a valid current.

This property was introduced in InCore 2.2.

:**› Type**: Double
:**› Signal**: currentChanged()
:**› Attributes**: Readonly


.. _property_AnalogInput_error:

.. _signal_AnalogInput_errorChanged:

.. index::
   single: error

error
+++++

This property holds the most recently occurred error or :ref:`AnalogInput.NoError <enumitem_AnalogInput_NoError>` if no error occurred. If the same error occurs multiple times this property does not change. Use the :ref:`errorOccurred() <signal_AnalogInput_errorOccurred>` signal to detect multiple occurrences of the same error.

:**› Type**: :ref:`Error <enum_AnalogInput_Error>`
:**› Signal**: errorChanged()
:**› Attributes**: Readonly


.. _property_AnalogInput_errorString:

.. _signal_AnalogInput_errorStringChanged:

.. index::
   single: errorString

errorString
+++++++++++

This property holds the current human readable error string corresponding to the current value in the :ref:`error <property_AnalogInput_error>` property. It may include additional information such as failure reasons or locations.

:**› Type**: String
:**› Signal**: errorStringChanged()
:**› Attributes**: Readonly


.. _property_AnalogInput_index:

.. _signal_AnalogInput_indexChanged:

.. index::
   single: index

index
+++++

This property holds the index of the input. This property has to be set to work properly.

:**› Type**: :ref:`Index <enum_AnalogInput_Index>`
:**› Default**: :ref:`AnalogInput.Invalid <enumitem_AnalogInput_Invalid>`
:**› Signal**: indexChanged()
:**› Attributes**: Writable


.. _property_AnalogInput_mode:

.. _signal_AnalogInput_modeChanged:

.. index::
   single: mode

mode
++++

This property holds the mode of the input. This property has to be set to work properly.

:**› Type**: :ref:`Mode <enum_AnalogInput_Mode>`
:**› Default**: :ref:`AnalogInput.ModeInvalid <enumitem_AnalogInput_ModeInvalid>`
:**› Signal**: modeChanged()
:**› Attributes**: Writable


.. _property_AnalogInput_value:

.. _signal_AnalogInput_valueChanged:

.. index::
   single: value

value
+++++

This property holds the current value of the measured current or voltage in digits.

:**› Type**: SignedInteger
:**› Signal**: valueChanged()
:**› Attributes**: Readonly, Requires :ref:`Polling <object_Polling>`


.. _property_AnalogInput_voltage:

.. _signal_AnalogInput_voltageChanged:

.. index::
   single: voltage

voltage
+++++++

This property holds the voltage calculated from :ref:`value <property_AnalogInput_value>` if :ref:`mode <property_AnalogInput_mode>` is set to :ref:`AnalogInput.Mode5V <enumitem_AnalogInput_Mode5V>`, :ref:`AnalogInput.Mode10V <enumitem_AnalogInput_Mode10V>` or :ref:`AnalogInput.Mode20V <enumitem_AnalogInput_Mode20V>`. Otherwise ``0`` will be returned. The voltage is updated whenever the :ref:`valueChanged() <signal_AnalogInput_valueChanged>` signal is emitted, so you have to poll :ref:`value <property_AnalogInput_value>` to read a valid voltage.

This property was introduced in InCore 2.2.

:**› Type**: Double
:**› Signal**: voltageChanged()
:**› Attributes**: Readonly

Methods
*******


.. _method_AnalogInput_pollAnalogFault:

.. index::
   single: pollAnalogFault

pollAnalogFault()
+++++++++++++++++

This method polls the :ref:`analogFault <property_AnalogInput_analogFault>` property. It is called automatically when using a :ref:`Polling <object_Polling>` property modifier on this property and usually does not have to be called manually.



.. _method_AnalogInput_pollValue:

.. index::
   single: pollValue

pollValue()
+++++++++++

This method polls the :ref:`value <property_AnalogInput_value>` property. It is called automatically when using a :ref:`Polling <object_Polling>` property modifier on this property and usually does not have to be called manually.


Signals
*******


.. _signal_AnalogInput_errorOccurred:

.. index::
   single: errorOccurred

errorOccurred()
+++++++++++++++

This signal is emitted whenever an error has occurred, regardless of whether the :ref:`error <property_AnalogInput_error>` property has changed or not. In contrast to the change notification signal of the :ref:`error <property_AnalogInput_error>` property this signal is also emitted several times if a certain error occurs several times in succession.


Enumerations
************


.. _enum_AnalogInput_Error:

.. index::
   single: Error

Error
+++++

This enumeration describes all errors which can occur in AnalogInput objects. The most recently occurred error is stored in the :ref:`error <property_AnalogInput_error>` property.

.. index::
   single: AnalogInput.NoError
.. index::
   single: AnalogInput.InvalidMode
.. index::
   single: AnalogInput.HardwareDriverNotAvailable
.. list-table::
  :widths: auto
  :header-rows: 1

  * - Name
    - Value
    - Description

      .. _enumitem_AnalogInput_NoError:
  * - ``AnalogInput.NoError``
    - ``0``
    - No error occurred or was detected.

      .. _enumitem_AnalogInput_InvalidMode:
  * - ``AnalogInput.InvalidMode``
    - ``1``
    - None or invalid mode set.

      .. _enumitem_AnalogInput_HardwareDriverNotAvailable:
  * - ``AnalogInput.HardwareDriverNotAvailable``
    - ``2``
    - No hardware driver available for this device.


.. _enum_AnalogInput_Index:

.. index::
   single: Index

Index
+++++

This enumeration describes the supported analog input indexes.

.. index::
   single: AnalogInput.Invalid
.. index::
   single: AnalogInput.AIN1
.. index::
   single: AnalogInput.AIN2
.. index::
   single: AnalogInput.AIN3
.. index::
   single: AnalogInput.AIN4
.. list-table::
  :widths: auto
  :header-rows: 1

  * - Name
    - Value
    - Description

      .. _enumitem_AnalogInput_Invalid:
  * - ``AnalogInput.Invalid``
    - ``0``
    - No index assigned.

      .. _enumitem_AnalogInput_AIN1:
  * - ``AnalogInput.AIN1``
    - ``1``
    - The first analog input.

      .. _enumitem_AnalogInput_AIN2:
  * - ``AnalogInput.AIN2``
    - ``2``
    - The second analog input.

      .. _enumitem_AnalogInput_AIN3:
  * - ``AnalogInput.AIN3``
    - ``3``
    - The third analog input.

      .. _enumitem_AnalogInput_AIN4:
  * - ``AnalogInput.AIN4``
    - ``4``
    - The fourth analog input.


.. _enum_AnalogInput_Mode:

.. index::
   single: Mode

Mode
++++

This enumeration describes supported modes for an analog input interface.

.. index::
   single: AnalogInput.ModeInvalid
.. index::
   single: AnalogInput.Mode5V
.. index::
   single: AnalogInput.Mode10V
.. index::
   single: AnalogInput.Mode20V
.. index::
   single: AnalogInput.Mode20mA
.. index::
   single: AnalogInput.Mode24V
.. list-table::
  :widths: auto
  :header-rows: 1

  * - Name
    - Value
    - Description

      .. _enumitem_AnalogInput_ModeInvalid:
  * - ``AnalogInput.ModeInvalid``
    - ``0``
    - No mode assigned.

      .. _enumitem_AnalogInput_Mode5V:
  * - ``AnalogInput.Mode5V``
    - ``1``
    - Measure an input voltage in the range [0..5V] (only HUB-GM100).

      .. _enumitem_AnalogInput_Mode10V:
  * - ``AnalogInput.Mode10V``
    - ``2``
    - Measure an input voltage in the range [0..10V].

      .. _enumitem_AnalogInput_Mode20V:
  * - ``AnalogInput.Mode20V``
    - ``3``
    - Measure an input voltage in the range [0..20V] (only HUB-GM100).

      .. _enumitem_AnalogInput_Mode20mA:
  * - ``AnalogInput.Mode20mA``
    - ``4``
    - Measure an input current in the range [4..20mA].

      .. _enumitem_AnalogInput_Mode24V:
  * - ``AnalogInput.Mode24V``
    - ``5``
    - Measure an input current in the range [0..24V].


.. _example_AnalogInput:


Example
*******

.. code-block:: qml

    import InCore.Foundation 2.5
    import InCore.IO 2.5
    
    Application {
    
        AnalogInput {
            index: AnalogInput.AIN1
            mode: AnalogInput.Mode10V
            Polling on value { interval: 100 }
            onValueChanged: console.log("Current ADC value is", value)
            onVoltageChanged: console.log("Current voltage is", voltage)
        }
    
    }
    