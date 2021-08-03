
.. _object_Relay:


:index:`Relay`
--------------

Description
***********

The Relay object allows controlling the internal relay of the HUB-GM100 device.

:**› Inherits**: :ref:`Object <object_Object>`

Overview
********

Properties
++++++++++

.. hlist::
  :columns: 1

  * :ref:`value <property_Relay_value>`
  * :ref:`Object.objectId <property_Object_objectId>`
  * :ref:`Object.parent <property_Object_parent>`

Methods
+++++++

.. hlist::
  :columns: 1

  * :ref:`Object.deserializeProperties() <method_Object_deserializeProperties>`
  * :ref:`Object.fromJson() <method_Object_fromJson>`
  * :ref:`Object.toJson() <method_Object_toJson>`

Signals
+++++++

.. hlist::
  :columns: 1

  * :ref:`Object.completed() <signal_Object_completed>`



Properties
**********


.. _property_Relay_value:

.. index::
   single: value

value
+++++

This property holds the current state of the relay.

:**› Type**: Boolean
:**› Default**: ``false``
:**› Attributes**: Writable


.. _example_Relay:


Example
*******

.. code-block:: qml

    import InCore.Foundation 2.0
    import InCore.IO 2.0
    
    Application {
    
        Relay {
            id: relay
        }
    
        // toggle relay every 1000 ms
        Timer {
            interval: 1000
            running: true
            onTriggered: relay.value = !relay.value
        }
    }
    
    