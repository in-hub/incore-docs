
.. _object_KeyboardManager:


:index:`KeyboardManager`
------------------------

Description
***********

The KeyboardManager object manages :ref:`Keyboard <object_Keyboard>` devices available on the system. It automatically populates and updates the :ref:`devices <property_KeyboardManager_devices>` list. To use a certain device, e.g. selected by properties such as :ref:`Keyboard.vendorIdentifier <property_Keyboard_vendorIdentifier>` or :ref:`Keyboard.productIdentifier <property_Keyboard_productIdentifier>`, connect to its signals as shown in the example below.

This object was introduced in InCore 2.3.

:**› Inherits**: :ref:`Object <object_Object>`

Overview
********

Properties
++++++++++

.. hlist::
  :columns: 1

  * :ref:`devices <property_KeyboardManager_devices>`
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

  * :ref:`devicesDataChanged() <signal_KeyboardManager_devicesDataChanged>`
  * :ref:`Object.completed() <signal_Object_completed>`



Properties
**********


.. _property_KeyboardManager_devices:

.. _signal_KeyboardManager_devicesChanged:

.. index::
   single: devices

devices
+++++++

This property holds all available :ref:`Keyboard <object_Keyboard>` objects.

:**› Type**: :ref:`List <object_List>`\<:ref:`Keyboard <object_Keyboard>`>
:**› Signal**: devicesChanged()
:**› Attributes**: Readonly

Signals
*******


.. _signal_KeyboardManager_devicesDataChanged:

.. index::
   single: devicesDataChanged

devicesDataChanged(SignedInteger index)
+++++++++++++++++++++++++++++++++++++++

This signal is emitted whenever the :ref:`List.dataChanged() <signal_List_dataChanged>` signal is emitted, i.e. the item at ``index`` in the :ref:`devices <property_KeyboardManager_devices>` list itself emitted the dataChanged() signal.



.. _example_KeyboardManager:


Example
*******

.. code-block:: qml

    import InCore.Foundation 2.5
    import InCore.IO 2.5
    
    Application {
        KeyboardManager {
            id: keyboardManager
            onDevicesChanged: {
                console.log("Keyboards:")
                for( var i = 0; i < devices.length; ++i )
                {
                    console.log("Input device file:", devices[i].inputDeviceFile,
                                "\n\tName:", devices[i].name,
                                "\n\tVendor identifier:", devices[i].vendorIdentifier,
                                "\n\tProduct identifier:", devices[i].productIdentifier,
                                "\n\tPhysical location:", devices[i].physicalLocation,
                                "\n\tUSB location:", devices[i].usbLocation,
                                )
                    devices[i].enabled = devices[i].vendorIdentifier > 0
                    devices[i].keyPressed.connect(
                                (key, modifiers) => {
                                    if(modifiers & Keyboard.ShiftModifier)
                                    {
                                        console.log("Key", key, "with Shift pressed.")
                                    } else {
                                        console.log("Key", key, "pressed.")
                                    }
                                } )
                    devices[i].keyReleased.connect((key) => { console.log("Key", key, "released.") } )
                    devices[i].textEntered.connect((text) => { console.log(("Text entered: \"%1\"").arg(text)) } )
                }
            }
        }
    
        // implement a barcode scanner object which buffers subsequently entered characters
        // until no more characters are entered for a certain time
        Object {
            id: barcodeScanner
    
            onBarcodeScanned: console.log("Barcode scanned:", barcode)
    
            signal barcodeScanned(string barcode)
    
            property Keyboard device
            property string barcodeCharacters
            readonly property var inputTimer : Timer {
                interval: 200
                repeat: false
                running: false
                onTriggered: {
                    parent.barcodeScanned(parent.barcodeCharacters)
                    parent.barcodeCharacters = ""
                }
            }
    
            Select on device {
                source: keyboardManager.devices
                // select barcode scanner from available input devices by vendor and product identifier
                select: item.vendorIdentifier === 0x0581 &&
                        ( item.productIdentifier === 0x0110 || item.productIdentifier === 0x0115 )
            }
    
            onDeviceChanged: {
                if(device)
                    device.textEntered.connect(
                                (text) => {
                                    barcodeCharacters += text
                                    inputTimer.restart()
                                } )
            }
        }
    }
    