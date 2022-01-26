
.. _object_File:


:index:`File`
-------------

Description
***********

The File object is an :ref:`IoDevice <object_IoDevice>` object allowing to :ref:`read <method_IoDevice_read>`,:ref:`write <method_IoDevice_write>` and :ref:`remove <method_File_remove>` files. In general a file is always stored on a certain :ref:`storage <property_File_storage>` which also predefines the absolute path to the file. A relative path (i.e. subdirectories) may be included in the :ref:`file name <property_File_fileName>`.

:**› Inherits**: :ref:`IoDevice <object_IoDevice>`

Overview
********

Properties
++++++++++

.. hlist::
  :columns: 3

  * :ref:`error <property_File_error>`
  * :ref:`errorString <property_File_errorString>`
  * :ref:`fileName <property_File_fileName>`
  * :ref:`storage <property_File_storage>`
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

  * :ref:`remove() <method_File_remove>`
  * :ref:`sync() <method_File_sync>`
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

  * :ref:`errorOccurred() <signal_File_errorOccurred>`
  * :ref:`IoDevice.lineAvailableForRead() <signal_IoDevice_lineAvailableForRead>`
  * :ref:`IoDevice.readyRead() <signal_IoDevice_readyRead>`
  * :ref:`Object.completed() <signal_Object_completed>`

Enumerations
++++++++++++

.. hlist::
  :columns: 1

  * :ref:`Error <enum_File_Error>`



Properties
**********


.. _property_File_error:

.. _signal_File_errorChanged:

.. index::
   single: error

error
+++++

This property holds the most recently occurred error or :ref:`File.NoError <enumitem_File_NoError>` if no error occurred. If the same error occurs multiple times this property does not change. Use the :ref:`errorOccurred() <signal_File_errorOccurred>` signal to detect multiple occurrences of the same error.

:**› Type**: :ref:`Error <enum_File_Error>`
:**› Signal**: errorChanged()
:**› Attributes**: Readonly


.. _property_File_errorString:

.. _signal_File_errorStringChanged:

.. index::
   single: errorString

errorString
+++++++++++

This property holds the current human readable error string corresponding to the current value in the :ref:`error <property_File_error>` property. It may include additional information such as failure reasons or locations.

:**› Type**: String
:**› Signal**: errorStringChanged()
:**› Attributes**: Readonly


.. _property_File_fileName:

.. _signal_File_fileNameChanged:

.. index::
   single: fileName

fileName
++++++++

This property holds the name of the file. It is always relative to the :ref:`storage <property_File_storage>` which this file is stored on. The file name has to be set before the file is :ref:`opened <method_IoDevice_open>`.

:**› Type**: String
:**› Signal**: fileNameChanged()
:**› Attributes**: Writable


.. _property_File_storage:

.. _signal_File_storageChanged:

.. index::
   single: storage

storage
+++++++

This property holds a reference to the storage which the file is stored on. It has to be set before the file is :ref:`opened <method_IoDevice_open>`.

:**› Type**: :ref:`Storage <object_Storage>`
:**› Signal**: storageChanged()
:**› Attributes**: Writable

Methods
*******


.. _method_File_remove:

.. index::
   single: remove

remove()
++++++++

This method removes the file specified by :ref:`fileName <property_File_fileName>` and stored on :ref:`storage <property_File_storage>`.

:**› Returns**: Boolean



.. _method_File_sync:

.. index::
   single: sync

sync()
++++++

This method calls :ref:`IoDevice.flush() <method_IoDevice_flush>` and tells the operating system to write all pending data to its storages. Calling this method might block the program execution for a while depending on the amount of data to be written.


Signals
*******


.. _signal_File_errorOccurred:

.. index::
   single: errorOccurred

errorOccurred()
+++++++++++++++

This signal is emitted whenever an error has occurred, regardless of whether the :ref:`error <property_File_error>` property has changed or not. In contrast to the change notification signal of the :ref:`error <property_File_error>` property this signal is also emitted several times if a certain error occurs several times in succession.


Enumerations
************


.. _enum_File_Error:

.. index::
   single: Error

Error
+++++

This enumeration describes all errors which can occur in File objects. The most recently occurred error is stored in the :ref:`error <property_File_error>` property.

.. index::
   single: File.NoError
.. index::
   single: File.InvalidStorageError
.. index::
   single: File.StoragePathError
.. index::
   single: File.OpenError
.. list-table::
  :widths: auto
  :header-rows: 1

  * - Name
    - Value
    - Description

      .. _enumitem_File_NoError:
  * - ``File.NoError``
    - ``0``
    - No error occurred or was detected.

      .. _enumitem_File_InvalidStorageError:
  * - ``File.InvalidStorageError``
    - ``1``
    - None or invalid storage set.

      .. _enumitem_File_StoragePathError:
  * - ``File.StoragePathError``
    - ``2``
    - Error while creating directories on storage.

      .. _enumitem_File_OpenError:
  * - ``File.OpenError``
    - ``3``
    - Error while opening file likely due to permission problem.

