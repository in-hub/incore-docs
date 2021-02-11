
.. _object_MqttWildcardSubscription:


:index:`MqttWildcardSubscription`
---------------------------------

Description
***********

The MqttWildcardSubscription object subscribes to an MQTT wildcard topic specified in the :ref:`name <property_MqttWildcardSubscription_name>` property and provides the received data in the :ref:`data <property_MqttWildcardSubscription_data>` property. The names of all received topics are available in the :ref:`topics <property_MqttWildcardSubscription_topics>` property.

The parent object must be of type :ref:`MqttClient <object_MqttClient>`.

This object was introduced in InCore 2.3.

:**› Inherits**: :ref:`Object <object_Object>`

Overview
********

Properties
++++++++++

.. hlist::
  :columns: 2

  * :ref:`data <property_MqttWildcardSubscription_data>`
  * :ref:`enabled <property_MqttWildcardSubscription_enabled>`
  * :ref:`name <property_MqttWildcardSubscription_name>`
  * :ref:`qos <property_MqttWildcardSubscription_qos>`
  * :ref:`subscribed <property_MqttWildcardSubscription_subscribed>`
  * :ref:`topics <property_MqttWildcardSubscription_topics>`
  * :ref:`Object.objectId <property_Object_objectId>`
  * :ref:`Object.parent <property_Object_parent>`

Methods
+++++++

.. hlist::
  :columns: 1

  * :ref:`Object.fromJson() <method_Object_fromJson>`
  * :ref:`Object.toJson() <method_Object_toJson>`

Signals
+++++++

.. hlist::
  :columns: 1

  * :ref:`Object.completed() <signal_Object_completed>`



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


.. _property_MqttWildcardSubscription_enabled:

.. _signal_MqttWildcardSubscription_enabledChanged:

.. index::
   single: enabled

enabled
+++++++

This property holds whether to subscribe the specified wildcard topic.

:**› Type**: Boolean
:**› Default**: ``true``
:**› Signal**: enabledChanged()
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


.. _property_MqttWildcardSubscription_qos:

.. _signal_MqttWildcardSubscription_qosChanged:

.. index::
   single: qos

qos
+++

This property holds the Quality of Service to set for the subscribed wildcard topic. See the :ref:`MqttSubscription.qos <property_MqttSubscription_qos>` property for further information.

:**› Type**: SignedInteger
:**› Default**: ``0``
:**› Signal**: qosChanged()
:**› Attributes**: Writable


.. _property_MqttWildcardSubscription_subscribed:

.. _signal_MqttWildcardSubscription_subscribedChanged:

.. index::
   single: subscribed

subscribed
++++++++++

This property holds whether the wildcard topic is actually subscribed.

:**› Type**: Boolean
:**› Default**: ``false``
:**› Signal**: subscribedChanged()
:**› Attributes**: Readonly


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


.. _example_MqttWildcardSubscription:


Example
*******

.. code-block:: qml

    import InCore.Foundation 2.3
    import InCore.Mqtt 2.3
    import InCore.IO 2.3
    
    Application {
        MqttClient {
            clientId: "MqttWildcardSubscriptionExample"
            hostname: "localhost"
    
            MqttWildcardSubscription {
                id: allTopics
                name: "#"
                onTopicsChanged: console.log("Names of all published topics:", topics)
                property var counter: topics.includes("incore/foo/counter") ? data.incore.foo.counter : 0
                onCounterChanged: console.log("Counter:", counter)
            }
            MqttWildcardSubscription {
                name: "incore/+/date"
                property var date: topics.includes("bar/date") ? data.bar.date : 0
                onDateChanged: console.log(date)
            }
        }
    
        DigitalIO {
            index: DigitalIO.IO1
            direction: DigitalIO.Output
            outputValue: allTopics.topics.includes("incore/foo/counter") ? allTopics.data.incore.foo.counter % 2 : 0
        }
    }
    