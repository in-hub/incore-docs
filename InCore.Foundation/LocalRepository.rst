
.. _object_LocalRepository:


:index:`LocalRepository`
------------------------

Description
***********

The LocalRepository object provides access to file resources which can be used e.g. for :ref:`UpdateManager <object_UpdateManager>` instances.

:**› Inherits**: :ref:`Repository <object_Repository>`
:**› Inherited by**: :ref:`UsbDriveRepository <object_UsbDriveRepository>`

Overview
********

Properties
++++++++++

.. hlist::
  :columns: 1

  * :ref:`storage <property_LocalRepository_storage>`
  * :ref:`Repository.error <property_Repository_error>`
  * :ref:`Repository.errorString <property_Repository_errorString>`
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

  * :ref:`Repository.errorOccurred() <signal_Repository_errorOccurred>`
  * :ref:`Object.completed() <signal_Object_completed>`

Enumerations
++++++++++++

.. hlist::
  :columns: 1

  * :ref:`Repository.Error <enum_Repository_Error>`



Properties
**********


.. _property_LocalRepository_storage:

.. _signal_LocalRepository_storageChanged:

.. index::
   single: storage

storage
+++++++

This property holds a reference to a :ref:`Storage <object_Storage>` object on which to search for update files. The :ref:`Storage.path <property_Storage_path>` property can be used to specify a subdirectory.

:**› Type**: :ref:`Storage <object_Storage>`
:**› Signal**: storageChanged()
:**› Attributes**: Writable

Example
*******
See :ref:`UpdateManager example <example_UpdateManager>` on how to use LocalRepository.
