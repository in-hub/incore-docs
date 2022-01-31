
.. _object_UsbPrinter:


:index:`UsbPrinter`
-------------------

Description
***********

The UsbPrinter object allows controlling a printer connected to a local USB port. When opened, data such as PostScript or ZPL can be sent to the printer using the :ref:`IoDevice.write() <method_IoDevice_write>` method.

This object was introduced in InCore 2.3.

:**› Inherits**: :ref:`File <object_File>`

Overview
********

Properties
++++++++++

.. hlist::
  :columns: 3

  * :ref:`index <property_UsbPrinter_index>`
  * :ref:`File.error <property_File_error>`
  * :ref:`File.errorString <property_File_errorString>`
  * :ref:`File.fileName <property_File_fileName>`
  * :ref:`File.storage <property_File_storage>`
  * :ref:`IoDevice.append <property_IoDevice_append>`
  * :ref:`IoDevice.atEnd <property_IoDevice_atEnd>`
  * :ref:`IoDevice.autoOpen <property_IoDevice_autoOpen>`
  * :ref:`IoDevice.bytesAvailable <property_IoDevice_bytesAvailable>`
  * :ref:`IoDevice.canReadLine <property_IoDevice_canReadLine>`
  * :ref:`IoDevice.deviceErrorString <property_IoDevice_deviceErrorString>`
  * :ref:`IoDevice.isOpen <property_IoDevice_isOpen>`
  * :ref:`IoDevice.isWritable <property_IoDevice_isWritable>`
  * :ref:`IoDevice.nameArgument <property_IoDevice_nameArgument>`
  * :ref:`IoDevice.pos <property_IoDevice_pos>`
  * :ref:`IoDevice.readOnly <property_IoDevice_readOnly>`
  * :ref:`IoDevice.size <property_IoDevice_size>`
  * :ref:`IoDevice.truncate <property_IoDevice_truncate>`
  * :ref:`IoDevice.unbuffered <property_IoDevice_unbuffered>`
  * :ref:`Object.objectId <property_Object_objectId>`
  * :ref:`Object.parent <property_Object_parent>`

Methods
+++++++

.. hlist::
  :columns: 3

  * :ref:`File.remove() <method_File_remove>`
  * :ref:`File.sync() <method_File_sync>`
  * :ref:`IoDevice.close() <method_IoDevice_close>`
  * :ref:`IoDevice.flush() <method_IoDevice_flush>`
  * :ref:`IoDevice.open() <method_IoDevice_open>`
  * :ref:`IoDevice.peekAll() <method_IoDevice_peekAll>`
  * :ref:`IoDevice.read() <method_IoDevice_read>`
  * :ref:`IoDevice.readAll() <method_IoDevice_readAll>`
  * :ref:`IoDevice.readLine() <method_IoDevice_readLine>`
  * :ref:`IoDevice.sync() <method_IoDevice_sync>`
  * :ref:`IoDevice.write() <method_IoDevice_write>`
  * :ref:`Object.deserializeProperties() <method_Object_deserializeProperties>`
  * :ref:`Object.fromJson() <method_Object_fromJson>`
  * :ref:`Object.serializeProperties() <method_Object_serializeProperties>`
  * :ref:`Object.toJson() <method_Object_toJson>`

Signals
+++++++

.. hlist::
  :columns: 1

  * :ref:`File.errorOccurred() <signal_File_errorOccurred>`
  * :ref:`IoDevice.lineAvailableForRead() <signal_IoDevice_lineAvailableForRead>`
  * :ref:`IoDevice.readyRead() <signal_IoDevice_readyRead>`
  * :ref:`Object.completed() <signal_Object_completed>`

Enumerations
++++++++++++

.. hlist::
  :columns: 1

  * :ref:`File.Error <enum_File_Error>`



Properties
**********


.. _property_UsbPrinter_index:

.. _signal_UsbPrinter_indexChanged:

.. index::
   single: index

index
+++++

This property holds the index of the printer which to communicate with.

:**› Type**: SignedInteger
:**› Default**: ``0``
:**› Signal**: indexChanged()
:**› Attributes**: Writable


.. _example_UsbPrinter:


Example
*******

.. code-block:: qml

    import InCore.IO 2.5
    
    UsbPrinter {
        index: 0
        autoOpen: true
    
        onIsOpenChanged: {
            console.log("printing")
            // print QR code on ZPL-based label printer
            write("^XA
    ^FO20,20^BQ,2,10^FDQA,0123456789ABCD 2D code^FS
    ^XZ")
            flush();
        }
    }
    