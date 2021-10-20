
.. _object_Counter:


:index:`Counter`
----------------

Description
***********

The Counter object provides a basic counter functionality. It increments the :ref:`value <property_Counter_value>` property periodically depending on the configured :ref:`interval <property_Counter_interval>`. It's also possible to count backwards by setting the :ref:`increment <property_Counter_increment>` property to a negative value and optionally setting the :ref:`startValue <property_Counter_startValue>` property.

:**› Inherits**: :ref:`Object <object_Object>`

Overview
********

Properties
++++++++++

.. hlist::
  :columns: 1

  * :ref:`increment <property_Counter_increment>`
  * :ref:`interval <property_Counter_interval>`
  * :ref:`running <property_Counter_running>`
  * :ref:`startValue <property_Counter_startValue>`
  * :ref:`value <property_Counter_value>`
  * :ref:`Object.objectId <property_Object_objectId>`
  * :ref:`Object.parent <property_Object_parent>`

Methods
+++++++

.. hlist::
  :columns: 1

  * :ref:`reset() <method_Counter_reset>`
  * :ref:`Object.deserializeProperties() <method_Object_deserializeProperties>`
  * :ref:`Object.fromJson() <method_Object_fromJson>`
  * :ref:`Object.toJson() <method_Object_toJson>`

Signals
+++++++

.. hlist::
  :columns: 1

  * :ref:`Object.completed() <signal_Object_completed>`



Properties
**********


.. _property_Counter_increment:

.. _signal_Counter_incrementChanged:

.. index::
   single: increment

increment
+++++++++

This property holds the number by which :ref:`value <property_Counter_value>` is incremented each period. It can be both positive and negative. Negative values will make the counter count backwards.

:**› Type**: SignedInteger
:**› Default**: ``1``
:**› Signal**: incrementChanged()
:**› Attributes**: Writable, Optional


.. _property_Counter_interval:

.. _signal_Counter_intervalChanged:

.. index::
   single: interval

interval
++++++++

This property holds the counter interval in milliseconds. The interval has to be greater than ``0`` in order to make the counter work properly. Additionally :ref:`running <property_Counter_running>` has to be ``true``.

:**› Type**: SignedInteger
:**› Default**: ``1000``
:**› Signal**: intervalChanged()
:**› Attributes**: Writable


.. _property_Counter_running:

.. _signal_Counter_runningChanged:

.. index::
   single: running

running
+++++++

This property holds whether the counter is running. Changing this property does not reset the counter's :ref:`value <property_Counter_value>`.

:**› Type**: Boolean
:**› Default**: ``true``
:**› Signal**: runningChanged()
:**› Attributes**: Writable


.. _property_Counter_startValue:

.. _signal_Counter_startValueChanged:

.. index::
   single: startValue

startValue
++++++++++

This property holds the start value which the :ref:`value <property_Counter_value>` property is initialized on start and every :ref:`reset() <method_Counter_reset>`. Changing this value has no effect on running counters until :ref:`reset() <method_Counter_reset>` is called.

:**› Type**: SignedInteger
:**› Default**: ``0``
:**› Signal**: startValueChanged()
:**› Attributes**: Writable


.. _property_Counter_value:

.. _signal_Counter_valueChanged:

.. index::
   single: value

value
+++++

This property holds the current value of the counter. On initial start and on every :ref:`reset() <method_Counter_reset>` the property is set to :ref:`startValue <property_Counter_startValue>`. It is incremented by :ref:`increment <property_Counter_increment>` every :ref:`interval <property_Counter_interval>` milliseconds.

:**› Type**: SignedBigInteger
:**› Default**: ``0``
:**› Signal**: valueChanged()
:**› Attributes**: Readonly

Methods
*******


.. _method_Counter_reset:

.. index::
   single: reset

reset()
+++++++

This method resets the counter by setting the :ref:`value <property_Counter_value>` back to :ref:`startValue <property_Counter_startValue>`. It can be called on both stopped and running counters. Running counters will continue to run after being reset.



.. _example_Counter:


Example
*******

.. code-block:: qml

    import InCore.Foundation 2.5
    import InCore.IO 2.5
    
    Application {
    
        DigitalIO {
            id: input
            direction: DigitalIO.Input
            index: DigitalIO.IO1
        }
    
        Counter {
            id: secCounter
            interval: 100 //10 per second
            running: input.value
            startValue: 0 //default
            onValueChanged: console.log( ( "input were %1 seconds on" ).arg( input.value / 10. ) )
        }
    }
    