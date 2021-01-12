
.. _object_DatabaseEventWriter:


:index:`DatabaseEventWriter`
----------------------------

Description
***********

The DatabaseEventWriter object is an :ref:`EventOutput <object_EventOutput>` which stores :ref:`Event <object_Event>` objects in a database whenever triggered. All inserted Events can later be queried using a :ref:`DatabaseQuery <object_DatabaseQuery>` object and assigning the :ref:`eventTable <property_DatabaseEventWriter_eventTable>` property to :ref:`DatabaseQuery.table <property_DatabaseQuery_table>`.

:**› Inherits**: :ref:`EventOutput <object_EventOutput>`

Overview
********

Properties
++++++++++

.. hlist::
  :columns: 2

  * :ref:`database <property_DatabaseEventWriter_database>`
  * :ref:`error <property_DatabaseEventWriter_error>`
  * :ref:`errorString <property_DatabaseEventWriter_errorString>`
  * :ref:`eventTable <property_DatabaseEventWriter_eventTable>`
  * :ref:`EventOutput.filterCategories <property_EventOutput_filterCategories>`
  * :ref:`EventOutput.filterExactSeverity <property_EventOutput_filterExactSeverity>`
  * :ref:`EventOutput.filterMinimumSeverity <property_EventOutput_filterMinimumSeverity>`
  * :ref:`Object.objectId <property_Object_objectId>`
  * :ref:`Object.parent <property_Object_parent>`

Methods
+++++++

.. hlist::
  :columns: 1

  * :ref:`Object.fromJson() <method_Object_fromJson>`
  * :ref:`Object.toJson() <method_Object_toJson>`

Signals
+++++++

.. hlist::
  :columns: 1

  * :ref:`errorOccurred() <signal_DatabaseEventWriter_errorOccurred>`
  * :ref:`EventOutput.filterCategoriesDataChanged() <signal_EventOutput_filterCategoriesDataChanged>`
  * :ref:`Object.completed() <signal_Object_completed>`

Enumerations
++++++++++++

.. hlist::
  :columns: 1

  * :ref:`Error <enum_DatabaseEventWriter_Error>`



Properties
**********


.. _property_DatabaseEventWriter_database:

.. _signal_DatabaseEventWriter_databaseChanged:

.. index::
   single: database

database
++++++++

This property holds the :ref:`Database <object_Database>` in which the :ref:`Event <object_Event>` objects are stored. If left blank a :ref:`LocalDatabase <object_LocalDatabase>` is created.

:**› Type**: :ref:`Database <object_Database>`
:**› Signal**: databaseChanged()
:**› Attributes**: Writable, Optional


.. _property_DatabaseEventWriter_error:

.. _signal_DatabaseEventWriter_errorChanged:

.. index::
   single: error

error
+++++

This property holds the most recently occurred error or :ref:`DatabaseEventWriter.NoError <enumitem_DatabaseEventWriter_NoError>` if no error occurred. If the same error occurs multiple times this property does not change. Use the :ref:`errorOccurred() <signal_DatabaseEventWriter_errorOccurred>` signal to detect multiple occurrences of the same error.

:**› Type**: :ref:`Error <enum_DatabaseEventWriter_Error>`
:**› Signal**: errorChanged()
:**› Attributes**: Readonly


.. _property_DatabaseEventWriter_errorString:

.. _signal_DatabaseEventWriter_errorStringChanged:

.. index::
   single: errorString

errorString
+++++++++++

This property holds the current human readable error string corresponding to the current value in the :ref:`error <property_DatabaseEventWriter_error>` property. It may include additional information such as failure reasons or locations.

:**› Type**: String
:**› Signal**: errorStringChanged()
:**› Attributes**: Readonly


.. _property_DatabaseEventWriter_eventTable:

.. _signal_DatabaseEventWriter_eventTableChanged:

.. index::
   single: eventTable

eventTable
++++++++++

This property holds the :ref:`DatabaseEventTable <object_DatabaseEventTable>` object which handles the mapping from :ref:`Event <object_Event>` properties to database table columns. During initialization it is attached to the database held by the :ref:`database <property_DatabaseEventWriter_database>` property.

:**› Type**: :ref:`DatabaseEventTable <object_DatabaseEventTable>`
:**› Signal**: eventTableChanged()
:**› Attributes**: Readonly

Signals
*******


.. _signal_DatabaseEventWriter_errorOccurred:

.. index::
   single: errorOccurred

errorOccurred()
+++++++++++++++

This signal is emitted whenever an error has occurred, regardless of whether the :ref:`error <property_DatabaseEventWriter_error>` property has changed or not. In contrast to the change notification signal of the :ref:`error <property_DatabaseEventWriter_error>` property this signal is also emitted several times if a certain error occurs several times in succession.


Enumerations
************


.. _enum_DatabaseEventWriter_Error:

.. index::
   single: Error

Error
+++++

This enumeration describes all errors which can occur in DatabaseEventWriter objects. The most recently occurred error is stored in the :ref:`error <property_DatabaseEventWriter_error>` property.

.. index::
   single: DatabaseEventWriter.NoError
.. index::
   single: DatabaseEventWriter.InvalidDatabase
.. index::
   single: DatabaseEventWriter.InvalidIdError
.. list-table::
  :widths: auto
  :header-rows: 1

  * - Name
    - Value
    - Description

      .. _enumitem_DatabaseEventWriter_NoError:
  * - ``DatabaseEventWriter.NoError``
    - ``0``
    - No error occurred or was detected.

      .. _enumitem_DatabaseEventWriter_InvalidDatabase:
  * - ``DatabaseEventWriter.InvalidDatabase``
    - ``1``
    - Invalid or no database set.

      .. _enumitem_DatabaseEventWriter_InvalidIdError:
  * - ``DatabaseEventWriter.InvalidIdError``
    - ``2``
    - Empty or invalid object ID (only alphanumeric characters allowed).


.. _example_DatabaseEventWriter:


Example
*******

.. code-block:: qml

    
    import InCore.Foundation 2.0
    import InCore.Database 2.0
    
    Application {
    
        EventLog {
            outputs: [
                DatabaseEventWriter {
                    id: eventWriter
    
                    //property database left blank to create a LocalDatabase
                } ]
    
            EventCategory { id: measurementValueCategory }
            EventGroup {
                Event {
                    id: temperatureEvent
                    description: "temperature above 70°C"
                }
                Event {
                    id: deviceStartedEvent
                    description: "device started"
                }
                Event {
                    id: measurementValueEvent
                    description: "measurement above threshold"
                    category: measurementValueCategory
                    severity: Event.Error
                }
            }
        }
    
        onCompleted: deviceStartedEvent.trigger()
    
        //trigger events here
    
    }
    