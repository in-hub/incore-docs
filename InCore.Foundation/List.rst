
.. _object_List:


:index:`List`
-------------

Description
***********

The List object provides a generic container for storing items or references to items. When instantiated explicitely it can be used to wrap simple ECMAScript/QML value arrays to properly support partial updates (i.e. emit the :ref:`dataChanged() <signal_List_dataChanged>` signal for individual items). Alternatively it can contain references to other objects. If these objects have a dataChanged() signal it is forwarded to the :ref:`dataChanged() <signal_List_dataChanged>` signal of the list as well. Wrapping another list is possible through the :ref:`reference <property_List_reference>` property.

:**› Inherits**: :ref:`Object <object_Object>`
:**› Inherited by**: :ref:`FifoBuffer <object_FifoBuffer>`

Overview
********

Properties
++++++++++

.. hlist::
  :columns: 1

  * :ref:`count <property_List_count>`
  * :ref:`items <property_List_items>`
  * :ref:`reference <property_List_reference>`
  * :ref:`Object.objectId <property_Object_objectId>`
  * :ref:`Object.parent <property_Object_parent>`

Methods
+++++++

.. hlist::
  :columns: 1

  * :ref:`setItem() <method_List_setItem>`
  * :ref:`Object.deserializeProperties() <method_Object_deserializeProperties>`
  * :ref:`Object.fromJson() <method_Object_fromJson>`
  * :ref:`Object.toJson() <method_Object_toJson>`

Signals
+++++++

.. hlist::
  :columns: 1

  * :ref:`changed() <signal_List_changed>`
  * :ref:`dataChanged() <signal_List_dataChanged>`
  * :ref:`itemAppended() <signal_List_itemAppended>`
  * :ref:`itemsCleared() <signal_List_itemsCleared>`
  * :ref:`objectAppended() <signal_List_objectAppended>`
  * :ref:`Object.completed() <signal_Object_completed>`



Properties
**********


.. _property_List_count:

.. _signal_List_countChanged:

.. index::
   single: count

count
+++++

This property holds the current number of items in the list. This property changes everytime the list is cleared or items are appended to the list.

:**› Type**: SignedInteger
:**› Signal**: countChanged()
:**› Attributes**: Readonly


.. _property_List_items:

.. _signal_List_itemsChanged:

.. index::
   single: items

items
+++++

This property holds a custom list of items stored as ECMAScript/QML arrays. Wrapping such arrays with a :ref:`List <object_List>` object allows using :ref:`property modifiers <object_PropertyModifier>` such as :ref:`Repeater <object_Repeater>` and :ref:`Gather <object_Gather>` on them.

:**› Type**: List
:**› Signal**: itemsChanged()
:**› Attributes**: Writable


.. _property_List_reference:

.. _signal_List_referenceChanged:

.. index::
   single: reference

reference
+++++++++

This property holds a reference to a another :ref:`List <object_List>` object. This makes this list behave exactly as the referenced list. This is usually only required when using :ref:`Gather <object_Gather>` to flatten hierarchical object lists.

:**› Type**: ListReference
:**› Signal**: referenceChanged()
:**› Attributes**: Writable

Methods
*******


.. _method_List_setItem:

.. index::
   single: setItem

setItem(SignedInteger index, Variant data)
++++++++++++++++++++++++++++++++++++++++++

This method changes a single element of the :ref:`custom item list <property_List_items>`. Use this method instead of writing ``list.items[n] = ...`` in order to properly emit the :ref:`dataChanged() <signal_List_dataChanged>` signal.


Signals
*******


.. _signal_List_changed:

.. index::
   single: changed

changed()
+++++++++

This signal is emitted whenever the list is changed, i.e. items have been appended, changed or cleared.



.. _signal_List_dataChanged:

.. index::
   single: dataChanged

dataChanged(SignedInteger index)
++++++++++++++++++++++++++++++++

This signal is emitted when an item at ``index`` has been updated or changed its value.



.. _signal_List_itemAppended:

.. index::
   single: itemAppended

itemAppended(SignedInteger index)
+++++++++++++++++++++++++++++++++

This signal is emitted when an item has been appended to the list. The index of the newly appended item is specified through the ``index`` parameter.



.. _signal_List_itemsCleared:

.. index::
   single: itemsCleared

itemsCleared()
++++++++++++++

This signal is emitted when the list has been cleared, i.e. contains no more items.



.. _signal_List_objectAppended:

.. index::
   single: objectAppended

objectAppended(:ref:`Object <object_Object>` object)
++++++++++++++++++++++++++++++++++++++++++++++++++++

This signal is emitted when an item of type :ref:`Object <object_Object>` or an inheriting object has been appended to the list. This special case is primarily used for internal purposes.



.. _example_List:


Example
*******

.. code-block:: qml

    import InCore.Foundation 2.5
    
    Application {
    
        // wrap value array into List object
        List {
            id: list
            items: [ 1, 2, 3 ]
            onChanged: console.log("List items:", items)
            onCountChanged: console.log("List has now", count, "items")
        }
    
        onCompleted: {
            list.setItem(1, 123)
            list.items = [ 2, 3, 4, 5 ];
            list.items = [ "A", "B", "C" ]
        }
    
    }
    