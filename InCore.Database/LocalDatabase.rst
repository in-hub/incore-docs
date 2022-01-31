
.. _object_LocalDatabase:


:index:`LocalDatabase`
----------------------

Description
***********

The LocalDatabase object is used to store data in a local database using SQLite. The filename is constructed based on the :ref:`Database.name <property_Database_name>` property or alternatively on the object ID, either specified through the QML object ID or the :ref:`Object.objectId <property_Object_objectId>` property.

:**› Inherits**: :ref:`Database <object_Database>`

Overview
********

Properties
++++++++++

.. hlist::
  :columns: 2

  * :ref:`storage <property_LocalDatabase_storage>`
  * :ref:`Database.autoOpen <property_Database_autoOpen>`
  * :ref:`Database.closeOnConnectionError <property_Database_closeOnConnectionError>`
  * :ref:`Database.debugSqlQueries <property_Database_debugSqlQueries>`
  * :ref:`Database.error <property_Database_error>`
  * :ref:`Database.errorDetails <property_Database_errorDetails>`
  * :ref:`Database.errorString <property_Database_errorString>`
  * :ref:`Database.name <property_Database_name>`
  * :ref:`Database.ready <property_Database_ready>`
  * :ref:`Database.reopenInterval <property_Database_reopenInterval>`
  * :ref:`Database.sqlQueries <property_Database_sqlQueries>`
  * :ref:`Database.tables <property_Database_tables>`
  * :ref:`Object.objectId <property_Object_objectId>`
  * :ref:`Object.parent <property_Object_parent>`

Methods
+++++++

.. hlist::
  :columns: 1

  * :ref:`Database.close() <method_Database_close>`
  * :ref:`Database.dropAllTables() <method_Database_dropAllTables>`
  * :ref:`Database.open() <method_Database_open>`
  * :ref:`Object.deserializeProperties() <method_Object_deserializeProperties>`
  * :ref:`Object.fromJson() <method_Object_fromJson>`
  * :ref:`Object.serializeProperties() <method_Object_serializeProperties>`
  * :ref:`Object.toJson() <method_Object_toJson>`

Signals
+++++++

.. hlist::
  :columns: 1

  * :ref:`Database.errorOccurred() <signal_Database_errorOccurred>`
  * :ref:`Database.sqlQueriesDataChanged() <signal_Database_sqlQueriesDataChanged>`
  * :ref:`Database.tablesDataChanged() <signal_Database_tablesDataChanged>`
  * :ref:`Object.completed() <signal_Object_completed>`

Enumerations
++++++++++++

.. hlist::
  :columns: 1

  * :ref:`Database.Error <enum_Database_Error>`



Properties
**********


.. _property_LocalDatabase_storage:

.. _signal_LocalDatabase_storageChanged:

.. index::
   single: storage

storage
+++++++

This property holds the storage where the database is saved. If left blank a :ref:`LocalStorage <object_LocalStorage>` object is used.

:**› Type**: :ref:`Storage <object_Storage>`
:**› Signal**: storageChanged()
:**› Attributes**: Writable, Optional


.. _example_LocalDatabase:


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
    
                submitMode: DatabaseTable.SubmitOnCompleteDataset
    
                DateTime { id: date }
                Measurement { id: temperature; data: 25 }
            }
    
            sqlQueries: [
                DatabaseSqlQuery {
                    forwardOnly: true
                    query: "SELECT AVG(temperature) AS average
                            FROM exampleTable"
                    Polling on results { interval: 10000 }
                    onResultsChanged: console.log( "average temperature", results[0].average )
                    onErrorChanged: console.log(errorString)
                }
            ]
        }
    
        Timer {
            onTriggered: temperature.data += -0.5 + Math.random()
        }
    }
    