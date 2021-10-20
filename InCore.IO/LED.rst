
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
  * :ref:`networkInterfaceName <property_LED_networkInterfaceName>`
  * :ref:`systemName <property_LED_systemName>`
  * :ref:`trigger <property_LED_trigger>`
  * :ref:`value <property_LED_value>`
  * :ref:`Object.objectId <property_Object_objectId>`
  * :ref:`Object.parent <property_Object_parent>`

Methods
+++++++

.. hlist::
  :columns: 1

  * :ref:`toggle() <method_LED_toggle>`
  * :ref:`Object.deserializeProperties() <method_Object_deserializeProperties>`
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
  * :ref:`Trigger <enum_LED_Trigger>`



Properties
**********


.. _property_LED_index:

.. _signal_LED_indexChanged:

.. index::
   single: index

index
+++++

This property holds the index of the LED which to control through the object instance. If :ref:`systemName <property_LED_systemName>` is set, this property is ignored.

:**› Type**: :ref:`Index <enum_LED_Index>`
:**› Default**: :ref:`LED.None <enumitem_LED_None>`
:**› Signal**: indexChanged()
:**› Attributes**: Writable


.. _property_LED_networkInterfaceName:

.. _signal_LED_networkInterfaceNameChanged:

.. index::
   single: networkInterfaceName

networkInterfaceName
++++++++++++++++++++

This property holds the name of the network interface (i.e. :ref:`NetworkInterface.hardwareName <property_NetworkInterface_hardwareName>`) which to indicate traffic for.

This property was introduced in InCore 2.5.

:**› Type**: String
:**› Signal**: networkInterfaceNameChanged()
:**› Attributes**: Writable


.. _property_LED_systemName:

.. _signal_LED_systemNameChanged:

.. index::
   single: systemName

systemName
++++++++++

This property holds the system name of the LED (i.e. the name of the corresponding entry in ``/sys/class/leds/``) which to control through the object instance. This property takes precedence over :ref:`index <property_LED_index>`.

This property was introduced in InCore 2.5.

:**› Type**: String
:**› Signal**: systemNameChanged()
:**› Attributes**: Writable


.. _property_LED_trigger:

.. _signal_LED_triggerChanged:

.. index::
   single: trigger

trigger
+++++++

This property holds a trigger which controls the LED at the system level automatically. See the :ref:`LED.Trigger <enum_LED_Trigger>` enumeration for details.

This property was introduced in InCore 2.5.

:**› Type**: :ref:`Trigger <enum_LED_Trigger>`
:**› Default**: :ref:`LED.NoTrigger <enumitem_LED_NoTrigger>`
:**› Signal**: triggerChanged()
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


.. _enum_LED_Trigger:

.. index::
   single: Trigger

Trigger
+++++++

This enumeration describes the supported triggers for controlling LEDs at the system level. A trigger makes the configured LED flash on certain events or under certain conditions.

This enumeration was introduced in InCore 2.5.

.. index::
   single: LED.NoTrigger
.. index::
   single: LED.Heartbeat
.. index::
   single: LED.StorageAccess
.. index::
   single: LED.NetworkTraffic
.. index::
   single: LED.SystemActivity
.. list-table::
  :widths: auto
  :header-rows: 1

  * - Name
    - Value
    - Description

      .. _enumitem_LED_NoTrigger:
  * - ``LED.NoTrigger``
    - ``0``
    - No trigger configured.

      .. _enumitem_LED_Heartbeat:
  * - ``LED.Heartbeat``
    - ``1``
    - A trigger indicating a running system as well as the system load.

      .. _enumitem_LED_StorageAccess:
  * - ``LED.StorageAccess``
    - ``2``
    - A trigger indicating access to the local storage (MMC/NAND).

      .. _enumitem_LED_NetworkTraffic:
  * - ``LED.NetworkTraffic``
    - ``3``
    - A trigger indicating traffic at a certain network interface (:ref:`networkInterfaceName <property_LED_networkInterfaceName>`).

      .. _enumitem_LED_SystemActivity:
  * - ``LED.SystemActivity``
    - ``4``
    - A trigger indicating any kind of CPU usage.


.. _example_LED:


Example
*******

.. code-block:: qml

    import InCore.Foundation 2.5
    import InCore.IO 2.5
    
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
    