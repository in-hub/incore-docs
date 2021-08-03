
.. _object_DigitalIO:


:index:`DigitalIO`
------------------

Description
***********

The DigitalIO object allows reading digital input signal or writing digital output signal.

:**› Inherits**: :ref:`Object <object_Object>`

Overview
********

Properties
++++++++++

.. hlist::
  :columns: 2

  * :ref:`direction <property_DigitalIO_direction>`
  * :ref:`error <property_DigitalIO_error>`
  * :ref:`errorString <property_DigitalIO_errorString>`
  * :ref:`index <property_DigitalIO_index>`
  * :ref:`inputValue <property_DigitalIO_inputValue>`
  * :ref:`openDrainFault <property_DigitalIO_openDrainFault>`
  * :ref:`outputValue <property_DigitalIO_outputValue>`
  * :ref:`value <property_DigitalIO_value>`
  * :ref:`Object.objectId <property_Object_objectId>`
  * :ref:`Object.parent <property_Object_parent>`

Methods
+++++++

.. hlist::
  :columns: 1

  * :ref:`pollInputValue() <method_DigitalIO_pollInputValue>`
  * :ref:`pollOpenDrainFault() <method_DigitalIO_pollOpenDrainFault>`
  * :ref:`pollValue() <method_DigitalIO_pollValue>`
  * :ref:`Object.deserializeProperties() <method_Object_deserializeProperties>`
  * :ref:`Object.fromJson() <method_Object_fromJson>`
  * :ref:`Object.toJson() <method_Object_toJson>`

Signals
+++++++

.. hlist::
  :columns: 1

  * :ref:`errorOccurred() <signal_DigitalIO_errorOccurred>`
  * :ref:`Object.completed() <signal_Object_completed>`

Enumerations
++++++++++++

.. hlist::
  :columns: 1

  * :ref:`Direction <enum_DigitalIO_Direction>`
  * :ref:`Error <enum_DigitalIO_Error>`
  * :ref:`Index <enum_DigitalIO_Index>`



Properties
**********


.. _property_DigitalIO_direction:

.. _signal_DigitalIO_directionChanged:

.. index::
   single: direction

direction
+++++++++

This property holds the direction of the IO. This property has to be set to work properly.

:**› Type**: :ref:`Direction <enum_DigitalIO_Direction>`
:**› Default**: :ref:`DigitalIO.Input <enumitem_DigitalIO_Input>`
:**› Signal**: directionChanged()
:**› Attributes**: Writable


.. _property_DigitalIO_error:

.. _signal_DigitalIO_errorChanged:

.. index::
   single: error

error
+++++

This property holds the most recently occurred error or :ref:`DigitalIO.NoError <enumitem_DigitalIO_NoError>` if no error occurred. If the same error occurs multiple times this property does not change. Use the :ref:`errorOccurred() <signal_DigitalIO_errorOccurred>` signal to detect multiple occurrences of the same error.

:**› Type**: :ref:`Error <enum_DigitalIO_Error>`
:**› Signal**: errorChanged()
:**› Attributes**: Readonly


.. _property_DigitalIO_errorString:

.. _signal_DigitalIO_errorStringChanged:

.. index::
   single: errorString

errorString
+++++++++++

This property holds the current human readable error string corresponding to the current value in the :ref:`error <property_DigitalIO_error>` property. It may include additional information such as failure reasons or locations.

:**› Type**: String
:**› Signal**: errorStringChanged()
:**› Attributes**: Readonly


.. _property_DigitalIO_index:

.. _signal_DigitalIO_indexChanged:

.. index::
   single: index

index
+++++

This property holds the index of the IO. This property has to be set to work properly.

:**› Type**: :ref:`Index <enum_DigitalIO_Index>`
:**› Default**: :ref:`DigitalIO.Invalid <enumitem_DigitalIO_Invalid>`
:**› Signal**: indexChanged()
:**› Attributes**: Writable


.. _property_DigitalIO_inputValue:

.. _signal_DigitalIO_inputValueChanged:

.. index::
   single: inputValue

inputValue
++++++++++

This property holds the value measured at the digital input if :ref:`direction <property_DigitalIO_direction>` is set to :ref:`DigitalIO.Input <enumitem_DigitalIO_Input>` and the property has been polled.

This property was introduced in InCore 2.1.

:**› Type**: Boolean
:**› Signal**: inputValueChanged()
:**› Attributes**: Readonly, Requires :ref:`Polling <object_Polling>`


.. _property_DigitalIO_openDrainFault:

.. _signal_DigitalIO_openDrainFaultChanged:

.. index::
   single: openDrainFault

openDrainFault
++++++++++++++

This property holds the current state of the Open-Drain Fault pin (HUB-GM200 only).

This property was introduced in InCore 2.0.

:**› Type**: Boolean
:**› Signal**: openDrainFaultChanged()
:**› Attributes**: Readonly, Requires :ref:`Polling <object_Polling>`


.. _property_DigitalIO_outputValue:

.. _signal_DigitalIO_outputValueChanged:

.. index::
   single: outputValue

outputValue
+++++++++++

This property holds the value to which the digital output is set if :ref:`direction <property_DigitalIO_direction>` is set to :ref:`DigitalIO.Output <enumitem_DigitalIO_Output>`.

This property was introduced in InCore 2.1.

:**› Type**: Boolean
:**› Default**: ``false``
:**› Signal**: outputValueChanged()
:**› Attributes**: Writable


.. _property_DigitalIO_value:

.. _signal_DigitalIO_valueChanged:

.. index::
   single: value

value
+++++

This property holds the value which to set :ref:`outputValue <property_DigitalIO_outputValue>` to when writing this property or the current value of the :ref:`inputValue <property_DigitalIO_inputValue>` property when reading the property. It is recommended to read or write the direction-specific properties explicitely instead.

:**› Type**: Boolean
:**› Default**: ``false``
:**› Signal**: valueChanged()
:**› Attributes**: Writable, Requires :ref:`Polling <object_Polling>`

Methods
*******


.. _method_DigitalIO_pollInputValue:

.. index::
   single: pollInputValue

pollInputValue()
++++++++++++++++

This method polls the :ref:`inputValue <property_DigitalIO_inputValue>` property. It is called automatically when using a :ref:`Polling <object_Polling>` property modifier on this property and usually does not have to be called manually.



.. _method_DigitalIO_pollOpenDrainFault:

.. index::
   single: pollOpenDrainFault

pollOpenDrainFault()
++++++++++++++++++++

This method polls the :ref:`openDrainFault <property_DigitalIO_openDrainFault>` property. It is called automatically when using a :ref:`Polling <object_Polling>` property modifier on this property and usually does not have to be called manually.



.. _method_DigitalIO_pollValue:

.. index::
   single: pollValue

pollValue()
+++++++++++

This method polls the :ref:`value <property_DigitalIO_value>` property. It is called automatically when using a :ref:`Polling <object_Polling>` property modifier on this property and usually does not have to be called manually. This method only works if :ref:`direction <property_DigitalIO_direction>` is set to :ref:`DigitalIO.Input <enumitem_DigitalIO_Input>`.


Signals
*******


.. _signal_DigitalIO_errorOccurred:

.. index::
   single: errorOccurred

errorOccurred()
+++++++++++++++

This signal is emitted whenever an error has occurred, regardless of whether the :ref:`error <property_DigitalIO_error>` property has changed or not. In contrast to the change notification signal of the :ref:`error <property_DigitalIO_error>` property this signal is also emitted several times if a certain error occurs several times in succession.


Enumerations
************


.. _enum_DigitalIO_Direction:

.. index::
   single: Direction

Direction
+++++++++

This enumeration describes the supported directions for the digital IO interface.

.. index::
   single: DigitalIO.Input
.. index::
   single: DigitalIO.Output
.. list-table::
  :widths: auto
  :header-rows: 1

  * - Name
    - Value
    - Description

      .. _enumitem_DigitalIO_Input:
  * - ``DigitalIO.Input``
    - ``0``
    - The IO is used as an input.

      .. _enumitem_DigitalIO_Output:
  * - ``DigitalIO.Output``
    - ``1``
    - The IO is used as an output.


.. _enum_DigitalIO_Error:

.. index::
   single: Error

Error
+++++

This enumeration describes all errors which can occur in DigitalIO objects. The most recently occurred error is stored in the :ref:`error <property_DigitalIO_error>` property.

.. index::
   single: DigitalIO.NoError
.. index::
   single: DigitalIO.HardwareDriverNotAvailable
.. index::
   single: DigitalIO.ConfigurationError
.. index::
   single: DigitalIO.OutputError
.. list-table::
  :widths: auto
  :header-rows: 1

  * - Name
    - Value
    - Description

      .. _enumitem_DigitalIO_NoError:
  * - ``DigitalIO.NoError``
    - ``0``
    - No error occurred or was detected.

      .. _enumitem_DigitalIO_HardwareDriverNotAvailable:
  * - ``DigitalIO.HardwareDriverNotAvailable``
    - ``1``
    - No hardware driver available for the current platform.

      .. _enumitem_DigitalIO_ConfigurationError:
  * - ``DigitalIO.ConfigurationError``
    - ``2``
    - Error while configuring DIO pins.

      .. _enumitem_DigitalIO_OutputError:
  * - ``DigitalIO.OutputError``
    - ``3``
    - Error while setting the output pin.


.. _enum_DigitalIO_Index:

.. index::
   single: Index

Index
+++++

This enumeration describes the supported digital input indexes.

.. index::
   single: DigitalIO.Invalid
.. index::
   single: DigitalIO.IO1
.. index::
   single: DigitalIO.IO2
.. index::
   single: DigitalIO.IO3
.. index::
   single: DigitalIO.IO4
.. index::
   single: DigitalIO.IO5
.. index::
   single: DigitalIO.IO6
.. list-table::
  :widths: auto
  :header-rows: 1

  * - Name
    - Value
    - Description

      .. _enumitem_DigitalIO_Invalid:
  * - ``DigitalIO.Invalid``
    - ``0``
    - No index assigned.

      .. _enumitem_DigitalIO_IO1:
  * - ``DigitalIO.IO1``
    - ``1``
    - The 1st digital IO.

      .. _enumitem_DigitalIO_IO2:
  * - ``DigitalIO.IO2``
    - ``2``
    - The 2nd digital IO.

      .. _enumitem_DigitalIO_IO3:
  * - ``DigitalIO.IO3``
    - ``3``
    - The 3rd digital IO (only HUB-GM200 and newer).

      .. _enumitem_DigitalIO_IO4:
  * - ``DigitalIO.IO4``
    - ``4``
    - The 4th digital IO (only HUB-GM200 and newer).

      .. _enumitem_DigitalIO_IO5:
  * - ``DigitalIO.IO5``
    - ``5``
    - The 5th digital IO (only HUB-GM200 and newer).

      .. _enumitem_DigitalIO_IO6:
  * - ``DigitalIO.IO6``
    - ``6``
    - The 6th digital IO (only HUB-GM200 and newer).


.. _example_DigitalIO:


Example
*******

.. code-block:: qml

    import InCore.Foundation 2.2
    import InCore.IO 2.2
    
    Application {
    
        DigitalIO {
            id: digitalInput
            index: DigitalIO.IO1
            direction: DigitalIO.Input
            Polling on inputValue { interval: 100 }
            onInputValueChanged: console.log("IO1 changed to", inputValue)
            EdgeDetector on inputValue {
                onRisingEdge: console.log("Rising edge detected")
            }
        }
    
        // output inverted signal of digital input
        DigitalIO {
            id: digitalOutput
            index: DigitalIO.IO2
            direction: DigitalIO.Output
            value: !digitalInput.value
        }
    
    }
    
    