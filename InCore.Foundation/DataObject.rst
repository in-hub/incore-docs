
.. _object_DataObject:


:index:`DataObject`
-------------------

Description
***********

The DataObject object provides common properties and metadata for all kinds of objects storing data.

:**› Inherits**: :ref:`Object <object_Object>`
:**› Inherited by**: :ref:`ConfigurationItem <object_ConfigurationItem>`, :ref:`DateTime <object_DateTime>`, :ref:`Event <object_Event>`, :ref:`Measurement <object_Measurement>`

Overview
********

Properties
++++++++++

.. hlist::
  :columns: 2

  * :ref:`data <property_DataObject_data>`
  * :ref:`dataType <property_DataObject_dataType>`
  * :ref:`description <property_DataObject_description>`
  * :ref:`name <property_DataObject_name>`
  * :ref:`timestamp <property_DataObject_timestamp>`
  * :ref:`uuid <property_DataObject_uuid>`
  * :ref:`view <property_DataObject_view>`
  * :ref:`Object.objectId <property_Object_objectId>`
  * :ref:`Object.parent <property_Object_parent>`

Methods
+++++++

.. hlist::
  :columns: 1

  * :ref:`touch() <method_DataObject_touch>`
  * :ref:`Object.deserializeProperties() <method_Object_deserializeProperties>`
  * :ref:`Object.fromJson() <method_Object_fromJson>`
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

  * :ref:`DataType <enum_DataObject_DataType>`



Properties
**********


.. _property_DataObject_data:

.. _signal_DataObject_dataChanged:

.. index::
   single: data

data
++++

This property holds the actual data represented by the object. It can be of any of the supported data types. Any actual changes to value or type of the value will trigger the :ref:`dataChanged() <signal_DataObject_dataChanged>` signal.

:**› Type**: Variant
:**› Signal**: dataChanged()
:**› Attributes**: Writable


.. _property_DataObject_dataType:

.. _signal_DataObject_dataTypeChanged:

.. index::
   single: dataType

dataType
++++++++

This property can be used to explicitely specify the data type for cases where the :ref:`data <property_DataObject_data>` property is not yet initialized and the default data value has is used instead. This is primarily used for initializing database table structures with correct data types for the columns.

:**› Type**: :ref:`DataType <enum_DataObject_DataType>`
:**› Default**: :ref:`DataObject.Invalid <enumitem_DataObject_Invalid>`
:**› Signal**: dataTypeChanged()
:**› Attributes**: Writable, Optional


.. _property_DataObject_description:

.. _signal_DataObject_descriptionChanged:

.. index::
   single: description

description
+++++++++++

This property holds a description of the data object and may contain an arbitrarily formatted string, usually used for display and user interface purposes.

:**› Type**: String
:**› Signal**: descriptionChanged()
:**› Attributes**: Writable, Optional


.. _property_DataObject_name:

.. _signal_DataObject_nameChanged:

.. index::
   single: name

name
++++

This property holds the name of the data object and may contain an arbitrarily formatted string, usually used for display and user interface purposes.

:**› Type**: String
:**› Signal**: nameChanged()
:**› Attributes**: Writable, Optional


.. _property_DataObject_timestamp:

.. _signal_DataObject_timestampChanged:

.. index::
   single: timestamp

timestamp
+++++++++

This property holds a timestamp in milliseconds of the last data update. The timestamp is updated even if writing the :ref:`data <property_DataObject_data>` property did not actually change it due to identical data. It therefore can be used to retrieve, e.g. the time of the last successful measurement or when an event was fired.

:**› Type**: SignedBigInteger
:**› Signal**: timestampChanged()
:**› Attributes**: Writable


.. _property_DataObject_uuid:

.. _signal_DataObject_uuidChanged:

.. index::
   single: uuid

uuid
++++

This property holds a UUID (Universally Unique Identifier). The UUID can be used for identifying data objects across applications.

:**› Type**: String
:**› Signal**: uuidChanged()
:**› Attributes**: Writable, Optional


.. _property_DataObject_view:

.. _signal_DataObject_viewChanged:

.. index::
   single: view

view
++++

This property holds an optionally attached view for the data object. Views are used for representing and displaying a DataObject in a user-defined frontend. See the documentation of :ref:`DataObjectView <object_DataObjectView>` for details.

:**› Type**: :ref:`DataObjectView <object_DataObjectView>`
:**› Signal**: viewChanged()
:**› Attributes**: Writable, Optional

Methods
*******


.. _method_DataObject_touch:

.. index::
   single: touch

touch()
+++++++

This method updates the timestamp in the :ref:`timestamp <property_DataObject_timestamp>` property. This method is called automatically whenever the :ref:`data <property_DataObject_data>` property is changed.


Enumerations
************


.. _enum_DataObject_DataType:

.. index::
   single: DataType

DataType
++++++++

This enumeration describes all possible types of data which can be represented by the :ref:`data <property_DataObject_data>` property.

.. index::
   single: DataObject.Invalid
.. index::
   single: DataObject.Boolean
.. index::
   single: DataObject.Date
.. index::
   single: DataObject.Time
.. index::
   single: DataObject.DateTime
.. index::
   single: DataObject.Float
.. index::
   single: DataObject.Double
.. index::
   single: DataObject.SignedInteger
.. index::
   single: DataObject.UnsignedInteger
.. index::
   single: DataObject.SignedBigInteger
.. index::
   single: DataObject.UnsignedBigInteger
.. index::
   single: DataObject.String
.. index::
   single: DataObject.StringList
.. index::
   single: DataObject.SignedSmallInteger
.. index::
   single: DataObject.UnsignedSmallInteger
.. list-table::
  :widths: auto
  :header-rows: 1

  * - Name
    - Value
    - Description

      .. _enumitem_DataObject_Invalid:
  * - ``DataObject.Invalid``
    - ``0``
    - An invalid data type used for representing null values.

      .. _enumitem_DataObject_Boolean:
  * - ``DataObject.Boolean``
    - ``1``
    - A boolean which can be ``true`` or ``false``.

      .. _enumitem_DataObject_Date:
  * - ``DataObject.Date``
    - ``2``
    - A date object representing a calendar date without time.

      .. _enumitem_DataObject_Time:
  * - ``DataObject.Time``
    - ``3``
    - A time object representing a relative time without a date.

      .. _enumitem_DataObject_DateTime:
  * - ``DataObject.DateTime``
    - ``4``
    - A date time object representing an absolute date and time.

      .. _enumitem_DataObject_Float:
  * - ``DataObject.Float``
    - ``5``
    - A single precision floating point number.

      .. _enumitem_DataObject_Double:
  * - ``DataObject.Double``
    - ``6``
    - A double precision floating point number.

      .. _enumitem_DataObject_SignedInteger:
  * - ``DataObject.SignedInteger``
    - ``7``
    - A signed 32 bit integer.

      .. _enumitem_DataObject_UnsignedInteger:
  * - ``DataObject.UnsignedInteger``
    - ``8``
    - An unsigned 32 bit integer.

      .. _enumitem_DataObject_SignedBigInteger:
  * - ``DataObject.SignedBigInteger``
    - ``9``
    - A signed 64 bit integer.

      .. _enumitem_DataObject_UnsignedBigInteger:
  * - ``DataObject.UnsignedBigInteger``
    - ``10``
    - An unsigned 64 bit integer.

      .. _enumitem_DataObject_String:
  * - ``DataObject.String``
    - ``11``
    - A variable-length UTF-8 character string.

      .. _enumitem_DataObject_StringList:
  * - ``DataObject.StringList``
    - ``12``
    - A list of variable-length UTF-8 character strings.

      .. _enumitem_DataObject_SignedSmallInteger:
  * - ``DataObject.SignedSmallInteger``
    - ``13``
    - A signed 16 bit integer.

      .. _enumitem_DataObject_UnsignedSmallInteger:
  * - ``DataObject.UnsignedSmallInteger``
    - ``14``
    - An unsigned 16 bit integer.


.. _example_DataObject:


Example
*******

.. code-block:: qml

    import InCore.Foundation 2.0
    
    Application {
    
        DataObject {
            id: testObject
            // name of this object - used for example by DataObjectWriters (e.g. CsvWriter)
            name: "Awesome object"
            description: "This is your awesome object example."
            // data can be of any supported data type but usually it is some numeric value
            data: 42
            // a signed 64 bit integer
            dataType: DataObject.SignedBigInteger
    
            onTimestampChanged: console.log( "data has been changed to", data )
            view: DataObjectView {
                hidden: false // default
                readOnly: true // only a hint for the frontend
                orderIndex: 0 // would appear at first if other widget would be added
                widget: DataObjectView.Slider // show a read only slider
            }
        }
    }
    