
.. _object_EventJournal:


:index:`EventJournal`
---------------------

Description
***********

The EventJournal object is an :ref:`EventOutput <object_EventOutput>` which formats the current date time, :ref:`Event::name <property_DataObject_name>` and :ref:`Event::description <property_DataObject_description>` to a string in one line and prints it to stdout. While debugging the output is forwarded to the debugger and visible in the appropriate view. In production the output is collected by the operating systems logging system and can be examined through ``journalctl``.

:**› Inherits**: :ref:`EventOutput <object_EventOutput>`

Overview
********

Properties
++++++++++

.. hlist::
  :columns: 1

  * :ref:`EventOutput.filterCategories <property_EventOutput_filterCategories>`
  * :ref:`EventOutput.filterExactSeverity <property_EventOutput_filterExactSeverity>`
  * :ref:`EventOutput.filterMinimumSeverity <property_EventOutput_filterMinimumSeverity>`
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

  * :ref:`EventOutput.filterCategoriesDataChanged() <signal_EventOutput_filterCategoriesDataChanged>`
  * :ref:`Object.completed() <signal_Object_completed>`



Properties
**********

Example
*******
See :ref:`Event example <example_Event>` on how to use EventJournal.
