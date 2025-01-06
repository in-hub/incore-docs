
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
  :columns: 2

  * :ref:`bytesReadPerSecond <property_LocalStorage_bytesReadPerSecond>`
  * :ref:`bytesWrittenPerSecond <property_LocalStorage_bytesWrittenPerSecond>`
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

  * :ref:`pollBytesReadPerSecond() <method_LocalStorage_pollBytesReadPerSecond>`
  * :ref:`pollBytesWrittenPerSecond() <method_LocalStorage_pollBytesWrittenPerSecond>`
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


.. _property_LocalStorage_bytesReadPerSecond:

.. _signal_LocalStorage_bytesReadPerSecondChanged:

.. index::
   single: bytesReadPerSecond

bytesReadPerSecond
++++++++++++++++++

This property holds the number of bytes read per second from the underlying block device during the last polling interval.

This property was introduced in InCore 2.8.

:**› Type**: SignedInteger
:**› Signal**: bytesReadPerSecondChanged()
:**› Attributes**: Readonly, Requires :ref:`Polling <object_Polling>`


.. _property_LocalStorage_bytesWrittenPerSecond:

.. _signal_LocalStorage_bytesWrittenPerSecondChanged:

.. index::
   single: bytesWrittenPerSecond

bytesWrittenPerSecond
+++++++++++++++++++++

This property holds the number of bytes written per second to the underlying block device during the last polling interval.

This property was introduced in InCore 2.8.

:**› Type**: SignedInteger
:**› Signal**: bytesWrittenPerSecondChanged()
:**› Attributes**: Readonly, Requires :ref:`Polling <object_Polling>`

Methods
*******


.. _method_LocalStorage_pollBytesReadPerSecond:

.. index::
   single: pollBytesReadPerSecond

pollBytesReadPerSecond()
++++++++++++++++++++++++

This method polls the :ref:`bytesReadPerSecond <property_LocalStorage_bytesReadPerSecond>` property. It is called automatically when using a :ref:`Polling <object_Polling>` property modifier on this property and usually does not have to be called manually.



.. _method_LocalStorage_pollBytesWrittenPerSecond:

.. index::
   single: pollBytesWrittenPerSecond

pollBytesWrittenPerSecond()
+++++++++++++++++++++++++++

This method polls the :ref:`bytesWrittenPerSecond <property_LocalStorage_bytesWrittenPerSecond>` property. It is called automatically when using a :ref:`Polling <object_Polling>` property modifier on this property and usually does not have to be called manually.


