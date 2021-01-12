.. _AnalogDigitalIOTutorial:

Analog & Digital I/O Tutorial
=============================

The :ref:`BlinkingLedTutorial` demonstrates how to use a :ref:`object_Timer` in combination with an :ref:`object_LED` object. In this tutorial we want explore further I/O mechanisms. The HUB-GM100 device has several analog inputs and digital I/Os which we want to integrate in this tutorial. You should prepare a current source which provides a configurable current in the range of 4…20 mA and connect it to the first analog input of the device.

The first analog input can be accessed through an :ref:`object_AnalogInput` object which we configure as a 4…20 mA analog input:

.. code-block:: qml

    import InCore.Foundation 2.2
    import InCore.IO 2.2

    Application {
        AnalogInput {
            index: AnalogInput.AIN1
            mode: AnalogInput.Mode20mA
        }
    }

The application so far consists of the analog input definition only and does nothing. Next we want to print the current measured by the analog input on the console whenever it changes:

.. code-block:: qml

    import InCore.Foundation 2.2
    import InCore.IO 2.2

    Application {
        AnalogInput {
            index: AnalogInput.AIN1
            mode: AnalogInput.Mode20mA
            onCurrentChanged: console.log(current)
        }
    }

This application does nothing since the :ref:`object_AnalogInput` object needs to be told when to actually read a new value from the underlying (12 bit) ADC. This is where the :ref:`object_Polling` object comes into play. It allows polling special polled properties such as :ref:`AnalogInput.value <property_AnalogInput_value>`:

.. code-block:: qml

    import InCore.Foundation 2.2
    import InCore.IO 2.2

    Application {
        AnalogInput {
            index: AnalogInput.AIN1
            mode: AnalogInput.Mode20mA
            onCurrentChanged: console.log(current)
            Polling on value { }
        }
    }

Run this program, play with the current of your source and observe the output.

Per default the :ref:`object_Polling` object polls its target property every 1000 milliseconds. This can be changed easily by setting the :ref:`Polling.interval <property_Polling_interval>` property:

.. code-block:: qml

    import InCore.Foundation 2.2
    import InCore.IO 2.2

    Application {
        AnalogInput {
            index: AnalogInput.AIN1
            mode: AnalogInput.Mode20mA
            onCurrentChanged: console.log(current)
            Polling on value { interval: 200 }
        }
    }

This version polls the analog input value every 200 milliseconds and prints the converted current on the console whenever it changes.

Instead of just printing a value we can use it for threshold detection. In the most simple case the red LED of the HUB-GM100 can be switched on if a certain threshold is exceeded:

.. code-block:: qml

    import InCore.Foundation 2.2
    import InCore.IO 2.2

    Application {
        AnalogInput {
            id: ain1
            index: AnalogInput.AIN1
            mode: AnalogInput.Mode20mA
            Polling on value { interval: 200 }
        }
        LED {
            index: LED.StatusRed
            value: ain1.current > 10
        }
    }

This application makes the red LED flash whenever the analog input exceeds 10 mA. The code demonstrates how to link two objects in a declarative manner and should give you an initial idea of how QML works. In traditional microcontroller programs you have to implement a timer routine, trigger an ADC conversion, compare the result imperatively and turn on or off the LED manually. Here all magic happens by simply using a :ref:`object_Polling` object and binding the QML expression ``ain1.current > 10`` to the :ref:`LED.value <property_LED_value>` property. All expressions are re-evaluated whenever parts of it change or are updated, e.g. object properties or variables.

Changing the code to control a digital output instead of an LED is quite simple:

.. code-block:: qml

    import InCore.Foundation 2.2
    import InCore.IO 2.2

    Application {
        AnalogInput {
            id: ain1
            index: AnalogInput.AIN1
            mode: AnalogInput.Mode20mA
            Polling on value { interval: 200 }
        }
        DigitalIO {
            index: DigitalIO.IO1
            direction: DigitalIO.Output
            value: ain1.current > 10
        }
    }

The last challenge in this tutorial is to implement a time-controlled threshold detection, i.e. only switch on the digital output if the threshold is exceeded for longer than 3 seconds. We already know :ref:`object_Timer` from the first tutorial. Therefor we could add two non-repeating :ref:`object_Timer` objects and restart them whenever the AIN value goes below or above the threshold:

.. code-block:: qml

    import InCore.Foundation 2.2
    import InCore.IO 2.2

    Application {
        AnalogInput {
            id: ain1
            index: AnalogInput.AIN1
            mode: AnalogInput.Mode20mA
            Polling on value { interval: 200 }
        }
        DigitalIO {
            id: dout1
            index: DigitalIO.IO1
            direction: DigitalIO.Output
        }
        Timer {
            id: startTimer
            running: ain1.current > 10
            interval: 3000
            repeat: false
            onTriggered: dout1.value = true
        }
        Timer {
            id: stopTimer
            running: ain1.current <= 10
            interval: 3000
            repeat: false
            onTriggered: dout1.value = false
        }
    }

This initial version works but is not very QML-like since it contains similar redundant property initializations and even requires two signal handler functions. Anyway we can do better thanks to the :ref:`object_Comparator` object:

.. code-block:: qml

    import InCore.Foundation 2.2
    import InCore.IO 2.2

    Application {
        AnalogInput {
            id: ain1
            index: AnalogInput.AIN1
            mode: AnalogInput.Mode20mA
            Polling on value { interval: 200 }
        }
        Comparator {
            id: comp
            input: ain1.current
            thresholdValueOn: 10
            timerIntervalOn: 3000
        }
        DigitalIO {
            id: dout1
            index: DigitalIO.IO1
            direction: DigitalIO.Output
            value: comp.output
        }
    }

The comparator changes its :ref:`output <property_Comparator_output>` to ``true`` if the input value exceeds the on-threshold for longer than :ref:`Comparator.timerIntervalOn <property_Comparator_timerIntervalOn>` milliseconds. The output of the comparator finally is bound to the :ref:`DigitalIO.value <property_DigitalIO_value>` property.
