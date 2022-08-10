
.. _module_Database:


:index:`InCore Database`
========================

Description
-----------

The Database module enables you to interact with databases. This module can be used to store or query datasets to/from local or remote databases. Every :ref:`Database <object_Database>` object has :ref:`DatabaseTables <object_DatabaseTable>` and :ref:`DatabaseQueries <object_DatabaseQuery>`. The DatabaseTable contains a list of objects which should be stored and which could be queried with DatabaseQuery. For deeper interference :ref:`DatabaseSqlQuery <object_DatabaseSqlQuery>` could be used to execute raw SQL or stored procedures. There are several objects for different database types. :ref:`LocalDatabase <object_LocalDatabase>` uses SQLite to store data on the device.


Objects
-------

.. toctree::
	:maxdepth: 1

	Database
	DatabaseEventTable
	DatabaseEventWriter
	DatabaseExporter
	DatabaseFieldOptions
	DatabaseMeasurementWriter
	DatabaseQuery
	DatabaseQueryFilter
	DatabaseQueryWhere
	DatabaseSqlQuery
	DatabaseTable
	DatabaseUpdate
	LocalDatabase
	MSSQLDatabase
	MeasurementBufferDatabase
	MySQLDatabase
	NetworkDatabase
	PostgreSQLDatabase
