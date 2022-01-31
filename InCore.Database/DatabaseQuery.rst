
.. _object_DatabaseQuery:


:index:`DatabaseQuery`
----------------------

Description
***********

The DatabaseQuery object is used to query objects from a database. It can be used to select a subset of the original dataset. The result can be sorted through the :ref:`orderBy <property_DatabaseQuery_orderBy>` property and limited through the :ref:`limitLength <property_DatabaseQuery_limitLength>` property.

.. note:: Pay attention to the usage of :ref:`results <property_DatabaseQuery_results>` each call will execute the query. See the example at bottom.

:**› Inherits**: :ref:`Object <object_Object>`
:**› Inherited by**: :ref:`DatabaseUpdate <object_DatabaseUpdate>`

Overview
********

Properties
++++++++++

.. hlist::
  :columns: 2

  * :ref:`error <property_DatabaseQuery_error>`
  * :ref:`errorString <property_DatabaseQuery_errorString>`
  * :ref:`filters <property_DatabaseQuery_filters>`
  * :ref:`limitLength <property_DatabaseQuery_limitLength>`
  * :ref:`limitPos <property_DatabaseQuery_limitPos>`
  * :ref:`objects <property_DatabaseQuery_objects>`
  * :ref:`orderBy <property_DatabaseQuery_orderBy>`
  * :ref:`orderByNames <property_DatabaseQuery_orderByNames>`
  * :ref:`results <property_DatabaseQuery_results>`
  * :ref:`table <property_DatabaseQuery_table>`
  * :ref:`Object.objectId <property_Object_objectId>`
  * :ref:`Object.parent <property_Object_parent>`

Methods
+++++++

.. hlist::
  :columns: 1

  * :ref:`execute() <method_DatabaseQuery_execute>`
  * :ref:`pollResults() <method_DatabaseQuery_pollResults>`
  * :ref:`Object.deserializeProperties() <method_Object_deserializeProperties>`
  * :ref:`Object.fromJson() <method_Object_fromJson>`
  * :ref:`Object.serializeProperties() <method_Object_serializeProperties>`
  * :ref:`Object.toJson() <method_Object_toJson>`

Signals
+++++++

.. hlist::
  :columns: 1

  * :ref:`errorOccurred() <signal_DatabaseQuery_errorOccurred>`
  * :ref:`filtersDataChanged() <signal_DatabaseQuery_filtersDataChanged>`
  * :ref:`objectsDataChanged() <signal_DatabaseQuery_objectsDataChanged>`
  * :ref:`orderByDataChanged() <signal_DatabaseQuery_orderByDataChanged>`
  * :ref:`Object.completed() <signal_Object_completed>`

Enumerations
++++++++++++

.. hlist::
  :columns: 1

  * :ref:`Error <enum_DatabaseQuery_Error>`



Properties
**********


.. _property_DatabaseQuery_error:

.. _signal_DatabaseQuery_errorChanged:

.. index::
   single: error

error
+++++

This property holds the most recently occurred error or :ref:`DatabaseQuery.NoError <enumitem_DatabaseQuery_NoError>` if no error occurred. If the same error occurs multiple times this property does not change. Use the :ref:`errorOccurred() <signal_DatabaseQuery_errorOccurred>` signal to detect multiple occurrences of the same error.

:**› Type**: :ref:`Error <enum_DatabaseQuery_Error>`
:**› Signal**: errorChanged()
:**› Attributes**: Readonly


.. _property_DatabaseQuery_errorString:

.. _signal_DatabaseQuery_errorStringChanged:

.. index::
   single: errorString

errorString
+++++++++++

This property holds the current human readable error string corresponding to the current value in the :ref:`error <property_DatabaseQuery_error>` property. It may include additional information such as failure reasons or locations.

:**› Type**: String
:**› Signal**: errorStringChanged()
:**› Attributes**: Readonly


.. _property_DatabaseQuery_filters:

.. _signal_DatabaseQuery_filtersChanged:

.. index::
   single: filters

filters
+++++++

This property holds a list of filters which restrict the result. Internally this list is transformed to a SQL-WHERE clause.

:**› Type**: :ref:`List <object_List>`\<:ref:`DatabaseQueryFilter <object_DatabaseQueryFilter>`>
:**› Signal**: filtersChanged()
:**› Attributes**: Readonly


.. _property_DatabaseQuery_limitLength:

.. _signal_DatabaseQuery_limitLengthChanged:

.. index::
   single: limitLength

limitLength
+++++++++++

This property holds the lenght of the limit to restrict the number of rows returned. This is the maximum number of rows returned.

:**› Type**: SignedInteger
:**› Default**: ``-1``
:**› Signal**: limitLengthChanged()
:**› Attributes**: Writable


.. _property_DatabaseQuery_limitPos:

.. _signal_DatabaseQuery_limitPosChanged:

.. index::
   single: limitPos

limitPos
++++++++

This property holds the start of a limit to restrict the number of rows returned. This can be seen as a offset.

:**› Type**: SignedInteger
:**› Default**: ``0``
:**› Signal**: limitPosChanged()
:**› Attributes**: Writable


.. _property_DatabaseQuery_objects:

.. _signal_DatabaseQuery_objectsChanged:

.. index::
   single: objects

objects
+++++++

This property holds the list of objects which column should be queried. The order is kept.

:**› Type**: :ref:`List <object_List>`\<:ref:`DataObject <object_DataObject>`>
:**› Signal**: objectsChanged()
:**› Attributes**: Readonly


.. _property_DatabaseQuery_orderBy:

.. _signal_DatabaseQuery_orderByChanged:

.. index::
   single: orderBy

orderBy
+++++++

This property holds a list of columns to use for ordering (sorting) the rows. Only ``ascending`` ordering is done. See also :ref:`orderByNames <property_DatabaseQuery_orderByNames>`.

:**› Type**: :ref:`List <object_List>`\<:ref:`DataObject <object_DataObject>`>
:**› Signal**: orderByChanged()
:**› Attributes**: Readonly


.. _property_DatabaseQuery_orderByNames:

.. _signal_DatabaseQuery_orderByNamesChanged:

.. index::
   single: orderByNames

orderByNames
++++++++++++

This property holds a string list of column ids to use for ordering (sorting) the rows. This will have no effect if :ref:`orderBy <property_DatabaseQuery_orderBy>` is set. The negative sign in front of an id indicates ``descending`` order. See also the example at the bottom.

This property was introduced in InCore 2.4.

:**› Type**: StringList
:**› Signal**: orderByNamesChanged()
:**› Attributes**: Writable


.. _property_DatabaseQuery_results:

.. _signal_DatabaseQuery_resultsChanged:

.. index::
   single: results

results
+++++++

This property holds the results of the query. This will include all :ref:`objects <property_DatabaseQuery_objects>` as columns. For example the column ``id`` of the second row can be read with ``results[1].id``. Pay attention to the usage of results and try to use local variables because each reference will execute the query.

:**› Type**: List
:**› Signal**: resultsChanged()
:**› Attributes**: Readonly, Requires :ref:`Polling <object_Polling>`


.. _property_DatabaseQuery_table:

.. _signal_DatabaseQuery_tableChanged:

.. index::
   single: table

table
+++++

This property holds the database table which should be queried. Can be left blank if the parent is a :ref:`DatabaseTable <object_DatabaseTable>`.

:**› Type**: :ref:`DatabaseTable <object_DatabaseTable>`
:**› Signal**: tableChanged()
:**› Attributes**: Writable, Optional

Methods
*******


.. _method_DatabaseQuery_execute:

.. index::
   single: execute

execute()
+++++++++

This method executes the query and updates :ref:`results <property_DatabaseQuery_results>`. On success, ``true`` is returned, otherwise ``false``.

:**› Returns**: Boolean



.. _method_DatabaseQuery_pollResults:

.. index::
   single: pollResults

pollResults()
+++++++++++++

This method polls the :ref:`results <property_DatabaseQuery_results>` property. It is called automatically when using a :ref:`Polling <object_Polling>` property modifier on this property and usually does not have to be called manually.


Signals
*******


.. _signal_DatabaseQuery_errorOccurred:

.. index::
   single: errorOccurred

errorOccurred()
+++++++++++++++

This signal is emitted whenever an error has occurred, regardless of whether the :ref:`error <property_DatabaseQuery_error>` property has changed or not. In contrast to the change notification signal of the :ref:`error <property_DatabaseQuery_error>` property this signal is also emitted several times if a certain error occurs several times in succession.



.. _signal_DatabaseQuery_filtersDataChanged:

.. index::
   single: filtersDataChanged

filtersDataChanged(SignedInteger index)
+++++++++++++++++++++++++++++++++++++++

This signal is emitted whenever the :ref:`List.dataChanged() <signal_List_dataChanged>` signal is emitted, i.e. the item at ``index`` in the :ref:`filters <property_DatabaseQuery_filters>` list itself emitted the dataChanged() signal.



.. _signal_DatabaseQuery_objectsDataChanged:

.. index::
   single: objectsDataChanged

objectsDataChanged(SignedInteger index)
+++++++++++++++++++++++++++++++++++++++

This signal is emitted whenever the :ref:`List.dataChanged() <signal_List_dataChanged>` signal is emitted, i.e. the item at ``index`` in the :ref:`objects <property_DatabaseQuery_objects>` list itself emitted the dataChanged() signal.



.. _signal_DatabaseQuery_orderByDataChanged:

.. index::
   single: orderByDataChanged

orderByDataChanged(SignedInteger index)
+++++++++++++++++++++++++++++++++++++++

This signal is emitted whenever the :ref:`List.dataChanged() <signal_List_dataChanged>` signal is emitted, i.e. the item at ``index`` in the :ref:`orderBy <property_DatabaseQuery_orderBy>` list itself emitted the dataChanged() signal.


Enumerations
************


.. _enum_DatabaseQuery_Error:

.. index::
   single: Error

Error
+++++

This enumeration describes all errors which can occur in DatabaseQuery objects. The most recently occurred error is stored in the :ref:`error <property_DatabaseQuery_error>` property.

.. index::
   single: DatabaseQuery.NoError
.. index::
   single: DatabaseQuery.InvalidQueryNameError
.. index::
   single: DatabaseQuery.InvalidTableError
.. index::
   single: DatabaseQuery.TableOpenError
.. list-table::
  :widths: auto
  :header-rows: 1

  * - Name
    - Value
    - Description

      .. _enumitem_DatabaseQuery_NoError:
  * - ``DatabaseQuery.NoError``
    - ``0``
    - No error occurred or was detected.

      .. _enumitem_DatabaseQuery_InvalidQueryNameError:
  * - ``DatabaseQuery.InvalidQueryNameError``
    - ``1``
    - Empty or invalid table name.

      .. _enumitem_DatabaseQuery_InvalidTableError:
  * - ``DatabaseQuery.InvalidTableError``
    - ``2``
    - Table property not set or parent is not a table.

      .. _enumitem_DatabaseQuery_TableOpenError:
  * - ``DatabaseQuery.TableOpenError``
    - ``3``
    - Table property not set or parent is not a table.

Example
*******
See :ref:`DatabaseTable example <example_DatabaseTable>` on how to use DatabaseQuery.
