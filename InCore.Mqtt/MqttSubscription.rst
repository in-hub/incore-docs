
.. _object_MqttSubscription:


:index:`MqttSubscription`
-------------------------

Description
***********

The MqttSubscription object manages subscriptions of one or multiple MQTT topics published by another instance on the MQTT broker. Unless disabled explicitely via the :ref:`autoSubscribe <property_MqttSubscription_autoSubscribe>` property all topics are subscribed automatically.

The parent object must be of type :ref:`MqttClient <object_MqttClient>`.

:**› Inherits**: :ref:`Object <object_Object>`

Overview
********

Properties
++++++++++

.. hlist::
  :columns: 2

  * :ref:`autoSubscribe <property_MqttSubscription_autoSubscribe>`
  * :ref:`error <property_MqttSubscription_error>`
  * :ref:`errorString <property_MqttSubscription_errorString>`
  * :ref:`qos <property_MqttSubscription_qos>`
  * :ref:`subscribed <property_MqttSubscription_subscribed>`
  * :ref:`topics <property_MqttSubscription_topics>`
  * :ref:`Object.objectId <property_Object_objectId>`
  * :ref:`Object.parent <property_Object_parent>`

Methods
+++++++

.. hlist::
  :columns: 1

  * :ref:`subscribe() <method_MqttSubscription_subscribe>`
  * :ref:`unsubscribe() <method_MqttSubscription_unsubscribe>`
  * :ref:`Object.fromJson() <method_Object_fromJson>`
  * :ref:`Object.toJson() <method_Object_toJson>`

Signals
+++++++

.. hlist::
  :columns: 1

  * :ref:`errorOccurred() <signal_MqttSubscription_errorOccurred>`
  * :ref:`topicsDataChanged() <signal_MqttSubscription_topicsDataChanged>`
  * :ref:`Object.completed() <signal_Object_completed>`

Enumerations
++++++++++++

.. hlist::
  :columns: 1

  * :ref:`Error <enum_MqttSubscription_Error>`



Properties
**********


.. _property_MqttSubscription_autoSubscribe:

.. _signal_MqttSubscription_autoSubscribeChanged:

.. index::
   single: autoSubscribe

autoSubscribe
+++++++++++++

This property holds whether to subscribe the :ref:`topics <property_MqttSubscription_topics>` automatically once the :ref:`MqttClient <object_MqttClient>` is connected to the MQTT broker.

:**› Type**: Boolean
:**› Default**: ``true``
:**› Signal**: autoSubscribeChanged()
:**› Attributes**: Writable


.. _property_MqttSubscription_error:

.. _signal_MqttSubscription_errorChanged:

.. index::
   single: error

error
+++++

This property holds the most recently occurred error or :ref:`MqttSubscription.NoError <enumitem_MqttSubscription_NoError>` if no error occurred. If the same error occurs multiple times this property does not change. Use the :ref:`errorOccurred() <signal_MqttSubscription_errorOccurred>` signal to detect multiple occurrences of the same error.

:**› Type**: :ref:`Error <enum_MqttSubscription_Error>`
:**› Signal**: errorChanged()
:**› Attributes**: Readonly


.. _property_MqttSubscription_errorString:

.. _signal_MqttSubscription_errorStringChanged:

.. index::
   single: errorString

errorString
+++++++++++

This property holds the current human readable error string corresponding to the current value in the :ref:`error <property_MqttSubscription_error>` property. It may include additional information such as failure reasons or locations.

:**› Type**: String
:**› Signal**: errorStringChanged()
:**› Attributes**: Readonly


.. _property_MqttSubscription_qos:

.. _signal_MqttSubscription_qosChanged:

.. index::
   single: qos

qos
+++

This property holds the Quality of Service to set for the subscribed topics. The QoS level defines how hard the broker will try to ensure that a message is received. MQTT defines three QoS levels:

* ``0``: The broker will deliver the message once, with no confirmation. This level could be used, for example, with ambient sensor data where it does not matter if an individual reading is lost as the next one will be published soon after.
* ``1``: The broker will deliver the message at least once, with confirmation required.
* ``2``: The broker will deliver the message exactly once by using a four step handshake. This level could be used, for example, with billing systems where duplicate or lost messages could lead to incorrect charges being applied.

:**› Type**: SignedInteger
:**› Default**: ``0``
:**› Signal**: qosChanged()
:**› Attributes**: Writable


.. _property_MqttSubscription_subscribed:

.. _signal_MqttSubscription_subscribedChanged:

.. index::
   single: subscribed

subscribed
++++++++++

This property holds whether the :ref:`topics <property_MqttSubscription_topics>` have been subscribed to successfully.

:**› Type**: Boolean
:**› Default**: ``false``
:**› Signal**: subscribedChanged()
:**› Attributes**: Readonly


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

Methods
*******


.. _method_MqttSubscription_subscribe:

.. index::
   single: subscribe

subscribe()
+++++++++++

This method subscribes the configured :ref:`topics <property_MqttSubscription_topics>` using the parent :ref:`MqttClient <object_MqttClient>` object. Once subscribed the :ref:`MqttTopic::data <property_DataObject_data>` properties are updated whenever the MQTT broker receives updates from the topic publisher.

This method usually never has to be called manually. Instead the :ref:`autoSubscribe <property_MqttSubscription_autoSubscribe>` property should be left at its default value or set to ``true``.



.. _method_MqttSubscription_unsubscribe:

.. index::
   single: unsubscribe

unsubscribe()
+++++++++++++

This method unsubscribes the configured :ref:`topics <property_MqttSubscription_topics>` using the parent :ref:`MqttClient <object_MqttClient>` object. The :ref:`MqttTopic::data <property_DataObject_data>` properties will not be updated any longer if the MQTT broker receives updates from the topic publisher.


Signals
*******


.. _signal_MqttSubscription_errorOccurred:

.. index::
   single: errorOccurred

errorOccurred()
+++++++++++++++

This signal is emitted whenever an error has occurred, regardless of whether the :ref:`error <property_MqttSubscription_error>` property has changed or not. In contrast to the change notification signal of the :ref:`error <property_MqttSubscription_error>` property this signal is also emitted several times if a certain error occurs several times in succession.



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

This enumeration describes all errors which can occur in MqttSubscription objects. The most recently occurred error is stored in the :ref:`error <property_MqttSubscription_error>` property.

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
                    name: "inhub/customerCount"
                    onDataChanged: console.log("Number of customers changed to", data)
                }
    
                MqttTopic {
                    name: "inhub/employeeCount"
                    onDataChanged: console.log("Number of employees changed to", data)
                }
            }
        }
    }
    