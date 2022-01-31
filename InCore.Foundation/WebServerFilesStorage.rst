
.. _object_WebServerFilesStorage:


:index:`WebServerFilesStorage`
------------------------------

Description
***********

The WebServerFilesStorage object provides access to data files served by a :ref:`WebServerService <object_WebServerService>`. It can be used to implement apps which dynamically generate downloadable content which is accessible through the web server at the ``/incore`` location, e.g. ``http://192.168.123.1/incore/foo.csv``.

This object was introduced in InCore 2.1.

:**› Inherits**: :ref:`Storage <object_Storage>`

Overview
********

Properties
++++++++++

.. hlist::
  :columns: 2

  * :ref:`persistent <property_WebServerFilesStorage_persistent>`
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


.. _property_WebServerFilesStorage_persistent:

.. _signal_WebServerFilesStorage_persistentChanged:

.. index::
   single: persistent

persistent
++++++++++

This property defines whether to store files on this storage persistently. When set to ``false`` all files are stored in memory only (similar to :ref:`InMemoryStorage <object_InMemoryStorage>`) and are lost on every restart of the device. Otherwise files are stored on the data partition of the local device (similar to :ref:`LocalStorage <object_LocalStorage>`).

:**› Type**: Boolean
:**› Default**: ``false``
:**› Signal**: persistentChanged()
:**› Attributes**: Writable

