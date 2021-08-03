
.. _object_ObjectArray:


:index:`ObjectArray`
--------------------

Description
***********

The ObjectArray object provides a container to group :ref:`Object <object_Object>` instances. This can be useful e.g. when :ref:`Gather <object_Gather>` is used to merge multiple lists or object hierarchies.

:**› Inherits**: :ref:`Object <object_Object>`
:**› Inherited by**: :ref:`Application <object_Application>`

Overview
********

Properties
++++++++++

.. hlist::
  :columns: 1

  * :ref:`objects <property_ObjectArray_objects>`
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

  * :ref:`objectsDataChanged() <signal_ObjectArray_objectsDataChanged>`
  * :ref:`Object.completed() <signal_Object_completed>`



Properties
**********


.. _property_ObjectArray_objects:

.. _signal_ObjectArray_objectsChanged:

.. index::
   single: objects

objects
+++++++

This property holds a list of :ref:`Object <object_Object>` instances.

:**› Type**: :ref:`List <object_List>`\<:ref:`Object <object_Object>`>
:**› Signal**: objectsChanged()
:**› Attributes**: Readonly

Signals
*******


.. _signal_ObjectArray_objectsDataChanged:

.. index::
   single: objectsDataChanged

objectsDataChanged(SignedInteger index)
+++++++++++++++++++++++++++++++++++++++

This signal is emitted whenever the :ref:`List.dataChanged() <signal_List_dataChanged>` signal is emitted, i.e. the item at ``index`` in the :ref:`objects <property_ObjectArray_objects>` list itself emitted the dataChanged() signal.



.. _example_ObjectArray:


Example
*******

.. code-block:: qml

    import InCore.Foundation 2.0
    
    Application {
    
        // Object Array with fixed elements - the usual way
        ObjectArray {
            id: objectArrayA
            Measurement {
                id: meas0
            }
            Measurement {
                id: meas1
            }
            onCompleted: console.log( "ObjectArray A ready with", objects.length, "objects" )
        }
    
        // ObjectArray with dynamic objects
        ObjectArray {
            id: objectArrayB
            Repeater on objects {
                model: 3
                Measurement {
                    objectId: "id" + index
                    data: index
                }
            }
            onObjectsChanged: console.log( "ObjectArray B has now", objects.length, "objects" )
        }
    
        // ObjectArray with elements of objectArrayA and objectArrayB
        ObjectArray {
            Gather on objects {
                source: ObjectArray {
                    List { reference: objectArrayA.objects }
                    List { reference: objectArrayB.objects }
                }
            }
            onObjectsChanged: console.log( "Combined list with", objects.length, "objects" )
        }
    
    }
    