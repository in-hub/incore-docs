
.. _object_DatabaseUpdate:


:index:`DatabaseUpdate`
-----------------------

Description
***********

The DatabaseUpdate object is used to update objects in a database table. The API is identical to :ref:`DatabaseQuery <object_DatabaseQuery>` except for the :ref:`execute() <method_DatabaseUpdate_execute>` method.

This object was introduced in InCore 2.5.

:**› Inherits**: :ref:`DatabaseQuery <object_DatabaseQuery>`

Overview
********

Properties
++++++++++

.. hlist::
  :columns: 2

  * :ref:`DatabaseQuery.error <property_DatabaseQuery_error>`
  * :ref:`DatabaseQuery.errorString <property_DatabaseQuery_errorString>`
  * :ref:`DatabaseQuery.filters <property_DatabaseQuery_filters>`
  * :ref:`DatabaseQuery.limitLength <property_DatabaseQuery_limitLength>`
  * :ref:`DatabaseQuery.limitPos <property_DatabaseQuery_limitPos>`
  * :ref:`DatabaseQuery.objects <property_DatabaseQuery_objects>`
  * :ref:`DatabaseQuery.orderBy <property_DatabaseQuery_orderBy>`
  * :ref:`DatabaseQuery.orderByNames <property_DatabaseQuery_orderByNames>`
  * :ref:`DatabaseQuery.results <property_DatabaseQuery_results>`
  * :ref:`DatabaseQuery.table <property_DatabaseQuery_table>`
  * :ref:`Object.objectId <property_Object_objectId>`
  * :ref:`Object.parent <property_Object_parent>`

Methods
+++++++

.. hlist::
  :columns: 1

  * :ref:`execute() <method_DatabaseUpdate_execute>`
  * :ref:`DatabaseQuery.execute() <method_DatabaseQuery_execute>`
  * :ref:`DatabaseQuery.pollResults() <method_DatabaseQuery_pollResults>`
  * :ref:`Object.deserializeProperties() <method_Object_deserializeProperties>`
  * :ref:`Object.fromJson() <method_Object_fromJson>`
  * :ref:`Object.serializeProperties() <method_Object_serializeProperties>`
  * :ref:`Object.toJson() <method_Object_toJson>`

Signals
+++++++

.. hlist::
  :columns: 1

  * :ref:`DatabaseQuery.errorOccurred() <signal_DatabaseQuery_errorOccurred>`
  * :ref:`DatabaseQuery.filtersDataChanged() <signal_DatabaseQuery_filtersDataChanged>`
  * :ref:`DatabaseQuery.objectsDataChanged() <signal_DatabaseQuery_objectsDataChanged>`
  * :ref:`DatabaseQuery.orderByDataChanged() <signal_DatabaseQuery_orderByDataChanged>`
  * :ref:`Object.completed() <signal_Object_completed>`

Enumerations
++++++++++++

.. hlist::
  :columns: 1

  * :ref:`DatabaseQuery.Error <enum_DatabaseQuery_Error>`



Properties
**********

Methods
*******


.. _method_DatabaseUpdate_execute:

.. index::
   single: execute

execute()
+++++++++

This method updates the columns specified by :ref:`DatabaseQuery.objects <property_DatabaseQuery_objects>` and rows filtered through :ref:`DatabaseQuery.filters <property_DatabaseQuery_filters>`. If at least one row has been updated and no error occurred, ``true`` is returned, otherwise ``false``. The number of updated rows can be retrieved using the :ref:`DatabaseQuery.results <property_DatabaseQuery_results>` property.

:**› Returns**: Boolean



.. _example_DatabaseUpdate:


Example
*******

.. code-block:: qml

    import InCore.Foundation 2.5
    import InCore.Database 2.5
    
    Application {
    
        LocalDatabase {
            id: exampleDatabase
    
            DatabaseTable {
                id: exampleTable
    
                // submit a new data row every 10s
                submitInterval: 10000
                submitMode: DatabaseTable.SubmitPeriodically
                onSubmitted: lastIdQuery.execute()
    
                DataObject {
                    id: exampleTableId
                    objectId: "id"
                    dataType: DataObject.SignedInteger
                    DatabaseFieldOptions.primaryKey: true
                    DatabaseFieldOptions.autoIncrement: true
                }
    
                Measurement {
                    id: sensor1
                    data: 1
                    onDataChanged: updateSensor1.execute()
                }
    
                Measurement {
                    id: sensor2
                    data: 123
                }
    
                queries: [
                    // always update last row with latest value of sensor1
                    DatabaseUpdate {
                        id: updateSensor1
                        objects: [sensor1]
                        DatabaseQueryFilter {
                            DatabaseQueryWhere {
                                key: exampleTableId
                                operation: DatabaseQueryWhere.Equals
                                value: lastIdQuery.results[0] ? lastIdQuery.results[0].id : -1
                            }
                        }
                    },
                    DatabaseQuery {
                        id: lastIdQuery
                        objects: [exampleTableId]
                        orderByNames: ["-id"]
                        limitPos: 0
                        limitLength: 1
                    }
                ]
            }
        }
    
        Timer {
            onTriggered: sensor1.data = Math.random() * 100
        }
    }
    