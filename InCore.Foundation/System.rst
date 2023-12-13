
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

  * :ref:`architecture <property_System_architecture>`
  * :ref:`bootloaderVersion <property_System_bootloaderVersion>`
  * :ref:`brokenDownCpuUsage <property_System_brokenDownCpuUsage>`
  * :ref:`clock <property_System_clock>`
  * :ref:`cpuLoad <property_System_cpuLoad>`
  * :ref:`cpuUsage <property_System_cpuUsage>`
  * :ref:`deviceHumidity <property_System_deviceHumidity>`
  * :ref:`deviceId <property_System_deviceId>`
  * :ref:`deviceName <property_System_deviceName>`
  * :ref:`deviceTemperature <property_System_deviceTemperature>`
  * :ref:`deviceTreeVariant <property_System_deviceTreeVariant>`
  * :ref:`deviceType <property_System_deviceType>`
  * :ref:`error <property_System_error>`
  * :ref:`errorString <property_System_errorString>`
  * :ref:`hostname <property_System_hostname>`
  * :ref:`memoryAvailable <property_System_memoryAvailable>`
  * :ref:`memoryTotal <property_System_memoryTotal>`
  * :ref:`networkInterfaces <property_System_networkInterfaces>`
  * :ref:`osEdition <property_System_osEdition>`
  * :ref:`osVersion <property_System_osVersion>`
  * :ref:`processor <property_System_processor>`
  * :ref:`services <property_System_services>`
  * :ref:`storageUsage <property_System_storageUsage>`
  * :ref:`systemProcesses <property_System_systemProcesses>`
  * :ref:`uptime <property_System_uptime>`
  * :ref:`Object.objectId <property_Object_objectId>`
  * :ref:`Object.parent <property_Object_parent>`

Methods
+++++++

.. hlist::
  :columns: 3

  * :ref:`pollBrokenDownCpuUsage() <method_System_pollBrokenDownCpuUsage>`
  * :ref:`pollCpuLoad() <method_System_pollCpuLoad>`
  * :ref:`pollCpuUsage() <method_System_pollCpuUsage>`
  * :ref:`pollDeviceHumidity() <method_System_pollDeviceHumidity>`
  * :ref:`pollDeviceTemperature() <method_System_pollDeviceTemperature>`
  * :ref:`pollMemoryAvailable() <method_System_pollMemoryAvailable>`
  * :ref:`pollStorageUsage() <method_System_pollStorageUsage>`
  * :ref:`pollSystemProcesses() <method_System_pollSystemProcesses>`
  * :ref:`pollUptime() <method_System_pollUptime>`
  * :ref:`reboot() <method_System_reboot>`
  * :ref:`resetVictoriaMetrics() <method_System_resetVictoriaMetrics>`
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

  * :ref:`Architecture <enum_System_Architecture>`
  * :ref:`DeviceType <enum_System_DeviceType>`
  * :ref:`Error <enum_System_Error>`
  * :ref:`Processor <enum_System_Processor>`



Properties
**********


.. _property_System_architecture:

.. index::
   single: architecture

architecture
++++++++++++

This property holds the architecture which the device running this application is based on.

This property was introduced in InCore 2.8.

:**› Type**: :ref:`Architecture <enum_System_Architecture>`
:**› Attributes**: Readonly


.. _property_System_bootloaderVersion:

.. index::
   single: bootloaderVersion

bootloaderVersion
+++++++++++++++++

This property holds the version of the bootloader used for booting the operating system.

:**› Type**: String
:**› Attributes**: Readonly


.. _property_System_brokenDownCpuUsage:

.. _signal_System_brokenDownCpuUsageChanged:

.. index::
   single: brokenDownCpuUsage

brokenDownCpuUsage
++++++++++++++++++

This property holds the average usage of each CPU in percent. When polled for the first time, it will return the total CPU usages since system start while subsequent polls return the CPU usages since the previous poll.

This property was introduced in InCore 2.8.

:**› Type**: List
:**› Signal**: brokenDownCpuUsageChanged()
:**› Attributes**: Readonly, Requires :ref:`Polling <object_Polling>`


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

This property holds the average usage of all CPUs in percent. When polled for the first time, it will return the total CPU usage since system start while subsequent polls return the CPU usage since the previous poll.

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


.. _property_System_deviceTreeVariant:

.. _signal_System_deviceTreeVariantChanged:

.. index::
   single: deviceTreeVariant

deviceTreeVariant
+++++++++++++++++

This property holds the device tree variant which is used for initializing the hardware of the current device. The proper values are :ref:`deviceType <property_System_deviceType>`-specific and only should be set by the vendor.

This property was introduced in InCore 2.8.

:**› Type**: String
:**› Signal**: deviceTreeVariantChanged()
:**› Attributes**: Writable


.. _property_System_deviceType:

.. index::
   single: deviceType

deviceType
++++++++++

This property holds the type of the device which the application currently is running on.

:**› Type**: :ref:`DeviceType <enum_System_DeviceType>`
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

This property holds the available (unused) memory of the system in kiB.

This property was introduced in InCore 2.5.

:**› Type**: SignedInteger
:**› Signal**: memoryAvailableChanged()
:**› Attributes**: Readonly, Requires :ref:`Polling <object_Polling>`


.. _property_System_memoryTotal:

.. index::
   single: memoryTotal

memoryTotal
+++++++++++

This property holds the total memory of the system in kiB.

This property was introduced in InCore 2.5.

:**› Type**: SignedInteger
:**› Attributes**: Readonly


.. _property_System_networkInterfaces:

.. _signal_System_networkInterfacesChanged:

.. index::
   single: networkInterfaces

networkInterfaces
+++++++++++++++++

This property holds the hardware names of all available network interfaces.

:**› Type**: StringList
:**› Signal**: networkInterfacesChanged()
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


.. _property_System_processor:

.. index::
   single: processor

processor
+++++++++

This property holds the processor of the device which the application currently is running on.

This property was introduced in InCore 2.8.

:**› Type**: :ref:`Processor <enum_System_Processor>`
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


.. _property_System_storageUsage:

.. _signal_System_storageUsageChanged:

.. index::
   single: storageUsage

storageUsage
++++++++++++

This property holds information about the specific usage of the storage partition.

This property was introduced in InCore 2.8.

:**› Type**: :ref:`QJsonObject <enum_System_QJsonObject>`
:**› Signal**: storageUsageChanged()
:**› Attributes**: Readonly, Requires :ref:`Polling <object_Polling>`


.. _property_System_systemProcesses:

.. _signal_System_systemProcessesChanged:

.. index::
   single: systemProcesses

systemProcesses
+++++++++++++++

This property holds information about all running system processes.

This property was introduced in InCore 2.8.

:**› Type**: :ref:`QJsonArray <enum_System_QJsonArray>`
:**› Signal**: systemProcessesChanged()
:**› Attributes**: Readonly, Requires :ref:`Polling <object_Polling>`


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


.. _method_System_pollBrokenDownCpuUsage:

.. index::
   single: pollBrokenDownCpuUsage

pollBrokenDownCpuUsage()
++++++++++++++++++++++++

This method polls the :ref:`brokenDownCpuUsage <property_System_brokenDownCpuUsage>` property. It is called automatically when using a :ref:`Polling <object_Polling>` property modifier on this property and usually does not have to be called manually.



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



.. _method_System_pollStorageUsage:

.. index::
   single: pollStorageUsage

pollStorageUsage()
++++++++++++++++++

This method polls the :ref:`storageUsage <property_System_storageUsage>` property. It is called automatically when using a :ref:`Polling <object_Polling>` property modifier on this property and usually does not have to be called manually.



.. _method_System_pollSystemProcesses:

.. index::
   single: pollSystemProcesses

pollSystemProcesses()
+++++++++++++++++++++

This method polls the :ref:`systemProcesses <property_System_systemProcesses>` property. It is called automatically when using a :ref:`Polling <object_Polling>` property modifier on this property and usually does not have to be called manually.



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



.. _method_System_resetVictoriaMetrics:

.. index::
   single: resetVictoriaMetrics

resetVictoriaMetrics()
++++++++++++++++++++++



:**› Returns**: Boolean



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


.. _enum_System_Architecture:

.. index::
   single: Architecture

Architecture
++++++++++++

This enumeration describes the device architecture which the application can run on.

This enumeration was introduced in InCore 2.8.

.. index::
   single: System.UnknownArchitecture
.. index::
   single: System.ARM32
.. index::
   single: System.ARM64
.. index::
   single: System.X64
.. list-table::
  :widths: auto
  :header-rows: 1

  * - Name
    - Value
    - Description

      .. _enumitem_System_UnknownArchitecture:
  * - ``System.UnknownArchitecture``
    - ``-1``
    - Other/unknown architecture.

      .. _enumitem_System_ARM32:
  * - ``System.ARM32``
    - ``0``
    - 32 bit ARM architecture.

      .. _enumitem_System_ARM64:
  * - ``System.ARM64``
    - ``1``
    - 64 bit ARM architecture.

      .. _enumitem_System_X64:
  * - ``System.X64``
    - ``2``
    - 64 bit x86 architecture.


.. _enum_System_DeviceType:

.. index::
   single: DeviceType

DeviceType
++++++++++

This enumeration describes the type of the device which the application can run on.

.. index::
   single: System.UnknownDeviceType
.. index::
   single: System.GM100
.. index::
   single: System.GM200
.. index::
   single: System.GM400
.. index::
   single: System.IO100
.. index::
   single: System.CO100
.. index::
   single: System.SE100
.. index::
   single: System.SI100
.. index::
   single: System.EN200
.. index::
   single: System.CCM60
.. list-table::
  :widths: auto
  :header-rows: 1

  * - Name
    - Value
    - Description

      .. _enumitem_System_UnknownDeviceType:
  * - ``System.UnknownDeviceType``
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

      .. _enumitem_System_IO100:
  * - ``System.IO100``
    - ``3``
    - A HUB-IO100 device.

      .. _enumitem_System_CO100:
  * - ``System.CO100``
    - ``4``
    - A HUB-CO100 device.

      .. _enumitem_System_SE100:
  * - ``System.SE100``
    - ``5``
    - A HUB-SE100 device.

      .. _enumitem_System_SI100:
  * - ``System.SI100``
    - ``6``
    - A HUB-SI100 device.

      .. _enumitem_System_EN200:
  * - ``System.EN200``
    - ``7``
    - A HUB-EN200 device.

      .. _enumitem_System_CCM60:
  * - ``System.CCM60``
    - ``8``
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


.. _enum_System_Processor:

.. index::
   single: Processor

Processor
+++++++++

This enumeration describes the processor which a device is equipped with.

This enumeration was introduced in InCore 2.8.

.. index::
   single: System.UnknownProcessor
.. index::
   single: System.AM335X
.. index::
   single: System.IMX6ULL
.. index::
   single: System.IMX7D
.. index::
   single: System.IMX8QXP
.. list-table::
  :widths: auto
  :header-rows: 1

  * - Name
    - Value
    - Description

      .. _enumitem_System_UnknownProcessor:
  * - ``System.UnknownProcessor``
    - ``-1``
    - Other/unknown processor.

      .. _enumitem_System_AM335X:
  * - ``System.AM335X``
    - ``0``
    - TI-AM335X processor.

      .. _enumitem_System_IMX6ULL:
  * - ``System.IMX6ULL``
    - ``1``
    - NXP-IMX6ULL processor .

      .. _enumitem_System_IMX7D:
  * - ``System.IMX7D``
    - ``2``
    - NXP-IMX7D processor.

      .. _enumitem_System_IMX8QXP:
  * - ``System.IMX8QXP``
    - ``3``
    - NXP-IMX8QXP processor.


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
    