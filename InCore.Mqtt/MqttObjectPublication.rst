
.. _object_MqttObjectPublication:


:index:`MqttObjectPublication`
------------------------------

Description
***********



:**› Inherits**: :ref:`MqttPublication <object_MqttPublication>`

Overview
********

Properties
++++++++++

.. hlist::
  :columns: 2

  * :ref:`source <property_MqttObjectPublication_source>`
  * :ref:`topicBaseName <property_MqttObjectPublication_topicBaseName>`
  * :ref:`MqttPublication.autoPublish <property_MqttPublication_autoPublish>`
  * :ref:`MqttPublication.error <property_MqttPublication_error>`
  * :ref:`MqttPublication.errorString <property_MqttPublication_errorString>`
  * :ref:`MqttPublication.qos <property_MqttPublication_qos>`
  * :ref:`MqttPublication.retain <property_MqttPublication_retain>`
  * :ref:`DataObjectWriter.datasetCount <property_DataObjectWriter_datasetCount>`
  * :ref:`DataObjectWriter.objects <property_DataObjectWriter_objects>`
  * :ref:`DataObjectWriter.running <property_DataObjectWriter_running>`
  * :ref:`DataObjectWriter.submitInterval <property_DataObjectWriter_submitInterval>`
  * :ref:`DataObjectWriter.submitMode <property_DataObjectWriter_submitMode>`
  * :ref:`Object.objectId <property_Object_objectId>`
  * :ref:`Object.parent <property_Object_parent>`

Methods
+++++++

.. hlist::
  :columns: 2

  * :ref:`MqttPublication.publish() <method_MqttPublication_publish>`
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

  * :ref:`MqttPublication.errorOccurred() <signal_MqttPublication_errorOccurred>`
  * :ref:`DataObjectWriter.objectsDataChanged() <signal_DataObjectWriter_objectsDataChanged>`
  * :ref:`DataObjectWriter.submitted() <signal_DataObjectWriter_submitted>`
  * :ref:`DataObjectWriter.truncated() <signal_DataObjectWriter_truncated>`
  * :ref:`Object.completed() <signal_Object_completed>`

Enumerations
++++++++++++

.. hlist::
  :columns: 1

  * :ref:`MqttPublication.Error <enum_MqttPublication_Error>`
  * :ref:`DataObjectWriter.SubmitMode <enum_DataObjectWriter_SubmitMode>`



Properties
**********


.. _property_MqttObjectPublication_source:

.. _signal_MqttObjectPublication_sourceChanged:

.. index::
   single: source

source
++++++



:**› Type**: :ref:`Object <object_Object>`
:**› Signal**: sourceChanged()
:**› Attributes**: Writable


.. _property_MqttObjectPublication_topicBaseName:

.. _signal_MqttObjectPublication_topicBaseNameChanged:

.. index::
   single: topicBaseName

topicBaseName
+++++++++++++



:**› Type**: String
:**› Signal**: topicBaseNameChanged()
:**› Attributes**: Writable


.. _example_MqttObjectPublication:


Example
*******

.. code-block:: qml

    import InCore.Foundation 2.5
    import InCore.Mqtt 2.5
    
    Application {
    
        Measurement { id: temperature; name: "Temperature"; data: 0.0; unit: "°C"}
    
        Timer {
            onTriggered: {
                temperature.data = Math.random()
            }
        }
    
        MqttBroker { }
    
        MqttClient {
            clientId: "MqttPublicationExample"
            hostname: "localhost"
    
            MqttObjectPublication {
                retain: true
                source: temperature
            }
        }
    }
    