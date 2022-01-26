
.. _object_Translator:


:index:`Translator`
-------------------

Description
***********

The Translator object is used to translate strings into a given language. Available languages can be found in the :ref:`Application.Language <enum_Application_Language>` enumeration. The translation file consists of tab separated columns. The first column contains an ID followed by the translated strings to the supported language.

The Translator is connected to the ``languageChanged`` signal of :ref:`Application <object_Application>`. Each ID in the translation file is propagated to the root context.

:**› Inherits**: :ref:`Object <object_Object>`

Overview
********

Properties
++++++++++

.. hlist::
  :columns: 1

  * :ref:`file <property_Translator_file>`
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


.. _property_Translator_file:

.. _signal_Translator_fileChanged:

.. index::
   single: file

file
++++

This property holds the file name and path of the translation file relative to the application.

:**› Type**: String
:**› Default**: ``translations.csv``
:**› Signal**: fileChanged()
:**› Attributes**: Writable

