
.. _object_MqttPublication:


:index:`MqttPublication`
------------------------

Description
***********

The MqttPublication object aggregates :ref:`DataObject <object_DataObject>` objects as topics to be published through the MQTT broker. Both :ref:`retain <property_MqttPublication_retain>` and :ref:`qos <property_MqttPublication_qos>` (Quality of Service) properties can be set to be used for all :ref:`topics <property_DataObjectWriter_objects>`.

The parent object must be of type :ref:`MqttClient <object_MqttClient>`.

The inherited :ref:`DataObjectWriter.submitMode <property_DataObjectWriter_submitMode>` property is initialized to :ref:`DataObjectWriter.SubmitOnAnyChange <enumitem_DataObjectWriter_SubmitOnAnyChange>` which will automatically publish any topic whenever it changes. The submit mode can be changed to e.g. only publish all topics when all of them have been updated (:ref:`DataObjectWriter.SubmitOnCompleteDataset <enumitem_DataObjectWriter_SubmitOnCompleteDataset>`) or periodically every :ref:`DataObjectWriter.submitInterval <property_DataObjectWriter_submitInterval>` milliseconds (:ref:`DataObjectWriter.SubmitPeriodically <enumitem_DataObjectWriter_SubmitPeriodically>`). Manual submission can be implemented through the :ref:`DataObjectWriter.SubmitManually <enumitem_DataObjectWriter_SubmitManually>` submit mode and calling :ref:`publish() <method_MqttPublication_publish>`.

:**› Inherits**: :ref:`DataObjectWriter <object_DataObjectWriter>`
:**› Inherited by**: :ref:`MqttMeasurementWriter <object_MqttMeasurementWriter>`, :ref:`MqttObjectPublication <object_MqttObjectPublication>`

Overview
********

Properties
++++++++++

.. hlist::
  :columns: 2

  * :ref:`autoPublish <property_MqttPublication_autoPublish>`
  * :ref:`error <property_MqttPublication_error>`
  * :ref:`errorString <property_MqttPublication_errorString>`
  * :ref:`qos <property_MqttPublication_qos>`
  * :ref:`retain <property_MqttPublication_retain>`
  * :ref:`DataObjectWriter.datasetCount <property_DataObjectWriter_datasetCount>`
  * :ref:`DataObjectWriter.objects <property_DataObjectWriter_objects>`
  * :ref:`DataObjectWriter.running <property_DataObjectWriter_running>`
  * :ref:`DataObjectWriter.submitChangedObjectsOnly <property_DataObjectWriter_submitChangedObjectsOnly>`
  * :ref:`DataObjectWriter.submitInterval <property_DataObjectWriter_submitInterval>`
  * :ref:`DataObjectWriter.submitMode <property_DataObjectWriter_submitMode>`
  * :ref:`Object.objectId <property_Object_objectId>`
  * :ref:`Object.parent <property_Object_parent>`

Methods
+++++++

.. hlist::
  :columns: 2

  * :ref:`publish() <method_MqttPublication_publish>`
  * :ref:`DataObjectWriter.close() <method_DataObjectWriter_close>`
  * :ref:`DataObjectWriter.open() <method_DataObjectWriter_open>`
  * :ref:`DataObjectWriter.submit() <method_DataObjectWriter_submit>`
  * :ref:`DataObjectWriter.sync() <method_DataObjectWriter_sync>`
  * :ref:`DataObjectWriter.truncate() <method_DataObjectWriter_truncate>`
  * :ref:`Object.deserializeProperties() <method_Object_deserializeProperties>`
  * :ref:`Object.fromJson() <method_Object_fromJson>`
  * :ref:`Object.serializeProperties() <method_Object_serializeProperties>`
  * :ref:`Object.toJson() <method_Object_toJson>`

Signals
+++++++

.. hlist::
  :columns: 1

  * :ref:`errorOccurred() <signal_MqttPublication_errorOccurred>`
  * :ref:`DataObjectWriter.objectsDataChanged() <signal_DataObjectWriter_objectsDataChanged>`
  * :ref:`DataObjectWriter.submitted() <signal_DataObjectWriter_submitted>`
  * :ref:`DataObjectWriter.truncated() <signal_DataObjectWriter_truncated>`
  * :ref:`Object.completed() <signal_Object_completed>`

Enumerations
++++++++++++

.. hlist::
  :columns: 1

  * :ref:`Error <enum_MqttPublication_Error>`
  * :ref:`DataObjectWriter.SubmitMode <enum_DataObjectWriter_SubmitMode>`



Properties
**********


.. _property_MqttPublication_autoPublish:

.. _signal_MqttPublication_autoPublishChanged:

.. index::
   single: autoPublish

autoPublish
+++++++++++

This property holds whether to automatically publish all topics whenever the :ref:`MQTT client <object_MqttClient>` established a connection to the MQTT broker.

:**› Type**: Boolean
:**› Default**: ``true``
:**› Signal**: autoPublishChanged()
:**› Attributes**: Writable


.. _property_MqttPublication_error:

.. _signal_MqttPublication_errorChanged:

.. index::
   single: error

error
+++++

This property holds the most recently occurred error or :ref:`MqttPublication.NoError <enumitem_MqttPublication_NoError>` if no error occurred. If the same error occurs multiple times this property does not change. Use the :ref:`errorOccurred() <signal_MqttPublication_errorOccurred>` signal to detect multiple occurrences of the same error.

:**› Type**: :ref:`Error <enum_MqttPublication_Error>`
:**› Signal**: errorChanged()
:**› Attributes**: Readonly


.. _property_MqttPublication_errorString:

.. _signal_MqttPublication_errorStringChanged:

.. index::
   single: errorString

errorString
+++++++++++

This property holds the current human readable error string corresponding to the current value in the :ref:`error <property_MqttPublication_error>` property. It may include additional information such as failure reasons or locations.

:**› Type**: String
:**› Signal**: errorStringChanged()
:**› Attributes**: Readonly


.. _property_MqttPublication_qos:

.. _signal_MqttPublication_qosChanged:

.. index::
   single: qos

qos
+++

This property holds the Quality of Service to set for the published topics. The QoS level defines how hard the client will try to ensure that a message is received. MQTT defines three QoS levels:

* ``0``: The client will deliver the message once, with no confirmation. This level could be used, for example, with ambient sensor data where it does not matter if an individual reading is lost as the next one will be published soon after.
* ``1``: The client will deliver the message at least once, with confirmation required.
* ``2``: The client will deliver the message exactly once by using a four step handshake. This level could be used, for example, with billing systems where duplicate or lost messages could lead to incorrect charges being applied.

:**› Type**: SignedInteger
:**› Default**: ``0``
:**› Signal**: qosChanged()
:**› Attributes**: Writable


.. _property_MqttPublication_retain:

.. _signal_MqttPublication_retainChanged:

.. index::
   single: retain

retain
++++++

This property holds whether to retain messages for new subscribers. See `mosquitto.org <https://mosquitto.org/man/mqtt-7.html>`_ for more information on retained messages.

:**› Type**: Boolean
:**› Default**: ``false``
:**› Signal**: retainChanged()
:**› Attributes**: Writable

Methods
*******


.. _method_MqttPublication_publish:

.. index::
   single: publish

publish()
+++++++++

This method publishes all topics manually. This is usually not required as a topic is published automatically whenever its :ref:`DataObject.data <property_DataObject_data>` property is changed and the :ref:`DataObjectWriter.submitMode <property_DataObjectWriter_submitMode>` property is set to its default value :ref:`DataObjectWriter.SubmitOnAnyChange <enumitem_DataObjectWriter_SubmitOnAnyChange>`.


Signals
*******


.. _signal_MqttPublication_errorOccurred:

.. index::
   single: errorOccurred

errorOccurred()
+++++++++++++++

This signal is emitted whenever an error has occurred, regardless of whether the :ref:`error <property_MqttPublication_error>` property has changed or not. In contrast to the change notification signal of the :ref:`error <property_MqttPublication_error>` property this signal is also emitted several times if a certain error occurs several times in succession.


Enumerations
************


.. _enum_MqttPublication_Error:

.. index::
   single: Error

Error
+++++

This enumeration describes all errors which can occur in MqttPublication objects. The most recently occurred error is stored in the :ref:`error <property_MqttPublication_error>` property.

.. index::
   single: MqttPublication.NoError
.. index::
   single: MqttPublication.InvalidClient
.. index::
   single: MqttPublication.EmptyTopicBasename
.. index::
   single: MqttPublication.MissingObjectsIds
.. list-table::
  :widths: auto
  :header-rows: 1

  * - Name
    - Value
    - Description

      .. _enumitem_MqttPublication_NoError:
  * - ``MqttPublication.NoError``
    - ``0``
    - No error occurred or was detected.

      .. _enumitem_MqttPublication_InvalidClient:
  * - ``MqttPublication.InvalidClient``
    - ``1``
    - Parent object is not an MqttClient.

      .. _enumitem_MqttPublication_EmptyTopicBasename:
  * - ``MqttPublication.EmptyTopicBasename``
    - ``2``
    - Topic base name not set.

      .. _enumitem_MqttPublication_MissingObjectsIds:
  * - ``MqttPublication.MissingObjectsIds``
    - ``3``
    - Some data objects do not have an object ID.


.. _example_MqttPublication:


Example
*******

.. code-block:: qml

    import InCore.Foundation 2.5
    import InCore.Mqtt 2.5
    
    Application {
        System {
            id: system
            Polling on deviceTemperature { interval: 5000 }
        }
    
        DateTime {
            id: dateTime
            dateFormat: DateTime.FormatISO
        }
    
        Counter {
            id: counter
            interval: 1000
        }
    
        MqttClient {
            clientId: "MqttPublicationExample"
            hostname: "localhost"
    
            MqttPublication {
                qos: 1
                retain: false
    
                // publish current device temperature which is polled and updated every 5 seconds
                MqttTopic {
                    name: "incore/temperature"
                    data: system.deviceTemperature
                }
    
                MqttTopic {
                    name: "incore/foo/counter"
                    data: counter.value
                }
    
                // publish current date string on every change (i.e. every second)
                MqttTopic {
                    name: "incore/bar/date"
                    dataType: MqttTopic.DateTime
                    data: dateTime.string
                }
    
                // publish array as comma separated string list
                MqttTopic {
                    name: "incore/array"
                    dataType: MqttTopic.StringList
                    data: [ 1, 2, 3 ]
                }
            }
        }
    }
    