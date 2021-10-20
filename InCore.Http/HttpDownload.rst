
.. _object_HttpDownload:


:index:`HttpDownload`
---------------------

Description
***********

The HttpDownload object provides a high-level interface for downloading files from HTTP servers. Once started via :ref:`start() <method_HttpDownload_start>` or the :ref:`running <property_HttpDownload_running>` property the download is performed asynchronously in the background. The progress can be monitored through the :ref:`bytesReceived <property_HttpDownload_bytesReceived>` property. When finished the :ref:`finished() <signal_HttpDownload_finished>` signal is emitted and the :ref:`running <property_HttpDownload_running>` property changes to ``false``.

:**› Inherits**: :ref:`Object <object_Object>`

Overview
********

Properties
++++++++++

.. hlist::
  :columns: 2

  * :ref:`bytesReceived <property_HttpDownload_bytesReceived>`
  * :ref:`bytesTotal <property_HttpDownload_bytesTotal>`
  * :ref:`error <property_HttpDownload_error>`
  * :ref:`errorString <property_HttpDownload_errorString>`
  * :ref:`outputFile <property_HttpDownload_outputFile>`
  * :ref:`request <property_HttpDownload_request>`
  * :ref:`running <property_HttpDownload_running>`
  * :ref:`url <property_HttpDownload_url>`
  * :ref:`Object.objectId <property_Object_objectId>`
  * :ref:`Object.parent <property_Object_parent>`

Methods
+++++++

.. hlist::
  :columns: 1

  * :ref:`start() <method_HttpDownload_start>`
  * :ref:`stop() <method_HttpDownload_stop>`
  * :ref:`Object.deserializeProperties() <method_Object_deserializeProperties>`
  * :ref:`Object.fromJson() <method_Object_fromJson>`
  * :ref:`Object.toJson() <method_Object_toJson>`

Signals
+++++++

.. hlist::
  :columns: 1

  * :ref:`errorOccurred() <signal_HttpDownload_errorOccurred>`
  * :ref:`finished() <signal_HttpDownload_finished>`
  * :ref:`Object.completed() <signal_Object_completed>`

Enumerations
++++++++++++

.. hlist::
  :columns: 1

  * :ref:`Error <enum_HttpDownload_Error>`



Properties
**********


.. _property_HttpDownload_bytesReceived:

.. _signal_HttpDownload_bytesReceivedChanged:

.. index::
   single: bytesReceived

bytesReceived
+++++++++++++

This property holds the number of bytes already downloaded.

:**› Type**: SignedBigInteger
:**› Signal**: bytesReceivedChanged()
:**› Attributes**: Readonly


.. _property_HttpDownload_bytesTotal:

.. _signal_HttpDownload_bytesTotalChanged:

.. index::
   single: bytesTotal

bytesTotal
++++++++++

This property holds the total number of bytes to download.

:**› Type**: SignedBigInteger
:**› Signal**: bytesTotalChanged()
:**› Attributes**: Readonly


.. _property_HttpDownload_error:

.. _signal_HttpDownload_errorChanged:

.. index::
   single: error

error
+++++

This property holds the most recently occurred error or :ref:`HttpDownload.NoError <enumitem_HttpDownload_NoError>` if no error occurred. If the same error occurs multiple times this property does not change. Use the :ref:`errorOccurred() <signal_HttpDownload_errorOccurred>` signal to detect multiple occurrences of the same error.

:**› Type**: :ref:`Error <enum_HttpDownload_Error>`
:**› Signal**: errorChanged()
:**› Attributes**: Readonly


.. _property_HttpDownload_errorString:

.. _signal_HttpDownload_errorStringChanged:

.. index::
   single: errorString

errorString
+++++++++++

This property holds the current human readable error string corresponding to the current value in the :ref:`error <property_HttpDownload_error>` property. It may include additional information such as failure reasons or locations.

:**› Type**: String
:**› Signal**: errorStringChanged()
:**› Attributes**: Readonly


.. _property_HttpDownload_outputFile:

.. _signal_HttpDownload_outputFileChanged:

.. index::
   single: outputFile

outputFile
++++++++++

This property holds a :ref:`File <object_File>` object representing the file which the downloaded data is written to.

:**› Type**: :ref:`File <object_File>`
:**› Signal**: outputFileChanged()
:**› Attributes**: Writable


.. _property_HttpDownload_request:

.. _signal_HttpDownload_requestChanged:

.. index::
   single: request

request
+++++++

This property holds the request used for initiating the download. It can be used for customizing e.g. the used HTTP headers.

:**› Type**: :ref:`HttpRequest <object_HttpRequest>`
:**› Signal**: requestChanged()
:**› Attributes**: Writable


.. _property_HttpDownload_running:

.. _signal_HttpDownload_runningChanged:

.. index::
   single: running

running
+++++++

This property holds whether the download is currently running. Changing this property is equivalent to calling :ref:`start() <method_HttpDownload_start>` and :ref:`stop() <method_HttpDownload_stop>`. After a download has been finished this property changes to ``false`` automatically.

:**› Type**: Boolean
:**› Default**: ``false``
:**› Signal**: runningChanged()
:**› Attributes**: Writable


.. _property_HttpDownload_url:

.. _signal_HttpDownload_urlChanged:

.. index::
   single: url

url
+++

This property holds the URL of the file to download. It wraps the :ref:`HttpRequest.url <property_HttpRequest_url>` property and is provided for convenience only.

:**› Type**: String
:**› Signal**: urlChanged()
:**› Attributes**: Writable

Methods
*******


.. _method_HttpDownload_start:

.. index::
   single: start

start()
+++++++

This method starts the download if it's not running already. It returns ``true`` if the download could be started succesfully. Otherwise an error is indicated through the :ref:`error <property_HttpDownload_error>` property. This method does not block. Instead the :ref:`finished() <signal_HttpDownload_finished>` signal is emitted when the download has been finished.

:**› Returns**: Boolean



.. _method_HttpDownload_stop:

.. index::
   single: stop

stop()
++++++

This method stops the download, i.e. aborts a running download. If it is not running, this method has no effect and does not raise an error.


Signals
*******


.. _signal_HttpDownload_errorOccurred:

.. index::
   single: errorOccurred

errorOccurred()
+++++++++++++++

This signal is emitted whenever an error has occurred, regardless of whether the :ref:`error <property_HttpDownload_error>` property has changed or not. In contrast to the change notification signal of the :ref:`error <property_HttpDownload_error>` property this signal is also emitted several times if a certain error occurs several times in succession.



.. _signal_HttpDownload_finished:

.. index::
   single: finished

finished()
++++++++++

This signal is emitted when a download has been finished. It's also emitted if an :ref:`error <property_HttpDownload_error>` occurred while downloading.


Enumerations
************


.. _enum_HttpDownload_Error:

.. index::
   single: Error

Error
+++++

This enumeration describes all errors which can occur in HttpDownload objects. The most recently occurred error is stored in the :ref:`error <property_HttpDownload_error>` property.

.. index::
   single: HttpDownload.NoError
.. index::
   single: HttpDownload.AlreadyRunning
.. index::
   single: HttpDownload.InvalidRequest
.. index::
   single: HttpDownload.InvalidOutputFile
.. index::
   single: HttpDownload.OutputFileNotWritable
.. list-table::
  :widths: auto
  :header-rows: 1

  * - Name
    - Value
    - Description

      .. _enumitem_HttpDownload_NoError:
  * - ``HttpDownload.NoError``
    - ``0``
    - No error occurred or was detected.

      .. _enumitem_HttpDownload_AlreadyRunning:
  * - ``HttpDownload.AlreadyRunning``
    - ``1``
    - The download is already running and can't be started.

      .. _enumitem_HttpDownload_InvalidRequest:
  * - ``HttpDownload.InvalidRequest``
    - ``2``
    - The request property is empty or invalid.

      .. _enumitem_HttpDownload_InvalidOutputFile:
  * - ``HttpDownload.InvalidOutputFile``
    - ``3``
    - The output file property is empty or invalid.

      .. _enumitem_HttpDownload_OutputFileNotWritable:
  * - ``HttpDownload.OutputFileNotWritable``
    - ``4``
    - The output file can't be opened for writing.


.. _example_HttpDownload:


Example
*******

.. code-block:: qml

    import InCore.Foundation 2.5
    import InCore.Http 2.5
    
    Application {
    
        HttpDownload {
            url: "http://archive.ubuntu.com/ubuntu/dists/bionic/main/installer-amd64/current/images/netboot/mini.iso"
            outputFile: File { fileName: "mini.iso"; storage: InMemoryStorage { } }
            onBytesReceivedChanged:
                console.log("Download progress:",
                            (bytesTotal > 0 ? Math.round(bytesReceived * 100 / bytesTotal) : 0) + "%");
            onFinished: console.log(bytesTotal, "bytes have been downloaded successfully to",
                                    outputFile.storage.path + "/" + outputFile.fileName)
            onCompleted: start();
        }
    
    }
    