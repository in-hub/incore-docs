
.. _object_NetworkConfiguration:


:index:`NetworkConfiguration`
-----------------------------

Description
***********

The NetworkConfiguration object manages the configuration of one or multiple :ref:`NetworkInterface <object_NetworkInterface>` objects. All :ref:`NetworkInterface <object_NetworkInterface>` objects require :ref:`NetworkConfiguration <object_NetworkConfiguration>` as parent to configure and control the represented network interfaces. An :ref:`NetworkConfiguration <object_NetworkConfiguration>` object loads and saves the corresponding configuration and tells the system's network management service to apply the configuration.

:**› Inherits**: :ref:`Configuration <object_Configuration>`

Overview
********

Properties
++++++++++

.. hlist::
  :columns: 2

  * :ref:`interfaces <property_NetworkConfiguration_interfaces>`
  * :ref:`Configuration.error <property_Configuration_error>`
  * :ref:`Configuration.errorString <property_Configuration_errorString>`
  * :ref:`Configuration.name <property_Configuration_name>`
  * :ref:`Configuration.objects <property_Configuration_objects>`
  * :ref:`Configuration.saveMode <property_Configuration_saveMode>`
  * :ref:`Configuration.storage <property_Configuration_storage>`
  * :ref:`Object.objectId <property_Object_objectId>`
  * :ref:`Object.parent <property_Object_parent>`

Methods
+++++++

.. hlist::
  :columns: 1

  * :ref:`Configuration.load() <method_Configuration_load>`
  * :ref:`Configuration.save() <method_Configuration_save>`
  * :ref:`Configuration.toDataMap() <method_Configuration_toDataMap>`
  * :ref:`Object.deserializeProperties() <method_Object_deserializeProperties>`
  * :ref:`Object.fromJson() <method_Object_fromJson>`
  * :ref:`Object.serializeProperties() <method_Object_serializeProperties>`
  * :ref:`Object.toJson() <method_Object_toJson>`

Signals
+++++++

.. hlist::
  :columns: 1

  * :ref:`interfacesDataChanged() <signal_NetworkConfiguration_interfacesDataChanged>`
  * :ref:`reconfigured() <signal_NetworkConfiguration_reconfigured>`
  * :ref:`Configuration.aboutToBeUpdated() <signal_Configuration_aboutToBeUpdated>`
  * :ref:`Configuration.errorOccurred() <signal_Configuration_errorOccurred>`
  * :ref:`Configuration.objectsDataChanged() <signal_Configuration_objectsDataChanged>`
  * :ref:`Configuration.updated() <signal_Configuration_updated>`
  * :ref:`Object.completed() <signal_Object_completed>`

Enumerations
++++++++++++

.. hlist::
  :columns: 1

  * :ref:`Configuration.Error <enum_Configuration_Error>`
  * :ref:`Configuration.SaveMode <enum_Configuration_SaveMode>`



Properties
**********


.. _property_NetworkConfiguration_interfaces:

.. _signal_NetworkConfiguration_interfacesChanged:

.. index::
   single: interfaces

interfaces
++++++++++

This property holds a list of network interfaces whose configuration to manage.

:**› Type**: :ref:`List <object_List>`\<:ref:`NetworkInterface <object_NetworkInterface>`>
:**› Signal**: interfacesChanged()
:**› Attributes**: Readonly

Signals
*******


.. _signal_NetworkConfiguration_interfacesDataChanged:

.. index::
   single: interfacesDataChanged

interfacesDataChanged(SignedInteger index)
++++++++++++++++++++++++++++++++++++++++++

This signal is emitted whenever the :ref:`List.dataChanged() <signal_List_dataChanged>` signal is emitted, i.e. the item at ``index`` in the :ref:`interfaces <property_NetworkConfiguration_interfaces>` list itself emitted the dataChanged() signal.



.. _signal_NetworkConfiguration_reconfigured:

.. index::
   single: reconfigured

reconfigured()
++++++++++++++

This signal is emitted whenever the configuration has been written to the system and the system's network management service has been instructed to apply it.


