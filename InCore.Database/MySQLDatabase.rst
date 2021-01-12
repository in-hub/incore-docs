
.. _object_MySQLDatabase:


:index:`MySQLDatabase`
----------------------

Description
***********

The MySQLDatabase object is used to connect to MySQL Server.

:**› Inherits**: :ref:`NetworkDatabase <object_NetworkDatabase>`

Overview
********

Properties
++++++++++

.. hlist::
  :columns: 3

  * :ref:`databaseName <property_MySQLDatabase_databaseName>`
  * :ref:`NetworkDatabase.password <property_NetworkDatabase_password>`
  * :ref:`NetworkDatabase.port <property_NetworkDatabase_port>`
  * :ref:`NetworkDatabase.server <property_NetworkDatabase_server>`
  * :ref:`NetworkDatabase.user <property_NetworkDatabase_user>`
  * :ref:`Database.autoOpen <property_Database_autoOpen>`
  * :ref:`Database.closeOnConnectionError <property_Database_closeOnConnectionError>`
  * :ref:`Database.debugSqlQueries <property_Database_debugSqlQueries>`
  * :ref:`Database.error <property_Database_error>`
  * :ref:`Database.errorDetails <property_Database_errorDetails>`
  * :ref:`Database.errorString <property_Database_errorString>`
  * :ref:`Database.name <property_Database_name>`
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
  * :ref:`Object.fromJson() <method_Object_fromJson>`
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


.. _property_MySQLDatabase_databaseName:

.. _signal_MySQLDatabase_databaseNameChanged:

.. index::
   single: databaseName

databaseName
++++++++++++

This property holds the name of the connection's database.

:**› Type**: String
:**› Signal**: databaseNameChanged()
:**› Attributes**: Writable


.. _example_MySQLDatabase:


Example
*******

.. code-block:: qml

    import InCore.Foundation 1.0
    import InCore.Database 1.0
    
    Application {
        version: "0.8.15"
    
        MySQLDatabase {
            id: mysqlDB
            user: "root"
            password: "mysql"
            databaseName: "test"
            server: "10.1.2.6"
            port: 3306
    
            sqlQueries: [
                DatabaseSqlQuery {
                    id: updateVersionQuery
                    forwardOnly: true
                    query: ("EXEC [updateVersion]
                        @Version = %1")
                    .arg( version )
    
                    onErrorChanged: console.log( errorString )
                }
            ]
    
            onCompleted: updateVersionQuery.execute()
        }
    }
    