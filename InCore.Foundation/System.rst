
.. _object_System:


:index:`System`
---------------

Description
***********

The System object provides device and operating system related properties such as :ref:`clock <property_System_clock>`, :ref:`cpuLoad <property_System_cpuLoad>` and :ref:`hostname <property_System_hostname>`. It also allows changing the system hostname and configure system services required and/or used by the application.

:**› Inherits**: :ref:`Object <object_Object>`

Overview
********

Properties
++++++++++

.. hlist::
  :columns: 3

  * :ref:`bootloaderVersion <property_System_bootloaderVersion>`
  * :ref:`clock <property_System_clock>`
  * :ref:`cpuLoad <property_System_cpuLoad>`
  * :ref:`cpuUsage <property_System_cpuUsage>`
  * :ref:`deviceHumidity <property_System_deviceHumidity>`
  * :ref:`deviceId <property_System_deviceId>`
  * :ref:`deviceName <property_System_deviceName>`
  * :ref:`deviceSubtype <property_System_deviceSubtype>`
  * :ref:`deviceTemperature <property_System_deviceTemperature>`
  * :ref:`deviceType <property_System_deviceType>`
  * :ref:`error <property_System_error>`
  * :ref:`errorString <property_System_errorString>`
  * :ref:`hostname <property_System_hostname>`
  * :ref:`memoryAvailable <property_System_memoryAvailable>`
  * :ref:`memoryTotal <property_System_memoryTotal>`
  * :ref:`osEdition <property_System_osEdition>`
  * :ref:`osVersion <property_System_osVersion>`
  * :ref:`services <property_System_services>`
  * :ref:`uptime <property_System_uptime>`
  * :ref:`Object.objectId <property_Object_objectId>`
  * :ref:`Object.parent <property_Object_parent>`

Methods
+++++++

.. hlist::
  :columns: 2

  * :ref:`pollCpuLoad() <method_System_pollCpuLoad>`
  * :ref:`pollCpuUsage() <method_System_pollCpuUsage>`
  * :ref:`pollDeviceHumidity() <method_System_pollDeviceHumidity>`
  * :ref:`pollDeviceTemperature() <method_System_pollDeviceTemperature>`
  * :ref:`pollMemoryAvailable() <method_System_pollMemoryAvailable>`
  * :ref:`pollUptime() <method_System_pollUptime>`
  * :ref:`reboot() <method_System_reboot>`
  * :ref:`setHardwareClocks() <method_System_setHardwareClocks>`
  * :ref:`shutdown() <method_System_shutdown>`
  * :ref:`Object.deserializeProperties() <method_Object_deserializeProperties>`
  * :ref:`Object.fromJson() <method_Object_fromJson>`
  * :ref:`Object.serializeProperties() <method_Object_serializeProperties>`
  * :ref:`Object.toJson() <method_Object_toJson>`

Signals
+++++++

.. hlist::
  :columns: 1

  * :ref:`errorOccurred() <signal_System_errorOccurred>`
  * :ref:`servicesDataChanged() <signal_System_servicesDataChanged>`
  * :ref:`Object.completed() <signal_Object_completed>`

Enumerations
++++++++++++

.. hlist::
  :columns: 1

  * :ref:`DeviceType <enum_System_DeviceType>`
  * :ref:`Error <enum_System_Error>`



Properties
**********


.. _property_System_bootloaderVersion:

.. index::
   single: bootloaderVersion

bootloaderVersion
+++++++++++++++++

This property holds the version of the bootloader used for booting the operating system.

:**› Type**: String
:**› Attributes**: Readonly


.. _property_System_clock:

.. index::
   single: clock

clock
+++++

This property holds the current UTC timestamp used by the system. This value is equivalent to the `well-known UNIX time <https://en.wikipedia.org/wiki/Unix_time>`_ and represents the number of seconds that have elapsed since 00:00:00 Thursday, 1 January 1970 (UTC) minus leap seconds.

:**› Type**: SignedBigInteger
:**› Attributes**: Readonly


.. _property_System_cpuLoad:

.. _signal_System_cpuLoadChanged:

.. index::
   single: cpuLoad

cpuLoad
+++++++

This property holds the system load average for the last minute. The value is equivalent to the `well-known UNIX load <https://en.wikipedia.org/wiki/Load_(computing)>`_ and indicates how many processes are consuming CPU time and waiting for I/O.

:**› Type**: Double
:**› Signal**: cpuLoadChanged()
:**› Attributes**: Readonly, Requires :ref:`Polling <object_Polling>`


.. _property_System_cpuUsage:

.. _signal_System_cpuUsageChanged:

.. index::
   single: cpuUsage

cpuUsage
++++++++

This property holds the average CPU usage in percent. When polled for the first time, it will return the total CPU usage since system start while subsequent polls return the CPU usage since the previous poll.

This property was introduced in InCore 2.5.

:**› Type**: SignedInteger
:**› Signal**: cpuUsageChanged()
:**› Attributes**: Readonly, Requires :ref:`Polling <object_Polling>`


.. _property_System_deviceHumidity:

.. _signal_System_deviceHumidityChanged:

.. index::
   single: deviceHumidity

deviceHumidity
++++++++++++++

This property holds the relative humidity measured inside the device.

:**› Type**: Float
:**› Signal**: deviceHumidityChanged()
:**› Attributes**: Readonly, Requires :ref:`Polling <object_Polling>`


.. _property_System_deviceId:

.. index::
   single: deviceId

deviceId
++++++++

This property holds a worldwide unique ID associated with the running device. The ID is based on the MAC address of the primary network interface and consists of 12 hexadecimal digits.

:**› Type**: String
:**› Attributes**: Readonly


.. _property_System_deviceName:

.. _signal_System_deviceNameChanged:

.. index::
   single: deviceName

deviceName
++++++++++

This property holds the name of the device. This can be a description with arbitrary UTF-8 characters.

:**› Type**: String
:**› Signal**: deviceNameChanged()
:**› Attributes**: Writable


.. _property_System_deviceSubtype:

.. _signal_System_deviceSubtypeChanged:

.. index::
   single: deviceSubtype

deviceSubtype
+++++++++++++

This property holds the subtype of the device which the application currently is running on. The proper values are :ref:`deviceType <property_System_deviceType>`-specific and only should be set by the vendor.

This property was introduced in InCore 2.6.

:**› Type**: String
:**› Signal**: deviceSubtypeChanged()
:**› Attributes**: Writable


.. _property_System_deviceTemperature:

.. _signal_System_deviceTemperatureChanged:

.. index::
   single: deviceTemperature

deviceTemperature
+++++++++++++++++

This property holds the temperature measured inside the device in °C. This temperature does not indicate the CPU temperature even though both temperatures correlate with each other.

:**› Type**: Float
:**› Signal**: deviceTemperatureChanged()
:**› Attributes**: Readonly, Requires :ref:`Polling <object_Polling>`


.. _property_System_deviceType:

.. _signal_System_deviceTypeChanged:

.. index::
   single: deviceType

deviceType
++++++++++

This property holds the type of the device which the application currently is running on.

:**› Type**: :ref:`DeviceType <enum_System_DeviceType>`
:**› Signal**: deviceTypeChanged()
:**› Attributes**: Readonly


.. _property_System_error:

.. _signal_System_errorChanged:

.. index::
   single: error

error
+++++

This property holds the most recently occurred error or :ref:`System.NoError <enumitem_System_NoError>` if no error occurred. If the same error occurs multiple times this property does not change. Use the :ref:`errorOccurred() <signal_System_errorOccurred>` signal to detect multiple occurrences of the same error.

:**› Type**: :ref:`Error <enum_System_Error>`
:**› Signal**: errorChanged()
:**› Attributes**: Readonly


.. _property_System_errorString:

.. _signal_System_errorStringChanged:

.. index::
   single: errorString

errorString
+++++++++++

This property holds the current human readable error string corresponding to the current value in the :ref:`error <property_System_error>` property. It may include additional information such as failure reasons or locations.

:**› Type**: String
:**› Signal**: errorStringChanged()
:**› Attributes**: Readonly


.. _property_System_hostname:

.. _signal_System_hostnameChanged:

.. index::
   single: hostname

hostname
++++++++

This property holds the hostname of the system.  The hostname must follow the usual conventions for allowed characters. Changing this property allows operating multiple devices of the same type in a network and address them through multicast DNS (i.e. ``<hostname>.local``) instead of regular DNS.

:**› Type**: String
:**› Signal**: hostnameChanged()
:**› Attributes**: Writable


.. _property_System_memoryAvailable:

.. _signal_System_memoryAvailableChanged:

.. index::
   single: memoryAvailable

memoryAvailable
+++++++++++++++

This property holds the available (unused) memory of the system in MiB.

This property was introduced in InCore 2.5.

:**› Type**: SignedInteger
:**› Signal**: memoryAvailableChanged()
:**› Attributes**: Readonly, Requires :ref:`Polling <object_Polling>`


.. _property_System_memoryTotal:

.. _signal_System_memoryTotalChanged:

.. index::
   single: memoryTotal

memoryTotal
+++++++++++

This property holds the total memory of the system in MiB.

This property was introduced in InCore 2.5.

:**› Type**: SignedInteger
:**› Signal**: memoryTotalChanged()
:**› Attributes**: Readonly


.. _property_System_osEdition:

.. index::
   single: osEdition

osEdition
+++++++++

This property holds the edition of the operating system currently running on the device.

This property was introduced in InCore 2.7.

:**› Type**: String
:**› Attributes**: Readonly


.. _property_System_osVersion:

.. index::
   single: osVersion

osVersion
+++++++++

This property holds the version of the operating system currently running on the device.

:**› Type**: String
:**› Attributes**: Readonly


.. _property_System_services:

.. _signal_System_servicesChanged:

.. index::
   single: services

services
++++++++

This property holds a list of system services to configure and use in the application. See the documentation for :ref:`SystemService <object_SystemService>` for details.

:**› Type**: :ref:`List <object_List>`\<:ref:`SystemService <object_SystemService>`>
:**› Signal**: servicesChanged()
:**› Attributes**: Readonly


.. _property_System_uptime:

.. _signal_System_uptimeChanged:

.. index::
   single: uptime

uptime
++++++

This property holds how long the system has been running since last boot. The uptime is provided in days, hours and minutes.

:**› Type**: String
:**› Signal**: uptimeChanged()
:**› Attributes**: Readonly, Requires :ref:`Polling <object_Polling>`

Methods
*******


.. _method_System_pollCpuLoad:

.. index::
   single: pollCpuLoad

pollCpuLoad()
+++++++++++++

This method polls the :ref:`cpuLoad <property_System_cpuLoad>` property. It is called automatically when using a :ref:`Polling <object_Polling>` property modifier on this property and usually does not have to be called manually.



.. _method_System_pollCpuUsage:

.. index::
   single: pollCpuUsage

pollCpuUsage()
++++++++++++++

This method polls the :ref:`cpuUsage <property_System_cpuUsage>` property. It is called automatically when using a :ref:`Polling <object_Polling>` property modifier on this property and usually does not have to be called manually.



.. _method_System_pollDeviceHumidity:

.. index::
   single: pollDeviceHumidity

pollDeviceHumidity()
++++++++++++++++++++

This method polls the :ref:`deviceHumidity <property_System_deviceHumidity>` property. It is called automatically when using a :ref:`Polling <object_Polling>` property modifier on this property and usually does not have to be called manually.



.. _method_System_pollDeviceTemperature:

.. index::
   single: pollDeviceTemperature

pollDeviceTemperature()
+++++++++++++++++++++++

This method polls the :ref:`deviceTemperature <property_System_deviceTemperature>` property. It is called automatically when using a :ref:`Polling <object_Polling>` property modifier on this property and usually does not have to be called manually.



.. _method_System_pollMemoryAvailable:

.. index::
   single: pollMemoryAvailable

pollMemoryAvailable()
+++++++++++++++++++++

This method polls the :ref:`memoryAvailable <property_System_memoryAvailable>` property. It is called automatically when using a :ref:`Polling <object_Polling>` property modifier on this property and usually does not have to be called manually.



.. _method_System_pollUptime:

.. index::
   single: pollUptime

pollUptime()
++++++++++++

This method polls the :ref:`uptime <property_System_uptime>` property. It is called automatically when using a :ref:`Polling <object_Polling>` property modifier on this property and usually does not have to be called manually.



.. _method_System_reboot:

.. index::
   single: reboot

reboot()
++++++++

This method initiates a full system restart. Since the application will be stopped almost immediately any actions such as logging or closing connections should be performed before calling this method.

This method was introduced in InCore 2.0.



.. _method_System_setHardwareClocks:

.. index::
   single: setHardwareClocks

setHardwareClocks()
+++++++++++++++++++

This method sets all available hardware clocks (RTCs) to the current system time.

This method was introduced in InCore 2.7.



.. _method_System_shutdown:

.. index::
   single: shutdown

shutdown()
++++++++++

This method initiates a clean system shutdown. Since the application will be stopped almost immediately any actions such as logging or closing connections should be performed before calling this method.

This method was introduced in InCore 2.7.


Signals
*******


.. _signal_System_errorOccurred:

.. index::
   single: errorOccurred

errorOccurred()
+++++++++++++++

This signal is emitted whenever an error has occurred, regardless of whether the :ref:`error <property_System_error>` property has changed or not. In contrast to the change notification signal of the :ref:`error <property_System_error>` property this signal is also emitted several times if a certain error occurs several times in succession.



.. _signal_System_servicesDataChanged:

.. index::
   single: servicesDataChanged

servicesDataChanged(SignedInteger index)
++++++++++++++++++++++++++++++++++++++++

This signal is emitted whenever the :ref:`List.dataChanged() <signal_List_dataChanged>` signal is emitted, i.e. the item at ``index`` in the :ref:`services <property_System_services>` list itself emitted the dataChanged() signal.


Enumerations
************


.. _enum_System_DeviceType:

.. index::
   single: DeviceType

DeviceType
++++++++++

This enumeration describes the type of the device which the application can be run on.

.. index::
   single: System.Other
.. index::
   single: System.GM100
.. index::
   single: System.GM200
.. index::
   single: System.GM400
.. index::
   single: System.IM6
.. index::
   single: System.CCM60
.. list-table::
  :widths: auto
  :header-rows: 1

  * - Name
    - Value
    - Description

      .. _enumitem_System_Other:
  * - ``System.Other``
    - ``-1``
    - Other/unknown device.

      .. _enumitem_System_GM100:
  * - ``System.GM100``
    - ``0``
    - A HUB-GM100 (single-core) device.

      .. _enumitem_System_GM200:
  * - ``System.GM200``
    - ``1``
    - A HUB-GM200 (dual-core) device.

      .. _enumitem_System_GM400:
  * - ``System.GM400``
    - ``2``
    - A HUB-GM400 (quad-core) device.

      .. _enumitem_System_IM6:
  * - ``System.IM6``
    - ``3``
    - An IM6-XXNNN device.

      .. _enumitem_System_CCM60:
  * - ``System.CCM60``
    - ``4``
    - A TURCK IM18-CCM60 device.


.. _enum_System_Error:

.. index::
   single: Error

Error
+++++

This enumeration describes all errors which can occur in System objects. The most recently occurred error is stored in the :ref:`error <property_System_error>` property.

.. index::
   single: System.NoError
.. index::
   single: System.EmptyHostname
.. index::
   single: System.InvalidHostname
.. list-table::
  :widths: auto
  :header-rows: 1

  * - Name
    - Value
    - Description

      .. _enumitem_System_NoError:
  * - ``System.NoError``
    - ``0``
    - No error occurred or was detected.

      .. _enumitem_System_EmptyHostname:
  * - ``System.EmptyHostname``
    - ``1``
    - Can't set empty hostname.

      .. _enumitem_System_InvalidHostname:
  * - ``System.InvalidHostname``
    - ``2``
    - Hostname is invalid, likely due to invalid characters.


.. _example_System:


Example
*******

.. code-block:: qml

    import InCore.Foundation 2.5
    
    Application {
        System {
            Polling on cpuUsage { }
            Polling on memoryAvailable { }
            onCpuUsageChanged: console.log("CPU usage:", cpuUsage, "%")
            onMemoryAvailableChanged: console.log(("%1 of %2 MiB used").arg(memoryTotal-memoryAvailable).arg(memoryTotal))
        }
    }
    