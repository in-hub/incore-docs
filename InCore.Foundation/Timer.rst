
.. _object_Timer:


:index:`Timer`
--------------

Description
***********

The Timer object implements a timer which triggers periodically or only once. Property :ref:`repeat <property_Timer_repeat>` controls the behaviour.

:**› Inherits**: :ref:`Object <object_Object>`

Overview
********

Properties
++++++++++

.. hlist::
  :columns: 2

  * :ref:`interval <property_Timer_interval>`
  * :ref:`msecsElapsed <property_Timer_msecsElapsed>`
  * :ref:`repeat <property_Timer_repeat>`
  * :ref:`running <property_Timer_running>`
  * :ref:`synchronize <property_Timer_synchronize>`
  * :ref:`timestamp <property_Timer_timestamp>`
  * :ref:`triggeredOnStart <property_Timer_triggeredOnStart>`
  * :ref:`triggeredOnStop <property_Timer_triggeredOnStop>`
  * :ref:`Object.objectId <property_Object_objectId>`
  * :ref:`Object.parent <property_Object_parent>`

Methods
+++++++

.. hlist::
  :columns: 2

  * :ref:`restart() <method_Timer_restart>`
  * :ref:`singleShot() <method_Timer_singleShot>`
  * :ref:`start() <method_Timer_start>`
  * :ref:`stop() <method_Timer_stop>`
  * :ref:`Object.deserializeProperties() <method_Object_deserializeProperties>`
  * :ref:`Object.fromJson() <method_Object_fromJson>`
  * :ref:`Object.serializeProperties() <method_Object_serializeProperties>`
  * :ref:`Object.toJson() <method_Object_toJson>`

Signals
+++++++

.. hlist::
  :columns: 1

  * :ref:`triggered() <signal_Timer_triggered>`
  * :ref:`Object.completed() <signal_Object_completed>`



Properties
**********


.. _property_Timer_interval:

.. _signal_Timer_intervalChanged:

.. index::
   single: interval

interval
++++++++

This property holds the interval which elapses before :ref:`triggered() <signal_Timer_triggered>` is emitted. The minimum value is ``1``.

:**› Type**: SignedInteger
:**› Default**: ``0``
:**› Signal**: intervalChanged()
:**› Attributes**: Writable


.. _property_Timer_msecsElapsed:

.. _signal_Timer_msecsElapsedChanged:

.. index::
   single: msecsElapsed

msecsElapsed
++++++++++++

This property holds returns the number of milliseconds since this timer was last started.

:**› Type**: SignedBigInteger
:**› Signal**: msecsElapsedChanged()
:**› Attributes**: Readonly


.. _property_Timer_repeat:

.. _signal_Timer_repeatChanged:

.. index::
   single: repeat

repeat
++++++

This property holds whether the timer triggers only once (:ref:`repeat <property_Timer_repeat>` set to ``false``) or repeatedly.

:**› Type**: Boolean
:**› Default**: ``true``
:**› Signal**: repeatChanged()
:**› Attributes**: Writable


.. _property_Timer_running:

.. _signal_Timer_runningChanged:

.. index::
   single: running

running
+++++++

This property holds whether the timer is running. Setting this property equals to calling :ref:`start() <method_Timer_start>` or :ref:`stop() <method_Timer_stop>`.

:**› Type**: Boolean
:**› Default**: ``true``
:**› Signal**: runningChanged()
:**› Attributes**: Writable


.. _property_Timer_synchronize:

.. _signal_Timer_synchronizeChanged:

.. index::
   single: synchronize

synchronize
+++++++++++

This property holds whether the timer should be synchronized to the system clock. When synchronized the actual timer start will be delayed such that the trigger time is a multiple of :ref:`interval <property_Timer_interval>` beginning at midnight UTC.

This property was introduced in InCore 2.7.

:**› Type**: Boolean
:**› Default**: ``false``
:**› Signal**: synchronizeChanged()
:**› Attributes**: Writable


.. _property_Timer_timestamp:

.. _signal_Timer_timestampChanged:

.. index::
   single: timestamp

timestamp
+++++++++

This property holds a timestamp in milliseconds of the last :ref:`triggered() <signal_Timer_triggered>` signal emission.

This property was introduced in InCore 2.7.

:**› Type**: SignedBigInteger
:**› Signal**: timestampChanged()
:**› Attributes**: Readonly


.. _property_Timer_triggeredOnStart:

.. _signal_Timer_triggeredOnStartChanged:

.. index::
   single: triggeredOnStart

triggeredOnStart
++++++++++++++++

This property holds whether the timer sends a :ref:`triggered() <signal_Timer_triggered>` signal when the timer is started.

:**› Type**: Boolean
:**› Default**: ``false``
:**› Signal**: triggeredOnStartChanged()
:**› Attributes**: Writable


.. _property_Timer_triggeredOnStop:

.. _signal_Timer_triggeredOnStopChanged:

.. index::
   single: triggeredOnStop

triggeredOnStop
+++++++++++++++

This property holds whether the timer sends a :ref:`triggered() <signal_Timer_triggered>` signal after the timer is stopped.

:**› Type**: Boolean
:**› Default**: ``false``
:**› Signal**: triggeredOnStopChanged()
:**› Attributes**: Writable

Methods
*******


.. _method_Timer_restart:

.. index::
   single: restart

restart()
+++++++++

This method restarts the timer. This is the same as calling :ref:`stop() <method_Timer_stop>` and :ref:`start() <method_Timer_start>` consecutively.



.. _method_Timer_singleShot:

.. index::
   single: singleShot

singleShot(SignedInteger msec, JSValue method)
++++++++++++++++++++++++++++++++++++++++++++++

This method calls the given method (e.g. lambda) after the specified number of milliseconds.

This method was introduced in InCore 2.7.



.. _method_Timer_start:

.. index::
   single: start

start()
+++++++

This method starts the timer. This is equal to setting :ref:`running <property_Timer_running>` to ``true``.



.. _method_Timer_stop:

.. index::
   single: stop

stop()
++++++

This method stops the timer. This is equal to setting :ref:`running <property_Timer_running>` to ``false``.


Signals
*******


.. _signal_Timer_triggered:

.. index::
   single: triggered

triggered()
+++++++++++

This signal is emitted when the timer timed out, i.e. the configured :ref:`interval <property_Timer_interval>` has elapsed since the last start or last timeout.



.. _example_Timer:


Example
*******

.. code-block:: qml

    import InCore.Foundation 2.7
    
    Application {
    
        onCompleted: {
            testTimer.singleShot(5000, () => { console.log("I was called through Timer.singleShot()") })
        }
    
        //minimal Timer with default values
        Timer {
            onTriggered: console.log( "i am a minimal Timer" )
        }
    
        Timer {
            repeat: false
            interval: 10000
            onTriggered: console.log( "i trigger only once after a while" )
        }
    
        Timer {
            id: testTimer
            interval: 500
            onTriggered: console.log( "i am running fast" )
        }
    
        Timer {
            id: onOffTimer
            interval: 2000
            onTriggered: {
                console.log( "switching testTimer", testTimer.running ? "off" : "on" )
                testTimer.running = !testTimer.running
            }
        }
    }
    