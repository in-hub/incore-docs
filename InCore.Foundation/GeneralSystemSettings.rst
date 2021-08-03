
.. _object_GeneralSystemSettings:


:index:`GeneralSystemSettings`
------------------------------

Description
***********

The GeneralSystemSettings object provides preinitialized :ref:`ConfigurationItem <object_ConfigurationItem>` objects for various general :ref:`System <object_System>` properties. The configuration items proxy the system's properties so they are synchronized in both directions automatically.

:**› Inherits**: :ref:`ConfigurationObject <object_ConfigurationObject>`

Overview
********

Properties
++++++++++

.. hlist::
  :columns: 2

  * :ref:`deviceName <property_GeneralSystemSettings_deviceName>`
  * :ref:`deviceNameItem <property_GeneralSystemSettings_deviceNameItem>`
  * :ref:`hostname <property_GeneralSystemSettings_hostname>`
  * :ref:`hostnameItem <property_GeneralSystemSettings_hostnameItem>`
  * :ref:`system <property_GeneralSystemSettings_system>`
  * :ref:`ConfigurationObject.items <property_ConfigurationObject_items>`
  * :ref:`ConfigurationObject.name <property_ConfigurationObject_name>`
  * :ref:`ConfigurationObject.nameItem <property_ConfigurationObject_nameItem>`
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

  * :ref:`ConfigurationObject.aboutToBeUpdated() <signal_ConfigurationObject_aboutToBeUpdated>`
  * :ref:`ConfigurationObject.itemsDataChanged() <signal_ConfigurationObject_itemsDataChanged>`
  * :ref:`ConfigurationObject.updated() <signal_ConfigurationObject_updated>`
  * :ref:`Object.completed() <signal_Object_completed>`



Properties
**********


.. _property_GeneralSystemSettings_deviceName:

.. _signal_GeneralSystemSettings_deviceNameChanged:

.. index::
   single: deviceName

deviceName
++++++++++

This property holds the proxied :ref:`System.deviceName <property_System_deviceName>` property.

:**› Type**: String
:**› Signal**: deviceNameChanged()
:**› Attributes**: Writable


.. _property_GeneralSystemSettings_deviceNameItem:

.. index::
   single: deviceNameItem

deviceNameItem
++++++++++++++

This property holds an internal :ref:`ConfigurationItem <object_ConfigurationItem>` instance for the :ref:`deviceName <property_GeneralSystemSettings_deviceName>` property.

:**› Type**: :ref:`ConfigurationItem <object_ConfigurationItem>`
:**› Attributes**: Readonly


.. _property_GeneralSystemSettings_hostname:

.. _signal_GeneralSystemSettings_hostnameChanged:

.. index::
   single: hostname

hostname
++++++++

This property holds the proxied :ref:`System.hostname <property_System_hostname>` property.

:**› Type**: String
:**› Signal**: hostnameChanged()
:**› Attributes**: Writable


.. _property_GeneralSystemSettings_hostnameItem:

.. index::
   single: hostnameItem

hostnameItem
++++++++++++

This property holds an internal :ref:`ConfigurationItem <object_ConfigurationItem>` instance for the :ref:`hostname <property_GeneralSystemSettings_hostname>` property.

:**› Type**: :ref:`ConfigurationItem <object_ConfigurationItem>`
:**› Attributes**: Readonly


.. _property_GeneralSystemSettings_system:

.. _signal_GeneralSystemSettings_systemChanged:

.. index::
   single: system

system
++++++

This property holds a reference to a :ref:`System <object_System>` object. Per default an instance is created and assigned automatically so there's no need to override it except an alternative global object ID should be used.

:**› Type**: :ref:`System <object_System>`
:**› Signal**: systemChanged()
:**› Attributes**: Writable

