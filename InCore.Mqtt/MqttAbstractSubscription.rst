
.. _object_MqttAbstractSubscription:


:index:`MqttAbstractSubscription`
---------------------------------

Description
***********

The MqttAbstractSubscription object provides common properties and mechanisms for subscription objects.

:**› Inherits**: :ref:`Object <object_Object>`
:**› Inherited by**: :ref:`MqttSubscription <object_MqttSubscription>`, :ref:`MqttWildcardSubscription <object_MqttWildcardSubscription>`

Overview
********

Properties
++++++++++

.. hlist::
  :columns: 1

  * :ref:`autoSubscribe <property_MqttAbstractSubscription_autoSubscribe>`
  * :ref:`error <property_MqttAbstractSubscription_error>`
  * :ref:`errorString <property_MqttAbstractSubscription_errorString>`
  * :ref:`qos <property_MqttAbstractSubscription_qos>`
  * :ref:`subscribed <property_MqttAbstractSubscription_subscribed>`
  * :ref:`Object.objectId <property_Object_objectId>`
  * :ref:`Object.parent <property_Object_parent>`

Methods
+++++++

.. hlist::
  :columns: 1

  * :ref:`subscribe() <method_MqttAbstractSubscription_subscribe>`
  * :ref:`unsubscribe() <method_MqttAbstractSubscription_unsubscribe>`
  * :ref:`Object.deserializeProperties() <method_Object_deserializeProperties>`
  * :ref:`Object.fromJson() <method_Object_fromJson>`
  * :ref:`Object.serializeProperties() <method_Object_serializeProperties>`
  * :ref:`Object.toJson() <method_Object_toJson>`

Signals
+++++++

.. hlist::
  :columns: 1

  * :ref:`errorOccurred() <signal_MqttAbstractSubscription_errorOccurred>`
  * :ref:`Object.completed() <signal_Object_completed>`

Enumerations
++++++++++++

.. hlist::
  :columns: 1

  * :ref:`Error <enum_MqttAbstractSubscription_Error>`



Properties
**********


.. _property_MqttAbstractSubscription_autoSubscribe:

.. _signal_MqttAbstractSubscription_autoSubscribeChanged:

.. index::
   single: autoSubscribe

autoSubscribe
+++++++++++++

This property holds whether to subscribe the topics automatically whenever the associated :ref:`MqttClient <object_MqttClient>` successfully established a connection to the MQTT broker.

:**› Type**: Boolean
:**› Default**: ``true``
:**› Signal**: autoSubscribeChanged()
:**› Attributes**: Writable


.. _property_MqttAbstractSubscription_error:

.. _signal_MqttAbstractSubscription_errorChanged:

.. index::
   single: error

error
+++++

This property holds the most recently occurred error or :ref:`MqttAbstractSubscription.NoError <enumitem_MqttAbstractSubscription_NoError>` if no error occurred. If the same error occurs multiple times this property does not change. Use the :ref:`errorOccurred() <signal_MqttAbstractSubscription_errorOccurred>` signal to detect multiple occurrences of the same error.

:**› Type**: :ref:`Error <enum_MqttAbstractSubscription_Error>`
:**› Signal**: errorChanged()
:**› Attributes**: Readonly


.. _property_MqttAbstractSubscription_errorString:

.. _signal_MqttAbstractSubscription_errorStringChanged:

.. index::
   single: errorString

errorString
+++++++++++

This property holds the current human readable error string corresponding to the current value in the :ref:`error <property_MqttAbstractSubscription_error>` property. It may include additional information such as failure reasons or locations.

:**› Type**: String
:**› Signal**: errorStringChanged()
:**› Attributes**: Readonly


.. _property_MqttAbstractSubscription_qos:

.. _signal_MqttAbstractSubscription_qosChanged:

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


.. _property_MqttAbstractSubscription_subscribed:

.. _signal_MqttAbstractSubscription_subscribedChanged:

.. index::
   single: subscribed

subscribed
++++++++++

This property holds whether the topics have been subscribed successfully.

:**› Type**: Boolean
:**› Default**: ``false``
:**› Signal**: subscribedChanged()
:**› Attributes**: Readonly

Methods
*******


.. _method_MqttAbstractSubscription_subscribe:

.. index::
   single: subscribe

subscribe()
+++++++++++

This method subscribes the configured topics using the parent :ref:`MqttClient <object_MqttClient>` object. Once subscribed the :ref:`MqttTopic::data <property_DataObject_data>` properties are updated whenever the MQTT broker receives updates from the topic publisher.

This method usually never has to be called manually. Instead the :ref:`autoSubscribe <property_MqttAbstractSubscription_autoSubscribe>` property should be left at its default value or set to ``true``.



.. _method_MqttAbstractSubscription_unsubscribe:

.. index::
   single: unsubscribe

unsubscribe()
+++++++++++++

This method unsubscribes the configured topics using the parent :ref:`MqttClient <object_MqttClient>` object. The :ref:`MqttTopic::data <property_DataObject_data>` properties will not be updated any longer if the MQTT broker receives updates from the topic publisher.


Signals
*******


.. _signal_MqttAbstractSubscription_errorOccurred:

.. index::
   single: errorOccurred

errorOccurred()
+++++++++++++++

This signal is emitted whenever an error has occurred, regardless of whether the :ref:`error <property_MqttAbstractSubscription_error>` property has changed or not. In contrast to the change notification signal of the :ref:`error <property_MqttAbstractSubscription_error>` property this signal is also emitted several times if a certain error occurs several times in succession.


Enumerations
************


.. _enum_MqttAbstractSubscription_Error:

.. index::
   single: Error

Error
+++++

This enumeration describes all errors which can occur in MqttAbstractSubscription objects. The most recently occurred error is stored in the :ref:`error <property_MqttAbstractSubscription_error>` property.

.. index::
   single: MqttAbstractSubscription.NoError
.. index::
   single: MqttAbstractSubscription.InvalidClient
.. list-table::
  :widths: auto
  :header-rows: 1

  * - Name
    - Value
    - Description

      .. _enumitem_MqttAbstractSubscription_NoError:
  * - ``MqttAbstractSubscription.NoError``
    - ``0``
    - No error occurred or was detected.

      .. _enumitem_MqttAbstractSubscription_InvalidClient:
  * - ``MqttAbstractSubscription.InvalidClient``
    - ``1``
    - Parent object is not an MqttClient.
