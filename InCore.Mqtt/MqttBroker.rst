
.. _object_MqttBroker:


:index:`MqttBroker`
-------------------

Description
***********

The MqttBroker object creates an MQTT broker listening for connections. An MQTT broker manages the exchange of subscribed and published topics for all connected clients.

:**› Inherits**: :ref:`Object <object_Object>`

Overview
********

Properties
++++++++++

.. hlist::
  :columns: 1

  * :ref:`enabled <property_MqttBroker_enabled>`
  * :ref:`internal <property_MqttBroker_internal>`
  * :ref:`listeners <property_MqttBroker_listeners>`
  * :ref:`maxConnections <property_MqttBroker_maxConnections>`
  * :ref:`Object.objectId <property_Object_objectId>`
  * :ref:`Object.parent <property_Object_parent>`

Methods
+++++++

.. hlist::
  :columns: 1

  * :ref:`Object.deserializeProperties() <method_Object_deserializeProperties>`
  * :ref:`Object.fromJson() <method_Object_fromJson>`
  * :ref:`Object.serializeProperties() <method_Object_serializeProperties>`
  * :ref:`Object.toJson() <method_Object_toJson>`

Signals
+++++++

.. hlist::
  :columns: 1

  * :ref:`listenersDataChanged() <signal_MqttBroker_listenersDataChanged>`
  * :ref:`Object.completed() <signal_Object_completed>`



Properties
**********


.. _property_MqttBroker_enabled:

.. _signal_MqttBroker_enabledChanged:

.. index::
   single: enabled

enabled
+++++++

This property holds whether the broker is enabled. If set to ``false`` the broker process is stopped.

:**› Type**: Boolean
:**› Default**: ``true``
:**› Signal**: enabledChanged()
:**› Attributes**: Writable


.. _property_MqttBroker_internal:

.. _signal_MqttBroker_internalChanged:

.. index::
   single: internal

internal
++++++++

This property holds whether the broker should listen for incoming connections on the local loopback interface only. If set to ``true`` the broker will not be reachable by other hosts on the network but internal clients such as docker containers (:ref:`DockerContainer <object_DockerContainer>`) only.

:**› Type**: Boolean
:**› Default**: ``true``
:**› Signal**: internalChanged()
:**› Attributes**: Writable


.. _property_MqttBroker_listeners:

.. _signal_MqttBroker_listenersChanged:

.. index::
   single: listeners

listeners
+++++++++

This property holds a list of :ref:`MqttListener <object_MqttListener>` objects which define the actual connectivity options of the broker.

This property was introduced in InCore 2.6.

:**› Type**: :ref:`List <object_List>`\<:ref:`MqttListener <object_MqttListener>`>
:**› Signal**: listenersChanged()
:**› Attributes**: Readonly


.. _property_MqttBroker_maxConnections:

.. _signal_MqttBroker_maxConnectionsChanged:

.. index::
   single: maxConnections

maxConnections
++++++++++++++

This property holds the maximum number of connections which the broker is allowed to manage concurrently.

:**› Type**: SignedInteger
:**› Default**: ``-1``
:**› Signal**: maxConnectionsChanged()
:**› Attributes**: Writable, Optional

Signals
*******


.. _signal_MqttBroker_listenersDataChanged:

.. index::
   single: listenersDataChanged

listenersDataChanged(SignedInteger index)
+++++++++++++++++++++++++++++++++++++++++

This signal is emitted whenever the :ref:`List.dataChanged() <signal_List_dataChanged>` signal is emitted, i.e. the item at ``index`` in the :ref:`listeners <property_MqttBroker_listeners>` list itself emitted the dataChanged() signal.



.. _example_MqttBroker:


Example
*******

.. code-block:: qml

    import InCore.Foundation 2.6
    import InCore.Mqtt 2.6
    
    Application {
    
        name: "MqttBrokerExample"
    
        Settings {
            id: settings
            property bool brokerEnabled : true;
        }
    
        // start an MQTT broker if enabled via settings
        MqttBroker {
            enabled: settings.brokerEnabled
            listeners: [
                MqttListener {
                    internal: false
                    port: 1883
                },
                MqttListener {
                    internal: false
                    port: 1884
                    protocol: MqttListener.Websockets
                }
            ]
        }
    }
    