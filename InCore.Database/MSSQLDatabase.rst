
.. _object_MSSQLDatabase:


:index:`MSSQLDatabase`
----------------------

Description
***********

The MSSQLDatabase object is used to connect to a Microsoft SQL Server using ODBC.

:**› Inherits**: :ref:`NetworkDatabase <object_NetworkDatabase>`

Overview
********

Properties
++++++++++

.. hlist::
  :columns: 3

  * :ref:`mars <property_MSSQLDatabase_mars>`
  * :ref:`tdsVersion <property_MSSQLDatabase_tdsVersion>`
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


.. _property_MSSQLDatabase_mars:

.. _signal_MSSQLDatabase_marsChanged:

.. index::
   single: mars

mars
++++

This property holds whether to enable `Multiple Active Result Sets (MARS) <https://docs.microsoft.com/en-us/dotnet/framework/data/adonet/sql/multiple-active-result-sets-mars>`_ when connecting to the server.

:**› Type**: Boolean
:**› Default**: ``false``
:**› Signal**: marsChanged()
:**› Attributes**: Writable, Optional


.. _property_MSSQLDatabase_tdsVersion:

.. _signal_MSSQLDatabase_tdsVersionChanged:

.. index::
   single: tdsVersion

tdsVersion
++++++++++

This property holds the TDS protocol version to use for connecting to the server. See `Choosing a TDS protocol version <https://www.freetds.org/userguide/choosingtdsprotocol.htm>`_ for details.

:**› Type**: String
:**› Signal**: tdsVersionChanged()
:**› Attributes**: Writable, Optional


.. _example_MSSQLDatabase:


Example
*******

.. code-block:: qml

    import InCore.Foundation 2.0
    import InCore.Database 2.0
    
    Application {
        version: "0.8.15"
    
        MSSQLDatabase {
            id: mssqlDB
            user: "yourUser"
            password: "y0urUserP@ssword"
            server: "mssql.yourcompany.com"
            port: 1433
    
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
    