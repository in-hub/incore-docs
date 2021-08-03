
.. _object_SerialPortManager:


:index:`SerialPortManager`
--------------------------

Description
***********

The SerialPortManager object manages SerialPort devices. When a device is connected it will be discovered in the next discover run.

:**› Inherits**: :ref:`Object <object_Object>`

Overview
********

Properties
++++++++++

.. hlist::
  :columns: 1

  * :ref:`devices <property_SerialPortManager_devices>`
  * :ref:`updateInterval <property_SerialPortManager_updateInterval>`
  * :ref:`Object.objectId <property_Object_objectId>`
  * :ref:`Object.parent <property_Object_parent>`

Methods
+++++++

.. hlist::
  :columns: 1

  * :ref:`Object.deserializeProperties() <method_Object_deserializeProperties>`
  * :ref:`Object.fromJson() <method_Object_fromJson>`
  * :ref:`Object.toJson() <method_Object_toJson>`

Signals
+++++++

.. hlist::
  :columns: 1

  * :ref:`devicesDataChanged() <signal_SerialPortManager_devicesDataChanged>`
  * :ref:`Object.completed() <signal_Object_completed>`



Properties
**********


.. _property_SerialPortManager_devices:

.. _signal_SerialPortManager_devicesChanged:

.. index::
   single: devices

devices
+++++++

This property holds all available :ref:`SerialPort <object_SerialPort>` objects.

:**› Type**: :ref:`List <object_List>`\<:ref:`SerialPort <object_SerialPort>`>
:**› Signal**: devicesChanged()
:**› Attributes**: Readonly


.. _property_SerialPortManager_updateInterval:

.. _signal_SerialPortManager_updateIntervalChanged:

.. index::
   single: updateInterval

updateInterval
++++++++++++++

This property holds the interval in milliseconds in which to update the device list.

:**› Type**: SignedInteger
:**› Default**: ``10000``
:**› Signal**: updateIntervalChanged()
:**› Attributes**: Writable

Signals
*******


.. _signal_SerialPortManager_devicesDataChanged:

.. index::
   single: devicesDataChanged

devicesDataChanged(SignedInteger index)
+++++++++++++++++++++++++++++++++++++++

This signal is emitted whenever the :ref:`List.dataChanged() <signal_List_dataChanged>` signal is emitted, i.e. the item at ``index`` in the :ref:`devices <property_SerialPortManager_devices>` list itself emitted the dataChanged() signal.



.. _example_SerialPortManager:


Example
*******

.. code-block:: qml

    import InCore.Foundation 2.0
    import InCore.IO 2.0
    
    Application {
        SerialPortManager {
            updateInterval: 1000
            onDevicesChanged: {
                console.log("Serial ports changed:")
                for( var i = 0; i < devices.length; ++i )
                {
                    console.log("Port:", devices[i].portName,
                                "\n\tSerial number:", devices[i].serialNumber,
                                "\n\tDescription:", devices[i].description,
                                "\n\tManufacturer:", devices[i].manufacturer,
                                "\n\tVendor identifier:", devices[i].vendorIdentifier,
                                "\n\tProduct identifier:", devices[i].productIdentifier,
                                )
                }
            }
        }
    }
    