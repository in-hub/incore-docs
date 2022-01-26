
.. _object_LocalStorage:


:index:`LocalStorage`
---------------------

Description
***********

The LocalStorage object provides a persistent storage on the local device. A data partition on the internal flash memory is used for this purpose. The total capacity of this data partition is about 6 GB. The :ref:`DockerService <object_DockerService>` object stores the Docker containers on this data partition as well which reduces the available space accordingly.

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
  * :ref:`Object.serializeProperties() <method_Object_serializeProperties>`
  * :ref:`Object.toJson() <method_Object_toJson>`

Signals
+++++++

.. hlist::
  :columns: 1

  * :ref:`Object.completed() <signal_Object_completed>`



Properties
**********

