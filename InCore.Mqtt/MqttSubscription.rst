
.. _object_MqttSubscription:


:index:`MqttSubscription`
-------------------------

Description
***********

The MqttSubscription object manages subscriptions of one or multiple MQTT :ref:`topics <property_MqttSubscription_topics>` published by another instance on the MQTT broker. Unless disabled explicitely via the :ref:`MqttAbstractSubscription.autoSubscribe <property_MqttAbstractSubscription_autoSubscribe>` property all topics are subscribed automatically.

The parent object must be of type :ref:`MqttClient <object_MqttClient>`.

:**› Inherits**: :ref:`MqttAbstractSubscription <object_MqttAbstractSubscription>`

Overview
********

Properties
++++++++++

.. hlist::
  :columns: 2

  * :ref:`topics <property_MqttSubscription_topics>`
  * :ref:`MqttAbstractSubscription.autoSubscribe <property_MqttAbstractSubscription_autoSubscribe>`
  * :ref:`MqttAbstractSubscription.error <property_MqttAbstractSubscription_error>`
  * :ref:`MqttAbstractSubscription.errorString <property_MqttAbstractSubscription_errorString>`
  * :ref:`MqttAbstractSubscription.qos <property_MqttAbstractSubscription_qos>`
  * :ref:`MqttAbstractSubscription.subscribed <property_MqttAbstractSubscription_subscribed>`
  * :ref:`Object.objectId <property_Object_objectId>`
  * :ref:`Object.parent <property_Object_parent>`

Methods
+++++++

.. hlist::
  :columns: 1

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

  * :ref:`topicsDataChanged() <signal_MqttSubscription_topicsDataChanged>`
  * :ref:`MqttAbstractSubscription.errorOccurred() <signal_MqttAbstractSubscription_errorOccurred>`
  * :ref:`Object.completed() <signal_Object_completed>`

Enumerations
++++++++++++

.. hlist::
  :columns: 1

  * :ref:`MqttAbstractSubscription.Error <enum_MqttAbstractSubscription_Error>`



Properties
**********


.. _property_MqttSubscription_topics:

.. _signal_MqttSubscription_topicsChanged:

.. index::
   single: topics

topics
++++++

This property holds a list of MQTT topics to subscribe.

:**› Type**: :ref:`List <object_List>`\<:ref:`MqttTopic <object_MqttTopic>`>
:**› Signal**: topicsChanged()
:**› Attributes**: Readonly

Signals
*******


.. _signal_MqttSubscription_topicsDataChanged:

.. index::
   single: topicsDataChanged

topicsDataChanged(SignedInteger index)
++++++++++++++++++++++++++++++++++++++

This signal is emitted whenever the :ref:`List.dataChanged() <signal_List_dataChanged>` signal is emitted, i.e. the item at ``index`` in the :ref:`topics <property_MqttSubscription_topics>` list itself emitted the dataChanged() signal.



.. _example_MqttSubscription:


Example
*******

.. code-block:: qml

    import InCore.Foundation 2.5
    import InCore.Mqtt 2.5
    
    Application {
        MqttClient {
            clientId: "MqttSubscriptionExample"
            hostname: "localhost"
    
            MqttSubscription {
                qos: 1
                onSubscribedChanged: console.log("Subscribed to topics")
    
                MqttTopic {
                    name: "incore/temperature"
                    dataType: MqttTopic.Float
                    onDataChanged: console.log("Device temperature changed to", data)
                }
    
                MqttTopic {
                    name: "incore/foo/counter"
                    onDataChanged: console.log("Counter changed to", data)
                }
    
                MqttTopic {
                    name: "incore/bar/date"
                    dataType: DataObject.DateTime
                    onDataChanged: console.log("Date changed to", data)
                }
    
                MqttTopic {
                    name: "incore/array"
                    dataType: DataObject.StringList
                    onDataChanged: console.log("Array data:", data)
                }
    
            }
        }
    }
    