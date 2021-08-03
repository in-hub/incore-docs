
.. _object_EnergyAddonEN100:


:index:`EnergyAddonEN100`
-------------------------

Description
***********

The EnergyAddonEN100 object represents an Energy Addon EN100 device on the backplane bus and can be used for retrieving measurements through :ref:`EnergyAddonChannel <object_EnergyAddonChannel>` objects.

:**› Inherits**: :ref:`BackplaneBusDevice <object_BackplaneBusDevice>`

Overview
********

Properties
++++++++++

.. hlist::
  :columns: 2

  * :ref:`channels <property_EnergyAddonEN100_channels>`
  * :ref:`operatingHours <property_EnergyAddonEN100_operatingHours>`
  * :ref:`supplyVoltage <property_EnergyAddonEN100_supplyVoltage>`
  * :ref:`temperature <property_EnergyAddonEN100_temperature>`
  * :ref:`BackplaneBusDevice.address <property_BackplaneBusDevice_address>`
  * :ref:`BackplaneBusDevice.online <property_BackplaneBusDevice_online>`
  * :ref:`BackplaneBusDevice.productId <property_BackplaneBusDevice_productId>`
  * :ref:`BackplaneBusDevice.serialNumber <property_BackplaneBusDevice_serialNumber>`
  * :ref:`Object.objectId <property_Object_objectId>`
  * :ref:`Object.parent <property_Object_parent>`

Methods
+++++++

.. hlist::
  :columns: 2

  * :ref:`pollChannels() <method_EnergyAddonEN100_pollChannels>`
  * :ref:`pollEnabledChannels() <method_EnergyAddonEN100_pollEnabledChannels>`
  * :ref:`pollOperatingHours() <method_EnergyAddonEN100_pollOperatingHours>`
  * :ref:`pollSupplyVoltage() <method_EnergyAddonEN100_pollSupplyVoltage>`
  * :ref:`pollTemperature() <method_EnergyAddonEN100_pollTemperature>`
  * :ref:`Object.deserializeProperties() <method_Object_deserializeProperties>`
  * :ref:`Object.fromJson() <method_Object_fromJson>`
  * :ref:`Object.toJson() <method_Object_toJson>`

Signals
+++++++

.. hlist::
  :columns: 1

  * :ref:`channelsDataChanged() <signal_EnergyAddonEN100_channelsDataChanged>`
  * :ref:`Object.completed() <signal_Object_completed>`



Properties
**********


.. _property_EnergyAddonEN100_channels:

.. _signal_EnergyAddonEN100_channelsChanged:

.. index::
   single: channels

channels
++++++++

This property holds a list of :ref:`EnergyAddonChannel <object_EnergyAddonChannel>` objects representing the physically connected input channels.

:**› Type**: :ref:`List <object_List>`\<:ref:`EnergyAddonChannel <object_EnergyAddonChannel>`>
:**› Signal**: channelsChanged()
:**› Attributes**: Readonly


.. _property_EnergyAddonEN100_operatingHours:

.. _signal_EnergyAddonEN100_operatingHoursChanged:

.. index::
   single: operatingHours

operatingHours
++++++++++++++

This property holds the operating hours of the Energy Addon EN100 since the last start. This property does not update automatically but has to be polled actively.

:**› Type**: Double
:**› Default**: ``0``
:**› Signal**: operatingHoursChanged()
:**› Attributes**: Writable


.. _property_EnergyAddonEN100_supplyVoltage:

.. _signal_EnergyAddonEN100_supplyVoltageChanged:

.. index::
   single: supplyVoltage

supplyVoltage
+++++++++++++

This property holds the current supply voltage of the Energy Addon EN100 in *V*. This property does not update automatically but has to be polled actively.

:**› Type**: Double
:**› Default**: ``0``
:**› Signal**: supplyVoltageChanged()
:**› Attributes**: Writable


.. _property_EnergyAddonEN100_temperature:

.. _signal_EnergyAddonEN100_temperatureChanged:

.. index::
   single: temperature

temperature
+++++++++++

This property holds the current temperature measured inside the Energy Addon EN100 in *°C*. This property does not update automatically but has to be polled actively.

:**› Type**: SignedInteger
:**› Default**: ``0``
:**› Signal**: temperatureChanged()
:**› Attributes**: Writable

Methods
*******


.. _method_EnergyAddonEN100_pollChannels:

.. index::
   single: pollChannels

pollChannels()
++++++++++++++

This method polls the :ref:`channels <property_EnergyAddonEN100_channels>` property. It is called automatically when using a :ref:`Polling <object_Polling>` property modifier on this property and usually does not have to be called manually.



.. _method_EnergyAddonEN100_pollEnabledChannels:

.. index::
   single: pollEnabledChannels

pollEnabledChannels()
+++++++++++++++++++++

This method queries the device for enabled channels causing the corresponding :ref:`EnergyAddonChannel.enabled <property_EnergyAddonChannel_enabled>` properties to be updated.



.. _method_EnergyAddonEN100_pollOperatingHours:

.. index::
   single: pollOperatingHours

pollOperatingHours()
++++++++++++++++++++

This method polls the :ref:`operatingHours <property_EnergyAddonEN100_operatingHours>` property. It is called automatically when using a :ref:`Polling <object_Polling>` property modifier on this property and usually does not have to be called manually.



.. _method_EnergyAddonEN100_pollSupplyVoltage:

.. index::
   single: pollSupplyVoltage

pollSupplyVoltage()
+++++++++++++++++++

This method polls the :ref:`supplyVoltage <property_EnergyAddonEN100_supplyVoltage>` property. It is called automatically when using a :ref:`Polling <object_Polling>` property modifier on this property and usually does not have to be called manually.



.. _method_EnergyAddonEN100_pollTemperature:

.. index::
   single: pollTemperature

pollTemperature()
+++++++++++++++++

This method polls the :ref:`temperature <property_EnergyAddonEN100_temperature>` property. It is called automatically when using a :ref:`Polling <object_Polling>` property modifier on this property and usually does not have to be called manually.


Signals
*******


.. _signal_EnergyAddonEN100_channelsDataChanged:

.. index::
   single: channelsDataChanged

channelsDataChanged(SignedInteger index)
++++++++++++++++++++++++++++++++++++++++

This signal is emitted whenever the :ref:`List.dataChanged() <signal_List_dataChanged>` signal is emitted, i.e. the item at ``index`` in the :ref:`channels <property_EnergyAddonEN100_channels>` list itself emitted the dataChanged() signal.



.. _example_EnergyAddonEN100:


Example
*******

.. code-block:: qml

    import InCore.Foundation 2.0
    import InCore.IO 2.0
    
    Application {
    
        BackplaneBus {
    
            EnergyAddonEN100 {
                address: 1
                Polling on supplyVoltage { interval: 5000 }
                Polling on temperature { interval: 5000 }
                Polling on operatingHours { interval: 5000 }
    
                onSerialNumberChanged: console.log("HUB-EN100 has serial number:", serialNumber)
                onSupplyVoltageChanged: console.log("Supply voltage:", supplyVoltage)
                onTemperatureChanged: console.log("EN100 temperature:", temperature)
                onOperatingHoursChanged: console.log("Operating hours:", operatingHours)
    
                Polling on channels { interval: 1000 }
    
                EnergyAddonChannel {
                    id: channel1
                    index: 1
                    onTimestampChanged: console.log("CH1", timestamp, current, frequency)
                }
    
                EnergyAddonChannel {
                    id: channel2
                    index: 2
                    onTimestampChanged: console.log("CH2", timestamp, current, frequency)
                }
            }
        }
    }
    