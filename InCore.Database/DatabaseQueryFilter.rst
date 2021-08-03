
.. _object_DatabaseQueryFilter:


:index:`DatabaseQueryFilter`
----------------------------

Description
***********

The DatabaseQueryFilter object represents a query filter used in :ref:`DatabaseQuery <object_DatabaseQuery>` objects. Each filter consists of a set of :ref:`DatabaseQueryWhere <object_DatabaseQueryWhere>` objects which are combined using logical ``OR``. This means that one of the defined ``WHERE`` conditions have to match to make the whole filter match for a particular row.

:**› Inherits**: :ref:`Object <object_Object>`

Overview
********

Properties
++++++++++

.. hlist::
  :columns: 1

  * :ref:`where <property_DatabaseQueryFilter_where>`
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

  * :ref:`whereDataChanged() <signal_DatabaseQueryFilter_whereDataChanged>`
  * :ref:`Object.completed() <signal_Object_completed>`



Properties
**********


.. _property_DatabaseQueryFilter_where:

.. _signal_DatabaseQueryFilter_whereChanged:

.. index::
   single: where

where
+++++

This property holds one or multiple :ref:`DatabaseQueryWhere <object_DatabaseQueryWhere>` instances or references to them used to create an SQL query for this filter.

:**› Type**: :ref:`List <object_List>`\<:ref:`DatabaseQueryWhere <object_DatabaseQueryWhere>`>
:**› Signal**: whereChanged()
:**› Attributes**: Readonly

Signals
*******


.. _signal_DatabaseQueryFilter_whereDataChanged:

.. index::
   single: whereDataChanged

whereDataChanged(SignedInteger index)
+++++++++++++++++++++++++++++++++++++

This signal is emitted whenever the :ref:`List.dataChanged() <signal_List_dataChanged>` signal is emitted, i.e. the item at ``index`` in the :ref:`where <property_DatabaseQueryFilter_where>` list itself emitted the dataChanged() signal.



.. _example_DatabaseQueryFilter:


Example
*******

.. code-block:: qml

    import InCore.Foundation 2.0
    import InCore.Database 2.0
    
    Application {
    
        LocalDatabase {
            id: exampleDatabase
    
            DatabaseTable {
                id: exampleTable
    
                DateTime { id: date }
                Measurement { id: temperature1 }
                Measurement { id: temperature2 }
    
                queries: [
                    DatabaseQuery {
                        id: exampleQuery
                        DatabaseQueryFilter {
                            DatabaseQueryWhere { key: temperature1; operation: DatabaseQueryWhere.GreaterThan; value: 20 }
                            DatabaseQueryWhere { key: temperature2; operation: DatabaseQueryWhere.LessThan; value: 30 }
                        }
    
                        onResultsChanged: console.log(toJson(results))
                    }
                ]
            }
        }
    
        Timer {
            onTriggered: {
                temperature1.data = 25 - Math.random() * 20
                temperature2.data = 25 + Math.random() * 20
                exampleTable.submit()
                exampleQuery.execute()
            }
        }
    
        onCompleted: exampleTable.drop()
    }
    