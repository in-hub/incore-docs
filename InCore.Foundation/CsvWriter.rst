
.. _object_CsvWriter:


:index:`CsvWriter`
------------------

Description
***********

The CsvWriter object is a special :ref:`DataObjectWriter <object_DataObjectWriter>` designed to write datasets as rows containing comma-separated values to an :ref:`output <property_CsvWriter_output>`, usually a :ref:`File <object_File>`. The format of the output data can be configured through the :ref:`delimiter <property_CsvWriter_delimiter>` and :ref:`writeHeader <property_CsvWriter_writeHeader>` properties.

:**› Inherits**: :ref:`DataObjectWriter <object_DataObjectWriter>`

Overview
********

Properties
++++++++++

.. hlist::
  :columns: 3

  * :ref:`delimiter <property_CsvWriter_delimiter>`
  * :ref:`error <property_CsvWriter_error>`
  * :ref:`errorString <property_CsvWriter_errorString>`
  * :ref:`output <property_CsvWriter_output>`
  * :ref:`outputMode <property_CsvWriter_outputMode>`
  * :ref:`rotationMode <property_CsvWriter_rotationMode>`
  * :ref:`writeByteOrderMark <property_CsvWriter_writeByteOrderMark>`
  * :ref:`writeHeader <property_CsvWriter_writeHeader>`
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
  :columns: 1

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

  * :ref:`errorOccurred() <signal_CsvWriter_errorOccurred>`
  * :ref:`DataObjectWriter.objectsDataChanged() <signal_DataObjectWriter_objectsDataChanged>`
  * :ref:`DataObjectWriter.submitted() <signal_DataObjectWriter_submitted>`
  * :ref:`DataObjectWriter.truncated() <signal_DataObjectWriter_truncated>`
  * :ref:`Object.completed() <signal_Object_completed>`

Enumerations
++++++++++++

.. hlist::
  :columns: 1

  * :ref:`Error <enum_CsvWriter_Error>`
  * :ref:`OutputMode <enum_CsvWriter_OutputMode>`
  * :ref:`RotationMode <enum_CsvWriter_RotationMode>`
  * :ref:`DataObjectWriter.SubmitMode <enum_DataObjectWriter_SubmitMode>`



Properties
**********


.. _property_CsvWriter_delimiter:

.. _signal_CsvWriter_delimiterChanged:

.. index::
   single: delimiter

delimiter
+++++++++

This property holds the delimiter for separating columns in a data row.

:**› Type**: String
:**› Default**: ``;``
:**› Signal**: delimiterChanged()
:**› Attributes**: Writable


.. _property_CsvWriter_error:

.. _signal_CsvWriter_errorChanged:

.. index::
   single: error

error
+++++

This property holds the most recently occurred error or :ref:`CsvWriter.NoError <enumitem_CsvWriter_NoError>` if no error occurred. If the same error occurs multiple times this property does not change. Use the :ref:`errorOccurred() <signal_CsvWriter_errorOccurred>` signal to detect multiple occurrences of the same error.

:**› Type**: :ref:`Error <enum_CsvWriter_Error>`
:**› Signal**: errorChanged()
:**› Attributes**: Readonly


.. _property_CsvWriter_errorString:

.. _signal_CsvWriter_errorStringChanged:

.. index::
   single: errorString

errorString
+++++++++++

This property holds the current human readable error string corresponding to the current value in the :ref:`error <property_CsvWriter_error>` property. It may include additional information such as failure reasons or locations.

:**› Type**: String
:**› Signal**: errorStringChanged()
:**› Attributes**: Readonly


.. _property_CsvWriter_output:

.. _signal_CsvWriter_outputChanged:

.. index::
   single: output

output
++++++

This property holds the output device which the CSV data is written to. Usually a :ref:`File <object_File>` object should be used here.

:**› Type**: :ref:`IoDevice <object_IoDevice>`
:**› Signal**: outputChanged()
:**› Attributes**: Writable


.. _property_CsvWriter_outputMode:

.. _signal_CsvWriter_outputModeChanged:

.. index::
   single: outputMode

outputMode
++++++++++

This property holds the output mode which defines how new rows are written to the output. See the :ref:`OutputMode <enum_CsvWriter_OutputMode>` enumeration for details.

:**› Type**: :ref:`OutputMode <enum_CsvWriter_OutputMode>`
:**› Default**: :ref:`CsvWriter.OutputAppend <enumitem_CsvWriter_OutputAppend>`
:**› Signal**: outputModeChanged()
:**› Attributes**: Writable


.. _property_CsvWriter_rotationMode:

.. _signal_CsvWriter_rotationModeChanged:

.. index::
   single: rotationMode

rotationMode
++++++++++++

This property holds the rotation mode which allows rotating files periodically in an automated manner. On every data row submission the :ref:`CsvWriter <object_CsvWriter>` checks whether a rotation period is elapsed and if necessary closes the current file and opens a file for the new period. The name of the file depends on the configured rotation mode. See the :ref:`RotationMode <enum_CsvWriter_RotationMode>` enumeration for details.

:**› Type**: :ref:`RotationMode <enum_CsvWriter_RotationMode>`
:**› Default**: :ref:`CsvWriter.NoRotation <enumitem_CsvWriter_NoRotation>`
:**› Signal**: rotationModeChanged()
:**› Attributes**: Writable


.. _property_CsvWriter_writeByteOrderMark:

.. _signal_CsvWriter_writeByteOrderMarkChanged:

.. index::
   single: writeByteOrderMark

writeByteOrderMark
++++++++++++++++++

This property holds whether to write the `Byte Order Mark (BOM) <https://en.wikipedia.org/wiki/Byte_order_mark>`_ ``EF BB BF`` as the first characters to the output. These BOM characters indicate that UTF-8 encoding should be used when reading the file.

This property was introduced in InCore 2.1.

:**› Type**: Boolean
:**› Default**: ``false``
:**› Signal**: writeByteOrderMarkChanged()
:**› Attributes**: Writable


.. _property_CsvWriter_writeHeader:

.. _signal_CsvWriter_writeHeaderChanged:

.. index::
   single: writeHeader

writeHeader
+++++++++++

This property holds whether to write a header with the column names (:ref:`DataObject.name <property_DataObject_name>`) to the output.

:**› Type**: Boolean
:**› Default**: ``true``
:**› Signal**: writeHeaderChanged()
:**› Attributes**: Writable

Signals
*******


.. _signal_CsvWriter_errorOccurred:

.. index::
   single: errorOccurred

errorOccurred()
+++++++++++++++

This signal is emitted whenever an error has occurred, regardless of whether the :ref:`error <property_CsvWriter_error>` property has changed or not. In contrast to the change notification signal of the :ref:`error <property_CsvWriter_error>` property this signal is also emitted several times if a certain error occurs several times in succession.


Enumerations
************


.. _enum_CsvWriter_Error:

.. index::
   single: Error

Error
+++++

This enumeration describes all errors which can occur in CsvWriter objects. The most recently occurred error is stored in the :ref:`error <property_CsvWriter_error>` property.

.. index::
   single: CsvWriter.NoError
.. index::
   single: CsvWriter.OutputNotSetError
.. index::
   single: CsvWriter.OutputOpenError
.. list-table::
  :widths: auto
  :header-rows: 1

  * - Name
    - Value
    - Description

      .. _enumitem_CsvWriter_NoError:
  * - ``CsvWriter.NoError``
    - ``0``
    - No error occurred or was detected.

      .. _enumitem_CsvWriter_OutputNotSetError:
  * - ``CsvWriter.OutputNotSetError``
    - ``1``
    - Output not set.

      .. _enumitem_CsvWriter_OutputOpenError:
  * - ``CsvWriter.OutputOpenError``
    - ``2``
    - Could not open output.


.. _enum_CsvWriter_OutputMode:

.. index::
   single: OutputMode

OutputMode
++++++++++

This enumeration describes the output mode which defines how new rows are written to the output.

.. index::
   single: CsvWriter.OutputAppend
.. index::
   single: CsvWriter.OutputTruncate
.. index::
   single: CsvWriter.OutputCustom
.. list-table::
  :widths: auto
  :header-rows: 1

  * - Name
    - Value
    - Description

      .. _enumitem_CsvWriter_OutputAppend:
  * - ``CsvWriter.OutputAppend``
    - ``0``
    - Always append rows to the output. This mode sets the :ref:`IoDevice.append <property_IoDevice_append>` property to ``true`` and clears the :ref:`IoDevice.truncate <property_IoDevice_truncate>` and :ref:`IoDevice.unbuffered <property_IoDevice_unbuffered>` properties.

      .. _enumitem_CsvWriter_OutputTruncate:
  * - ``CsvWriter.OutputTruncate``
    - ``1``
    - Truncate the output on every submission to make it always contain only one row with the latest data. This mode clears the :ref:`IoDevice.append <property_IoDevice_append>` property and sets the :ref:`IoDevice.truncate <property_IoDevice_truncate>` and :ref:`IoDevice.unbuffered <property_IoDevice_unbuffered>` properties to ``true``.

      .. _enumitem_CsvWriter_OutputCustom:
  * - ``CsvWriter.OutputCustom``
    - ``2``
    - Open the output without changing the :ref:`IoDevice.append <property_IoDevice_append>`, :ref:`IoDevice.truncate <property_IoDevice_truncate>` and :ref:`IoDevice.unbuffered <property_IoDevice_unbuffered>` properties. This allows implementing a custom output mode by setting these properties manually.


.. _enum_CsvWriter_RotationMode:

.. index::
   single: RotationMode

RotationMode
++++++++++++

This enumeration describes all supported modes for rotating files periodically.

.. index::
   single: CsvWriter.NoRotation
.. index::
   single: CsvWriter.RotateMinutely
.. index::
   single: CsvWriter.RotateHourly
.. index::
   single: CsvWriter.RotateDaily
.. index::
   single: CsvWriter.RotateWeekly
.. index::
   single: CsvWriter.RotateMonthly
.. index::
   single: CsvWriter.RotateYearly
.. list-table::
  :widths: auto
  :header-rows: 1

  * - Name
    - Value
    - Description

      .. _enumitem_CsvWriter_NoRotation:
  * - ``CsvWriter.NoRotation``
    - ``0``
    - Disable periodical file rotation.

      .. _enumitem_CsvWriter_RotateMinutely:
  * - ``CsvWriter.RotateMinutely``
    - ``1``
    - Rotate every minute with file suffix `<yyyyMMddTHHmm>`.

      .. _enumitem_CsvWriter_RotateHourly:
  * - ``CsvWriter.RotateHourly``
    - ``2``
    - Rotate every hour with file suffix `<yyyyMMddTHH00>`.

      .. _enumitem_CsvWriter_RotateDaily:
  * - ``CsvWriter.RotateDaily``
    - ``3``
    - Rotate every day with file suffix `<yyyyMMdd>`.

      .. _enumitem_CsvWriter_RotateWeekly:
  * - ``CsvWriter.RotateWeekly``
    - ``4``
    - Rotate every week with file suffix `<yyyyWW>`.

      .. _enumitem_CsvWriter_RotateMonthly:
  * - ``CsvWriter.RotateMonthly``
    - ``5``
    - Rotate every month with file suffix `<yyyyMM>`.

      .. _enumitem_CsvWriter_RotateYearly:
  * - ``CsvWriter.RotateYearly``
    - ``6``
    - Rotate every year with file suffix `<yyyy>`.


.. _example_CsvWriter:


Example
*******

.. code-block:: qml

    import InCore.Foundation 2.0
    
    Application {
    
        // record measurements and append new lines after all data objects have been updated
        CsvWriter {
            id: writer1
            Repeater on objects {
                model: 3
                Measurement {
                    id: measurement
                    name: "meas" + index
                    property var updateTimer : Timer {
                        interval: 1000
                        running: true
                        onTriggered: measurement.data = Math.random() * 100;
                    }
                }
            }
    
            output: File {
                fileName: "all-values.csv"
                storage: LocalStorage { }
            }
    
            outputMode: CsvWriter.OutputAppend
            submitMode: CsvWriter.SubmitOnCompleteDataset
        }
    
        // continuously update a file in memory which always contains only one line with the most recent values
        CsvWriter {
            objects: writer1.objects
    
            output: File {
                unbuffered: true
                fileName: "current-values.txt"
                storage: InMemoryStorage { }
            }
    
            writeHeader: false
            delimiter: " "
            outputMode: CsvWriter.OutputTruncate
            submitMode: CsvWriter.SubmitOnAnyChange
        }
    }
    