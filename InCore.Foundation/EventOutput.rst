
.. _object_EventOutput:


:index:`EventOutput`
--------------------

Description
***********

The EventOutput object is the base object for all kinds of items which transform or handle events. It defines some overall properties for filtering which of the given events should be handled. This object can't be used directly and is available for internal purposes only. Use dedicated items instead:

* :ref:`EventJournal <object_EventJournal>`
* :ref:`EventLogFile <object_EventLogFile>`
* :ref:`DatabaseEventWriter <object_DatabaseEventWriter>`
* :ref:`CloudOfThingsEventWriter <object_CloudOfThingsEventWriter>`


:**› Inherits**: :ref:`Object <object_Object>`
:**› Inherited by**: :ref:`EventJournal <object_EventJournal>`, :ref:`EventLogFile <object_EventLogFile>`

Overview
********

Properties
++++++++++

.. hlist::
  :columns: 1

  * :ref:`filterCategories <property_EventOutput_filterCategories>`
  * :ref:`filterExactSeverity <property_EventOutput_filterExactSeverity>`
  * :ref:`filterMinimumSeverity <property_EventOutput_filterMinimumSeverity>`
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

  * :ref:`filterCategoriesDataChanged() <signal_EventOutput_filterCategoriesDataChanged>`
  * :ref:`Object.completed() <signal_Object_completed>`



Properties
**********


.. _property_EventOutput_filterCategories:

.. _signal_EventOutput_filterCategoriesChanged:

.. index::
   single: filterCategories

filterCategories
++++++++++++++++

This property holds a list of :ref:`EventCategory <object_EventCategory>` objects. Given :ref:`Event <object_Event>` objects will only be handled if its :ref:`Event.category <property_Event_category>` property matches with one item of this list. Leaving this property blank, disables this constraint.

:**› Type**: :ref:`List <object_List>`\<:ref:`EventCategory <object_EventCategory>`>
:**› Signal**: filterCategoriesChanged()
:**› Attributes**: Readonly


.. _property_EventOutput_filterExactSeverity:

.. _signal_EventOutput_filterExactSeverityChanged:

.. index::
   single: filterExactSeverity

filterExactSeverity
+++++++++++++++++++

This property holds the severity a given :ref:`Event <object_Event>` has to match to be handled. This property is implemented as an exclusive or with :ref:`filterMinimumSeverity <property_EventOutput_filterMinimumSeverity>`. Leaving this property set to :ref:`Event.NoSeverity <enumitem_Event_NoSeverity>` to disable this constraint.

:**› Type**: :ref:`Event.Severity <enum_Event_Severity>`
:**› Default**: :ref:`Event.NoSeverity <enumitem_Event_NoSeverity>`
:**› Signal**: filterExactSeverityChanged()
:**› Attributes**: Writable


.. _property_EventOutput_filterMinimumSeverity:

.. _signal_EventOutput_filterMinimumSeverityChanged:

.. index::
   single: filterMinimumSeverity

filterMinimumSeverity
+++++++++++++++++++++

This property holds the minimum serverity a given :ref:`Event <object_Event>` has to have to be handled. This property is implemented as an exclusive or with :ref:`filterExactSeverity <property_EventOutput_filterExactSeverity>`. Leaving this property set to :ref:`Event.NoSeverity <enumitem_Event_NoSeverity>` to disable this constraint.

:**› Type**: :ref:`Event.Severity <enum_Event_Severity>`
:**› Default**: :ref:`Event.NoSeverity <enumitem_Event_NoSeverity>`
:**› Signal**: filterMinimumSeverityChanged()
:**› Attributes**: Writable

Signals
*******


.. _signal_EventOutput_filterCategoriesDataChanged:

.. index::
   single: filterCategoriesDataChanged

filterCategoriesDataChanged(SignedInteger index)
++++++++++++++++++++++++++++++++++++++++++++++++

This signal is emitted whenever the :ref:`List.dataChanged() <signal_List_dataChanged>` signal is emitted, i.e. the item at ``index`` in the :ref:`filterCategories <property_EventOutput_filterCategories>` list itself emitted the dataChanged() signal.

