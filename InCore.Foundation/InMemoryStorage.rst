
.. _object_InMemoryStorage:


:index:`InMemoryStorage`
------------------------

Description
***********

The InMemoryStorage object provides volatile storage in memory. It's limited by the amount of available RAM and cleared on every device start. It can be used to e.g. store temporary databases and caches which require fast I/O operations with low latencies but do not have to be persistent.

:**› Inherits**: :ref:`Storage <object_Storage>`

Overview
********

Properties
++++++++++

.. hlist::
  :columns: 1

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
  * :ref:`Object.toJson() <method_Object_toJson>`

Signals
+++++++

.. hlist::
  :columns: 1

  * :ref:`Object.completed() <signal_Object_completed>`



Properties
**********

