
.. _object_IoDevice:


:index:`IoDevice`
-----------------

Description
***********

The IoDevice object is the base interface class of all I/O devices. It provides both a common implementation and an interface for devices that support reading and writing of blocks of data, such as :ref:`File <object_File>`. It is therefore never used directly.

Before accessing data the device must be configured through the corresponding properties such as :ref:`readOnly <property_IoDevice_readOnly>`, :ref:`append <property_IoDevice_append>` and :ref:`truncate <property_IoDevice_truncate>`. It can then be opened via :ref:`open() <method_IoDevice_open>`. Objects interacting with I/O devices (e.g. :ref:`CsvWriter <object_CsvWriter>` or :ref:`EventLogFile <object_EventLogFile>`) usually open them automatically.

:**› Inherits**: :ref:`Object <object_Object>`
:**› Inherited by**: :ref:`File <object_File>`, :ref:`IpSocket <object_IpSocket>`, :ref:`WebSocket <object_WebSocket>`

Overview
********

Properties
++++++++++

.. hlist::
  :columns: 3

  * :ref:`append <property_IoDevice_append>`
  * :ref:`atEnd <property_IoDevice_atEnd>`
  * :ref:`autoOpen <property_IoDevice_autoOpen>`
  * :ref:`bytesAvailable <property_IoDevice_bytesAvailable>`
  * :ref:`canReadLine <property_IoDevice_canReadLine>`
  * :ref:`deviceErrorString <property_IoDevice_deviceErrorString>`
  * :ref:`isOpen <property_IoDevice_isOpen>`
  * :ref:`isWritable <property_IoDevice_isWritable>`
  * :ref:`nameArgument <property_IoDevice_nameArgument>`
  * :ref:`pos <property_IoDevice_pos>`
  * :ref:`readOnly <property_IoDevice_readOnly>`
  * :ref:`size <property_IoDevice_size>`
  * :ref:`truncate <property_IoDevice_truncate>`
  * :ref:`unbuffered <property_IoDevice_unbuffered>`
  * :ref:`Object.objectId <property_Object_objectId>`
  * :ref:`Object.parent <property_Object_parent>`

Methods
+++++++

.. hlist::
  :columns: 2

  * :ref:`close() <method_IoDevice_close>`
  * :ref:`flush() <method_IoDevice_flush>`
  * :ref:`open() <method_IoDevice_open>`
  * :ref:`peekAll() <method_IoDevice_peekAll>`
  * :ref:`read() <method_IoDevice_read>`
  * :ref:`readAll() <method_IoDevice_readAll>`
  * :ref:`readLine() <method_IoDevice_readLine>`
  * :ref:`sync() <method_IoDevice_sync>`
  * :ref:`write() <method_IoDevice_write>`
  * :ref:`Object.deserializeProperties() <method_Object_deserializeProperties>`
  * :ref:`Object.fromJson() <method_Object_fromJson>`
  * :ref:`Object.serializeProperties() <method_Object_serializeProperties>`
  * :ref:`Object.toJson() <method_Object_toJson>`

Signals
+++++++

.. hlist::
  :columns: 1

  * :ref:`lineAvailableForRead() <signal_IoDevice_lineAvailableForRead>`
  * :ref:`readyRead() <signal_IoDevice_readyRead>`
  * :ref:`Object.completed() <signal_Object_completed>`



Properties
**********


.. _property_IoDevice_append:

.. _signal_IoDevice_appendChanged:

.. index::
   single: append

append
++++++

This property holds whether the I/O device should be opened in append mode so that new data is always written to the end of the file. Changing this property on an open I/O device will call :ref:`close() <method_IoDevice_close>`.

:**› Type**: Boolean
:**› Default**: ``true``
:**› Signal**: appendChanged()
:**› Attributes**: Writable


.. _property_IoDevice_atEnd:

.. _signal_IoDevice_atEndChanged:

.. index::
   single: atEnd

atEnd
+++++

This property holds whether the current read and write position is at the end of the device (i.e. there is no more data available for reading on the device).

:**› Type**: Boolean
:**› Signal**: atEndChanged()
:**› Attributes**: Readonly


.. _property_IoDevice_autoOpen:

.. _signal_IoDevice_autoOpenChanged:

.. index::
   single: autoOpen

autoOpen
++++++++

This property holds whether to call :ref:`open() <method_IoDevice_open>` on initialization automatically.

This property was introduced in InCore 2.0.

:**› Type**: Boolean
:**› Default**: ``false``
:**› Signal**: autoOpenChanged()
:**› Attributes**: Writable


.. _property_IoDevice_bytesAvailable:

.. _signal_IoDevice_bytesAvailableChanged:

.. index::
   single: bytesAvailable

bytesAvailable
++++++++++++++

This property holds the number of bytes that are available for reading from the I/O device.

This property was introduced in InCore 2.0.

:**› Type**: SignedBigInteger
:**› Signal**: bytesAvailableChanged()
:**› Attributes**: Readonly


.. _property_IoDevice_canReadLine:

.. _signal_IoDevice_canReadLineChanged:

.. index::
   single: canReadLine

canReadLine
+++++++++++

This property holds whether a complete line of data can be read from the device.

This property was introduced in InCore 2.3.

:**› Type**: Boolean
:**› Signal**: canReadLineChanged()
:**› Attributes**: Readonly


.. _property_IoDevice_deviceErrorString:

.. _signal_IoDevice_deviceErrorStringChanged:

.. index::
   single: deviceErrorString

deviceErrorString
+++++++++++++++++

This property holds a human-readable description of the last device error that occurred.

:**› Type**: String
:**› Signal**: deviceErrorStringChanged()
:**› Attributes**: Readonly


.. _property_IoDevice_isOpen:

.. _signal_IoDevice_isOpenChanged:

.. index::
   single: isOpen

isOpen
++++++

This property holds whether the device is open. A device is open if it can be read from and/or written to.

:**› Type**: Boolean
:**› Signal**: isOpenChanged()
:**› Attributes**: Readonly


.. _property_IoDevice_isWritable:

.. _signal_IoDevice_isWritableChanged:

.. index::
   single: isWritable

isWritable
++++++++++

This property holds whether data can be written to the device, i.e. :ref:`readOnly <property_IoDevice_readOnly>` is ``false`` and the specified device or file is writable by the app.

:**› Type**: Boolean
:**› Signal**: isWritableChanged()
:**› Attributes**: Readonly


.. _property_IoDevice_nameArgument:

.. _signal_IoDevice_nameArgumentChanged:

.. index::
   single: nameArgument

nameArgument
++++++++++++

This property holds the data which is inserted in filenames if they contain a placeholder. This internal property is mainly used by :ref:`CsvWriter <object_CsvWriter>` to implement log file rotation.

:**› Type**: String
:**› Signal**: nameArgumentChanged()
:**› Attributes**: Writable


.. _property_IoDevice_pos:

.. _signal_IoDevice_posChanged:

.. index::
   single: pos

pos
+++

This property holds the current position of the device pointer. The next read or write operation always takes place at this position.

:**› Type**: SignedBigInteger
:**› Signal**: posChanged()
:**› Attributes**: Writable


.. _property_IoDevice_readOnly:

.. _signal_IoDevice_readOnlyChanged:

.. index::
   single: readOnly

readOnly
++++++++

This property holds whether the I/O device should be opened and accessed read-only. Changing this property on an open I/O device will call :ref:`close() <method_IoDevice_close>`.

:**› Type**: Boolean
:**› Default**: ``false``
:**› Signal**: readOnlyChanged()
:**› Attributes**: Writable


.. _property_IoDevice_size:

.. _signal_IoDevice_sizeChanged:

.. index::
   single: size

size
++++

This property holds the current size of the I/O device.

:**› Type**: SignedBigInteger
:**› Signal**: sizeChanged()
:**› Attributes**: Readonly


.. _property_IoDevice_truncate:

.. _signal_IoDevice_truncateChanged:

.. index::
   single: truncate

truncate
++++++++

This property holds whether the I/O device should always be truncated when opened. All previous contents of the device are lost. Changing this property on an open I/O device will call :ref:`close() <method_IoDevice_close>`.

:**› Type**: Boolean
:**› Default**: ``false``
:**› Signal**: truncateChanged()
:**› Attributes**: Writable


.. _property_IoDevice_unbuffered:

.. _signal_IoDevice_unbufferedChanged:

.. index::
   single: unbuffered

unbuffered
++++++++++

This property holds whether the I/O device should be opened in unbuffered mode. This will bypass any internal buffers and caches. Reading data will never fetch more data than requested. When writing all data is written to the underlying storage immediately. Changing this property on an open I/O device will call :ref:`close() <method_IoDevice_close>`.

:**› Type**: Boolean
:**› Default**: ``false``
:**› Signal**: unbufferedChanged()
:**› Attributes**: Writable

Methods
*******


.. _method_IoDevice_close:

.. index::
   single: close

close()
+++++++

This method flushes any buffered data and closes the I/O device.



.. _method_IoDevice_flush:

.. index::
   single: flush

flush()
+++++++

This method flushes all write buffers and possibly buffered data of the I/O device to the operating system.

This method was introduced in InCore 2.3.



.. _method_IoDevice_open:

.. index::
   single: open

open()
++++++

This method opens the I/O device for reading or writing depending on the corresponding properties. If the device could not be opened, ``false`` is returned. Otherwise ``true`` is returned. If :ref:`truncate <property_IoDevice_truncate>` is set to ``true`` the device is also truncated.

:**› Returns**: Boolean



.. _method_IoDevice_peekAll:

.. index::
   single: peekAll

peekAll()
+++++++++

This method reads all data from the I/O device without draining the read buffer. This is useful when implementing communications based on non-trivial protocols.

This method was introduced in InCore 2.0.

:**› Returns**: ArrayBuffer



.. _method_IoDevice_read:

.. index::
   single: read

read(SignedBigInteger maxSize)
++++++++++++++++++++++++++++++

This method reads at most the given number of bytes from the I/O device. An empty buffer is returned if either no more data is available for reading or reading failed for some reason.

:**› Returns**: ArrayBuffer



.. _method_IoDevice_readAll:

.. index::
   single: readAll

readAll()
+++++++++

This method reads all remaining data from the I/O device.

This method was introduced in InCore 2.0.

:**› Returns**: ArrayBuffer



.. _method_IoDevice_readLine:

.. index::
   single: readLine

readLine()
++++++++++

This method reads a line from the device (maximum 65535 characters) and returns the result as a UTF-8 encoded string. This function has no way of reporting errors, i.e. an empty string can mean either that no data was currently available for reading, or that an error occurred.

This method was introduced in InCore 2.3.

:**› Returns**: String



.. _method_IoDevice_sync:

.. index::
   single: sync

sync()
++++++

This method calls :ref:`IoDevice.flush() <method_IoDevice_flush>` and tells the operating system to write all pending data to its storages. Calling this method might block the program execution for a while depending on the amount of data to be written.



.. _method_IoDevice_write:

.. index::
   single: write

write(ArrayBuffer data)
+++++++++++++++++++++++

This method writes the given data to the I/O device. If :ref:`unbuffered <property_IoDevice_unbuffered>` is ``false`` the data may not actually be written until the device is closed or :ref:`flush() <method_IoDevice_flush>` is called.

:**› Returns**: SignedBigInteger


Signals
*******


.. _signal_IoDevice_lineAvailableForRead:

.. index::
   single: lineAvailableForRead

lineAvailableForRead()
++++++++++++++++++++++

This signal is emitted once everytime a a complete line of data can be read from the device. It will only be emitted again once new data is available, such as when a new payload of network data has arrived on a network socket, or when a new block of data has been appended to the device.

This signal was introduced in InCore 2.3.



.. _signal_IoDevice_readyRead:

.. index::
   single: readyRead

readyRead()
+++++++++++

This signal is emitted once everytime new data is available for reading from the device's current read channel. It will only be emitted again once new data is available, such as when a new payload of network data has arrived on a network socket, or when a new block of data has been appended to the device.

This signal was introduced in InCore 2.0.

