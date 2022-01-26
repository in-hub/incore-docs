
.. _object_Process:


:index:`Process`
----------------

Description
***********

The Process object allows running and managing an external process.

:**› Inherits**: :ref:`Object <object_Object>`

Overview
********

Properties
++++++++++

.. hlist::
  :columns: 2

  * :ref:`arguments <property_Process_arguments>`
  * :ref:`error <property_Process_error>`
  * :ref:`errorString <property_Process_errorString>`
  * :ref:`exitCode <property_Process_exitCode>`
  * :ref:`program <property_Process_program>`
  * :ref:`running <property_Process_running>`
  * :ref:`Object.objectId <property_Object_objectId>`
  * :ref:`Object.parent <property_Object_parent>`

Methods
+++++++

.. hlist::
  :columns: 1

  * :ref:`kill() <method_Process_kill>`
  * :ref:`start() <method_Process_start>`
  * :ref:`stop() <method_Process_stop>`
  * :ref:`Object.deserializeProperties() <method_Object_deserializeProperties>`
  * :ref:`Object.fromJson() <method_Object_fromJson>`
  * :ref:`Object.serializeProperties() <method_Object_serializeProperties>`
  * :ref:`Object.toJson() <method_Object_toJson>`

Signals
+++++++

.. hlist::
  :columns: 1

  * :ref:`errorOccurred() <signal_Process_errorOccurred>`
  * :ref:`finished() <signal_Process_finished>`
  * :ref:`started() <signal_Process_started>`
  * :ref:`Object.completed() <signal_Object_completed>`

Enumerations
++++++++++++

.. hlist::
  :columns: 1

  * :ref:`Error <enum_Process_Error>`



Properties
**********


.. _property_Process_arguments:

.. _signal_Process_argumentsChanged:

.. index::
   single: arguments

arguments
+++++++++

This property holds the arguments which to pass to the program.

:**› Type**: StringList
:**› Signal**: argumentsChanged()
:**› Attributes**: Writable


.. _property_Process_error:

.. _signal_Process_errorChanged:

.. index::
   single: error

error
+++++

This property holds the most recently occurred error or :ref:`Process.NoError <enumitem_Process_NoError>` if no error occurred. If the same error occurs multiple times this property does not change. Use the :ref:`errorOccurred() <signal_Process_errorOccurred>` signal to detect multiple occurrences of the same error.

:**› Type**: :ref:`Error <enum_Process_Error>`
:**› Signal**: errorChanged()
:**› Attributes**: Readonly


.. _property_Process_errorString:

.. _signal_Process_errorStringChanged:

.. index::
   single: errorString

errorString
+++++++++++

This property holds the current human readable error string corresponding to the current value in the :ref:`error <property_Process_error>` property. It may include additional information such as failure reasons or locations.

:**› Type**: String
:**› Signal**: errorStringChanged()
:**› Attributes**: Readonly


.. _property_Process_exitCode:

.. _signal_Process_exitCodeChanged:

.. index::
   single: exitCode

exitCode
++++++++

This property holds the exit code of the last process that finished. It's only valid if no :ref:`Process.Crashed <enumitem_Process_Crashed>` error occurred.

This property was introduced in InCore 1.1.

:**› Type**: SignedInteger
:**› Signal**: exitCodeChanged()
:**› Attributes**: Readonly


.. _property_Process_program:

.. _signal_Process_programChanged:

.. index::
   single: program

program
+++++++

This property holds the name of the program to run. If not in ``PATH`` a relative or absolute path has to be specified as well.

:**› Type**: String
:**› Signal**: programChanged()
:**› Attributes**: Writable


.. _property_Process_running:

.. _signal_Process_runningChanged:

.. index::
   single: running

running
+++++++

This property holds whether the program is running. It can be used for both querying and changing the status and is updated automatically when calling :ref:`start() <method_Process_start>` and :ref:`stop() <method_Process_stop>`.

:**› Type**: Boolean
:**› Default**: ``false``
:**› Signal**: runningChanged()
:**› Attributes**: Writable

Methods
*******


.. _method_Process_kill:

.. index::
   single: kill

kill()
++++++

This method kills the program to using the ``SIGKILL`` signal.



.. _method_Process_start:

.. index::
   single: start

start()
+++++++

This method starts the program asynchronously. Any errors will be signaled via the :ref:`error <property_Process_error>` property and the :ref:`errorOccurred() <signal_Process_errorOccurred>` signal.

:**› Returns**: Boolean



.. _method_Process_stop:

.. index::
   single: stop

stop()
++++++

This method requests the program to stop using the ``SIGTERM`` signal.


Signals
*******


.. _signal_Process_errorOccurred:

.. index::
   single: errorOccurred

errorOccurred()
+++++++++++++++

This signal is emitted whenever an error has occurred, regardless of whether the :ref:`error <property_Process_error>` property has changed or not. In contrast to the change notification signal of the :ref:`error <property_Process_error>` property this signal is also emitted several times if a certain error occurs several times in succession.



.. _signal_Process_finished:

.. index::
   single: finished

finished()
++++++++++

This signal is emitted when the process finishes and :ref:`running <property_Process_running>` equals ``false``. The exit code of the program is available in the :ref:`exitCode <property_Process_exitCode>` property.

This signal was introduced in InCore 1.1.



.. _signal_Process_started:

.. index::
   single: started

started()
+++++++++

This signal is emitted when the process has started and :ref:`running <property_Process_running>` equals ``true``.

This signal was introduced in InCore 1.1.


Enumerations
************


.. _enum_Process_Error:

.. index::
   single: Error

Error
+++++

This enumeration describes all errors which can occur in Process objects. The most recently occurred error is stored in the :ref:`error <property_Process_error>` property.

.. index::
   single: Process.NoError
.. index::
   single: Process.AlreadyRunning
.. index::
   single: Process.InvalidProgram
.. index::
   single: Process.FailedToStart
.. index::
   single: Process.Crashed
.. index::
   single: Process.Timedout
.. index::
   single: Process.UnknownError
.. list-table::
  :widths: auto
  :header-rows: 1

  * - Name
    - Value
    - Description

      .. _enumitem_Process_NoError:
  * - ``Process.NoError``
    - ``0``
    - No error occurred or was detected.

      .. _enumitem_Process_AlreadyRunning:
  * - ``Process.AlreadyRunning``
    - ``1``
    - Process is already running and has to be stopped first.

      .. _enumitem_Process_InvalidProgram:
  * - ``Process.InvalidProgram``
    - ``2``
    - Program is empty or invalid.

      .. _enumitem_Process_FailedToStart:
  * - ``Process.FailedToStart``
    - ``3``
    - The process failed to start. Either the specified program does not exist or permissions are lacking to invoke the program.

      .. _enumitem_Process_Crashed:
  * - ``Process.Crashed``
    - ``4``
    - The process crashed some time after starting successfully.

      .. _enumitem_Process_Timedout:
  * - ``Process.Timedout``
    - ``5``
    - Waiting for the process to start or stop timed out.

      .. _enumitem_Process_UnknownError:
  * - ``Process.UnknownError``
    - ``6``
    - Unknown/other error occurred.


.. _example_Process:


Example
*******

.. code-block:: qml

    import InCore.Foundation 2.5
    
    Application {
        Process {
            program: "tar"
            arguments: [ "czf", "/tmp/logs.tar.gz", "/storage/incore/myapp/logs/" ]
            onCompleted: start();
            onStarted: console.log("Started log file export")
            onFinished: {
                if (error === Process.NoError && exitCode === 0)
                {
                    console.log("All log files have been exported successfully")
                }
                else if (error !== Process.NoError)
                {
                    console.log("Export failed due to process error", errorString)
                }
                else
                {
                    console.log("Export failed with exit code", exitCode)
                }
            }
        }
    }
    