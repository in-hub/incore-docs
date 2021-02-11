
.. _object_DatabaseEventTable:


:index:`DatabaseEventTable`
---------------------------

Description
***********

The DatabaseEventTable object is a special :ref:`DatabaseTable <object_DatabaseTable>` which can stores :ref:`Event <object_Event>` objects. The additional properties correspond to each property of :ref:`Event <object_Event>`.

:**› Inherits**: :ref:`DatabaseTable <object_DatabaseTable>`

Overview
********

Properties
++++++++++

.. hlist::
  :columns: 3

  * :ref:`category <property_DatabaseEventTable_category>`
  * :ref:`data <property_DatabaseEventTable_data>`
  * :ref:`description <property_DatabaseEventTable_description>`
  * :ref:`errorCode <property_DatabaseEventTable_errorCode>`
  * :ref:`eventId <property_DatabaseEventTable_eventId>`
  * :ref:`severity <property_DatabaseEventTable_severity>`
  * :ref:`timestamp <property_DatabaseEventTable_timestamp>`
  * :ref:`uuid <property_DatabaseEventTable_uuid>`
  * :ref:`DatabaseTable.database <property_DatabaseTable_database>`
  * :ref:`DatabaseTable.defaultFieldOptions <property_DatabaseTable_defaultFieldOptions>`
  * :ref:`DatabaseTable.error <property_DatabaseTable_error>`
  * :ref:`DatabaseTable.errorString <property_DatabaseTable_errorString>`
  * :ref:`DatabaseTable.operationsEnabled <property_DatabaseTable_operationsEnabled>`
  * :ref:`DatabaseTable.pseudoRingBufferOrderBy <property_DatabaseTable_pseudoRingBufferOrderBy>`
  * :ref:`DatabaseTable.pseudoRingBufferSize <property_DatabaseTable_pseudoRingBufferSize>`
  * :ref:`DatabaseTable.queries <property_DatabaseTable_queries>`
  * :ref:`DatabaseTable.structure <property_DatabaseTable_structure>`
  * :ref:`DataObjectWriter.datasetCount <property_DataObjectWriter_datasetCount>`
  * :ref:`DataObjectWriter.objects <property_DataObjectWriter_objects>`
  * :ref:`DataObjectWriter.running <property_DataObjectWriter_running>`
  * :ref:`DataObjectWriter.submitInterval <property_DataObjectWriter_submitInterval>`
  * :ref:`DataObjectWriter.submitMode <property_DataObjectWriter_submitMode>`
  * :ref:`Object.objectId <property_Object_objectId>`
  * :ref:`Object.parent <property_Object_parent>`

Methods
+++++++

.. hlist::
  :columns: 2

  * :ref:`DatabaseTable.drop() <method_DatabaseTable_drop>`
  * :ref:`DataObjectWriter.close() <method_DataObjectWriter_close>`
  * :ref:`DataObjectWriter.open() <method_DataObjectWriter_open>`
  * :ref:`DataObjectWriter.submit() <method_DataObjectWriter_submit>`
  * :ref:`DataObjectWriter.sync() <method_DataObjectWriter_sync>`
  * :ref:`DataObjectWriter.truncate() <method_DataObjectWriter_truncate>`
  * :ref:`Object.fromJson() <method_Object_fromJson>`
  * :ref:`Object.toJson() <method_Object_toJson>`

Signals
+++++++

.. hlist::
  :columns: 1

  * :ref:`DatabaseTable.errorOccurred() <signal_DatabaseTable_errorOccurred>`
  * :ref:`DatabaseTable.queriesDataChanged() <signal_DatabaseTable_queriesDataChanged>`
  * :ref:`DatabaseTable.structureDataChanged() <signal_DatabaseTable_structureDataChanged>`
  * :ref:`DataObjectWriter.objectsDataChanged() <signal_DataObjectWriter_objectsDataChanged>`
  * :ref:`DataObjectWriter.submitted() <signal_DataObjectWriter_submitted>`
  * :ref:`DataObjectWriter.truncated() <signal_DataObjectWriter_truncated>`
  * :ref:`Object.completed() <signal_Object_completed>`

Enumerations
++++++++++++

.. hlist::
  :columns: 1

  * :ref:`DatabaseTable.Error <enum_DatabaseTable_Error>`
  * :ref:`DataObjectWriter.SubmitMode <enum_DataObjectWriter_SubmitMode>`



Properties
**********


.. _property_DatabaseEventTable_category:

.. _signal_DatabaseEventTable_categoryChanged:

.. index::
   single: category

category
++++++++

This property holds a :ref:`DataObject <object_DataObject>` for the category property of :ref:`Event <object_Event>`.

:**› Type**: :ref:`DataObject <object_DataObject>`
:**› Signal**: categoryChanged()
:**› Attributes**: Readonly


.. _property_DatabaseEventTable_data:

.. _signal_DatabaseEventTable_dataChanged:

.. index::
   single: data

data
++++

This property holds a :ref:`DataObject <object_DataObject>` for the data property of :ref:`Event <object_Event>`.

:**› Type**: :ref:`DataObject <object_DataObject>`
:**› Signal**: dataChanged()
:**› Attributes**: Readonly


.. _property_DatabaseEventTable_description:

.. _signal_DatabaseEventTable_descriptionChanged:

.. index::
   single: description

description
+++++++++++

This property holds a :ref:`DataObject <object_DataObject>` for the description property of :ref:`Event <object_Event>`.

:**› Type**: :ref:`DataObject <object_DataObject>`
:**› Signal**: descriptionChanged()
:**› Attributes**: Readonly


.. _property_DatabaseEventTable_errorCode:

.. _signal_DatabaseEventTable_errorCodeChanged:

.. index::
   single: errorCode

errorCode
+++++++++

This property holds a :ref:`DataObject <object_DataObject>` for the errorCode property of :ref:`Event <object_Event>`.

:**› Type**: :ref:`DataObject <object_DataObject>`
:**› Signal**: errorCodeChanged()
:**› Attributes**: Readonly


.. _property_DatabaseEventTable_eventId:

.. _signal_DatabaseEventTable_eventIdChanged:

.. index::
   single: eventId

eventId
+++++++

This property holds a :ref:`DataObject <object_DataObject>` for the id property of :ref:`Event <object_Event>`.

:**› Type**: :ref:`DataObject <object_DataObject>`
:**› Signal**: eventIdChanged()
:**› Attributes**: Readonly


.. _property_DatabaseEventTable_severity:

.. _signal_DatabaseEventTable_severityChanged:

.. index::
   single: severity

severity
++++++++

This property holds a :ref:`DataObject <object_DataObject>` for the severity property of :ref:`Event <object_Event>`.

:**› Type**: :ref:`DataObject <object_DataObject>`
:**› Signal**: severityChanged()
:**› Attributes**: Readonly


.. _property_DatabaseEventTable_timestamp:

.. _signal_DatabaseEventTable_timestampChanged:

.. index::
   single: timestamp

timestamp
+++++++++

This property holds a :ref:`DataObject <object_DataObject>` for the timestamp property of :ref:`Event <object_Event>`.

:**› Type**: :ref:`DataObject <object_DataObject>`
:**› Signal**: timestampChanged()
:**› Attributes**: Readonly


.. _property_DatabaseEventTable_uuid:

.. _signal_DatabaseEventTable_uuidChanged:

.. index::
   single: uuid

uuid
++++

This property holds a :ref:`DataObject <object_DataObject>` for the uuid property of :ref:`Event <object_Event>`.

:**› Type**: :ref:`DataObject <object_DataObject>`
:**› Signal**: uuidChanged()
:**› Attributes**: Readonly


.. _example_DatabaseEventTable:


Example
*******

.. code-block:: qml

    import InCore.Foundation 2.0
    import InCore.Database 2.0
    
    Application {
        name: "EventDemo"
        description: "Event Demo"
    
        property alias evntTbl: eventWriter.eventTable
    
        DatabaseQuery {
            id: eventQuery
            table: evntTbl
            objects: [ evntTbl.data, evntTbl.timestamp, evntTbl.eventId ]
            filters: [
                DatabaseQueryFilter {
                    DatabaseQueryWhere { key: evntTbl.severity; operation: DatabaseQueryWhere.GreaterOrEquals; value: Event.Warning }
                }
            ]
            onResultsChanged: {
                console.log("data, timestamp, id")
                for(var i = 0; i < results.length; i++) {
                    console.log(results[i].data, results[i].timestamp, results[i].eventId)
                }
            }
            onCompleted: eventQuery.execute()
        }
    
        EventLog {
            outputs: [
                DatabaseEventWriter { id: eventWriter }
            ]
    
            // categories allow filtering events for outputs based on OR (instead of severity which filters by number)
            EventCategory { id: ioErrorCategory }
    
            EventGroup {
                severity: Event.Information // Info Warning Debug Fatal
                Event {
                    id: generalErrorEvent
                    severity: Event.Error
                    uuid: "7f160be3-4ba9-42f0-a524-5359057c034b"
                    description: "General error"
                }
    
                Event {
                    id: fileOpenErrorEvent
                    category: ioErrorCategory
                    errorCode: 42
                    description: "Could not open file %1"
                }
    
                Event {
                    id: deviceStartedEvent
                    description: "Database error: %1"
                }
            }
    
            onCompleted: deviceStartedEvent.trigger()
        }
    }
    