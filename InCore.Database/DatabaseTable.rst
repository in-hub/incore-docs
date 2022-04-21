
.. _object_DatabaseTable:


:index:`DatabaseTable`
----------------------

Description
***********

The DatabaseTable object represents a database table in a database. The :ref:`Object.objectId <property_Object_objectId>` property or alternatively the `QML ID attribute <https://doc.qt.io/qt-5/qtqml-syntax-objectattributes.html#the-id-attribute>`_ is used as name of the table in the database. If :ref:`DataObjectWriter.objects <property_DataObjectWriter_objects>` contains an object which value is ``NaN`` or ``Inf`` it will be saved as ``0`` due to database limitations.

:**› Inherits**: :ref:`DataObjectWriter <object_DataObjectWriter>`
:**› Inherited by**: :ref:`DatabaseEventTable <object_DatabaseEventTable>`

Overview
********

Properties
++++++++++

.. hlist::
  :columns: 3

  * :ref:`database <property_DatabaseTable_database>`
  * :ref:`defaultFieldOptions <property_DatabaseTable_defaultFieldOptions>`
  * :ref:`error <property_DatabaseTable_error>`
  * :ref:`errorString <property_DatabaseTable_errorString>`
  * :ref:`operationsEnabled <property_DatabaseTable_operationsEnabled>`
  * :ref:`pseudoRingBufferOrderBy <property_DatabaseTable_pseudoRingBufferOrderBy>`
  * :ref:`pseudoRingBufferSize <property_DatabaseTable_pseudoRingBufferSize>`
  * :ref:`queries <property_DatabaseTable_queries>`
  * :ref:`ready <property_DatabaseTable_ready>`
  * :ref:`structure <property_DatabaseTable_structure>`
  * :ref:`DataObjectWriter.datasetCount <property_DataObjectWriter_datasetCount>`
  * :ref:`DataObjectWriter.objects <property_DataObjectWriter_objects>`
  * :ref:`DataObjectWriter.running <property_DataObjectWriter_running>`
  * :ref:`DataObjectWriter.submitChangedObjectsOnly <property_DataObjectWriter_submitChangedObjectsOnly>`
  * :ref:`DataObjectWriter.submitInterval <property_DataObjectWriter_submitInterval>`
  * :ref:`DataObjectWriter.submitMode <property_DataObjectWriter_submitMode>`
  * :ref:`Object.objectId <property_Object_objectId>`
  * :ref:`Object.parent <property_Object_parent>`

Methods
+++++++

.. hlist::
  :columns: 2

  * :ref:`drop() <method_DatabaseTable_drop>`
  * :ref:`DataObjectWriter.close() <method_DataObjectWriter_close>`
  * :ref:`DataObjectWriter.open() <method_DataObjectWriter_open>`
  * :ref:`DataObjectWriter.submit() <method_DataObjectWriter_submit>`
  * :ref:`DataObjectWriter.sync() <method_DataObjectWriter_sync>`
  * :ref:`DataObjectWriter.truncate() <method_DataObjectWriter_truncate>`
  * :ref:`Object.deserializeProperties() <method_Object_deserializeProperties>`
  * :ref:`Object.fromJson() <method_Object_fromJson>`
  * :ref:`Object.serializeProperties() <method_Object_serializeProperties>`
  * :ref:`Object.toJson() <method_Object_toJson>`

Signals
+++++++

.. hlist::
  :columns: 1

  * :ref:`errorOccurred() <signal_DatabaseTable_errorOccurred>`
  * :ref:`queriesDataChanged() <signal_DatabaseTable_queriesDataChanged>`
  * :ref:`structureDataChanged() <signal_DatabaseTable_structureDataChanged>`
  * :ref:`DataObjectWriter.objectsDataChanged() <signal_DataObjectWriter_objectsDataChanged>`
  * :ref:`DataObjectWriter.submitted() <signal_DataObjectWriter_submitted>`
  * :ref:`DataObjectWriter.truncated() <signal_DataObjectWriter_truncated>`
  * :ref:`Object.completed() <signal_Object_completed>`

Enumerations
++++++++++++

.. hlist::
  :columns: 1

  * :ref:`Error <enum_DatabaseTable_Error>`
  * :ref:`DataObjectWriter.SubmitMode <enum_DataObjectWriter_SubmitMode>`



Properties
**********


.. _property_DatabaseTable_database:

.. _signal_DatabaseTable_databaseChanged:

.. index::
   single: database

database
++++++++

This property holds a :ref:`Database <object_Database>` object to which database the table belongs. If left blank the parent is used.

:**› Type**: :ref:`Database <object_Database>`
:**› Signal**: databaseChanged()
:**› Attributes**: Writable, Optional


.. _property_DatabaseTable_defaultFieldOptions:

.. _signal_DatabaseTable_defaultFieldOptionsChanged:

.. index::
   single: defaultFieldOptions

defaultFieldOptions
+++++++++++++++++++

This property holds default options to apply to all :ref:`DataObjectWriter.objects <property_DataObjectWriter_objects>` which do not have a property of type :ref:`DatabaseFieldOptions <object_DatabaseFieldOptions>`. This can be used to e.g. allow ``NULL`` values for every column without having to set :ref:`DatabaseFieldOptions.notNull <property_DatabaseFieldOptions_notNull>` to ``false`` for every object.

This property was introduced in InCore 1.1.

:**› Type**: :ref:`DatabaseFieldOptions <object_DatabaseFieldOptions>`
:**› Signal**: defaultFieldOptionsChanged()
:**› Attributes**: Writable, Optional


.. _property_DatabaseTable_error:

.. _signal_DatabaseTable_errorChanged:

.. index::
   single: error

error
+++++

This property holds the most recently occurred error or :ref:`DatabaseTable.NoError <enumitem_DatabaseTable_NoError>` if no error occurred. If the same error occurs multiple times this property does not change. Use the :ref:`errorOccurred() <signal_DatabaseTable_errorOccurred>` signal to detect multiple occurrences of the same error.

:**› Type**: :ref:`Error <enum_DatabaseTable_Error>`
:**› Signal**: errorChanged()
:**› Attributes**: Readonly


.. _property_DatabaseTable_errorString:

.. _signal_DatabaseTable_errorStringChanged:

.. index::
   single: errorString

errorString
+++++++++++

This property holds the current human readable error string corresponding to the current value in the :ref:`error <property_DatabaseTable_error>` property. It may include additional information such as failure reasons or locations.

:**› Type**: String
:**› Signal**: errorStringChanged()
:**› Attributes**: Readonly


.. _property_DatabaseTable_operationsEnabled:

.. _signal_DatabaseTable_operationsEnabledChanged:

.. index::
   single: operationsEnabled

operationsEnabled
+++++++++++++++++

This property holds whether the database table is ready for operations. The :ref:`DataObjectWriter.objects <property_DataObjectWriter_objects>` property must be populated completely before operations may be enabled. Otherwise columns could be missing when creating a database table the first time. For statically initialized objects this property can be left at its default value. However special care needs to be taken in cases where the object list is populated dynamically, e.g. when using property modifiers such as :ref:`Repeater <object_Repeater>` or populating the list in a function manually. Whenever this applies operations must be enabled only after the list has been initialized. The list must not be changed after this property is changed from ``false`` to ``true``.

:**› Type**: Boolean
:**› Default**: ``true``
:**› Signal**: operationsEnabledChanged()
:**› Attributes**: Writable, Optional


.. _property_DatabaseTable_pseudoRingBufferOrderBy:

.. _signal_DatabaseTable_pseudoRingBufferOrderByChanged:

.. index::
   single: pseudoRingBufferOrderBy

pseudoRingBufferOrderBy
+++++++++++++++++++++++

This property holds an optional sort criterion specifying which data should be removed first whenever the dataset count exceeds :ref:`pseudoRingBufferSize <property_DatabaseTable_pseudoRingBufferSize>`. This string must be set to an id or :ref:`Object.objectId <property_Object_objectId>` of an object in :ref:`DataObjectWriter.objects <property_DataObjectWriter_objects>` to work. For example if there is a :ref:`DateTime <object_DateTime>` object with id ``date`` and the oldest dateset is to be removed first, :ref:`pseudoRingBufferOrderBy <property_DatabaseTable_pseudoRingBufferOrderBy>` has to be set to ``date`` (ascending order - oldest will be found and removed first). To use a descending order prepend :ref:`pseudoRingBufferOrderBy <property_DatabaseTable_pseudoRingBufferOrderBy>` with '-'.

.. note:: The column ``id`` will be inserted as an auto-incrementing primary key in every :ref:`DatabaseTable <object_DatabaseTable>` and can be used to determine the least recently inserted datasets.

:**› Type**: String
:**› Default**: ``id``
:**› Signal**: pseudoRingBufferOrderByChanged()
:**› Attributes**: Writable


.. _property_DatabaseTable_pseudoRingBufferSize:

.. _signal_DatabaseTable_pseudoRingBufferSizeChanged:

.. index::
   single: pseudoRingBufferSize

pseudoRingBufferSize
++++++++++++++++++++

This property holds an optional dataset limit. When set to a value greater 0 the number of datasets in this table will be limited automatically. If a new dataset is inserted and :ref:`DataObjectWriter.datasetCount <property_DataObjectWriter_datasetCount>` exceeds the configured value the oldest or least recent dataset will be removed. Setting this property makes the table behave like a ring buffer. You can specify a different sort criterion through the :ref:`pseudoRingBufferOrderBy <property_DatabaseTable_pseudoRingBufferOrderBy>` property.

:**› Type**: SignedInteger
:**› Default**: ``0``
:**› Signal**: pseudoRingBufferSizeChanged()
:**› Attributes**: Writable


.. _property_DatabaseTable_queries:

.. _signal_DatabaseTable_queriesChanged:

.. index::
   single: queries

queries
+++++++

This property holds a list of :ref:`DatabaseQuery <object_DatabaseQuery>` objects which should be performed on this table.

:**› Type**: :ref:`List <object_List>`\<:ref:`DatabaseQuery <object_DatabaseQuery>`>
:**› Signal**: queriesChanged()
:**› Attributes**: Readonly


.. _property_DatabaseTable_ready:

.. _signal_DatabaseTable_readyChanged:

.. index::
   single: ready

ready
+++++

This property holds whether the database table has been opened and initialized successfully and is ready to execute queries.

This property was introduced in InCore 2.5.

:**› Type**: Boolean
:**› Default**: ``false``
:**› Signal**: readyChanged()
:**› Attributes**: Readonly


.. _property_DatabaseTable_structure:

.. _signal_DatabaseTable_structureChanged:

.. index::
   single: structure

structure
+++++++++

This property holds an alternate list of :ref:`DataObject <object_DataObject>` objects describing the desired database table structure upon initialization and creation. Usually this list can be left blank so :ref:`DataObjectWriter.objects <property_DataObjectWriter_objects>` are used. In some cases however only a subset of :ref:`DataObject <object_DataObject>` objects might be configured to be enabled after the table has been created. In such cases all possible objects can be assigned to :ref:`structure <property_DatabaseTable_structure>` so that the table does not have to be dropped and recreated on every configuration change.

This property was introduced in InCore 1.1.

:**› Type**: :ref:`List <object_List>`\<:ref:`DataObject <object_DataObject>`>
:**› Signal**: structureChanged()
:**› Attributes**: Readonly, Optional

Methods
*******


.. _method_DatabaseTable_drop:

.. index::
   single: drop

drop()
++++++

This method removes the table from the database. If you want to remove the datasets only and keep the table structure, call :ref:`DataObjectWriter.truncate() <method_DataObjectWriter_truncate>` instead.

:**› Returns**: Boolean


Signals
*******


.. _signal_DatabaseTable_errorOccurred:

.. index::
   single: errorOccurred

errorOccurred()
+++++++++++++++

This signal is emitted whenever an error has occurred, regardless of whether the :ref:`error <property_DatabaseTable_error>` property has changed or not. In contrast to the change notification signal of the :ref:`error <property_DatabaseTable_error>` property this signal is also emitted several times if a certain error occurs several times in succession.



.. _signal_DatabaseTable_queriesDataChanged:

.. index::
   single: queriesDataChanged

queriesDataChanged(SignedInteger index)
+++++++++++++++++++++++++++++++++++++++

This signal is emitted whenever the :ref:`List.dataChanged() <signal_List_dataChanged>` signal is emitted, i.e. the item at ``index`` in the :ref:`queries <property_DatabaseTable_queries>` list itself emitted the dataChanged() signal.



.. _signal_DatabaseTable_structureDataChanged:

.. index::
   single: structureDataChanged

structureDataChanged(SignedInteger index)
+++++++++++++++++++++++++++++++++++++++++

This signal is emitted whenever the :ref:`List.dataChanged() <signal_List_dataChanged>` signal is emitted, i.e. the item at ``index`` in the :ref:`structure <property_DatabaseTable_structure>` list itself emitted the dataChanged() signal.


Enumerations
************


.. _enum_DatabaseTable_Error:

.. index::
   single: Error

Error
+++++

This enumeration describes all errors which can occur in DatabaseTable objects. The most recently occurred error is stored in the :ref:`error <property_DatabaseTable_error>` property.

.. index::
   single: DatabaseTable.NoError
.. index::
   single: DatabaseTable.InvalidDatabase
.. index::
   single: DatabaseTable.InvalidTableIdError
.. index::
   single: DatabaseTable.DatabaseContextError
.. index::
   single: DatabaseTable.MissingObjectsIds
.. index::
   single: DatabaseTable.MissingDefaultData
.. index::
   single: DatabaseTable.ObjectsChangedWhileOpen
.. index::
   single: DatabaseTable.StructureChangedWhileOpen
.. index::
   single: DatabaseTable.OperationsNotEnabled
.. index::
   single: DatabaseTable.SubmitError
.. list-table::
  :widths: auto
  :header-rows: 1

  * - Name
    - Value
    - Description

      .. _enumitem_DatabaseTable_NoError:
  * - ``DatabaseTable.NoError``
    - ``0``
    - No error occurred or was detected.

      .. _enumitem_DatabaseTable_InvalidDatabase:
  * - ``DatabaseTable.InvalidDatabase``
    - ``1``
    - Empty or invalid database property or parent.

      .. _enumitem_DatabaseTable_InvalidTableIdError:
  * - ``DatabaseTable.InvalidTableIdError``
    - ``2``
    - Empty or invalid object id.

      .. _enumitem_DatabaseTable_DatabaseContextError:
  * - ``DatabaseTable.DatabaseContextError``
    - ``3``
    - Could not switch database context.

      .. _enumitem_DatabaseTable_MissingObjectsIds:
  * - ``DatabaseTable.MissingObjectsIds``
    - ``4``
    - Some data objects do not have an object ID.

      .. _enumitem_DatabaseTable_MissingDefaultData:
  * - ``DatabaseTable.MissingDefaultData``
    - ``5``
    - Some data objects do not have valid default data.

      .. _enumitem_DatabaseTable_ObjectsChangedWhileOpen:
  * - ``DatabaseTable.ObjectsChangedWhileOpen``
    - ``6``
    - Data objects have changed after table has been created and opened.

      .. _enumitem_DatabaseTable_StructureChangedWhileOpen:
  * - ``DatabaseTable.StructureChangedWhileOpen``
    - ``7``
    - Structure has changed after table has been created and opened.

      .. _enumitem_DatabaseTable_OperationsNotEnabled:
  * - ``DatabaseTable.OperationsNotEnabled``
    - ``8``
    - Operation requested before operationsEnabled is set to true.

      .. _enumitem_DatabaseTable_SubmitError:
  * - ``DatabaseTable.SubmitError``
    - ``9``
    - Failed to submit a new data row, probably due to a broken database connection or mismatching table structure.


.. _example_DatabaseTable:


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
    
                submitInterval: 1000
                submitMode: DatabaseTable.SubmitPeriodically
                // save only 1000 datasets in the database
                pseudoRingBufferSize: 1000
                // order by date - delete oldest dataset first
                pseudoRingBufferOrderBy: "date"
    
                // objects to store
                DateTime { id: date }
                Measurement { id: sensor1; data: 1 }
                Measurement { id: sensor2; data: 2 }
                Measurement { id: sensor3; data: 123 }
    
                queries: [
                    DatabaseQuery {
                        // objects to query
                        objects: [sensor1, sensor2, sensor3]
                        orderBy: [sensor3]
    
                        // only get 15 values from start on
                        limitPos: 0
                        limitLength: 15
                        onResultsChanged: {
                            // use a local variable
                            // this will only trigger execute once and store the result in r
                            var r = results
                            // read the data
                            for(var i = 0; i < r.length; i++)
                                console.log("S1, S2, S3:", r[i].sensor1, r[i].sensor2, r[i].sensor3)
                        }
    
                        Polling on results { interval: 10000 }
                    },
    
                    DatabaseQuery {
                        // query only sensor3 data
                        objects: [sensor3]
                        // sort by sensor3 descending, then sensor2 ascending
                        orderByNames: ["-sensor3", "sensor2"]
    
                        // only get 10 values descending
                        limitPos: 0
                        limitLength: 10
                    }
                ]
            }
        }
    }
    