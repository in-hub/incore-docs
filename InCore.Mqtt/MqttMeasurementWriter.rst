
.. _object_MqttMeasurementWriter:


:index:`MqttMeasurementWriter`
------------------------------

Description
***********

The MqttMeasurementWriter object is a special :ref:`MqttPublication <object_MqttPublication>` object which publishes a set of :ref:`Measurement <object_Measurement>` objects in a certain topic structure or data format. The :ref:`Object.objectId <property_Object_objectId>` property of each measurement is used as the corresponding key in the measurements JSON/CBOR array (in :ref:`MqttMeasurementWriter.JsonMap <enumitem_MqttMeasurementWriter_JsonMap>` or :ref:`MqttMeasurementWriter.CborMap <enumitem_MqttMeasurementWriter_CborMap>` mode) or to construct the topic name (in :ref:`MqttMeasurementWriter.TopicTree <enumitem_MqttMeasurementWriter_TopicTree>` mode).

This object was introduced in InCore 2.5.

:**› Inherits**: :ref:`MqttPublication <object_MqttPublication>`

Overview
********

Properties
++++++++++

.. hlist::
  :columns: 3

  * :ref:`bufferDatabase <property_MqttMeasurementWriter_bufferDatabase>`
  * :ref:`container <property_MqttMeasurementWriter_container>`
  * :ref:`fields <property_MqttMeasurementWriter_fields>`
  * :ref:`grouping <property_MqttMeasurementWriter_grouping>`
  * :ref:`measurementsFieldName <property_MqttMeasurementWriter_measurementsFieldName>`
  * :ref:`mode <property_MqttMeasurementWriter_mode>`
  * :ref:`topicBaseName <property_MqttMeasurementWriter_topicBaseName>`
  * :ref:`MqttPublication.autoPublish <property_MqttPublication_autoPublish>`
  * :ref:`MqttPublication.error <property_MqttPublication_error>`
  * :ref:`MqttPublication.errorString <property_MqttPublication_errorString>`
  * :ref:`MqttPublication.qos <property_MqttPublication_qos>`
  * :ref:`MqttPublication.retain <property_MqttPublication_retain>`
  * :ref:`DataObjectWriter.datasetCount <property_DataObjectWriter_datasetCount>`
  * :ref:`DataObjectWriter.objects <property_DataObjectWriter_objects>`
  * :ref:`DataObjectWriter.running <property_DataObjectWriter_running>`
  * :ref:`DataObjectWriter.submitChangedObjectsOnly <property_DataObjectWriter_submitChangedObjectsOnly>`
  * :ref:`DataObjectWriter.submitInterval <property_DataObjectWriter_submitInterval>`
  * :ref:`DataObjectWriter.submitMode <property_DataObjectWriter_submitMode>`
  * :ref:`Object.objectId <property_Object_objectId>`
  * :ref:`Object.parent <property_Object_parent>`

Methods
+++++++

.. hlist::
  :columns: 2

  * :ref:`MqttPublication.publish() <method_MqttPublication_publish>`
  * :ref:`DataObjectWriter.close() <method_DataObjectWriter_close>`
  * :ref:`DataObjectWriter.open() <method_DataObjectWriter_open>`
  * :ref:`DataObjectWriter.submit() <method_DataObjectWriter_submit>`
  * :ref:`DataObjectWriter.sync() <method_DataObjectWriter_sync>`
  * :ref:`DataObjectWriter.truncate() <method_DataObjectWriter_truncate>`
  * :ref:`Object.deserializeProperties() <method_Object_deserializeProperties>`
  * :ref:`Object.fromJson() <method_Object_fromJson>`
  * :ref:`Object.serializeProperties() <method_Object_serializeProperties>`
  * :ref:`Object.toJson() <method_Object_toJson>`

Signals
+++++++

.. hlist::
  :columns: 1

  * :ref:`MqttPublication.errorOccurred() <signal_MqttPublication_errorOccurred>`
  * :ref:`DataObjectWriter.objectsDataChanged() <signal_DataObjectWriter_objectsDataChanged>`
  * :ref:`DataObjectWriter.submitted() <signal_DataObjectWriter_submitted>`
  * :ref:`DataObjectWriter.truncated() <signal_DataObjectWriter_truncated>`
  * :ref:`Object.completed() <signal_Object_completed>`

Enumerations
++++++++++++

.. hlist::
  :columns: 1

  * :ref:`Fields <enum_MqttMeasurementWriter_Fields>`
  * :ref:`Mode <enum_MqttMeasurementWriter_Mode>`
  * :ref:`MqttPublication.Error <enum_MqttPublication_Error>`
  * :ref:`DataObjectWriter.SubmitMode <enum_DataObjectWriter_SubmitMode>`



Properties
**********


.. _property_MqttMeasurementWriter_bufferDatabase:

.. _signal_MqttMeasurementWriter_bufferDatabaseChanged:

.. index::
   single: bufferDatabase

bufferDatabase
++++++++++++++

This property holds the database to which the measurements are written temporarily when :ref:`MeasurementBufferDatabase.buffering <property_MeasurementBufferDatabase_buffering>` is set to ``true`` and the MQTT client is not connected to a broker.

:**› Type**: :ref:`MeasurementBufferDatabase <object_MeasurementBufferDatabase>`
:**› Signal**: bufferDatabaseChanged()
:**› Attributes**: Readonly


.. _property_MqttMeasurementWriter_container:

.. _signal_MqttMeasurementWriter_containerChanged:

.. index::
   single: container

container
+++++++++

This property holds a map with keys/values in which to embed the JSON/CBOR data in the :ref:`measurementsFieldName <property_MqttMeasurementWriter_measurementsFieldName>` field. This allows publish additional metadata such as the device name or location. If empty, the string representation of the JSON/CBOR data is published directly.

:**› Type**: Map
:**› Signal**: containerChanged()
:**› Attributes**: Writable


.. _property_MqttMeasurementWriter_fields:

.. _signal_MqttMeasurementWriter_fieldsChanged:

.. index::
   single: fields

fields
++++++

This property holds a combination of :ref:`MqttMeasurementWriter.Field <enum_MqttMeasurementWriter_Field>` flags specifying which properties of each :ref:`Measurement <object_Measurement>` to publish.

:**› Type**: :ref:`Fields <enum_MqttMeasurementWriter_Fields>`
:**› Default**: \enumitem{MqttMeasurementWriter::Field::}
:**› Signal**: fieldsChanged()
:**› Attributes**: Writable


.. _property_MqttMeasurementWriter_grouping:

.. _signal_MqttMeasurementWriter_groupingChanged:

.. index::
   single: grouping

grouping
++++++++

This property holds whether an additional hierarchy level for measurement groups should be used. When enabled, the :ref:`Object.objectId <property_Object_objectId>`s of all :ref:`MeasurementGroup <object_MeasurementGroup>` associated with the :ref:`objects <property_MqttMeasurementWriter_objects>` is added to :ref:`topicBaseName <property_MqttMeasurementWriter_topicBaseName>` or inserted in the JSON/CBOR map.

:**› Type**: Boolean
:**› Default**: ``false``
:**› Signal**: groupingChanged()
:**› Attributes**: Writable


.. _property_MqttMeasurementWriter_measurementsFieldName:

.. _signal_MqttMeasurementWriter_measurementsFieldNameChanged:

.. index::
   single: measurementsFieldName

measurementsFieldName
+++++++++++++++++++++

This property holds the name of the field in the :ref:`container <property_MqttMeasurementWriter_container>` map in which to embed the JSON/CBOR-encoded measurements.

:**› Type**: String
:**› Default**: ``measurements``
:**› Signal**: measurementsFieldNameChanged()
:**› Attributes**: Writable


.. _property_MqttMeasurementWriter_mode:

.. _signal_MqttMeasurementWriter_modeChanged:

.. index::
   single: mode

mode
++++

This property holds the mode specifying how the measurements are published.

:**› Type**: :ref:`MqttMeasurementWriter.Mode <enum_MqttMeasurementWriter_Mode>`
:**› Default**: :ref:`MqttMeasurementWriter.JsonMap <enumitem_MqttMeasurementWriter_JsonMap>`
:**› Signal**: modeChanged()
:**› Attributes**: Writable


.. _property_MqttMeasurementWriter_topicBaseName:

.. _signal_MqttMeasurementWriter_topicBaseNameChanged:

.. index::
   single: topicBaseName

topicBaseName
+++++++++++++

This property holds a string which to prepend to the topic name of all publications.

:**› Type**: String
:**› Signal**: topicBaseNameChanged()
:**› Attributes**: Writable

Enumerations
************


.. _enum_MqttMeasurementWriter_Fields:

.. index::
   single: Fields

Fields
++++++

This enumeration describes flags for fields which the writer can publish.

.. index::
   single: MqttMeasurementWriter.Value
.. index::
   single: MqttMeasurementWriter.Timestamp
.. index::
   single: MqttMeasurementWriter.Name
.. index::
   single: MqttMeasurementWriter.Description
.. index::
   single: MqttMeasurementWriter.Unit
.. index::
   single: MqttMeasurementWriter.SiPrefix
.. index::
   single: MqttMeasurementWriter.Decimals
.. index::
   single: MqttMeasurementWriter.Range
.. list-table::
  :widths: auto
  :header-rows: 1

  * - Name
    - Value
    - Description

      .. _enumitem_MqttMeasurementWriter_Value:
  * - ``MqttMeasurementWriter.Value``
    - ``1``
    - publish the :ref:`DataObject.data <property_DataObject_data>` property.

      .. _enumitem_MqttMeasurementWriter_Timestamp:
  * - ``MqttMeasurementWriter.Timestamp``
    - ``2``
    - publish the :ref:`DataObject.timestamp <property_DataObject_timestamp>` property.

      .. _enumitem_MqttMeasurementWriter_Name:
  * - ``MqttMeasurementWriter.Name``
    - ``4``
    - publish the :ref:`DataObject.name <property_DataObject_name>` property.

      .. _enumitem_MqttMeasurementWriter_Description:
  * - ``MqttMeasurementWriter.Description``
    - ``8``
    - publish the :ref:`DataObject.description <property_DataObject_description>` property.

      .. _enumitem_MqttMeasurementWriter_Unit:
  * - ``MqttMeasurementWriter.Unit``
    - ``16``
    - publish the :ref:`Measurement.unit <property_Measurement_unit>` property.

      .. _enumitem_MqttMeasurementWriter_SiPrefix:
  * - ``MqttMeasurementWriter.SiPrefix``
    - ``32``
    - publish the :ref:`Measurement.siPrefix <property_Measurement_siPrefix>` property.

      .. _enumitem_MqttMeasurementWriter_Decimals:
  * - ``MqttMeasurementWriter.Decimals``
    - ``64``
    - publish the :ref:`Measurement.decimals <property_Measurement_decimals>` property.

      .. _enumitem_MqttMeasurementWriter_Range:
  * - ``MqttMeasurementWriter.Range``
    - ``128``
    - publish the :ref:`MeasurementView.range <property_MeasurementView_range>` property.


.. _enum_MqttMeasurementWriter_Mode:

.. index::
   single: Mode

Mode
++++

This enumeration describes all supported modes in which the writer can operate.

.. index::
   single: MqttMeasurementWriter.TopicTree
.. index::
   single: MqttMeasurementWriter.JsonMap
.. index::
   single: MqttMeasurementWriter.CborMap
.. index::
   single: MqttMeasurementWriter.JsonArray
.. index::
   single: MqttMeasurementWriter.CborArray
.. list-table::
  :widths: auto
  :header-rows: 1

  * - Name
    - Value
    - Description

      .. _enumitem_MqttMeasurementWriter_TopicTree:
  * - ``MqttMeasurementWriter.TopicTree``
    - ``0``
    - publish measurements and their properties in subtopics, e.g. ``topicBaseName/myMeasurement/value`` (with :ref:`grouping <property_MqttMeasurementWriter_grouping>` set to ``false``) or ``topicBaseName/myGroup/myMeasurement/value`` (with :ref:`grouping <property_MqttMeasurementWriter_grouping>` set to ``true``).

      .. _enumitem_MqttMeasurementWriter_JsonMap:
  * - ``MqttMeasurementWriter.JsonMap``
    - ``1``
    - publish measurements and their properties as a JSON map.

      .. _enumitem_MqttMeasurementWriter_CborMap:
  * - ``MqttMeasurementWriter.CborMap``
    - ``2``
    - publish measurements and their properties as a CBOR map.

      .. _enumitem_MqttMeasurementWriter_JsonArray:
  * - ``MqttMeasurementWriter.JsonArray``
    - ``3``
    - publish measurements and their properties as a JSON array.

      .. _enumitem_MqttMeasurementWriter_CborArray:
  * - ``MqttMeasurementWriter.CborArray``
    - ``4``
    - publish measurements and their properties as a CBOR array.


.. _example_MqttMeasurementWriter:


Example
*******

.. code-block:: qml

    import InCore.Foundation 2.5
    import InCore.Mqtt 2.5
    
    Application {
    
        ObjectArray {
            id: measurements
            MeasurementGroup {
                objectId: "weather"
                Measurement {
                    objectId: "temperature"
                    name: "Temperature"
                    data: 25
                    dataType: Measurement.Float
                    unit: Measurement.DegreeCelsius
                    property var t: Timer { onTriggered: parent.data += Math.random() - 0.5 }
                }
                Measurement {
                    objectId: "humidity"
                    name: "Relative humidity"
                    data: 65
                    dataType: Measurement.SignedInteger
                    unit: "%"
                    property var t: Timer { onTriggered: parent.data += Math.random() - 0.5 }
                }
            }
        }
    
        MqttClient {
            clientId: "MqttMeasurementWriterExample"
            hostname: "localhost"
    
            MqttMeasurementWriter {
                qos: 1
                retain: true
                topicBaseName: "weather"
                grouping: true
                submitMode: MqttMeasurementWriter.SubmitOnCompleteDataset
                mode: MqttMeasurementWriter.JsonMap
                fields: MqttMeasurementWriter.Timestamp | MqttMeasurementWriter.Value |
                        MqttMeasurementWriter.Name | MqttMeasurementWriter.Unit
                Gather on objects {
                    source: measurements
                    typeFilter: Measurement {}
                }
            }
        }
    }
    