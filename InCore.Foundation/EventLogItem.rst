
.. _object_EventLogItem:


:index:`EventLogItem`
---------------------

Description
***********

The EventLogItem object is the base object for all kinds of items within an :ref:`EventLog <object_EventLog>` object. It can't be used directly and is available for internal purposes only. Use dedicated items instead:

* :ref:`EventCategory <object_EventCategory>`
* :ref:`EventGroup <object_EventGroup>`


:**› Inherits**: :ref:`Object <object_Object>`
:**› Inherited by**: :ref:`ErrorCollector <object_ErrorCollector>`, :ref:`EventCategory <object_EventCategory>`, :ref:`EventGroup <object_EventGroup>`

Overview
********

Properties
++++++++++

.. hlist::
  :columns: 1

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
