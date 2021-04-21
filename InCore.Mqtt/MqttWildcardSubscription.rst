
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
  * :ref:`name <property_MqttWildcardSubscription_name>`
  * :ref:`topics <property_MqttWildcardSubscription_topics>`
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

  * :ref:`MqttAbstractSubscription.errorOccurred() <signal_MqttAbstractSubscription_errorOccurred>`
  * :ref:`Object.completed() <signal_Object_completed>`

Enumerations
++++++++++++

.. hlist::
  :columns: 1

  * :ref:`Error <enum_MqttWildcardSubscription_Error>`
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

Enumerations
************


.. _enum_MqttWildcardSubscription_Error:

.. index::
   single: Error

Error
+++++

This enumeration describes all errors which can occur in MqttAbstractSubscription objects. The most recently occurred error is stored in the :ref:`error <property_MqttWildcardSubscription_error>` property.

.. index::
   single: MqttWildcardSubscription.NoError
.. index::
   single: MqttWildcardSubscription.InvalidClient
.. list-table::
  :widths: auto
  :header-rows: 1

  * - Name
    - Value
    - Description

      .. _enumitem_MqttWildcardSubscription_NoError:
  * - ``MqttWildcardSubscription.NoError``
    - ``0``
    - No error occurred or was detected.

      .. _enumitem_MqttWildcardSubscription_InvalidClient:
  * - ``MqttWildcardSubscription.InvalidClient``
    - ``1``
    - Parent object is not an MqttClient.


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
    