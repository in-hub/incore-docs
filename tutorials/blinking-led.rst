.. _BlinkingLedTutorial:

Blinking LED Tutorial
=====================

The minimal hello world example from the :ref:`Development Manual <DevelopmentManual>` can be enhanced easily to make use of the I/O capabilities of a HUB-GM100. In general all I/O-related objects are part of the :ref:`InCore IO <module_IO>` module:

.. code-block:: qml

    import InCore.IO 2.0

Instead of printing a message on the console, the blue LED of the HUB-GM100 can be turned on using the following code:

.. code-block:: qml

    import InCore.Foundation 2.0
    import InCore.IO 2.0

    Application {
        LED {
            index: LED.StatusBlue
            value: true
        }
    }

The :ref:`index <property_LED_index>` property indicates which LED of a HUB-GM100 to represent and control by this particular object. The actual state of the LED is controlled through the :ref:`value <property_LED_value>` property.

Turning on an LED is not very spectacular so let's make things a little more dynamic:

.. code-block:: qml

    import InCore.Foundation 2.0
    import InCore.IO 2.0

    Application {

        LED {
            id: blueLed
            index: LED.StatusBlue
        }

        // toggle blue LED every 500 ms
        Timer {
            interval: 500
            onTriggered: {
                blueLed.toggle()
            }
        }
    }

This adds an ID to the LED (``blueLed``). An object ID is a name by which the object and its properties can be referenced throughout the whole program. The new :ref:`Timer <object_Timer>` instance is configured to trigger every 500 ms. A simple code block is attached to the :ref:`triggered <signal_Timer_triggered>` signal. It does nothing but calling the :ref:`toggle() <method_LED_toggle>` method of the LED.

