
.. _object_EventLogFile:


:index:`EventLogFile`
---------------------

Description
***********

The EventLogFile object is a :ref:`EventOutput <object_EventOutput>` and writes events to a :ref:`IoDevice <object_IoDevice>` for example a :ref:`File <object_File>`. Each event is printed in a new line prefixed with the current date and time and the event's severity. The :ref:`log() <method_EventLogFile_log>` method can be used to print messages to the IoDevice directly.

:**› Inherits**: :ref:`EventOutput <object_EventOutput>`

Overview
********

Properties
++++++++++

.. hlist::
  :columns: 2

  * :ref:`dateTime <property_EventLogFile_dateTime>`
  * :ref:`error <property_EventLogFile_error>`
  * :ref:`errorString <property_EventLogFile_errorString>`
  * :ref:`output <property_EventLogFile_output>`
  * :ref:`outputMode <property_EventLogFile_outputMode>`
  * :ref:`EventOutput.filterCategories <property_EventOutput_filterCategories>`
  * :ref:`EventOutput.filterExactSeverity <property_EventOutput_filterExactSeverity>`
  * :ref:`EventOutput.filterMinimumSeverity <property_EventOutput_filterMinimumSeverity>`
  * :ref:`Object.objectId <property_Object_objectId>`
  * :ref:`Object.parent <property_Object_parent>`

Methods
+++++++

.. hlist::
  :columns: 1

  * :ref:`log() <method_EventLogFile_log>`
  * :ref:`Object.deserializeProperties() <method_Object_deserializeProperties>`
  * :ref:`Object.fromJson() <method_Object_fromJson>`
  * :ref:`Object.toJson() <method_Object_toJson>`

Signals
+++++++

.. hlist::
  :columns: 1

  * :ref:`errorOccurred() <signal_EventLogFile_errorOccurred>`
  * :ref:`EventOutput.filterCategoriesDataChanged() <signal_EventOutput_filterCategoriesDataChanged>`
  * :ref:`Object.completed() <signal_Object_completed>`

Enumerations
++++++++++++

.. hlist::
  :columns: 1

  * :ref:`Error <enum_EventLogFile_Error>`
  * :ref:`OutputMode <enum_EventLogFile_OutputMode>`



Properties
**********


.. _property_EventLogFile_dateTime:

.. _signal_EventLogFile_dateTimeChanged:

.. index::
   single: dateTime

dateTime
++++++++

This property holds a :ref:`DateTime <property_EventLogFile_DateTime>` object whose :ref:`DateTime.highPrecisionString <property_DateTime_highPrecisionString>` property is used to format the date for log messages. It can be used to customize the date formatting.

:**› Type**: :ref:`DateTime <object_DateTime>`
:**› Signal**: dateTimeChanged()
:**› Attributes**: Writable


.. _property_EventLogFile_error:

.. _signal_EventLogFile_errorChanged:

.. index::
   single: error

error
+++++

This property holds the most recently occurred error or :ref:`EventLogFile.NoError <enumitem_EventLogFile_NoError>` if no error occurred. If the same error occurs multiple times this property does not change. Use the :ref:`errorOccurred() <signal_EventLogFile_errorOccurred>` signal to detect multiple occurrences of the same error.

:**› Type**: :ref:`Error <enum_EventLogFile_Error>`
:**› Signal**: errorChanged()
:**› Attributes**: Readonly


.. _property_EventLogFile_errorString:

.. _signal_EventLogFile_errorStringChanged:

.. index::
   single: errorString

errorString
+++++++++++

This property holds the current human readable error string corresponding to the current value in the :ref:`error <property_EventLogFile_error>` property. It may include additional information such as failure reasons or locations.

:**› Type**: String
:**› Signal**: errorStringChanged()
:**› Attributes**: Readonly


.. _property_EventLogFile_output:

.. _signal_EventLogFile_outputChanged:

.. index::
   single: output

output
++++++

This property holds the output device (e.g. :ref:`File <object_File>`) to which the log messages are written.

:**› Type**: :ref:`IoDevice <object_IoDevice>`
:**› Signal**: outputChanged()
:**› Attributes**: Writable


.. _property_EventLogFile_outputMode:

.. _signal_EventLogFile_outputModeChanged:

.. index::
   single: outputMode

outputMode
++++++++++

This property holds the output mode which specifies how to open the output at start, i.e. append messages or start from scratch everytime.

:**› Type**: :ref:`OutputMode <enum_EventLogFile_OutputMode>`
:**› Default**: :ref:`EventLogFile.OutputAppend <enumitem_EventLogFile_OutputAppend>`
:**› Signal**: outputModeChanged()
:**› Attributes**: Writable

Methods
*******


.. _method_EventLogFile_log:

.. index::
   single: log

log(args)
+++++++++

This method prints a new line to the IoDevice. Each line consists of a date time and the given arguments separated by space.


Signals
*******


.. _signal_EventLogFile_errorOccurred:

.. index::
   single: errorOccurred

errorOccurred()
+++++++++++++++

This signal is emitted whenever an error has occurred, regardless of whether the :ref:`error <property_EventLogFile_error>` property has changed or not. In contrast to the change notification signal of the :ref:`error <property_EventLogFile_error>` property this signal is also emitted several times if a certain error occurs several times in succession.


Enumerations
************


.. _enum_EventLogFile_Error:

.. index::
   single: Error

Error
+++++

This enumeration describes all errors which can occur in EventLogFile objects. The most recently occurred error is stored in the :ref:`error <property_EventLogFile_error>` property.

.. index::
   single: EventLogFile.NoError
.. index::
   single: EventLogFile.OutputNotSetError
.. index::
   single: EventLogFile.OutputOpenError
.. list-table::
  :widths: auto
  :header-rows: 1

  * - Name
    - Value
    - Description

      .. _enumitem_EventLogFile_NoError:
  * - ``EventLogFile.NoError``
    - ``0``
    - No error occurred or was detected.

      .. _enumitem_EventLogFile_OutputNotSetError:
  * - ``EventLogFile.OutputNotSetError``
    - ``1``
    - Output not set.

      .. _enumitem_EventLogFile_OutputOpenError:
  * - ``EventLogFile.OutputOpenError``
    - ``2``
    - Could not open output.


.. _enum_EventLogFile_OutputMode:

.. index::
   single: OutputMode

OutputMode
++++++++++

This enumeration describes the output mode of the :ref:`EventLogFile <object_EventLogFile>`.

.. index::
   single: EventLogFile.OutputAppend
.. index::
   single: EventLogFile.OutputTruncate
.. list-table::
  :widths: auto
  :header-rows: 1

  * - Name
    - Value
    - Description

      .. _enumitem_EventLogFile_OutputAppend:
  * - ``EventLogFile.OutputAppend``
    - ``0``
    - Append lines at the end of :ref:`output <property_EventLogFile_output>`. The file is never deleted or truncated with this mode.

      .. _enumitem_EventLogFile_OutputTruncate:
  * - ``EventLogFile.OutputTruncate``
    - ``1``
    - Truncate the file each time it is opened, i.e. every application start or whenever opened and closed manually.


.. _example_EventLogFile:


Example
*******

.. code-block:: qml

    import InCore.Foundation 2.0
    
    Application {
    
        EventLogFile {
            id: logFile
            // log to file stored on persistent local storage
            output: File {
                storage: LocalStorage { }
                fileName: "myapp.log"
            }
        }
    
        onCompleted: logFile.log("App started with random value", Math.random())
    }
    