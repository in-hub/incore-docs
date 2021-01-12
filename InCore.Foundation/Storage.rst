
.. _object_Storage:


:index:`Storage`
----------------

Description
***********

The Storage object provides common functionality for all storage implementations such as :ref:`LocalStorage <object_LocalStorage>`, :ref:`InMemoryStorage <object_InMemoryStorage>` and :ref:`UsbStorage <object_UsbStorage>`. Being an abstract base it can't be instantiated.

:**› Inherits**: :ref:`Object <object_Object>`
:**› Inherited by**: :ref:`InMemoryStorage <object_InMemoryStorage>`, :ref:`LocalStorage <object_LocalStorage>`, :ref:`UsbStorage <object_UsbStorage>`, :ref:`WebServerFilesStorage <object_WebServerFilesStorage>`

Overview
********

Properties
++++++++++

.. hlist::
  :columns: 1

  * :ref:`available <property_Storage_available>`
  * :ref:`bytesFree <property_Storage_bytesFree>`
  * :ref:`bytesTotal <property_Storage_bytesTotal>`
  * :ref:`path <property_Storage_path>`
  * :ref:`readOnly <property_Storage_readOnly>`
  * :ref:`Object.objectId <property_Object_objectId>`
  * :ref:`Object.parent <property_Object_parent>`

Methods
+++++++

.. hlist::
  :columns: 1

  * :ref:`Object.fromJson() <method_Object_fromJson>`
  * :ref:`Object.toJson() <method_Object_toJson>`

Signals
+++++++

.. hlist::
  :columns: 1

  * :ref:`Object.completed() <signal_Object_completed>`



Properties
**********


.. _property_Storage_available:

.. _signal_Storage_availableChanged:

.. index::
   single: available

available
+++++++++

This property holds whether the storage is available. This typically applies to removable storage devices or network shares.

:**› Type**: Boolean
:**› Signal**: availableChanged()
:**› Attributes**: Readonly


.. _property_Storage_bytesFree:

.. index::
   single: bytesFree

bytesFree
+++++++++

This property holds the available capacity on the storage in bytes. It is not updated automatically and needs to be read whenever required.

:**› Type**: SignedBigInteger
:**› Attributes**: Readonly


.. _property_Storage_bytesTotal:

.. index::
   single: bytesTotal

bytesTotal
++++++++++

This property holds the total capacity of the storage in bytes. It is not updated automatically and needs to be read whenever required.

:**› Type**: SignedBigInteger
:**› Attributes**: Readonly


.. _property_Storage_path:

.. _signal_Storage_pathChanged:

.. index::
   single: path

path
++++

This property holds the absolute filesystem path of the storage.

:**› Type**: String
:**› Signal**: pathChanged()
:**› Attributes**: Readonly


.. _property_Storage_readOnly:

.. _signal_Storage_readOnlyChanged:

.. index::
   single: readOnly

readOnly
++++++++

This property holds whether the storage can be accessed read only. Write accesses to the storage are only possible if this property is ``false``.

:**› Type**: Boolean
:**› Signal**: readOnlyChanged()
:**› Attributes**: Readonly
