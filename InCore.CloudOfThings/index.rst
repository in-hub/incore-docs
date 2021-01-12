
.. _module_CloudOfThings:


:index:`InCore CloudOfThings`
=============================

Description
-----------

The CloudOfThings module is designed to communicate with Cloud of Things of Telekom.

The Cloud of Things is a cloud platform for the Internet of Things. It allows you to remotely monitor, manage and control connected devices and machines. The :ref:`CloudOfThingsClient <object_CloudOfThingsClient>` encapsulates a MQTT-client which communicates with the cloud and contains overall properties. :ref:`Measurement <object_Measurement>` objects can be published to the cloud or stored temporary in case of lost connection with :ref:`CloudOfThingsMeasurementWriter <object_CloudOfThingsMeasurementWriter>`. The same applies to :ref:`Event <object_Event>` and :ref:`CloudOfThingsEventWriter <object_CloudOfThingsEventWriter>`.For detailed information see `Cloud of Things <https://iot.telekom.com/iot-en/platforms/cloud-of-things>`_ .


Objects
-------

.. toctree::
	:maxdepth: 1

	CloudOfThingsClient
	CloudOfThingsDeviceManager
	CloudOfThingsDeviceRegistrator
	CloudOfThingsEventDatabase
	CloudOfThingsEventWriter
	CloudOfThingsMeasurementDatabase
	CloudOfThingsMeasurementWriter
	CloudOfThingsRemoteConnectionManager
	CloudOfThingsTransport
