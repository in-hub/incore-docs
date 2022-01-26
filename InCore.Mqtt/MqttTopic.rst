
.. _object_MqttTopic:


:index:`MqttTopic`
------------------

Description
***********

The MqttTopic object represents an MQTT topic identified by its :ref:`name <property_DataObject_name>`. MQTT topics can be either subscribed or published and need to be specified within :ref:`MqttSubscription <object_MqttSubscription>` or :ref:`MqttPublication <object_MqttPublication>` objects.

The :ref:`DataObject.name <property_DataObject_name>` property holds the name of the topic, e.g. ``machine/sensor0``. More information on MQTT topic names is available at `mosquitto.org <https://mosquitto.org/man/mqtt-7.html>`_.

The :ref:`DataObject.data <property_DataObject_data>` property holds the data to publish or the subscribed (received) data.

:**› Inherits**: :ref:`DataObject <object_DataObject>`

Overview
********

Properties
++++++++++

.. hlist::
  :columns: 2

  * :ref:`DataObject.data <property_DataObject_data>`
  * :ref:`DataObject.dataType <property_DataObject_dataType>`
  * :ref:`DataObject.description <property_DataObject_description>`
  * :ref:`DataObject.name <property_DataObject_name>`
  * :ref:`DataObject.timestamp <property_DataObject_timestamp>`
  * :ref:`DataObject.uuid <property_DataObject_uuid>`
  * :ref:`DataObject.view <property_DataObject_view>`
  * :ref:`Object.objectId <property_Object_objectId>`
  * :ref:`Object.parent <property_Object_parent>`

Methods
+++++++

.. hlist::
  :columns: 1

  * :ref:`DataObject.touch() <method_DataObject_touch>`
  * :ref:`Object.deserializeProperties() <method_Object_deserializeProperties>`
  * :ref:`Object.fromJson() <method_Object_fromJson>`
  * :ref:`Object.serializeProperties() <method_Object_serializeProperties>`
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

  * :ref:`DataObject.DataType <enum_DataObject_DataType>`



Properties
**********

Example
*******
See :ref:`MqttClient example <example_MqttClient>` on how to use MqttTopic.
