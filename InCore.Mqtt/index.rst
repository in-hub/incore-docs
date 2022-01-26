
.. _module_Mqtt:


:index:`InCore Mqtt`
====================

Description
-----------

The Mqtt module enables you to create applications and devices that can communicate over the MQ telemetry transport (MQTT) protocol. It fully complies to the MQTT protocol specification.

MQTT is a machine-to-machine connectivity protocol that operates on the publish-and-subscribe model. An MQTT client is a program or device that uses MQTT to create a network connection to an MQTT server, also called a broker. Once a connection is created, the client can send messages to the broker. The other clients can subscribe to notifications on particular topics sent by the client.


Objects
-------

.. toctree::
	:maxdepth: 1

	MqttAbstractSubscription
	MqttBroker
	MqttClient
	MqttMeasurementWriter
	MqttObjectPublication
	MqttPublication
	MqttSubscription
	MqttTopic
	MqttWildcardSubscription
