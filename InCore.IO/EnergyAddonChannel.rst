
.. _object_EnergyAddonChannel:


:index:`EnergyAddonChannel`
---------------------------

Description
***********

The EnergyAddonChannel object represents a channel of a :ref:`EnergyAddonEN100 <object_EnergyAddonEN100>` device and holds properties for measured values. In order to initiate a measurement the desired properties have to be polled through a :ref:`Polling <object_Polling>` object or by calling :ref:`pollCurrent() <method_EnergyAddonChannel_pollCurrent>` and/or :ref:`pollFrequency() <method_EnergyAddonChannel_pollFrequency>` manually.

:**› Inherits**: :ref:`Object <object_Object>`

Overview
********

Properties
++++++++++

.. hlist::
  :columns: 1

  * :ref:`current <property_EnergyAddonChannel_current>`
  * :ref:`enabled <property_EnergyAddonChannel_enabled>`
  * :ref:`frequency <property_EnergyAddonChannel_frequency>`
  * :ref:`index <property_EnergyAddonChannel_index>`
  * :ref:`timestamp <property_EnergyAddonChannel_timestamp>`
  * :ref:`Object.objectId <property_Object_objectId>`
  * :ref:`Object.parent <property_Object_parent>`

Methods
+++++++

.. hlist::
  :columns: 1

  * :ref:`pollCurrent() <method_EnergyAddonChannel_pollCurrent>`
  * :ref:`pollFrequency() <method_EnergyAddonChannel_pollFrequency>`
  * :ref:`Object.deserializeProperties() <method_Object_deserializeProperties>`
  * :ref:`Object.fromJson() <method_Object_fromJson>`
  * :ref:`Object.serializeProperties() <method_Object_serializeProperties>`
  * :ref:`Object.toJson() <method_Object_toJson>`

Signals
+++++++

.. hlist::
  :columns: 1

  * :ref:`Object.completed() <signal_Object_completed>`



Properties
**********


.. _property_EnergyAddonChannel_current:

.. _signal_EnergyAddonChannel_currentChanged:

.. index::
   single: current

current
+++++++

This property holds the measured current in *A*. The value needs to be polled actively.

:**› Type**: Double
:**› Signal**: currentChanged()
:**› Attributes**: Readonly, Requires :ref:`Polling <object_Polling>`


.. _property_EnergyAddonChannel_enabled:

.. _signal_EnergyAddonChannel_enabledChanged:

.. index::
   single: enabled

enabled
+++++++

This property holds whether the channel is enabled for measurements. When disabled, no measured values will be received and updated.

:**› Type**: Boolean
:**› Default**: ``true``
:**› Signal**: enabledChanged()
:**› Attributes**: Writable


.. _property_EnergyAddonChannel_frequency:

.. _signal_EnergyAddonChannel_frequencyChanged:

.. index::
   single: frequency

frequency
+++++++++

This property holds the measured frequency in *Hz*. The value needs to be polled actively.

:**› Type**: Double
:**› Signal**: frequencyChanged()
:**› Attributes**: Readonly, Requires :ref:`Polling <object_Polling>`


.. _property_EnergyAddonChannel_index:

.. _signal_EnergyAddonChannel_indexChanged:

.. index::
   single: index

index
+++++

This property holds the index which specifies the channel to read measurements from.

:**› Type**: SignedInteger
:**› Default**: ``0``
:**› Signal**: indexChanged()
:**› Attributes**: Writable


.. _property_EnergyAddonChannel_timestamp:

.. _signal_EnergyAddonChannel_timestampChanged:

.. index::
   single: timestamp

timestamp
+++++++++

This property holds a timestamp of the last measurement in milliseconds. This value wraps every minute, i.e. at 60000 milliseconds and can be used to detect a successful measurement even if the measured values have not changed between the measurements.

:**› Type**: UnsignedBigInteger
:**› Default**: ``0``
:**› Signal**: timestampChanged()
:**› Attributes**: Writable

Methods
*******


.. _method_EnergyAddonChannel_pollCurrent:

.. index::
   single: pollCurrent

pollCurrent()
+++++++++++++

This method polls the :ref:`current <property_EnergyAddonChannel_current>` property. It is called automatically when using a :ref:`Polling <object_Polling>` property modifier on this property and usually does not have to be called manually.



.. _method_EnergyAddonChannel_pollFrequency:

.. index::
   single: pollFrequency

pollFrequency()
+++++++++++++++

This method polls the :ref:`frequency <property_EnergyAddonChannel_frequency>` property. It is called automatically when using a :ref:`Polling <object_Polling>` property modifier on this property and usually does not have to be called manually.


Example
*******
See :ref:`EnergyAddonEN100 example <example_EnergyAddonEN100>` on how to use EnergyAddonChannel.
