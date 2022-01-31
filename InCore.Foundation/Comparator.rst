
.. _object_Comparator:


:index:`Comparator`
-------------------

Description
***********

The Comparator object is a class to process both discrete and continuous signals such as measurements from digital inputs or analog sensors. Depending on the configuration it acts like a comparator with or without an hysteresis or a limiter. The intervals can be used to delay state changes for example to debounce a digital signal or filter flicker.

:**› Inherits**: :ref:`Object <object_Object>`

Overview
********

Properties
++++++++++

.. hlist::
  :columns: 2

  * :ref:`input <property_Comparator_input>`
  * :ref:`output <property_Comparator_output>`
  * :ref:`outputValueOff <property_Comparator_outputValueOff>`
  * :ref:`outputValueOn <property_Comparator_outputValueOn>`
  * :ref:`state <property_Comparator_state>`
  * :ref:`thresholdValueOff <property_Comparator_thresholdValueOff>`
  * :ref:`thresholdValueOn <property_Comparator_thresholdValueOn>`
  * :ref:`timerIntervalOff <property_Comparator_timerIntervalOff>`
  * :ref:`timerIntervalOn <property_Comparator_timerIntervalOn>`
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

  * :ref:`inputFallingEdge() <signal_Comparator_inputFallingEdge>`
  * :ref:`inputRisingEdge() <signal_Comparator_inputRisingEdge>`
  * :ref:`outputFallingEdge() <signal_Comparator_outputFallingEdge>`
  * :ref:`outputRisingEdge() <signal_Comparator_outputRisingEdge>`
  * :ref:`Object.completed() <signal_Object_completed>`



Properties
**********


.. _property_Comparator_input:

.. _signal_Comparator_inputChanged:

.. index::
   single: input

input
+++++

This property holds the input value to compare with the thresholds.

:**› Type**: Variant
:**› Signal**: inputChanged()
:**› Attributes**: Writable


.. _property_Comparator_output:

.. _signal_Comparator_outputChanged:

.. index::
   single: output

output
++++++

This property holds the output value of the comparator. If :ref:`state <property_Comparator_state>` is ``true`` it is equal to :ref:`outputValueOn <property_Comparator_outputValueOn>`. Otherwise it corresponds to :ref:`outputValueOff <property_Comparator_outputValueOff>`.

:**› Type**: Variant
:**› Signal**: outputChanged()
:**› Attributes**: Readonly


.. _property_Comparator_outputValueOff:

.. _signal_Comparator_outputValueOffChanged:

.. index::
   single: outputValueOff

outputValueOff
++++++++++++++

This property holds the value for the *off* state. If :ref:`state <property_Comparator_state>` is ``false`` :ref:`output <property_Comparator_output>` is set to this value. Binding an expression to this property will make the :ref:`output <property_Comparator_output>` property being updated as well.

:**› Type**: Variant
:**› Default**: ``false``
:**› Signal**: outputValueOffChanged()
:**› Attributes**: Writable


.. _property_Comparator_outputValueOn:

.. _signal_Comparator_outputValueOnChanged:

.. index::
   single: outputValueOn

outputValueOn
+++++++++++++

This property holds the value for the *on* state. If :ref:`state <property_Comparator_state>` is ``true`` :ref:`output <property_Comparator_output>` is set to this value. Contains this value a binding, it is also mapped to :ref:`output <property_Comparator_output>`.

:**› Type**: Variant
:**› Default**: ``true``
:**› Signal**: outputValueOnChanged()
:**› Attributes**: Writable


.. _property_Comparator_state:

.. _signal_Comparator_stateChanged:

.. index::
   single: state

state
+++++

This property holds the current state of the comparator.

:**› Type**: Boolean
:**› Default**: ``false``
:**› Signal**: stateChanged()
:**› Attributes**: Readonly


.. _property_Comparator_thresholdValueOff:

.. _signal_Comparator_thresholdValueOffChanged:

.. index::
   single: thresholdValueOff

thresholdValueOff
+++++++++++++++++

This property holds the lower threshold. The value of the :ref:`input <property_Comparator_input>` property has to be less or equal to this value to switch :ref:`state <property_Comparator_state>` to ``false``. If set to ``undefined`` or left blank the value of property :ref:`thresholdValueOn <property_Comparator_thresholdValueOn>` is used instead, i.e. no value hysteresis functionality is realized.

:**› Type**: Variant
:**› Signal**: thresholdValueOffChanged()
:**› Attributes**: Writable


.. _property_Comparator_thresholdValueOn:

.. _signal_Comparator_thresholdValueOnChanged:

.. index::
   single: thresholdValueOn

thresholdValueOn
++++++++++++++++

This property holds the upper threshold. The value of the :ref:`input <property_Comparator_input>` property has to be greater or equal to this value to switch :ref:`state <property_Comparator_state>` to ``true``.

:**› Type**: Variant
:**› Default**: ``0``
:**› Signal**: thresholdValueOnChanged()
:**› Attributes**: Writable


.. _property_Comparator_timerIntervalOff:

.. _signal_Comparator_timerIntervalOffChanged:

.. index::
   single: timerIntervalOff

timerIntervalOff
++++++++++++++++

This property holds the time in milliseconds for which :ref:`input <property_Comparator_input>` has to be less or equal :ref:`thresholdValueOff <property_Comparator_thresholdValueOff>` to switch :ref:`state <property_Comparator_state>` to ``false``.

:**› Type**: SignedInteger
:**› Default**: ``0``
:**› Signal**: timerIntervalOffChanged()
:**› Attributes**: Writable


.. _property_Comparator_timerIntervalOn:

.. _signal_Comparator_timerIntervalOnChanged:

.. index::
   single: timerIntervalOn

timerIntervalOn
+++++++++++++++

This property holds the time in milliseconds for which :ref:`input <property_Comparator_input>` has to be greater or equal :ref:`thresholdValueOn <property_Comparator_thresholdValueOn>` to switch :ref:`state <property_Comparator_state>` to ``true``.

:**› Type**: SignedInteger
:**› Default**: ``0``
:**› Signal**: timerIntervalOnChanged()
:**› Attributes**: Writable

Signals
*******


.. _signal_Comparator_inputFallingEdge:

.. index::
   single: inputFallingEdge

inputFallingEdge()
++++++++++++++++++

This signal is emitted immediately whenever the :ref:`input <property_Comparator_input>` signal falls below :ref:`thresholdValueOff <property_Comparator_thresholdValueOff>` independent of any configured timer intervals. This allows using :ref:`Comparator <object_Comparator>` for falling edge detection on the input signal.



.. _signal_Comparator_inputRisingEdge:

.. index::
   single: inputRisingEdge

inputRisingEdge()
+++++++++++++++++

This signal is emitted immediately whenever the :ref:`input <property_Comparator_input>` signal exceeds :ref:`thresholdValueOn <property_Comparator_thresholdValueOn>` independent of any configured timer intervals. This allows using :ref:`Comparator <object_Comparator>` for rising edge detection on the input signal.



.. _signal_Comparator_outputFallingEdge:

.. index::
   single: outputFallingEdge

outputFallingEdge()
+++++++++++++++++++

This signal is emitted whenever the :ref:`state <property_Comparator_state>` property changes from ``true`` to ``false``. If :ref:`timerIntervalOff <property_Comparator_timerIntervalOff>` is ``0`` this signal is emitted at the same time as the :ref:`inputFallingEdge() <signal_Comparator_inputFallingEdge>` signal. Otherwise it's not emitted until the state change actually takes place. This allows using :ref:`Comparator <object_Comparator>` for falling edge detection on the output signal. If both rising and falling edges need to be detected the :ref:`stateChanged() <signal_Comparator_stateChanged>` signal can be used instead.



.. _signal_Comparator_outputRisingEdge:

.. index::
   single: outputRisingEdge

outputRisingEdge()
++++++++++++++++++

This signal is emitted whenever the :ref:`state <property_Comparator_state>` property changes from ``false`` to ``true``. If :ref:`timerIntervalOn <property_Comparator_timerIntervalOn>` is ``0`` this signal is emitted at the same time as the :ref:`inputRisingEdge() <signal_Comparator_inputRisingEdge>` signal. Otherwise it's not emitted until the state change actually takes place. This allows using :ref:`Comparator <object_Comparator>` for rising edge detection on the output signal. If both rising and falling edges need to be detected the :ref:`stateChanged() <signal_Comparator_stateChanged>` signal can be used instead.



.. _example_Comparator:


Example
*******

.. code-block:: qml

    import InCore.Foundation 2.5
    
    Application {
    
        // define fake temperature measurement with random values
        Measurement {
            id: temperature;
            data: 25
        }
    
        Timer {
            running: true
            interval: 100
            onTriggered: temperature.data += 0.5 - Math.random()
        }
    
        // simple Comparator which outputs a boolean indicating whether the temperature exceeds a given threshold
        Comparator {
            input: temperature.data
            thresholdValueOn: 30
            onOutputChanged: {
                if (output)
                    console.log("Temperature above", thresholdValueOn)
                else
                    console.log("Temperature below", thresholdValueOn)
            }
        }
    
        // define a threshold and time hysteresis
        Comparator {
            id: hystComp
            input: temperature.data
            thresholdValueOn: 30
            thresholdValueOff: 20
            timerIntervalOn: 30000
            timerIntervalOff: 15000
            onOutputRisingEdge: console.log("Temperature exceeded", thresholdValueOn, "for more than", timerIntervalOn, "seconds")
            onOutputFallingEdge: console.log("Temperature fell below", thresholdValueOff, "for more than", timerIntervalOff, "seconds")
        }
    
        // use Comparator output to count number of seconds which temperature is not in range
        Counter {
            running: hystComp.output
            interval: 1000
            onValueChanged: console.log( "Temperature outside allowed range for", value, "seconds")
        }
    }
    