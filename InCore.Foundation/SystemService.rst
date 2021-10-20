
.. _object_SystemService:


:index:`SystemService`
----------------------

Description
***********

The SystemService object represents a system service and allows one to :ref:`start() <method_SystemService_start>` and :ref:`stop() <method_SystemService_stop>` it and query its state through the :ref:`running <property_SystemService_running>` property. Even though it's technically possible to control any systemd-based service by setting the :ref:`name <property_SystemService_name>` property to the appropriate systemd unit name, it's recommended to use the services modeled by the inherited objects only:

* :ref:`DockerService <object_DockerService>`
* :ref:`SshService <object_SshService>`
* :ref:`WebServerService <object_WebServerService>`


:**› Inherits**: :ref:`Object <object_Object>`
:**› Inherited by**: :ref:`DockerService <object_DockerService>`, :ref:`OpenVpnClientService <object_OpenVpnClientService>`, :ref:`SshService <object_SshService>`, :ref:`WebServerService <object_WebServerService>`

Overview
********

Properties
++++++++++

.. hlist::
  :columns: 1

  * :ref:`description <property_SystemService_description>`
  * :ref:`enabled <property_SystemService_enabled>`
  * :ref:`name <property_SystemService_name>`
  * :ref:`running <property_SystemService_running>`
  * :ref:`timeout <property_SystemService_timeout>`
  * :ref:`Object.objectId <property_Object_objectId>`
  * :ref:`Object.parent <property_Object_parent>`

Methods
+++++++

.. hlist::
  :columns: 1

  * :ref:`start() <method_SystemService_start>`
  * :ref:`stop() <method_SystemService_stop>`
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


.. _property_SystemService_description:

.. _signal_SystemService_descriptionChanged:

.. index::
   single: description

description
+++++++++++

This property holds a user-defined description for the service. This property is not evaluated by the InCore framework.

:**› Type**: String
:**› Signal**: descriptionChanged()
:**› Attributes**: Writable


.. _property_SystemService_enabled:

.. _signal_SystemService_enabledChanged:

.. index::
   single: enabled

enabled
+++++++

This property holds whether the service is enabled. When enabled it's started automatically whenever the application is started.

:**› Type**: Boolean
:**› Default**: ``true``
:**› Signal**: enabledChanged()
:**› Attributes**: Writable


.. _property_SystemService_name:

.. _signal_SystemService_nameChanged:

.. index::
   single: name

name
++++

This property holds the name of the service, i.e. the systemd unit file name.

:**› Type**: String
:**› Signal**: nameChanged()
:**› Attributes**: Writable


.. _property_SystemService_running:

.. _signal_SystemService_runningChanged:

.. index::
   single: running

running
+++++++

This property holds the current state of the service. If the service is running, this property is ``true``, otherwise it's ``false``.

:**› Type**: Boolean
:**› Default**: ``false``
:**› Signal**: runningChanged()
:**› Attributes**: Readonly


.. _property_SystemService_timeout:

.. _signal_SystemService_timeoutChanged:

.. index::
   single: timeout

timeout
+++++++

This property holds a timeout in milliseconds for service-related operations such as starting and stopping.

:**› Type**: SignedInteger
:**› Default**: ``30000``
:**› Signal**: timeoutChanged()
:**› Attributes**: Writable

Methods
*******


.. _method_SystemService_start:

.. index::
   single: start

start()
+++++++

This method starts the service and returns ``true`` on success.

:**› Returns**: Boolean



.. _method_SystemService_stop:

.. index::
   single: stop

stop()
++++++

This method stops the service and returns ``true`` on success.

:**› Returns**: Boolean



.. _example_SystemService:


Example
*******

.. code-block:: qml

    import InCore.Foundation 2.5
    
    Application {
    
        Settings {
            property bool debugging: false;
        }
    
        System {
            SshService {
                enabled: debugging
            }
    
            WebServerService { }
        }
    }
    