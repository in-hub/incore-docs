
.. _object_Serializer:


:index:`Serializer`
-------------------

Description
***********

The Serializer object can be used to serialize properties of the :ref:`source <property_Serializer_source>` object. This can be used to replicate a object in a variant map or human readable in a JSON format. 

.. note:: Be carefully when :ref:`mode <property_Serializer_mode>` is set to :ref:`Serializer.SerializeOnChange <enumitem_Serializer_SerializeOnChange>`. This can update :ref:`data <property_Serializer_data>` multiple times. For example updating the :ref:`data property of an DataObject <property_DataObject_data>` will also update its timestamp and hence serialize twice. This is also noted in the example at the bottom. If this behaviour is a problem for your application use :ref:`Serializer.SerializeManually <enumitem_Serializer_SerializeManually>` and connect :ref:`update() <method_Serializer_update>` to a unique signal.

:**› Inherits**: :ref:`Object <object_Object>`

Overview
********

Properties
++++++++++

.. hlist::
  :columns: 2

  * :ref:`data <property_Serializer_data>`
  * :ref:`excludedProperties <property_Serializer_excludedProperties>`
  * :ref:`format <property_Serializer_format>`
  * :ref:`interval <property_Serializer_interval>`
  * :ref:`mode <property_Serializer_mode>`
  * :ref:`source <property_Serializer_source>`
  * :ref:`Object.objectId <property_Object_objectId>`
  * :ref:`Object.parent <property_Object_parent>`

Methods
+++++++

.. hlist::
  :columns: 1

  * :ref:`update() <method_Serializer_update>`
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

  * :ref:`Format <enum_Serializer_Format>`
  * :ref:`Mode <enum_Serializer_Mode>`



Properties
**********


.. _property_Serializer_data:

.. _signal_Serializer_dataChanged:

.. index::
   single: data

data
++++

This property holds the output of the serialization.

:**› Type**: Variant
:**› Signal**: dataChanged()
:**› Attributes**: Writable


.. _property_Serializer_excludedProperties:

.. _signal_Serializer_excludedPropertiesChanged:

.. index::
   single: excludedProperties

excludedProperties
++++++++++++++++++

This property holds a list of source property names as strings which should not be serialized.

:**› Type**: StringList
:**› Signal**: excludedPropertiesChanged()
:**› Attributes**: Writable


.. _property_Serializer_format:

.. _signal_Serializer_formatChanged:

.. index::
   single: format

format
++++++

This property holds the format which is used for the serialization.

:**› Type**: :ref:`Format <enum_Serializer_Format>`
:**› Default**: :ref:`Serializer.CompactJsonString <enumitem_Serializer_CompactJsonString>`
:**› Signal**: formatChanged()
:**› Attributes**: Writable


.. _property_Serializer_interval:

.. _signal_Serializer_intervalChanged:

.. index::
   single: interval

interval
++++++++

This property holds the interval of the periodically serialization. This property does not have a effect when :ref:`mode <property_Serializer_mode>` is not set to :ref:`Serializer.SerializePeriodically <enumitem_Serializer_SerializePeriodically>`.

:**› Type**: SignedInteger
:**› Default**: ``0``
:**› Signal**: intervalChanged()
:**› Attributes**: Writable


.. _property_Serializer_mode:

.. _signal_Serializer_modeChanged:

.. index::
   single: mode

mode
++++

This property holds the mode which defined the moment when the source should be serialized.

:**› Type**: :ref:`Mode <enum_Serializer_Mode>`
:**› Default**: :ref:`Serializer.SerializeManually <enumitem_Serializer_SerializeManually>`
:**› Signal**: modeChanged()
:**› Attributes**: Writable


.. _property_Serializer_source:

.. _signal_Serializer_sourceChanged:

.. index::
   single: source

source
++++++

This property holds the object which should be serialized.

:**› Type**: :ref:`Object <object_Object>`
:**› Signal**: sourceChanged()
:**› Attributes**: Writable

Methods
*******


.. _method_Serializer_update:

.. index::
   single: update

update()
++++++++

This method updates :ref:`data <property_Serializer_data>` with the serialized duplicate of :ref:`source <property_Serializer_source>`.


Enumerations
************


.. _enum_Serializer_Format:

.. index::
   single: Format

Format
++++++

This enumeration describes which format should be used to output the serialized data.

.. index::
   single: Serializer.IndentedJsonString
.. index::
   single: Serializer.CompactJsonString
.. index::
   single: Serializer.Native
.. list-table::
  :widths: auto
  :header-rows: 1

  * - Name
    - Value
    - Description

      .. _enumitem_Serializer_IndentedJsonString:
  * - ``Serializer.IndentedJsonString``
    - ``0``
    - defines human readable output with indention and line breaks after each key value pair.

      .. _enumitem_Serializer_CompactJsonString:
  * - ``Serializer.CompactJsonString``
    - ``1``
    - defines human readable output in one line without spaces.

      .. _enumitem_Serializer_Native:
  * - ``Serializer.Native``
    - ``2``
    - the :ref:`data <property_Serializer_data>` is left unformatted as a map.


.. _enum_Serializer_Mode:

.. index::
   single: Mode

Mode
++++

This enumeration describes all available modes when the :ref:`source <property_Serializer_source>` object should be serialized.

.. index::
   single: Serializer.SerializeManually
.. index::
   single: Serializer.SerializePeriodically
.. index::
   single: Serializer.SerializeOnChange
.. list-table::
  :widths: auto
  :header-rows: 1

  * - Name
    - Value
    - Description

      .. _enumitem_Serializer_SerializeManually:
  * - ``Serializer.SerializeManually``
    - ``0``
    - serialize only when :ref:`update() <method_Serializer_update>` is called.

      .. _enumitem_Serializer_SerializePeriodically:
  * - ``Serializer.SerializePeriodically``
    - ``1``
    - serialize periodically with the given :ref:`interval <property_Serializer_interval>`.

      .. _enumitem_Serializer_SerializeOnChange:
  * - ``Serializer.SerializeOnChange``
    - ``2``
    - serialize properties whenever a property was changed.


.. _example_Serializer:


Example
*******

.. code-block:: qml

    import InCore.Foundation 2.5
    
    Application {
    
        // counts uptime in seconds
        Counter {
            // default interval is 1 s
            id: counter
            increment: 1
            startValue: 0
        }
    
        // measurement to display uptime
        MeasurementGroup {
            id: measurementGroup
            Measurement {
                id: measurement
                data: counter.value
                name: "uptime"
            }
        }
    
        // pack data to a string
        Serializer {
            source: measurementGroup
            mode: Serializer.SerializeOnChange
            format: Serializer.CompactJsonString
            excludedProperties: ["displayString", "siPrefix"]
            onDataChanged: console.log( "serialized data changed", data )
        }
    }
    