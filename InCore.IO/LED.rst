
.. _object_LED:


:index:`LED`
------------

Description
***********

The LED object represents an LED attached to the device. It allows turning on/off or toggling an LED.

This object was introduced in InCore 2.0.

:**› Inherits**: :ref:`Object <object_Object>`

Overview
********

Properties
++++++++++

.. hlist::
  :columns: 1

  * :ref:`index <property_LED_index>`
  * :ref:`value <property_LED_value>`
  * :ref:`Object.objectId <property_Object_objectId>`
  * :ref:`Object.parent <property_Object_parent>`

Methods
+++++++

.. hlist::
  :columns: 1

  * :ref:`toggle() <method_LED_toggle>`
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

  * :ref:`Index <enum_LED_Index>`



Properties
**********


.. _property_LED_index:

.. _signal_LED_indexChanged:

.. index::
   single: index

index
+++++

This property holds the index of the LED which to control through the current instance.

:**› Type**: :ref:`Index <enum_LED_Index>`
:**› Default**: :ref:`LED.None <enumitem_LED_None>`
:**› Signal**: indexChanged()
:**› Attributes**: Writable


.. _property_LED_value:

.. _signal_LED_valueChanged:

.. index::
   single: value

value
+++++

This property holds the desired state of the LED.

:**› Type**: Boolean
:**› Default**: ``false``
:**› Signal**: valueChanged()
:**› Attributes**: Writable

Methods
*******


.. _method_LED_toggle:

.. index::
   single: toggle

toggle()
++++++++

This method toggles the current state of the LED, i.e. inverts the :ref:`value <property_LED_value>` property.


Enumerations
************


.. _enum_LED_Index:

.. index::
   single: Index

Index
+++++

This enumeration describes the supported LED indexes.

.. index::
   single: LED.None
.. index::
   single: LED.StatusRed
.. index::
   single: LED.StatusGreen
.. index::
   single: LED.StatusBlue
.. list-table::
  :widths: auto
  :header-rows: 1

  * - Name
    - Value
    - Description

      .. _enumitem_LED_None:
  * - ``LED.None``
    - ``0``
    - No valid LED configured.

      .. _enumitem_LED_StatusRed:
  * - ``LED.StatusRed``
    - ``1``
    - The red status LED.

      .. _enumitem_LED_StatusGreen:
  * - ``LED.StatusGreen``
    - ``2``
    - The green status LED.

      .. _enumitem_LED_StatusBlue:
  * - ``LED.StatusBlue``
    - ``3``
    - The blue status LED.


.. _example_LED:


Example
*******

.. code-block:: qml

    import InCore.Foundation 2.0
    import InCore.IO 2.0
    
    Application {
    
        LED {
            id: blueLed
            index: LED.StatusBlue
        }
    
        // toggle blue LED every 1000 ms
        Timer {
            onTriggered: blueLed.toggle()
        }
    
        AnalogInput {
            id: ain
            index: AnalogInput.AIN1
            mode: AnalogInput.Mode10V
            Polling on value { }
        }
    
        // turn on red LED if AIN1 exceeds 5 V
        LED {
            index: LED.StatusRed
            value: ain.value > 2048
        }
    }
    