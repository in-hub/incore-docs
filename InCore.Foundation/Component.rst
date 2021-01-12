
.. _object_Component:


:index:`Component`
------------------

Description
***********

The Component object encapsulates a QML component definition. Components are reusable, encapsulated QML types with well-defined interfaces. A component can be instantiated through a :ref:`Repeater <object_Repeater>` or used for filtering types via :ref:`Gather.typeFilter <property_Gather_typeFilter>`.

This object was introduced in InCore 2.0.

:**› Inherits**: :ref:`Object <object_Object>`

Overview
********

Properties
++++++++++

.. hlist::
  :columns: 1

  * :ref:`source <property_Component_source>`
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


.. _property_Component_source:

.. _signal_Component_sourceChanged:

.. index::
   single: source

source
++++++

This property holds the actual QML component definition, e.g. `Measurement { ... }`.

:**› Type**: <QML component>
:**› Signal**: sourceChanged()
:**› Attributes**: Writable

