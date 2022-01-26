
.. _object_OpenVpnClientService:


:index:`OpenVpnClientService`
-----------------------------

Description
***********

The OpenVpnClientService object represents an OpenVPN client service instance. When enabled/started an OpenVPN client instance for the configuration specified via the :ref:`configurationName <property_OpenVpnClientService_configurationName>` property is started. The corresponding configuration and key files have to be stored inside the ``/storage/system/openvpn/client`` directory.

:**› Inherits**: :ref:`SystemService <object_SystemService>`

Overview
********

Properties
++++++++++

.. hlist::
  :columns: 2

  * :ref:`configurationName <property_OpenVpnClientService_configurationName>`
  * :ref:`SystemService.description <property_SystemService_description>`
  * :ref:`SystemService.enabled <property_SystemService_enabled>`
  * :ref:`SystemService.name <property_SystemService_name>`
  * :ref:`SystemService.running <property_SystemService_running>`
  * :ref:`SystemService.timeout <property_SystemService_timeout>`
  * :ref:`Object.objectId <property_Object_objectId>`
  * :ref:`Object.parent <property_Object_parent>`

Methods
+++++++

.. hlist::
  :columns: 1

  * :ref:`SystemService.start() <method_SystemService_start>`
  * :ref:`SystemService.stop() <method_SystemService_stop>`
  * :ref:`Object.deserializeProperties() <method_Object_deserializeProperties>`
  * :ref:`Object.fromJson() <method_Object_fromJson>`
  * :ref:`Object.serializeProperties() <method_Object_serializeProperties>`
  * :ref:`Object.toJson() <method_Object_toJson>`

Signals
+++++++

.. hlist::
  :columns: 1

  * :ref:`Object.completed() <signal_Object_completed>`



Properties
**********


.. _property_OpenVpnClientService_configurationName:

.. _signal_OpenVpnClientService_configurationNameChanged:

.. index::
   single: configurationName

configurationName
+++++++++++++++++

This property holds the name of the configuration, i.e. the name of the OpenVPN client configuration file without the ``.conf`` or ``.ovpn`` suffix.

:**› Type**: String
:**› Signal**: configurationNameChanged()
:**› Attributes**: Writable


.. _example_OpenVpnClientService:


Example
*******

.. code-block:: qml

    import InCore.Foundation 2.5
    
    Application {
        OpenVpnClientService {
            // use OpenVPN configuration from /storage/system/openvpn/client/my-device.conf
            configurationName: "my-device"
        }
    }
    