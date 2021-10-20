
.. _object_NetworkDatabase:


:index:`NetworkDatabase`
------------------------

Description
***********

The NetworkDatabase object holds common properties for all kinds of databases reachable through network connections.

:**› Inherits**: :ref:`Database <object_Database>`
:**› Inherited by**: :ref:`MSSQLDatabase <object_MSSQLDatabase>`, :ref:`MySQLDatabase <object_MySQLDatabase>`, :ref:`PostgreSQLDatabase <object_PostgreSQLDatabase>`

Overview
********

Properties
++++++++++

.. hlist::
  :columns: 3

  * :ref:`password <property_NetworkDatabase_password>`
  * :ref:`port <property_NetworkDatabase_port>`
  * :ref:`server <property_NetworkDatabase_server>`
  * :ref:`user <property_NetworkDatabase_user>`
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


.. _property_NetworkDatabase_password:

.. _signal_NetworkDatabase_passwordChanged:

.. index::
   single: password

password
++++++++

This property holds the password to use for connecting to the database.

:**› Type**: String
:**› Signal**: passwordChanged()
:**› Attributes**: Writable


.. _property_NetworkDatabase_port:

.. _signal_NetworkDatabase_portChanged:

.. index::
   single: port

port
++++

This property holds the port of the database server to connect to. This property is initialized with the database-specific default value, e.g. ``3306`` for :ref:`MySQLDatabase <object_MySQLDatabase>` or ``1433`` for :ref:`MSSQLDatabase <object_MSSQLDatabase>`.

:**› Type**: SignedInteger
:**› Default**: ``-1``
:**› Signal**: portChanged()
:**› Attributes**: Writable


.. _property_NetworkDatabase_server:

.. _signal_NetworkDatabase_serverChanged:

.. index::
   single: server

server
++++++

This property holds the hostname or IP address of the database server to connect to.

:**› Type**: String
:**› Signal**: serverChanged()
:**› Attributes**: Writable


.. _property_NetworkDatabase_user:

.. _signal_NetworkDatabase_userChanged:

.. index::
   single: user

user
++++

This property holds the username to use for connecting to the database.

:**› Type**: String
:**› Signal**: userChanged()
:**› Attributes**: Writable
