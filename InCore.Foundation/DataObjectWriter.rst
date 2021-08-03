
.. _object_DataObjectWriter:


:index:`DataObjectWriter`
-------------------------

Description
***********

The DataObjectWriter object holds common properties and provides common mechanisms for writing a set of :ref:`DataObject <object_DataObject>` objects to an external resource such as a file or database. Submission mode and interval can be configured through the :ref:`submitMode <property_DataObjectWriter_submitMode>` and :ref:`submitInterval <property_DataObjectWriter_submitInterval>` properties. The number of written datasets can be retrieved using the :ref:`datasetCount <property_DataObjectWriter_datasetCount>` property.

:ref:`DataObjectWriter <object_DataObjectWriter>` is an abstract base object and thus can't be used directly. Instead inheriting objects such as :ref:`CsvWriter <object_CsvWriter>` or :ref:`DatabaseTable <object_DatabaseTable>` have to be instantiated.

:**› Inherits**: :ref:`Object <object_Object>`
:**› Inherited by**: :ref:`CsvWriter <object_CsvWriter>`

Overview
********

Properties
++++++++++

.. hlist::
  :columns: 1

  * :ref:`datasetCount <property_DataObjectWriter_datasetCount>`
  * :ref:`objects <property_DataObjectWriter_objects>`
  * :ref:`running <property_DataObjectWriter_running>`
  * :ref:`submitInterval <property_DataObjectWriter_submitInterval>`
  * :ref:`submitMode <property_DataObjectWriter_submitMode>`
  * :ref:`Object.objectId <property_Object_objectId>`
  * :ref:`Object.parent <property_Object_parent>`

Methods
+++++++

.. hlist::
  :columns: 2

  * :ref:`close() <method_DataObjectWriter_close>`
  * :ref:`open() <method_DataObjectWriter_open>`
  * :ref:`submit() <method_DataObjectWriter_submit>`
  * :ref:`sync() <method_DataObjectWriter_sync>`
  * :ref:`truncate() <method_DataObjectWriter_truncate>`
  * :ref:`Object.deserializeProperties() <method_Object_deserializeProperties>`
  * :ref:`Object.fromJson() <method_Object_fromJson>`
  * :ref:`Object.toJson() <method_Object_toJson>`

Signals
+++++++

.. hlist::
  :columns: 1

  * :ref:`objectsDataChanged() <signal_DataObjectWriter_objectsDataChanged>`
  * :ref:`submitted() <signal_DataObjectWriter_submitted>`
  * :ref:`truncated() <signal_DataObjectWriter_truncated>`
  * :ref:`Object.completed() <signal_Object_completed>`

Enumerations
++++++++++++

.. hlist::
  :columns: 1

  * :ref:`SubmitMode <enum_DataObjectWriter_SubmitMode>`



Properties
**********


.. _property_DataObjectWriter_datasetCount:

.. index::
   single: datasetCount

datasetCount
++++++++++++

This property holds the current number of datasets stored in the destination resource, e.g. lines in a CSV file or rows in a database table. This number does not necessarily have to be equal to the number of datasets written in the current session.

:**› Type**: SignedInteger
:**› Attributes**: Readonly


.. _property_DataObjectWriter_objects:

.. _signal_DataObjectWriter_objectsChanged:

.. index::
   single: objects

objects
+++++++

This property holds a list of :ref:`DataObject <object_DataObject>` objects which to write to the destination resource.

:**› Type**: :ref:`List <object_List>`\<:ref:`DataObject <object_DataObject>`>
:**› Signal**: objectsChanged()
:**› Attributes**: Readonly


.. _property_DataObjectWriter_running:

.. _signal_DataObjectWriter_runningChanged:

.. index::
   single: running

running
+++++++

This property holds whether the periodical data submission via :ref:`submitMode <property_DataObjectWriter_submitMode>` and :ref:`submitInterval <property_DataObjectWriter_submitInterval>` is enabled. This allows configuring a fixed interval and start or stop data submission using this property.

:**› Type**: Boolean
:**› Default**: ``true``
:**› Signal**: runningChanged()
:**› Attributes**: Writable


.. _property_DataObjectWriter_submitInterval:

.. _signal_DataObjectWriter_submitIntervalChanged:

.. index::
   single: submitInterval

submitInterval
++++++++++++++

This property holds the interval in `ms` between automated calls of the :ref:`submit() <method_DataObjectWriter_submit>` method when :ref:`submitMode <property_DataObjectWriter_submitMode>` is set to :ref:`DataObjectWriter.SubmitPeriodically <enumitem_DataObjectWriter_SubmitPeriodically>`. A value of ``0`` disables automatic data submission.

:**› Type**: SignedInteger
:**› Default**: ``0``
:**› Signal**: submitIntervalChanged()
:**› Attributes**: Writable


.. _property_DataObjectWriter_submitMode:

.. _signal_DataObjectWriter_submitModeChanged:

.. index::
   single: submitMode

submitMode
++++++++++

This property holds the mode which defines how and when to submit datasets to the destination resource.

:**› Type**: :ref:`SubmitMode <enum_DataObjectWriter_SubmitMode>`
:**› Default**: :ref:`DataObjectWriter.SubmitManually <enumitem_DataObjectWriter_SubmitManually>`
:**› Signal**: submitModeChanged()
:**› Attributes**: Writable

Methods
*******


.. _method_DataObjectWriter_close:

.. index::
   single: close

close()
+++++++

This method closes the destination resource. When closed no more data can be submitted. This method usually doesn't have to be called manually.



.. _method_DataObjectWriter_open:

.. index::
   single: open

open()
++++++

This method opens the destination resource for writing. It returns ``true`` on success, otherwise ``false``. Errors may be raised by the specific object implementation. This method is called automatically upon data submission and doesn't have to be called manually in most cases.

:**› Returns**: Boolean



.. _method_DataObjectWriter_submit:

.. index::
   single: submit

submit()
++++++++

This method submits a new dataset to the destination resource, i.e. a new row in the output file or a database table. A dataset consists of all configured :ref:`objects <property_DataObjectWriter_objects>` and usually is represented as a row in the destination resource. Instead of calling this method manually one of the submit modes should be configured through the :ref:`submitMode <property_DataObjectWriter_submitMode>` property.



.. _method_DataObjectWriter_sync:

.. index::
   single: sync

sync()
++++++

This method synchronizes any pending data or buffers to the target resource or storage. It can be called before ejecting or unmounting the underlying storage, e.g. an USB drive. In case no buffering is desired at all, appropriate modes for the target resource should be configured instead, e.g. :ref:`IoDevice.unbuffered <property_IoDevice_unbuffered>` for I/O devices and files.



.. _method_DataObjectWriter_truncate:

.. index::
   single: truncate

truncate()
++++++++++

This method removes all previously written datasets from the destination resource, e.g. truncate an output file or remove all rows in a database table.


Signals
*******


.. _signal_DataObjectWriter_objectsDataChanged:

.. index::
   single: objectsDataChanged

objectsDataChanged(SignedInteger index)
+++++++++++++++++++++++++++++++++++++++

This signal is emitted whenever the :ref:`List.dataChanged() <signal_List_dataChanged>` signal is emitted, i.e. the item at ``index`` in the :ref:`objects <property_DataObjectWriter_objects>` list itself emitted the dataChanged() signal.



.. _signal_DataObjectWriter_submitted:

.. index::
   single: submitted

submitted()
+++++++++++

This signal is emitted when :ref:`objects <property_DataObjectWriter_objects>` have been successfully submitted.

This signal was introduced in InCore 2.3.



.. _signal_DataObjectWriter_truncated:

.. index::
   single: truncated

truncated()
+++++++++++

This signal is emitted when :ref:`objects <property_DataObjectWriter_objects>` have been truncated.

This signal was introduced in InCore 2.3.


Enumerations
************


.. _enum_DataObjectWriter_SubmitMode:

.. index::
   single: SubmitMode

SubmitMode
++++++++++

This enumeration describes the mode which specifies when and under which circumstances data objects should be submitted to the target. Depending on the inheriting object this can be writing a data row to a CSV file or inserting a data row in a database table.

.. index::
   single: DataObjectWriter.SubmitManually
.. index::
   single: DataObjectWriter.SubmitPeriodically
.. index::
   single: DataObjectWriter.SubmitOnAnyChange
.. index::
   single: DataObjectWriter.SubmitOnCompleteDataset
.. list-table::
  :widths: auto
  :header-rows: 1

  * - Name
    - Value
    - Description

      .. _enumitem_DataObjectWriter_SubmitManually:
  * - ``DataObjectWriter.SubmitManually``
    - ``0``
    - Submit data objects manually whenever :ref:`submit() <method_DataObjectWriter_submit>` is called.

      .. _enumitem_DataObjectWriter_SubmitPeriodically:
  * - ``DataObjectWriter.SubmitPeriodically``
    - ``1``
    - Submit periodically depending on :ref:`submitInterval <property_DataObjectWriter_submitInterval>` and :ref:`running <property_DataObjectWriter_running>`.

      .. _enumitem_DataObjectWriter_SubmitOnAnyChange:
  * - ``DataObjectWriter.SubmitOnAnyChange``
    - ``2``
    - Submit whenever any data object changes.

      .. _enumitem_DataObjectWriter_SubmitOnCompleteDataset:
  * - ``DataObjectWriter.SubmitOnCompleteDataset``
    - ``3``
    - Submit once a dataset is complete, i.e. all data objects have changed since last submission.
