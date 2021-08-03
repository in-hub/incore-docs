
.. _object_OpcUaServerNamespace:


:index:`OpcUaServerNamespace`
-----------------------------

Description
***********



This object was introduced in InCore 2.3.

:**› Inherits**: :ref:`Object <object_Object>`

Overview
********

Properties
++++++++++

.. hlist::
  :columns: 1

  * :ref:`index <property_OpcUaServerNamespace_index>`
  * :ref:`objects <property_OpcUaServerNamespace_objects>`
  * :ref:`uri <property_OpcUaServerNamespace_uri>`
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

  * :ref:`objectsDataChanged() <signal_OpcUaServerNamespace_objectsDataChanged>`
  * :ref:`Object.completed() <signal_Object_completed>`



Properties
**********


.. _property_OpcUaServerNamespace_index:

.. _signal_OpcUaServerNamespace_indexChanged:

.. index::
   single: index

index
+++++



:**› Type**: SignedInteger
:**› Signal**: indexChanged()
:**› Attributes**: Readonly


.. _property_OpcUaServerNamespace_objects:

.. _signal_OpcUaServerNamespace_objectsChanged:

.. index::
   single: objects

objects
+++++++



:**› Type**: :ref:`List <object_List>`\<:ref:`OpcUaServerObjectNode <object_OpcUaServerObjectNode>`>
:**› Signal**: objectsChanged()
:**› Attributes**: Readonly


.. _property_OpcUaServerNamespace_uri:

.. _signal_OpcUaServerNamespace_uriChanged:

.. index::
   single: uri

uri
+++



:**› Type**: String
:**› Signal**: uriChanged()
:**› Attributes**: Writable

Signals
*******


.. _signal_OpcUaServerNamespace_objectsDataChanged:

.. index::
   single: objectsDataChanged

objectsDataChanged(SignedInteger index)
+++++++++++++++++++++++++++++++++++++++

This signal is emitted whenever the :ref:`List.dataChanged() <signal_List_dataChanged>` signal is emitted, i.e. the item at ``index`` in the :ref:`objects <property_OpcUaServerNamespace_objects>` list itself emitted the dataChanged() signal.


Example
*******
See :ref:`OpcUaServer example <example_OpcUaServer>` on how to use OpcUaServerNamespace.
