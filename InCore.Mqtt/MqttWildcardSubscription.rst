
.. _object_MqttWildcardSubscription:


:index:`MqttWildcardSubscription`
---------------------------------

Description
***********

The MqttWildcardSubscription object subscribes to an MQTT wildcard topic specified in the :ref:`name <property_MqttWildcardSubscription_name>` property and provides the received data in the :ref:`data <property_MqttWildcardSubscription_data>` property. The names of all received topics are available in the :ref:`topics <property_MqttWildcardSubscription_topics>` property.

The parent object must be of type :ref:`MqttClient <object_MqttClient>`.

This object was introduced in InCore 2.3.

:**› Inherits**: :ref:`MqttAbstractSubscription <object_MqttAbstractSubscription>`

Overview
********

Properties
++++++++++

.. hlist::
  :columns: 2

  * :ref:`data <property_MqttWildcardSubscription_data>`
  * :ref:`dataType <property_MqttWildcardSubscription_dataType>`
  * :ref:`mode <property_MqttWildcardSubscription_mode>`
  * :ref:`name <property_MqttWildcardSubscription_name>`
  * :ref:`topics <property_MqttWildcardSubscription_topics>`
  * :ref:`updateTopics <property_MqttWildcardSubscription_updateTopics>`
  * :ref:`MqttAbstractSubscription.autoSubscribe <property_MqttAbstractSubscription_autoSubscribe>`
  * :ref:`MqttAbstractSubscription.enabled <property_MqttAbstractSubscription_enabled>`
  * :ref:`MqttAbstractSubscription.error <property_MqttAbstractSubscription_error>`
  * :ref:`MqttAbstractSubscription.errorString <property_MqttAbstractSubscription_errorString>`
  * :ref:`MqttAbstractSubscription.qos <property_MqttAbstractSubscription_qos>`
  * :ref:`MqttAbstractSubscription.subscribed <property_MqttAbstractSubscription_subscribed>`
  * :ref:`Object.objectId <property_Object_objectId>`
  * :ref:`Object.parent <property_Object_parent>`

Methods
+++++++

.. hlist::
  :columns: 2

  * :ref:`mapDataObject() <method_MqttWildcardSubscription_mapDataObject>`
  * :ref:`unmapDataObject() <method_MqttWildcardSubscription_unmapDataObject>`
  * :ref:`MqttAbstractSubscription.subscribe() <method_MqttAbstractSubscription_subscribe>`
  * :ref:`MqttAbstractSubscription.unsubscribe() <method_MqttAbstractSubscription_unsubscribe>`
  * :ref:`Object.deserializeProperties() <method_Object_deserializeProperties>`
  * :ref:`Object.fromJson() <method_Object_fromJson>`
  * :ref:`Object.serializeProperties() <method_Object_serializeProperties>`
  * :ref:`Object.toJson() <method_Object_toJson>`

Signals
+++++++

.. hlist::
  :columns: 1

  * :ref:`valueReceived() <signal_MqttWildcardSubscription_valueReceived>`
  * :ref:`MqttAbstractSubscription.errorOccurred() <signal_MqttAbstractSubscription_errorOccurred>`
  * :ref:`Object.completed() <signal_Object_completed>`

Enumerations
++++++++++++

.. hlist::
  :columns: 1

  * :ref:`Mode <enum_MqttWildcardSubscription_Mode>`
  * :ref:`MqttAbstractSubscription.Error <enum_MqttAbstractSubscription_Error>`



Properties
**********


.. _property_MqttWildcardSubscription_data:

.. _signal_MqttWildcardSubscription_dataChanged:

.. index::
   single: data

data
++++

This property holds a map with the data of all topics matching the wildcard topic :ref:`name <property_MqttWildcardSubscription_name>`.

:**› Type**: Map
:**› Signal**: dataChanged()
:**› Attributes**: Readonly


.. _property_MqttWildcardSubscription_dataType:

.. _signal_MqttWildcardSubscription_dataTypeChanged:

.. index::
   single: dataType

dataType
++++++++

This property holds the data type which to convert the payload of incoming messages automatically. If not specified, the payload will not be converted and inserted as raw data in the :ref:`data <property_MqttWildcardSubscription_data>` map or passed as raw data to the :ref:`valueReceived() <signal_MqttWildcardSubscription_valueReceived>` signal.

This property was introduced in InCore 2.4.

:**› Type**: :ref:`DataObject.DataType <enum_DataObject_DataType>`
:**› Default**: :ref:`DataObject.Invalid <enumitem_DataObject_Invalid>`
:**› Signal**: dataTypeChanged()
:**› Attributes**: Writable


.. _property_MqttWildcardSubscription_mode:

.. _signal_MqttWildcardSubscription_modeChanged:

.. index::
   single: mode

mode
++++

This property holds the mode which specifies how to process incoming messages. See the :ref:`MqttWildcardSubscription.Mode <enum_MqttWildcardSubscription_Mode>` enumeration for details.

:**› Type**: :ref:`Mode <enum_MqttWildcardSubscription_Mode>`
:**› Default**: :ref:`MqttWildcardSubscription.UpdateDataMap <enumitem_MqttWildcardSubscription_UpdateDataMap>`
:**› Signal**: modeChanged()
:**› Attributes**: Writable


.. _property_MqttWildcardSubscription_name:

.. _signal_MqttWildcardSubscription_nameChanged:

.. index::
   single: name

name
++++

This property holds the name of the wildcard topic to subscribe.

:**› Type**: String
:**› Signal**: nameChanged()
:**› Attributes**: Writable


.. _property_MqttWildcardSubscription_topics:

.. _signal_MqttWildcardSubscription_topicsChanged:

.. index::
   single: topics

topics
++++++

This property holds a list of names with all received topics matching the wildcard topic :ref:`name <property_MqttWildcardSubscription_name>`.

:**› Type**: StringList
:**› Signal**: topicsChanged()
:**› Attributes**: Readonly


.. _property_MqttWildcardSubscription_updateTopics:

.. _signal_MqttWildcardSubscription_updateTopicsChanged:

.. index::
   single: updateTopics

updateTopics
++++++++++++

This property holds whether to update the :ref:`topics <property_MqttWildcardSubscription_topics>` property on every incoming message. If the topic list is not required, you can set this property to ``false`` to improve performance.

This property was introduced in InCore 2.7.

:**› Type**: Boolean
:**› Default**: ``true``
:**› Signal**: updateTopicsChanged()
:**› Attributes**: Writable

Methods
*******


.. _method_MqttWildcardSubscription_mapDataObject:

.. index::
   single: mapDataObject

mapDataObject(String topicName, :ref:`DataObject <enum_MqttWildcardSubscription_DataObject>` dataObject)
++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

This method registers the given :ref:`DataObject <object_DataObject>` instance to receive value for a certain topic name in the :ref:`DataObject.data <property_DataObject_data>` property directly.

This method was introduced in InCore 2.7.



.. _method_MqttWildcardSubscription_unmapDataObject:

.. index::
   single: unmapDataObject

unmapDataObject(:ref:`DataObject <enum_MqttWildcardSubscription_DataObject>` dataObject)
++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

This method removes the :ref:`DataObject <object_DataObject>` registration for a certain object.

This method was introduced in InCore 2.7.


Signals
*******


.. _signal_MqttWildcardSubscription_valueReceived:

.. index::
   single: valueReceived

valueReceived(String topicName, Variant value)
++++++++++++++++++++++++++++++++++++++++++++++

This signal is emitted whenever a new value has been received and :ref:`mode <property_MqttWildcardSubscription_mode>` is set to :ref:`MqttWildcardSubscription.ReceiveValues <enumitem_MqttWildcardSubscription_ReceiveValues>`. The name of the topic and the actual value are passed.

This signal was introduced in InCore 2.4.


Enumerations
************


.. _enum_MqttWildcardSubscription_Mode:

.. index::
   single: Mode

Mode
++++

This enumeration describes all supported modes for processing incoming messages

This enumeration was introduced in InCore 2.4.

.. index::
   single: MqttWildcardSubscription.UpdateDataMap
.. index::
   single: MqttWildcardSubscription.ReceiveValues
.. index::
   single: MqttWildcardSubscription.WriteToDataOfMappedDataObjects
.. index::
   single: MqttWildcardSubscription.WriteToTimestampOfMappedDataObjects
.. list-table::
  :widths: auto
  :header-rows: 1

  * - Name
    - Value
    - Description

      .. _enumitem_MqttWildcardSubscription_UpdateDataMap:
  * - ``MqttWildcardSubscription.UpdateDataMap``
    - ``0``
    - Update the :ref:`data <property_MqttWildcardSubscription_data>` map property. Use bindings to individual subproperties of the :ref:`data <property_MqttWildcardSubscription_data>` property to use the actual data or react to ``xxxChanged()`` signals (see example).

      .. _enumitem_MqttWildcardSubscription_ReceiveValues:
  * - ``MqttWildcardSubscription.ReceiveValues``
    - ``1``
    - Emits the :ref:`valueReceived() <signal_MqttWildcardSubscription_valueReceived>` signal on every incoming message. In this mode, the :ref:`data <property_MqttWildcardSubscription_data>` map is not updated which can improve performance if you only need to process incoming (possibly converted) data value directly anyway.

      .. _enumitem_MqttWildcardSubscription_WriteToDataOfMappedDataObjects:
  * - ``MqttWildcardSubscription.WriteToDataOfMappedDataObjects``
    - ``2``
    - writes the received value to the :ref:`DataObject.data <property_DataObject_data>` property of the :ref:`DataObject <object_DataObject>` which has been associated with the respective topic name using the :ref:`mapDataObject() <method_MqttWildcardSubscription_mapDataObject>` method.

      .. _enumitem_MqttWildcardSubscription_WriteToTimestampOfMappedDataObjects:
  * - ``MqttWildcardSubscription.WriteToTimestampOfMappedDataObjects``
    - ``3``
    - writes the received value to the :ref:`DataObject.timestamp <property_DataObject_timestamp>` property of the :ref:`DataObject <object_DataObject>` which has been associated with the respective topic name using the :ref:`mapDataObject() <method_MqttWildcardSubscription_mapDataObject>` method.


.. _example_MqttWildcardSubscription:


Example
*******

.. code-block:: qml

    import InCore.Foundation 2.5
    import InCore.Mqtt 2.5
    
    Application {
        MqttClient {
            clientId: "MqttWildcardSubscriptionExample"
            hostname: "localhost"
    
            MqttWildcardSubscription {
                id: allTopics
                name: "#"
                onTopicsChanged: console.log("Names of all published topics:", topics)
                property var counter: topics.includes("incore/foo/counter") ? parseInt(data.incore.foo.counter) : 0
                onCounterChanged: console.log("Counter:", counter)
            }
            MqttWildcardSubscription {
                name: "incore/+/date"
                dataType: MqttTopic.DateTime
                mode: MqttWildcardSubscription.ReceiveValues
                onValueReceived: console.log("Date:", value)
            }
    
            MqttWildcardSubscription {
                id: measurements
                dataType: MqttTopic.Float
                name: "measurements/#"
            }
        }
    
        ObjectArray {
            Repeater on objects {
                model: measurements.topics
                Measurement {
                    objectId: modelData
                    data: measurements.data[modelData]
                    onDataChanged: console.log("Measurement value:", objectId, data)
                }
            }
        }
    }
    