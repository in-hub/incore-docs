
.. _object_Database:


:index:`Database`
-----------------

Description
***********

The Database object is the base class of all database objects. It contains a list of :ref:`DatabaseTable <object_DatabaseTable>` objects and :ref:`DatabaseSqlQuery <object_DatabaseSqlQuery>` objects.

:**› Inherits**: :ref:`Object <object_Object>`
:**› Inherited by**: :ref:`LocalDatabase <object_LocalDatabase>`, :ref:`NetworkDatabase <object_NetworkDatabase>`

Overview
********

Properties
++++++++++

.. hlist::
  :columns: 2

  * :ref:`autoOpen <property_Database_autoOpen>`
  * :ref:`closeOnConnectionError <property_Database_closeOnConnectionError>`
  * :ref:`debugSqlQueries <property_Database_debugSqlQueries>`
  * :ref:`error <property_Database_error>`
  * :ref:`errorDetails <property_Database_errorDetails>`
  * :ref:`errorString <property_Database_errorString>`
  * :ref:`name <property_Database_name>`
  * :ref:`reopenInterval <property_Database_reopenInterval>`
  * :ref:`sqlQueries <property_Database_sqlQueries>`
  * :ref:`tables <property_Database_tables>`
  * :ref:`Object.objectId <property_Object_objectId>`
  * :ref:`Object.parent <property_Object_parent>`

Methods
+++++++

.. hlist::
  :columns: 1

  * :ref:`close() <method_Database_close>`
  * :ref:`dropAllTables() <method_Database_dropAllTables>`
  * :ref:`open() <method_Database_open>`
  * :ref:`Object.deserializeProperties() <method_Object_deserializeProperties>`
  * :ref:`Object.fromJson() <method_Object_fromJson>`
  * :ref:`Object.toJson() <method_Object_toJson>`

Signals
+++++++

.. hlist::
  :columns: 1

  * :ref:`errorOccurred() <signal_Database_errorOccurred>`
  * :ref:`sqlQueriesDataChanged() <signal_Database_sqlQueriesDataChanged>`
  * :ref:`tablesDataChanged() <signal_Database_tablesDataChanged>`
  * :ref:`Object.completed() <signal_Object_completed>`

Enumerations
++++++++++++

.. hlist::
  :columns: 1

  * :ref:`Error <enum_Database_Error>`



Properties
**********


.. _property_Database_autoOpen:

.. _signal_Database_autoOpenChanged:

.. index::
   single: autoOpen

autoOpen
++++++++

This property holds whether to automatically open a connection to the database.

:**› Type**: Boolean
:**› Default**: ``true``
:**› Signal**: autoOpenChanged()
:**› Attributes**: Writable


.. _property_Database_closeOnConnectionError:

.. _signal_Database_closeOnConnectionErrorChanged:

.. index::
   single: closeOnConnectionError

closeOnConnectionError
++++++++++++++++++++++

This property holds whether to automatically call :ref:`close() <method_Database_close>` whenever a connection error (:ref:`Database.ConnectionError <enumitem_Database_ConnectionError>`) occurs. In conjunction with :ref:`autoOpen <property_Database_autoOpen>` enabling this property allows implementing resilient database connections.

This property was introduced in InCore 1.1.

:**› Type**: Boolean
:**› Default**: ``true``
:**› Signal**: closeOnConnectionErrorChanged()
:**› Attributes**: Writable


.. _property_Database_debugSqlQueries:

.. _signal_Database_debugSqlQueriesChanged:

.. index::
   single: debugSqlQueries

debugSqlQueries
+++++++++++++++

This property holds whether to log all executed SQL queries and resulting error messages to the console.

This property was introduced in InCore 1.1.

:**› Type**: Boolean
:**› Default**: ``false``
:**› Signal**: debugSqlQueriesChanged()
:**› Attributes**: Writable, Optional


.. _property_Database_error:

.. _signal_Database_errorChanged:

.. index::
   single: error

error
+++++

This property holds the most recently occurred error or :ref:`Database.NoError <enumitem_Database_NoError>` if no error occurred. If the same error occurs multiple times this property does not change. Use the :ref:`errorOccurred() <signal_Database_errorOccurred>` signal to detect multiple occurrences of the same error.

:**› Type**: :ref:`Error <enum_Database_Error>`
:**› Signal**: errorChanged()
:**› Attributes**: Readonly


.. _property_Database_errorDetails:

.. index::
   single: errorDetails

errorDetails
++++++++++++

This property holds a human-readable database- or driver-specific description of the last error. It may provide additional information to :ref:`errorString <property_Database_errorString>` whenever an :ref:`error occurs <signal_Database_errorOccurred>`.

:**› Type**: String
:**› Attributes**: Readonly


.. _property_Database_errorString:

.. _signal_Database_errorStringChanged:

.. index::
   single: errorString

errorString
+++++++++++

This property holds the current human readable error string corresponding to the current value in the :ref:`error <property_Database_error>` property. It may include additional information such as failure reasons or locations.

:**› Type**: String
:**› Signal**: errorStringChanged()
:**› Attributes**: Readonly


.. _property_Database_name:

.. _signal_Database_nameChanged:

.. index::
   single: name

name
++++

This property holds the name of the database to access. It depends on the actually used database implementation and the server configuration whether this property is honored or even required.

:**› Type**: String
:**› Signal**: nameChanged()
:**› Attributes**: Writable


.. _property_Database_reopenInterval:

.. _signal_Database_reopenIntervalChanged:

.. index::
   single: reopenInterval

reopenInterval
++++++++++++++

This property holds the interval in milliseconds in which the database is reopened in case a connection is lost or failed. Set to 0 to disable this behaviour.

:**› Type**: SignedInteger
:**› Default**: ``60000``
:**› Signal**: reopenIntervalChanged()
:**› Attributes**: Writable


.. _property_Database_sqlQueries:

.. _signal_Database_sqlQueriesChanged:

.. index::
   single: sqlQueries

sqlQueries
++++++++++

This property holds a list of :ref:`DatabaseSqlQuery <object_DatabaseSqlQuery>` objects.

:**› Type**: :ref:`List <object_List>`\<:ref:`DatabaseSqlQuery <object_DatabaseSqlQuery>`>
:**› Signal**: sqlQueriesChanged()
:**› Attributes**: Readonly


.. _property_Database_tables:

.. _signal_Database_tablesChanged:

.. index::
   single: tables

tables
++++++

This property holds a list of :ref:`DatabaseTable <object_DatabaseTable>` objects. Each table will be mapped to a table in the database file.

:**› Type**: :ref:`List <object_List>`\<:ref:`DatabaseTable <object_DatabaseTable>`>
:**› Signal**: tablesChanged()
:**› Attributes**: Readonly

Methods
*******


.. _method_Database_close:

.. index::
   single: close

close()
+++++++

This method closes the database and frees all internal resources.

This method was introduced in InCore 1.1.



.. _method_Database_dropAllTables:

.. index::
   single: dropAllTables

dropAllTables()
+++++++++++++++

This method removes all tables from the database. All tables are closed before being dropping.

:**› Returns**: Boolean



.. _method_Database_open:

.. index::
   single: open

open()
++++++

This method (re)opens the database. The internal database is recreated.


Signals
*******


.. _signal_Database_errorOccurred:

.. index::
   single: errorOccurred

errorOccurred()
+++++++++++++++

This signal is emitted whenever an error has occurred, regardless of whether the :ref:`error <property_Database_error>` property has changed or not. In contrast to the change notification signal of the :ref:`error <property_Database_error>` property this signal is also emitted several times if a certain error occurs several times in succession.



.. _signal_Database_sqlQueriesDataChanged:

.. index::
   single: sqlQueriesDataChanged

sqlQueriesDataChanged(SignedInteger index)
++++++++++++++++++++++++++++++++++++++++++

This signal is emitted whenever the :ref:`List.dataChanged() <signal_List_dataChanged>` signal is emitted, i.e. the item at ``index`` in the :ref:`sqlQueries <property_Database_sqlQueries>` list itself emitted the dataChanged() signal.



.. _signal_Database_tablesDataChanged:

.. index::
   single: tablesDataChanged

tablesDataChanged(SignedInteger index)
++++++++++++++++++++++++++++++++++++++

This signal is emitted whenever the :ref:`List.dataChanged() <signal_List_dataChanged>` signal is emitted, i.e. the item at ``index`` in the :ref:`tables <property_Database_tables>` list itself emitted the dataChanged() signal.


Enumerations
************


.. _enum_Database_Error:

.. index::
   single: Error

Error
+++++

This enumeration describes all errors which can occur in Database objects. The most recently occurred error is stored in the :ref:`error <property_Database_error>` property.

.. index::
   single: Database.NoError
.. index::
   single: Database.InvalidStorageError
.. index::
   single: Database.StoragePathError
.. index::
   single: Database.OpenError
.. index::
   single: Database.InitializationError
.. index::
   single: Database.CreateTablesError
.. index::
   single: Database.InvalidCredentials
.. index::
   single: Database.InvalidNameError
.. index::
   single: Database.ConnectionError
.. list-table::
  :widths: auto
  :header-rows: 1

  * - Name
    - Value
    - Description

      .. _enumitem_Database_NoError:
  * - ``Database.NoError``
    - ``0``
    - No error occurred or was detected.

      .. _enumitem_Database_InvalidStorageError:
  * - ``Database.InvalidStorageError``
    - ``1``
    - None or invalid storage set.

      .. _enumitem_Database_StoragePathError:
  * - ``Database.StoragePathError``
    - ``2``
    - Error while creating directories on storage.

      .. _enumitem_Database_OpenError:
  * - ``Database.OpenError``
    - ``3``
    - Can't open database.

      .. _enumitem_Database_InitializationError:
  * - ``Database.InitializationError``
    - ``4``
    - Error while performing database initialization tasks.

      .. _enumitem_Database_CreateTablesError:
  * - ``Database.CreateTablesError``
    - ``5``
    - Failed to create tables in database.

      .. _enumitem_Database_InvalidCredentials:
  * - ``Database.InvalidCredentials``
    - ``6``
    - Some credentials are missing or invalid, e.g. no password set.

      .. _enumitem_Database_InvalidNameError:
  * - ``Database.InvalidNameError``
    - ``7``
    - None or invalid database name specified.

      .. _enumitem_Database_ConnectionError:
  * - ``Database.ConnectionError``
    - ``8``
    - Connection lost.
