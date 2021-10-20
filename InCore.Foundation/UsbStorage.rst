
.. _object_UsbStorage:


:index:`UsbStorage`
-------------------

Description
***********

The UsbStorage object is a :ref:`Storage <object_Storage>` object which provides access to a USB drive connected to the local device. Whenever a USB drive is detected by the system, the :ref:`UsbStorage <object_UsbStorage>` object mounts it automatically and updates the :ref:`Storage.available <property_Storage_available>` property. When writing files to a USB drive make sure to call :ref:`eject() <method_UsbStorage_eject>` before allowing the user to unplug the drive.

:**› Inherits**: :ref:`Storage <object_Storage>`

Overview
********

Properties
++++++++++

.. hlist::
  :columns: 2

  * :ref:`error <property_UsbStorage_error>`
  * :ref:`errorString <property_UsbStorage_errorString>`
  * :ref:`Storage.available <property_Storage_available>`
  * :ref:`Storage.bytesFree <property_Storage_bytesFree>`
  * :ref:`Storage.bytesTotal <property_Storage_bytesTotal>`
  * :ref:`Storage.path <property_Storage_path>`
  * :ref:`Storage.readOnly <property_Storage_readOnly>`
  * :ref:`Object.objectId <property_Object_objectId>`
  * :ref:`Object.parent <property_Object_parent>`

Methods
+++++++

.. hlist::
  :columns: 1

  * :ref:`eject() <method_UsbStorage_eject>`
  * :ref:`sync() <method_UsbStorage_sync>`
  * :ref:`Object.deserializeProperties() <method_Object_deserializeProperties>`
  * :ref:`Object.fromJson() <method_Object_fromJson>`
  * :ref:`Object.toJson() <method_Object_toJson>`

Signals
+++++++

.. hlist::
  :columns: 1

  * :ref:`errorOccurred() <signal_UsbStorage_errorOccurred>`
  * :ref:`Object.completed() <signal_Object_completed>`

Enumerations
++++++++++++

.. hlist::
  :columns: 1

  * :ref:`Error <enum_UsbStorage_Error>`



Properties
**********


.. _property_UsbStorage_error:

.. _signal_UsbStorage_errorChanged:

.. index::
   single: error

error
+++++

This property holds the most recently occurred error or :ref:`UsbStorage.NoError <enumitem_UsbStorage_NoError>` if no error occurred. If the same error occurs multiple times this property does not change. Use the :ref:`errorOccurred() <signal_UsbStorage_errorOccurred>` signal to detect multiple occurrences of the same error.

:**› Type**: :ref:`Error <enum_UsbStorage_Error>`
:**› Signal**: errorChanged()
:**› Attributes**: Readonly


.. _property_UsbStorage_errorString:

.. _signal_UsbStorage_errorStringChanged:

.. index::
   single: errorString

errorString
+++++++++++

This property holds the current human readable error string corresponding to the current value in the :ref:`error <property_UsbStorage_error>` property. It may include additional information such as failure reasons or locations.

:**› Type**: String
:**› Signal**: errorStringChanged()
:**› Attributes**: Readonly

Methods
*******


.. _method_UsbStorage_eject:

.. index::
   single: eject

eject()
+++++++

This method writes all pending data to the USB drive and unmounts it so it can be removed safely. After unmounting it's not accessible any longer until the USB drive is physically plugged in again.

:**› Returns**: Boolean



.. _method_UsbStorage_sync:

.. index::
   single: sync

sync()
++++++

This method writes all pending data (i.e. write buffers/caches) to the USB drive.


Signals
*******


.. _signal_UsbStorage_errorOccurred:

.. index::
   single: errorOccurred

errorOccurred()
+++++++++++++++

This signal is emitted whenever an error has occurred, regardless of whether the :ref:`error <property_UsbStorage_error>` property has changed or not. In contrast to the change notification signal of the :ref:`error <property_UsbStorage_error>` property this signal is also emitted several times if a certain error occurs several times in succession.


Enumerations
************


.. _enum_UsbStorage_Error:

.. index::
   single: Error

Error
+++++

This enumeration describes all errors which can occur in UsbStorage objects. The most recently occurred error is stored in the :ref:`error <property_UsbStorage_error>` property.

.. index::
   single: UsbStorage.NoError
.. index::
   single: UsbStorage.MountError
.. list-table::
  :widths: auto
  :header-rows: 1

  * - Name
    - Value
    - Description

      .. _enumitem_UsbStorage_NoError:
  * - ``UsbStorage.NoError``
    - ``0``
    - No error occurred or was detected.

      .. _enumitem_UsbStorage_MountError:
  * - ``UsbStorage.MountError``
    - ``1``
    - Error while mounting USB drive ().


.. _example_UsbStorage:


Example
*******

.. code-block:: qml

    import InCore.Foundation 2.5
    
    Application {
    
        CsvWriter {
            id: csvWriter
    
            // create fictional measurements
            Repeater on objects {
                model: 3
                Measurement {
                    name: "meas" + index
                    data: index
                }
            }
    
            // write one data row to CSV file to USB drive whenever it is plugged in and eject it afterwards
            output: File {
                fileName: "measurements.csv"
                storage: UsbStorage {
                    onAvailableChanged: {
                        csvWriter.submit()
                        eject();
                    }
                }
            }
        }
    
    }
    