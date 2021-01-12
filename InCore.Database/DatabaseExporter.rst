
.. _object_DatabaseExporter:


:index:`DatabaseExporter`
-------------------------

Description
***********

The DatabaseExporter object is used to export data from a database to a :ref:`DataObjectWriter <object_DataObjectWriter>` for example a CSV-exporter. The :ref:`query <property_DatabaseExporter_query>` property is used to select, limit and format the output.

:**› Inherits**: :ref:`Object <object_Object>`

Overview
********

Properties
++++++++++

.. hlist::
  :columns: 2

  * :ref:`chunkSize <property_DatabaseExporter_chunkSize>`
  * :ref:`dataFormat <property_DatabaseExporter_dataFormat>`
  * :ref:`error <property_DatabaseExporter_error>`
  * :ref:`errorString <property_DatabaseExporter_errorString>`
  * :ref:`output <property_DatabaseExporter_output>`
  * :ref:`progress <property_DatabaseExporter_progress>`
  * :ref:`query <property_DatabaseExporter_query>`
  * :ref:`rowFilter <property_DatabaseExporter_rowFilter>`
  * :ref:`running <property_DatabaseExporter_running>`
  * :ref:`table <property_DatabaseExporter_table>`
  * :ref:`Object.objectId <property_Object_objectId>`
  * :ref:`Object.parent <property_Object_parent>`

Methods
+++++++

.. hlist::
  :columns: 1

  * :ref:`execute() <method_DatabaseExporter_execute>`
  * :ref:`Object.fromJson() <method_Object_fromJson>`
  * :ref:`Object.toJson() <method_Object_toJson>`

Signals
+++++++

.. hlist::
  :columns: 1

  * :ref:`errorOccurred() <signal_DatabaseExporter_errorOccurred>`
  * :ref:`finished() <signal_DatabaseExporter_finished>`
  * :ref:`Object.completed() <signal_Object_completed>`

Enumerations
++++++++++++

.. hlist::
  :columns: 1

  * :ref:`DataFormat <enum_DatabaseExporter_DataFormat>`
  * :ref:`Error <enum_DatabaseExporter_Error>`



Properties
**********


.. _property_DatabaseExporter_chunkSize:

.. _signal_DatabaseExporter_chunkSizeChanged:

.. index::
   single: chunkSize

chunkSize
+++++++++

This property holds the number of datasets to export in each internal iteration. Reducing this value improves the responsiveness but decreases the performance. When a custom :ref:`query <property_DatabaseExporter_query>` is used, this value is not used and all datasets are exported at once.

This property was introduced in InCore 2.1.

:**› Type**: SignedInteger
:**› Default**: ``1000``
:**› Signal**: chunkSizeChanged()
:**› Attributes**: Writable


.. _property_DatabaseExporter_dataFormat:

.. _signal_DatabaseExporter_dataFormatChanged:

.. index::
   single: dataFormat

dataFormat
++++++++++

This property holds whether the data should be formatted according to the object (for example a :ref:`Measurement <object_Measurement>` would be printed with unit) or be left unformatted (the value is printed as string).

:**› Type**: :ref:`DataFormat <enum_DatabaseExporter_DataFormat>`
:**› Default**: :ref:`DatabaseExporter.RawValues <enumitem_DatabaseExporter_RawValues>`
:**› Signal**: dataFormatChanged()
:**› Attributes**: Writable


.. _property_DatabaseExporter_error:

.. _signal_DatabaseExporter_errorChanged:

.. index::
   single: error

error
+++++

This property holds the most recently occurred error or :ref:`DatabaseExporter.NoError <enumitem_DatabaseExporter_NoError>` if no error occurred. If the same error occurs multiple times this property does not change. Use the :ref:`errorOccurred() <signal_DatabaseExporter_errorOccurred>` signal to detect multiple occurrences of the same error.

:**› Type**: :ref:`Error <enum_DatabaseExporter_Error>`
:**› Signal**: errorChanged()
:**› Attributes**: Readonly


.. _property_DatabaseExporter_errorString:

.. _signal_DatabaseExporter_errorStringChanged:

.. index::
   single: errorString

errorString
+++++++++++

This property holds the current human readable error string corresponding to the current value in the :ref:`error <property_DatabaseExporter_error>` property. It may include additional information such as failure reasons or locations.

:**› Type**: String
:**› Signal**: errorStringChanged()
:**› Attributes**: Readonly


.. _property_DatabaseExporter_output:

.. _signal_DatabaseExporter_outputChanged:

.. index::
   single: output

output
++++++

This property holds the :ref:`DataObjectWriter <object_DataObjectWriter>` to output the data. The format and location of the data is defined by the output.

:**› Type**: :ref:`DataObjectWriter <object_DataObjectWriter>`
:**› Signal**: outputChanged()
:**› Attributes**: Writable


.. _property_DatabaseExporter_progress:

.. _signal_DatabaseExporter_progressChanged:

.. index::
   single: progress

progress
++++++++

This property holds the overall progress of the current export operatoin

This property was introduced in InCore 2.1.

:**› Type**: SignedInteger
:**› Default**: ``0``
:**› Signal**: progressChanged()
:**› Attributes**: Readonly


.. _property_DatabaseExporter_query:

.. _signal_DatabaseExporter_queryChanged:

.. index::
   single: query

query
+++++

This property holds the query which defines which data should be exported. If left blank the whole :ref:`table <property_DatabaseExporter_table>` is exported.

:**› Type**: :ref:`DatabaseQuery <object_DatabaseQuery>`
:**› Signal**: queryChanged()
:**› Attributes**: Writable, Optional


.. _property_DatabaseExporter_rowFilter:

.. _signal_DatabaseExporter_rowFilterChanged:

.. index::
   single: rowFilter

rowFilter
+++++++++

This property holds an expression which is used to filter rows when :ref:`query <property_DatabaseExporter_query>` can't be used. The respective data row is provided in the ``item`` variable. Therefore an expression looks like ``item.myField > 123`` or ``item.userId !== undefined``.

This property was introduced in InCore 2.1.

:**› Type**: <QML expression>
:**› Signal**: rowFilterChanged()
:**› Attributes**: Writable


.. _property_DatabaseExporter_running:

.. _signal_DatabaseExporter_runningChanged:

.. index::
   single: running

running
+++++++

This property holds whether an export operation is in progress.

This property was introduced in InCore 2.1.

:**› Type**: Boolean
:**› Default**: ``false``
:**› Signal**: runningChanged()
:**› Attributes**: Writable


.. _property_DatabaseExporter_table:

.. _signal_DatabaseExporter_tableChanged:

.. index::
   single: table

table
+++++

This property holds the table which data should be exported. If left blank the table of the :ref:`query <property_DatabaseExporter_query>` property is used. If :ref:`query <property_DatabaseExporter_query>` is left blank or you want to export the whole table you have to set this property properly.

:**› Type**: :ref:`DatabaseTable <object_DatabaseTable>`
:**› Signal**: tableChanged()
:**› Attributes**: Writable

Methods
*******


.. _method_DatabaseExporter_execute:

.. index::
   single: execute

execute()
+++++++++

This method checks for errors and starts an export operation. The :ref:`finished() <signal_DatabaseExporter_finished>` signal will be emitted after execution has finished.

:**› Returns**: Boolean


Signals
*******


.. _signal_DatabaseExporter_errorOccurred:

.. index::
   single: errorOccurred

errorOccurred()
+++++++++++++++

This signal is emitted whenever an error has occurred, regardless of whether the :ref:`error <property_DatabaseExporter_error>` property has changed or not. In contrast to the change notification signal of the :ref:`error <property_DatabaseExporter_error>` property this signal is also emitted several times if a certain error occurs several times in succession.



.. _signal_DatabaseExporter_finished:

.. index::
   single: finished

finished()
++++++++++

This signal is emitted after the export has been finished. Check the :ref:`error <property_DatabaseExporter_error>` property or connect to the :ref:`errorOccurred() <signal_DatabaseExporter_errorOccurred>` signal to detect errors occurred during the export.

This signal was introduced in InCore 2.1.


Enumerations
************


.. _enum_DatabaseExporter_DataFormat:

.. index::
   single: DataFormat

DataFormat
++++++++++

This enumeration describes the ways the data can be formatted.

.. index::
   single: DatabaseExporter.RawValues
.. index::
   single: DatabaseExporter.FormattedData
.. list-table::
  :widths: auto
  :header-rows: 1

  * - Name
    - Value
    - Description

      .. _enumitem_DatabaseExporter_RawValues:
  * - ``DatabaseExporter.RawValues``
    - ``0``
    - The raw value is converted to a string.

      .. _enumitem_DatabaseExporter_FormattedData:
  * - ``DatabaseExporter.FormattedData``
    - ``1``
    - The value is formatted by the corresponding object according to the configured settings (for example :ref:`Measurement <object_Measurement>` may add the :ref:`unit <property_Measurement_unit>`, format the floating point value with the configured number of :ref:`decimals <property_Measurement_decimals>` and apply the :ref:`SI prefix <property_Measurement_siPrefix>`, e.g. `123456` → `"1234.5 kPa"`).


.. _enum_DatabaseExporter_Error:

.. index::
   single: Error

Error
+++++

This enumeration describes all errors which can occur in DatabaseExporter objects. The most recently occurred error is stored in the :ref:`error <property_DatabaseExporter_error>` property.

.. index::
   single: DatabaseExporter.NoError
.. index::
   single: DatabaseExporter.InvalidOutputError
.. index::
   single: DatabaseExporter.InvalidTableError
.. index::
   single: DatabaseExporter.DataError
.. index::
   single: DatabaseExporter.OutputOpenError
.. index::
   single: DatabaseExporter.WriteError
.. list-table::
  :widths: auto
  :header-rows: 1

  * - Name
    - Value
    - Description

      .. _enumitem_DatabaseExporter_NoError:
  * - ``DatabaseExporter.NoError``
    - ``0``
    - No error occurred or was detected.

      .. _enumitem_DatabaseExporter_InvalidOutputError:
  * - ``DatabaseExporter.InvalidOutputError``
    - ``1``
    - Invalid or no output set.

      .. _enumitem_DatabaseExporter_InvalidTableError:
  * - ``DatabaseExporter.InvalidTableError``
    - ``2``
    - No table set in query or exporter or table not open.

      .. _enumitem_DatabaseExporter_DataError:
  * - ``DatabaseExporter.DataError``
    - ``3``
    - Internal error while fetching data.

      .. _enumitem_DatabaseExporter_OutputOpenError:
  * - ``DatabaseExporter.OutputOpenError``
    - ``4``
    - Opening the output caused an error.

      .. _enumitem_DatabaseExporter_WriteError:
  * - ``DatabaseExporter.WriteError``
    - ``5``
    - Internal error while exporting data to file.


.. _example_DatabaseExporter:


Example
*******

.. code-block:: qml

    import InCore.Foundation 2.0
    import InCore.Database 2.0
    
    Application {
    
        LocalDatabase {
            id: exampleDatabase
            onErrorChanged: console.log("LocalDatabase error:", errorString)
    
            DatabaseTable {
                id: exampleTable
                onErrorChanged: console.log("DatabaseTable error:", errorString)
    
                DateTime { id: date }
                Measurement { id: sensor1; unit: "°C"; decimals: 1 }
                Measurement { id: sensor2; unit: "Pa"; decimals: 2; siPrefix: Measurement.Kilo }
            }
        }
    
        DatabaseExporter {
            id: dbExporter
            onErrorChanged: console.log("Export error:", errorString)
            table: exampleTable
            dataFormat: DatabaseExporter.FormattedData
            output: CsvWriter {
                output: File {
                    fileName: "SensorValues.csv"
                    storage: UsbStorage { }
                }
            }
        }
    
        Timer {
            onTriggered: {
                sensor1.data = Math.random() * 100
                sensor2.data = 1000 + Math.random() * 100
                exampleTable.submit();
            }
        }
    
        Timer {
            interval: 10*1000
            onTriggered: {
                dbExporter.execute();
                exampleTable.truncate()
            }
        }
    }
    
    