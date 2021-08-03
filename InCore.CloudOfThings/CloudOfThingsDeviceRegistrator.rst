
.. _object_CloudOfThingsDeviceRegistrator:


:index:`CloudOfThingsDeviceRegistrator`
---------------------------------------

Description
***********

The CloudOfThingsDeviceRegistrator object deals with the device registration of Cloud of Things. Every device communication with Cloud of Things has to be registered. This can be done by the device itself during a process called bootstrap. With initial bootstrap credentials the device registeres itself and create unique credentials after it is accepted in the device management of Cloud of Things. A reconnect is performed and the device can be used to communicate, send measurements, etc. It is also possible to register a bulk of devices, then no bootstrap is needed. See <link> Cloud of Things for further information.

:**› Inherits**: :ref:`Object <object_Object>`

Overview
********

Properties
++++++++++

.. hlist::
  :columns: 1

  * :ref:`bootstrapPassword <property_CloudOfThingsDeviceRegistrator_bootstrapPassword>`
  * :ref:`bootstrapUser <property_CloudOfThingsDeviceRegistrator_bootstrapUser>`
  * :ref:`isRegistered <property_CloudOfThingsDeviceRegistrator_isRegistered>`
  * :ref:`password <property_CloudOfThingsDeviceRegistrator_password>`
  * :ref:`state <property_CloudOfThingsDeviceRegistrator_state>`
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

Enumerations
++++++++++++

.. hlist::
  :columns: 1

  * :ref:`State <enum_CloudOfThingsDeviceRegistrator_State>`



Properties
**********


.. _property_CloudOfThingsDeviceRegistrator_bootstrapPassword:

.. _signal_CloudOfThingsDeviceRegistrator_bootstrapPasswordChanged:

.. index::
   single: bootstrapPassword

bootstrapPassword
+++++++++++++++++

This property holds the bootstrap password.

:**› Type**: String
:**› Signal**: bootstrapPasswordChanged()
:**› Attributes**: Writable


.. _property_CloudOfThingsDeviceRegistrator_bootstrapUser:

.. _signal_CloudOfThingsDeviceRegistrator_bootstrapUserChanged:

.. index::
   single: bootstrapUser

bootstrapUser
+++++++++++++

This property holds the bootstrap user name. Only necessary if no pre registration is possible and :ref:`isRegistered <property_CloudOfThingsDeviceRegistrator_isRegistered>` equals ``false``.

:**› Type**: String
:**› Signal**: bootstrapUserChanged()
:**› Attributes**: Writable


.. _property_CloudOfThingsDeviceRegistrator_isRegistered:

.. _signal_CloudOfThingsDeviceRegistrator_isRegisteredChanged:

.. index::
   single: isRegistered

isRegistered
++++++++++++

This property holds whether the device is registered for example in a bulk registration (isRegistered equals ``true``) or it has to register itself (isRegistered equals ``false``).

:**› Type**: Boolean
:**› Default**: ``false``
:**› Signal**: isRegisteredChanged()
:**› Attributes**: Writable


.. _property_CloudOfThingsDeviceRegistrator_password:

.. _signal_CloudOfThingsDeviceRegistrator_passwordChanged:

.. index::
   single: password

password
++++++++

This property holds the password for registered devices.

:**› Type**: String
:**› Signal**: passwordChanged()
:**› Attributes**: Writable


.. _property_CloudOfThingsDeviceRegistrator_state:

.. _signal_CloudOfThingsDeviceRegistrator_stateChanged:

.. index::
   single: state

state
+++++

This property holds the state of registration.

:**› Type**: :ref:`State <enum_CloudOfThingsDeviceRegistrator_State>`
:**› Default**: :ref:`CloudOfThingsDeviceRegistrator.Unregistered <enumitem_CloudOfThingsDeviceRegistrator_Unregistered>`
:**› Signal**: stateChanged()
:**› Attributes**: Writable

Enumerations
************


.. _enum_CloudOfThingsDeviceRegistrator_State:

.. index::
   single: State

State
+++++

This enumeration describes the state of the registration of the Cloud of Things Client. This object is used to register new devices in Cloud of Things and deal with the bootstrap.

.. index::
   single: CloudOfThingsDeviceRegistrator.Unregistered
.. index::
   single: CloudOfThingsDeviceRegistrator.WaitingForAccept
.. index::
   single: CloudOfThingsDeviceRegistrator.Reconnecting
.. index::
   single: CloudOfThingsDeviceRegistrator.Registered
.. list-table::
  :widths: auto
  :header-rows: 1

  * - Name
    - Value
    - Description

      .. _enumitem_CloudOfThingsDeviceRegistrator_Unregistered:
  * - ``CloudOfThingsDeviceRegistrator.Unregistered``
    - ``0``
    - Initial state, no other information found.

      .. _enumitem_CloudOfThingsDeviceRegistrator_WaitingForAccept:
  * - ``CloudOfThingsDeviceRegistrator.WaitingForAccept``
    - ``1``
    - The device is known to Cloud of Things, but it is waiting for accept.

      .. _enumitem_CloudOfThingsDeviceRegistrator_Reconnecting:
  * - ``CloudOfThingsDeviceRegistrator.Reconnecting``
    - ``2``
    - After the device is accepted, a reconnect is performed to use the new credentials.

      .. _enumitem_CloudOfThingsDeviceRegistrator_Registered:
  * - ``CloudOfThingsDeviceRegistrator.Registered``
    - ``3``
    - The device is known to Cloud of Things and working.


.. _example_CloudOfThingsDeviceRegistrator:


Example
*******

.. code-block:: qml

    import InCore.Foundation 2.0
    import InCore.CloudOfThings 2.0
    
    Application {
    
        //settings object which store credentials if available
        Settings {
            id: settings
            category: "deviceCredentials"
            property bool isPreregistered: false
            property bool devicePassword
        }
    
        CloudOfThingsClient {
            id: client
            tenant: "mustercloud"
            transport {
                tenantForMQTT: "nb-iot"
    
                //log important state changes
                onConnected: console.log( "Cloud of Things client connected" )
                onErrorChanged: console.log( "error occurred", errorString )
            }
    
            registrator {
                isRegistered: settings.isPreregistered
    
                //bootstrap credentials - used if device is not yet registered
                bootstrapUser: "deviceBootstrap"
                bootstrapPassword: "b@@tstrapP4ssword"
    
                //password if device is registered - otherwise ignored
                password: settings.devicePassword
            }
    
            //do your stuff here
            /*
            CloudOfThingsMeasurementWriter
            {
                ...
            }
            */
        }
    }
    