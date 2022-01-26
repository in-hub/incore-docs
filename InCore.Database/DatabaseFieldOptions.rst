
.. _object_DatabaseFieldOptions:


:index:`DatabaseFieldOptions`
-----------------------------

Description
***********

The DatabaseFieldOptions object defines additional options for a database field represented by a :ref:`DataObject <object_DataObject>`. It can be set through attached properties or instantiated as an arbitrarily-named custom property of the corresponding :ref:`DataObject <object_DataObject>`. See the example for details.

This object was introduced in InCore 1.1.

:**› Inherits**: :ref:`Object <object_Object>`

Overview
********

Properties
++++++++++

.. hlist::
  :columns: 2

  * :ref:`autoIncrement <property_DatabaseFieldOptions_autoIncrement>`
  * :ref:`blank <property_DatabaseFieldOptions_blank>`
  * :ref:`dbColumn <property_DatabaseFieldOptions_dbColumn>`
  * :ref:`dbIndex <property_DatabaseFieldOptions_dbIndex>`
  * :ref:`maxLength <property_DatabaseFieldOptions_maxLength>`
  * :ref:`notNull <property_DatabaseFieldOptions_notNull>`
  * :ref:`onDelete <property_DatabaseFieldOptions_onDelete>`
  * :ref:`primaryKey <property_DatabaseFieldOptions_primaryKey>`
  * :ref:`unique <property_DatabaseFieldOptions_unique>`
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

  * :ref:`ForeignKeyConstraint <enum_DatabaseFieldOptions_ForeignKeyConstraint>`



Properties
**********


.. _property_DatabaseFieldOptions_autoIncrement:

.. _signal_DatabaseFieldOptions_autoIncrementChanged:

.. index::
   single: autoIncrement

autoIncrement
+++++++++++++

This property holds whether this field should be marked as auto-increment if this field is the primary key as well.

:**› Type**: Boolean
:**› Default**: ``false``
:**› Signal**: autoIncrementChanged()
:**› Attributes**: Writable


.. _property_DatabaseFieldOptions_blank:

.. _signal_DatabaseFieldOptions_blankChanged:

.. index::
   single: blank

blank
+++++

This property holds whether to allow this field to be empty when inserting a new data row.

:**› Type**: Boolean
:**› Default**: ``false``
:**› Signal**: blankChanged()
:**› Attributes**: Writable


.. _property_DatabaseFieldOptions_dbColumn:

.. _signal_DatabaseFieldOptions_dbColumnChanged:

.. index::
   single: dbColumn

dbColumn
++++++++

This property holds the name of the database column for the field, otherwise per default the object ID is be used.

:**› Type**: String
:**› Signal**: dbColumnChanged()
:**› Attributes**: Writable


.. _property_DatabaseFieldOptions_dbIndex:

.. _signal_DatabaseFieldOptions_dbIndexChanged:

.. index::
   single: dbIndex

dbIndex
+++++++

This property holds whether to create an index on this field.

:**› Type**: Boolean
:**› Default**: ``false``
:**› Signal**: dbIndexChanged()
:**› Attributes**: Writable


.. _property_DatabaseFieldOptions_maxLength:

.. _signal_DatabaseFieldOptions_maxLengthChanged:

.. index::
   single: maxLength

maxLength
+++++++++

This property holds the maximum length of the field used when creating the database table. Leave at ``0`` to disable a maximum length.

:**› Type**: SignedInteger
:**› Default**: ``0``
:**› Signal**: maxLengthChanged()
:**› Attributes**: Writable


.. _property_DatabaseFieldOptions_notNull:

.. _signal_DatabaseFieldOptions_notNullChanged:

.. index::
   single: notNull

notNull
+++++++

This property holds whether to insert empty values or ``NULL`` values if the field value is empty or not specified.

:**› Type**: Boolean
:**› Default**: ``true``
:**› Signal**: notNullChanged()
:**› Attributes**: Writable


.. _property_DatabaseFieldOptions_onDelete:

.. _signal_DatabaseFieldOptions_onDeleteChanged:

.. index::
   single: onDelete

onDelete
++++++++

This property holds the foreign key constraint to create on this field. See `SQL Server Foreign Key Update and Delete Rules <https://koukia.ca/sql-server-foreign-key-update-and-delete-rules-556cf09117fe>`_ and the :ref:`ForeignKeyConstraint <enum_DatabaseFieldOptions_ForeignKeyConstraint>` enumeration for details.

:**› Type**: :ref:`ForeignKeyConstraint <enum_DatabaseFieldOptions_ForeignKeyConstraint>`
:**› Default**: :ref:`DatabaseFieldOptions.NoAction <enumitem_DatabaseFieldOptions_NoAction>`
:**› Signal**: onDeleteChanged()
:**› Attributes**: Writable


.. _property_DatabaseFieldOptions_primaryKey:

.. _signal_DatabaseFieldOptions_primaryKeyChanged:

.. index::
   single: primaryKey

primaryKey
++++++++++

This property holds whether to use this field as the primary key. If no primary key is explicitly defined, an auto-increment integer field will be added.

:**› Type**: Boolean
:**› Default**: ``false``
:**› Signal**: primaryKeyChanged()
:**› Attributes**: Writable


.. _property_DatabaseFieldOptions_unique:

.. _signal_DatabaseFieldOptions_uniqueChanged:

.. index::
   single: unique

unique
++++++

This property holds whether this field must be unique throughout the table.

:**› Type**: Boolean
:**› Default**: ``false``
:**› Signal**: uniqueChanged()
:**› Attributes**: Writable

Enumerations
************


.. _enum_DatabaseFieldOptions_ForeignKeyConstraint:

.. index::
   single: ForeignKeyConstraint

ForeignKeyConstraint
++++++++++++++++++++

This enumeration describes all possible constraints which can be set for foreign keys.

.. index::
   single: DatabaseFieldOptions.NoAction
.. index::
   single: DatabaseFieldOptions.Restrict
.. index::
   single: DatabaseFieldOptions.Cascade
.. index::
   single: DatabaseFieldOptions.SetNull
.. list-table::
  :widths: auto
  :header-rows: 1

  * - Name
    - Value
    - Description

      .. _enumitem_DatabaseFieldOptions_NoAction:
  * - ``DatabaseFieldOptions.NoAction``
    - ``0``
    - No constraint will be set.

      .. _enumitem_DatabaseFieldOptions_Restrict:
  * - ``DatabaseFieldOptions.Restrict``
    - ``1``
    - Operation not allowed if it would alter the integrity of the database.

      .. _enumitem_DatabaseFieldOptions_Cascade:
  * - ``DatabaseFieldOptions.Cascade``
    - ``2``
    - The change is allowed and propagates on the child table. For example, if a parent row is deleted, the child row is also deleted; if a parent row's ID changes, the child row's ID will also change.

      .. _enumitem_DatabaseFieldOptions_SetNull:
  * - ``DatabaseFieldOptions.SetNull``
    - ``3``
    - The change is allowed and the child row's foreign key columns are set to ``NULL``. .


.. _example_DatabaseFieldOptions:


Example
*******

.. code-block:: qml

    import InCore.Foundation 2.5
    import InCore.Database 2.5
    
    Application {
    
        LocalDatabase {
            id: exampleDatabase
    
            DatabaseTable {
                id: messages
    
                DateTime {
                    id: date
                    DatabaseFieldOptions.dbIndex: true
                }
                DataObject {
                    id: text
                    dataType: DataObject.String
                    data: "<default message>"
                    property var options : DatabaseFieldOptions { maxLength: 127; notNull: true }
                }
            }
        }
    
        onCompleted: messages.submit()
    }
    