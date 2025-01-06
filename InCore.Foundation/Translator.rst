
.. _object_Translator:


:index:`Translator`
-------------------

Description
***********

The Translator object is used to load translation files for the :ref:`Application <object_Application>`'s current language.

This object was introduced in InCore 2.8.

:**› Inherits**: :ref:`Object <object_Object>`

Overview
********

Properties
++++++++++

.. hlist::
  :columns: 1

  * :ref:`path <property_Translator_path>`
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


.. _property_Translator_path:

.. _signal_Translator_pathChanged:

.. index::
   single: path

path
++++

This property holds the path of a directory which to the load translation file from.

:**› Type**: String
:**› Signal**: pathChanged()
:**› Attributes**: Writable

