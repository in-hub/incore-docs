
.. _object_UpdateTarget:


:index:`UpdateTarget`
---------------------

Description
***********

The UpdateTarget object represents a system component which can be updated using an update bundle.

:**› Inherits**: :ref:`Object <object_Object>`

Overview
********

Properties
++++++++++

.. hlist::
  :columns: 1

  * :ref:`bundlePrefix <property_UpdateTarget_bundlePrefix>`
  * :ref:`bundleSuffix <property_UpdateTarget_bundleSuffix>`
  * :ref:`currentVersion <property_UpdateTarget_currentVersion>`
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


.. _property_UpdateTarget_bundlePrefix:

.. _signal_UpdateTarget_bundlePrefixChanged:

.. index::
   single: bundlePrefix

bundlePrefix
++++++++++++

This property holds the prefix for valid update bundles. All files with different prefixes will not be installed to this target.

:**› Type**: String
:**› Signal**: bundlePrefixChanged()
:**› Attributes**: Writable


.. _property_UpdateTarget_bundleSuffix:

.. _signal_UpdateTarget_bundleSuffixChanged:

.. index::
   single: bundleSuffix

bundleSuffix
++++++++++++

This property holds the suffix for valid update bundles. All files with different suffixes will not be installed to this target.

:**› Type**: String
:**› Default**: ``.raucb``
:**› Signal**: bundleSuffixChanged()
:**› Attributes**: Writable


.. _property_UpdateTarget_currentVersion:

.. _signal_UpdateTarget_currentVersionChanged:

.. index::
   single: currentVersion

currentVersion
++++++++++++++

This property holds the currently installed version of the component.

:**› Type**: String
:**› Signal**: currentVersionChanged()
:**› Attributes**: Writable

Example
*******
See :ref:`UpdateManager example <example_UpdateManager>` on how to use UpdateTarget.
