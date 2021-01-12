
.. _object_DatabaseSqlQuery:


:index:`DatabaseSqlQuery`
-------------------------

Description
***********

The DatabaseSqlQuery object encapsulates a SQL query and handles errors or results.

:**› Inherits**: :ref:`Object <object_Object>`

Overview
********

Properties
++++++++++

.. hlist::
  :columns: 1

  * :ref:`error <property_DatabaseSqlQuery_error>`
  * :ref:`errorString <property_DatabaseSqlQuery_errorString>`
  * :ref:`forwardOnly <property_DatabaseSqlQuery_forwardOnly>`
  * :ref:`query <property_DatabaseSqlQuery_query>`
  * :ref:`results <property_DatabaseSqlQuery_results>`
  * :ref:`Object.objectId <property_Object_objectId>`
  * :ref:`Object.parent <property_Object_parent>`

Methods
+++++++

.. hlist::
  :columns: 1

  * :ref:`execute() <method_DatabaseSqlQuery_execute>`
  * :ref:`pollResults() <method_DatabaseSqlQuery_pollResults>`
  * :ref:`Object.fromJson() <method_Object_fromJson>`
  * :ref:`Object.toJson() <method_Object_toJson>`

Signals
+++++++

.. hlist::
  :columns: 1

  * :ref:`errorOccurred() <signal_DatabaseSqlQuery_errorOccurred>`
  * :ref:`Object.completed() <signal_Object_completed>`

Enumerations
++++++++++++

.. hlist::
  :columns: 1

  * :ref:`Error <enum_DatabaseSqlQuery_Error>`



Properties
**********


.. _property_DatabaseSqlQuery_error:

.. _signal_DatabaseSqlQuery_errorChanged:

.. index::
   single: error

error
+++++

This property holds the most recently occurred error or :ref:`DatabaseSqlQuery.NoError <enumitem_DatabaseSqlQuery_NoError>` if no error occurred. If the same error occurs multiple times this property does not change. Use the :ref:`errorOccurred() <signal_DatabaseSqlQuery_errorOccurred>` signal to detect multiple occurrences of the same error.

:**› Type**: :ref:`Error <enum_DatabaseSqlQuery_Error>`
:**› Signal**: errorChanged()
:**› Attributes**: Readonly


.. _property_DatabaseSqlQuery_errorString:

.. _signal_DatabaseSqlQuery_errorStringChanged:

.. index::
   single: errorString

errorString
+++++++++++

This property holds the current human readable error string corresponding to the current value in the :ref:`error <property_DatabaseSqlQuery_error>` property. It may include additional information such as failure reasons or locations.

:**› Type**: String
:**› Signal**: errorStringChanged()
:**› Attributes**: Readonly


.. _property_DatabaseSqlQuery_forwardOnly:

.. _signal_DatabaseSqlQuery_forwardOnlyChanged:

.. index::
   single: forwardOnly

forwardOnly
+++++++++++

This property holds whether the query is forward only. For some queries :ref:`forwardOnly <property_DatabaseSqlQuery_forwardOnly>` has to be ``true`` to work properly. Forward only mode can be (depending on the driver) more memory efficient since results do not need to be cached. It will also improve performance on some databases.

:**› Type**: Boolean
:**› Default**: ``false``
:**› Signal**: forwardOnlyChanged()
:**› Attributes**: Writable


.. _property_DatabaseSqlQuery_query:

.. _signal_DatabaseSqlQuery_queryChanged:

.. index::
   single: query

query
+++++

This property holds the query string which will be executed.

:**› Type**: String
:**› Signal**: queryChanged()
:**› Attributes**: Writable


.. _property_DatabaseSqlQuery_results:

.. _signal_DatabaseSqlQuery_resultsChanged:

.. index::
   single: results

results
+++++++

This property holds the results of the query. For example the column ``id`` of the second row can be read through ``results[1].id``.

:**› Type**: List
:**› Signal**: resultsChanged()
:**› Attributes**: Readonly, Requires :ref:`Polling <object_Polling>`

Methods
*******


.. _method_DatabaseSqlQuery_execute:

.. index::
   single: execute

execute()
+++++++++

This method executes the query and updates :ref:`results <property_DatabaseSqlQuery_results>`



.. _method_DatabaseSqlQuery_pollResults:

.. index::
   single: pollResults

pollResults()
+++++++++++++

This method polls the :ref:`results <property_DatabaseSqlQuery_results>` property. It is called automatically when using a :ref:`Polling <object_Polling>` property modifier on this property and usually does not have to be called manually.


Signals
*******


.. _signal_DatabaseSqlQuery_errorOccurred:

.. index::
   single: errorOccurred

errorOccurred()
+++++++++++++++

This signal is emitted whenever an error has occurred, regardless of whether the :ref:`error <property_DatabaseSqlQuery_error>` property has changed or not. In contrast to the change notification signal of the :ref:`error <property_DatabaseSqlQuery_error>` property this signal is also emitted several times if a certain error occurs several times in succession.


Enumerations
************


.. _enum_DatabaseSqlQuery_Error:

.. index::
   single: Error

Error
+++++

This enumeration describes all errors which can occur in DatabaseSqlQuery objects. The most recently occurred error is stored in the :ref:`error <property_DatabaseSqlQuery_error>` property.

.. index::
   single: DatabaseSqlQuery.NoError
.. index::
   single: DatabaseSqlQuery.InvalidDatabase
.. index::
   single: DatabaseSqlQuery.EmptyQueryError
.. index::
   single: DatabaseSqlQuery.InvalidQueryError
.. index::
   single: DatabaseSqlQuery.TransactionError
.. index::
   single: DatabaseSqlQuery.UnknownError
.. list-table::
  :widths: auto
  :header-rows: 1

  * - Name
    - Value
    - Description

      .. _enumitem_DatabaseSqlQuery_NoError:
  * - ``DatabaseSqlQuery.NoError``
    - ``0``
    - No error occurred or was detected.

      .. _enumitem_DatabaseSqlQuery_InvalidDatabase:
  * - ``DatabaseSqlQuery.InvalidDatabase``
    - ``1``
    - Parent is not a database object.

      .. _enumitem_DatabaseSqlQuery_EmptyQueryError:
  * - ``DatabaseSqlQuery.EmptyQueryError``
    - ``2``
    - Empty query string.

      .. _enumitem_DatabaseSqlQuery_InvalidQueryError:
  * - ``DatabaseSqlQuery.InvalidQueryError``
    - ``3``
    - The query caused an error: .

      .. _enumitem_DatabaseSqlQuery_TransactionError:
  * - ``DatabaseSqlQuery.TransactionError``
    - ``4``
    - The query caused an transaction error: .

      .. _enumitem_DatabaseSqlQuery_UnknownError:
  * - ``DatabaseSqlQuery.UnknownError``
    - ``5``
    - The query caused an unknown error: .

Example
*******
See :ref:`LocalDatabase example <example_LocalDatabase>` on how to use DatabaseSqlQuery.
