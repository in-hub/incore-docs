
.. _object_DatabaseQueryWhere:


:index:`DatabaseQueryWhere`
---------------------------

Description
***********

The DatabaseQueryWhere object represents a condition used in :ref:`DatabaseQueryFilter <object_DatabaseQueryFilter>` objects. It allows modelling the SQL statement ``WHERE`` in a declarative manner.

:**› Inherits**: :ref:`Object <object_Object>`

Overview
********

Properties
++++++++++

.. hlist::
  :columns: 1

  * :ref:`key <property_DatabaseQueryWhere_key>`
  * :ref:`operation <property_DatabaseQueryWhere_operation>`
  * :ref:`value <property_DatabaseQueryWhere_value>`
  * :ref:`Object.objectId <property_Object_objectId>`
  * :ref:`Object.parent <property_Object_parent>`

Methods
+++++++

.. hlist::
  :columns: 1

  * :ref:`Object.deserializeProperties() <method_Object_deserializeProperties>`
  * :ref:`Object.fromJson() <method_Object_fromJson>`
  * :ref:`Object.serializeProperties() <method_Object_serializeProperties>`
  * :ref:`Object.toJson() <method_Object_toJson>`

Signals
+++++++

.. hlist::
  :columns: 1

  * :ref:`Object.completed() <signal_Object_completed>`

Enumerations
++++++++++++

.. hlist::
  :columns: 1

  * :ref:`Operation <enum_DatabaseQueryWhere_Operation>`



Properties
**********


.. _property_DatabaseQueryWhere_key:

.. _signal_DatabaseQueryWhere_keyChanged:

.. index::
   single: key

key
+++

This property holds a reference to a :ref:`DataObject <object_DataObject>` object representing a column in the database. The values of this column are compared with :ref:`value <property_DatabaseQueryWhere_value>` as specified in the :ref:`operation <property_DatabaseQueryWhere_operation>` property.

:**› Type**: :ref:`DataObject <object_DataObject>`
:**› Signal**: keyChanged()
:**› Attributes**: Writable


.. _property_DatabaseQueryWhere_operation:

.. _signal_DatabaseQueryWhere_operationChanged:

.. index::
   single: operation

operation
+++++++++

This property holds the operation which specifies how to compare values in a database column (specified by :ref:`key <property_DatabaseQueryWhere_key>`) with the value given in the :ref:`value <property_DatabaseQueryWhere_value>` property.

:**› Type**: :ref:`Operation <enum_DatabaseQueryWhere_Operation>`
:**› Default**: :ref:`DatabaseQueryWhere.None <enumitem_DatabaseQueryWhere_None>`
:**› Signal**: operationChanged()
:**› Attributes**: Writable


.. _property_DatabaseQueryWhere_value:

.. _signal_DatabaseQueryWhere_valueChanged:

.. index::
   single: value

value
+++++

This property holds the value to compare with the values in a database column. It should be of the same type as the database column.

:**› Type**: Variant
:**› Signal**: valueChanged()
:**› Attributes**: Writable

Enumerations
************


.. _enum_DatabaseQueryWhere_Operation:

.. index::
   single: Operation

Operation
+++++++++

This enumeration describes all supported comparison operations on a database column value.

.. index::
   single: DatabaseQueryWhere.None
.. index::
   single: DatabaseQueryWhere.Equals
.. index::
   single: DatabaseQueryWhere.NotEquals
.. index::
   single: DatabaseQueryWhere.GreaterThan
.. index::
   single: DatabaseQueryWhere.LessThan
.. index::
   single: DatabaseQueryWhere.GreaterOrEquals
.. index::
   single: DatabaseQueryWhere.LessOrEquals
.. index::
   single: DatabaseQueryWhere.StartsWith
.. index::
   single: DatabaseQueryWhere.EndsWith
.. index::
   single: DatabaseQueryWhere.Contains
.. index::
   single: DatabaseQueryWhere.IsIn
.. index::
   single: DatabaseQueryWhere.IsNull
.. index::
   single: DatabaseQueryWhere.IEquals
.. index::
   single: DatabaseQueryWhere.INotEquals
.. index::
   single: DatabaseQueryWhere.IStartsWith
.. index::
   single: DatabaseQueryWhere.IEndsWith
.. index::
   single: DatabaseQueryWhere.IContains
.. list-table::
  :widths: auto
  :header-rows: 1

  * - Name
    - Value
    - Description

      .. _enumitem_DatabaseQueryWhere_None:
  * - ``DatabaseQueryWhere.None``
    - ``0``
    - Matches always.

      .. _enumitem_DatabaseQueryWhere_Equals:
  * - ``DatabaseQueryWhere.Equals``
    - ``1``
    - Matches if the column value is equal to the given value.

      .. _enumitem_DatabaseQueryWhere_NotEquals:
  * - ``DatabaseQueryWhere.NotEquals``
    - ``2``
    - Matches if the column value is not equal to the given value.

      .. _enumitem_DatabaseQueryWhere_GreaterThan:
  * - ``DatabaseQueryWhere.GreaterThan``
    - ``3``
    - Matches if the column value is greater than the given value.

      .. _enumitem_DatabaseQueryWhere_LessThan:
  * - ``DatabaseQueryWhere.LessThan``
    - ``4``
    - Matches if the column value is less than the given value.

      .. _enumitem_DatabaseQueryWhere_GreaterOrEquals:
  * - ``DatabaseQueryWhere.GreaterOrEquals``
    - ``5``
    - Matches if the column value is greater or equal to the given value.

      .. _enumitem_DatabaseQueryWhere_LessOrEquals:
  * - ``DatabaseQueryWhere.LessOrEquals``
    - ``6``
    - Matches if the column value is less or equal to the given value.

      .. _enumitem_DatabaseQueryWhere_StartsWith:
  * - ``DatabaseQueryWhere.StartsWith``
    - ``7``
    - Matches if the column value starts with the given value (strings only).

      .. _enumitem_DatabaseQueryWhere_EndsWith:
  * - ``DatabaseQueryWhere.EndsWith``
    - ``8``
    - Matches if the column value ends with the given value (strings only).

      .. _enumitem_DatabaseQueryWhere_Contains:
  * - ``DatabaseQueryWhere.Contains``
    - ``9``
    - Matches if the column value contains the given value (strings only).

      .. _enumitem_DatabaseQueryWhere_IsIn:
  * - ``DatabaseQueryWhere.IsIn``
    - ``10``
    - Matches if the column value is one of the given values.

      .. _enumitem_DatabaseQueryWhere_IsNull:
  * - ``DatabaseQueryWhere.IsNull``
    - ``11``
    - Matches if the column value is null.

      .. _enumitem_DatabaseQueryWhere_IEquals:
  * - ``DatabaseQueryWhere.IEquals``
    - ``12``
    - Matches if the column value is equal to the given value (case-insensitive).

      .. _enumitem_DatabaseQueryWhere_INotEquals:
  * - ``DatabaseQueryWhere.INotEquals``
    - ``13``
    - Matches if the column value is not equal to the given value (case-insensitive).

      .. _enumitem_DatabaseQueryWhere_IStartsWith:
  * - ``DatabaseQueryWhere.IStartsWith``
    - ``14``
    - Matches if the column value starts with the given value (strings only, case-insensitive).

      .. _enumitem_DatabaseQueryWhere_IEndsWith:
  * - ``DatabaseQueryWhere.IEndsWith``
    - ``15``
    - Matches if the column value ends with the given value (strings only, case-insensitive).

      .. _enumitem_DatabaseQueryWhere_IContains:
  * - ``DatabaseQueryWhere.IContains``
    - ``16``
    - Matches if the column value contains the given value (strings only, case-insensitive).

Example
*******
See :ref:`DatabaseQueryFilter example <example_DatabaseQueryFilter>` on how to use DatabaseQueryWhere.
