
.. _object_MqttSubscription:


:index:`MqttSubscription`
-------------------------

Description
***********

The MqttSubscription object manages subscriptions of one or multiple MQTT :ref:`topics <property_MqttSubscription_topics>` published by another instance on the MQTT broker. Unless disabled explicitely via the :ref:`autoSubscribe <property_MqttSubscription_autoSubscribe>` property all topics are subscribed automatically.

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
  * :ref:`Object.fromJson() <method_Object_fromJson>`
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

  * :ref:`Error <enum_MqttSubscription_Error>`
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


Enumerations
************


.. _enum_MqttSubscription_Error:

.. index::
   single: Error

Error
+++++

This enumeration describes all errors which can occur in MqttAbstractSubscription objects. The most recently occurred error is stored in the :ref:`error <property_MqttSubscription_error>` property.

.. index::
   single: MqttSubscription.NoError
.. index::
   single: MqttSubscription.InvalidClient
.. list-table::
  :widths: auto
  :header-rows: 1

  * - Name
    - Value
    - Description

      .. _enumitem_MqttSubscription_NoError:
  * - ``MqttSubscription.NoError``
    - ``0``
    - No error occurred or was detected.

      .. _enumitem_MqttSubscription_InvalidClient:
  * - ``MqttSubscription.InvalidClient``
    - ``1``
    - Parent object is not an MqttClient.


.. _example_MqttSubscription:


Example
*******

.. code-block:: qml

    import InCore.Foundation 2.3
    import InCore.Mqtt 2.3
    
    Application {
        MqttClient {
            clientId: "MqttSubscriptionExample"
            hostname: "mqtt.inhub.de"
    
            MqttSubscription {
                qos: 1
                onSubscribedChanged: console.log("Subscribed to topics")
    
                MqttTopic {
                    name: "inhub/address"
                    onDataChanged: console.log("Address changed to", data)
                }
    
                MqttTopic {
                    name: "inhub/customerCount"
                    dataType: MqttTopic.UnsignedInteger
                    onDataChanged: console.log("Number of customers changed to", data)
                }
    
                MqttTopic {
                    name: "inhub/isGreat"
                    dataType: MqttTopic.Boolean
                    onDataChanged: console.log("isGreat changed to", data)
                }
            }
        }
    }
    