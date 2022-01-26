
.. _object_GeneralApplicationSettings:


:index:`GeneralApplicationSettings`
-----------------------------------

Description
***********

The GeneralApplicationSettings object provides preinitialized :ref:`ConfigurationItem <object_ConfigurationItem>` objects for various general :ref:`Application <object_Application>` properties. The configuration items proxy the application's properties so they are synchronized in both directions automatically.

:**› Inherits**: :ref:`ConfigurationObject <object_ConfigurationObject>`

Overview
********

Properties
++++++++++

.. hlist::
  :columns: 2

  * :ref:`country <property_GeneralApplicationSettings_country>`
  * :ref:`countryItem <property_GeneralApplicationSettings_countryItem>`
  * :ref:`language <property_GeneralApplicationSettings_language>`
  * :ref:`languageItem <property_GeneralApplicationSettings_languageItem>`
  * :ref:`measurementSystem <property_GeneralApplicationSettings_measurementSystem>`
  * :ref:`measurementSystemItem <property_GeneralApplicationSettings_measurementSystemItem>`
  * :ref:`timeZone <property_GeneralApplicationSettings_timeZone>`
  * :ref:`timeZoneItem <property_GeneralApplicationSettings_timeZoneItem>`
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
  * :ref:`Object.serializeProperties() <method_Object_serializeProperties>`
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


.. _property_GeneralApplicationSettings_country:

.. _signal_GeneralApplicationSettings_countryChanged:

.. index::
   single: country

country
+++++++

This property holds the proxied :ref:`Application.country <property_Application_country>` property.

:**› Type**: :ref:`Application.Country <enum_Application_Country>`
:**› Signal**: countryChanged()
:**› Attributes**: Writable


.. _property_GeneralApplicationSettings_countryItem:

.. index::
   single: countryItem

countryItem
+++++++++++

This property holds an internal :ref:`ConfigurationItem <object_ConfigurationItem>` instance for the :ref:`country <property_GeneralApplicationSettings_country>` property.

:**› Type**: :ref:`ConfigurationItem <object_ConfigurationItem>`
:**› Attributes**: Readonly


.. _property_GeneralApplicationSettings_language:

.. _signal_GeneralApplicationSettings_languageChanged:

.. index::
   single: language

language
++++++++

This property holds the proxied :ref:`Application.language <property_Application_language>` property.

:**› Type**: :ref:`Application.Language <enum_Application_Language>`
:**› Signal**: languageChanged()
:**› Attributes**: Writable


.. _property_GeneralApplicationSettings_languageItem:

.. index::
   single: languageItem

languageItem
++++++++++++

This property holds an internal :ref:`ConfigurationItem <object_ConfigurationItem>` instance for the :ref:`language <property_GeneralApplicationSettings_language>` property.

:**› Type**: :ref:`ConfigurationItem <object_ConfigurationItem>`
:**› Attributes**: Readonly


.. _property_GeneralApplicationSettings_measurementSystem:

.. _signal_GeneralApplicationSettings_measurementSystemChanged:

.. index::
   single: measurementSystem

measurementSystem
+++++++++++++++++

This property holds the proxied :ref:`Application.measurementSystem <property_Application_measurementSystem>` property.

:**› Type**: :ref:`Measurement.System <enum_Measurement_System>`
:**› Signal**: measurementSystemChanged()
:**› Attributes**: Writable


.. _property_GeneralApplicationSettings_measurementSystemItem:

.. index::
   single: measurementSystemItem

measurementSystemItem
+++++++++++++++++++++

This property holds an internal :ref:`ConfigurationItem <object_ConfigurationItem>` instance for the :ref:`measurementSystem <property_GeneralApplicationSettings_measurementSystem>` property.

:**› Type**: :ref:`ConfigurationItem <object_ConfigurationItem>`
:**› Attributes**: Readonly


.. _property_GeneralApplicationSettings_timeZone:

.. _signal_GeneralApplicationSettings_timeZoneChanged:

.. index::
   single: timeZone

timeZone
++++++++

This property holds the proxied :ref:`Application.timeZone <property_Application_timeZone>` property.

:**› Type**: String
:**› Signal**: timeZoneChanged()
:**› Attributes**: Writable


.. _property_GeneralApplicationSettings_timeZoneItem:

.. index::
   single: timeZoneItem

timeZoneItem
++++++++++++

This property holds an internal :ref:`ConfigurationItem <object_ConfigurationItem>` instance for the :ref:`timeZone <property_GeneralApplicationSettings_timeZone>` property.

:**› Type**: :ref:`ConfigurationItem <object_ConfigurationItem>`
:**› Attributes**: Readonly

