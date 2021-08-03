
.. _object_PropertyModifier:


:index:`PropertyModifier`
-------------------------

Description
***********

The PropertyModifier object is the base object for all objects which modify properties of foreign objects in a certain way. Property modifier objects are instantiated and used through the special ``on`` keyword inside the target objects:

.. code-block:: qml

    MySensorObject {
        ...
        Polling on sensorValueProperty { ... }
    }


:**› Inherits**: :ref:`Object <object_Object>`
:**› Inherited by**: :ref:`Gather <object_Gather>`, :ref:`Polling <object_Polling>`, :ref:`ReduceList <object_ReduceList>`, :ref:`Repeater <object_Repeater>`, :ref:`Select <object_Select>`, :ref:`TransformList <object_TransformList>`

Overview
********

Properties
++++++++++

.. hlist::
  :columns: 1

  * :ref:`targetValue <property_PropertyModifier_targetValue>`
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

  * :ref:`Object.completed() <signal_Object_completed>`



Properties
**********


.. _property_PropertyModifier_targetValue:

.. _signal_PropertyModifier_targetValueChanged:

.. index::
   single: targetValue

targetValue
+++++++++++

This property holds the value of the property this modifier operates on.

:**› Type**: Variant
:**› Signal**: targetValueChanged()
:**› Attributes**: Readonly

