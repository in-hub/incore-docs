
.. _object_ConfigurationArray:


:index:`ConfigurationArray`
---------------------------

Description
***********

The ConfigurationArray object encapsulates a list of :ref:`Configuration <object_Configuration>` objects. Mostly to be used with Fluentum.

:**› Inherits**: :ref:`Object <object_Object>`

Overview
********

Properties
++++++++++

.. hlist::
  :columns: 1

  * :ref:`configurations <property_ConfigurationArray_configurations>`
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

  * :ref:`configurationsDataChanged() <signal_ConfigurationArray_configurationsDataChanged>`
  * :ref:`Object.completed() <signal_Object_completed>`



Properties
**********


.. _property_ConfigurationArray_configurations:

.. _signal_ConfigurationArray_configurationsChanged:

.. index::
   single: configurations

configurations
++++++++++++++

This property holds a list of :ref:`Configuration <object_Configuration>` objects or objects derived from it.

:**› Type**: :ref:`List <object_List>`\<:ref:`Configuration <object_Configuration>`>
:**› Signal**: configurationsChanged()
:**› Attributes**: Readonly

Signals
*******


.. _signal_ConfigurationArray_configurationsDataChanged:

.. index::
   single: configurationsDataChanged

configurationsDataChanged(SignedInteger index)
++++++++++++++++++++++++++++++++++++++++++++++

This signal is emitted whenever the :ref:`List.dataChanged() <signal_List_dataChanged>` signal is emitted, i.e. the item at ``index`` in the :ref:`configurations <property_ConfigurationArray_configurations>` list itself emitted the dataChanged() signal.


