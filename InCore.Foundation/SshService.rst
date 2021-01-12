
.. _object_SshService:


:index:`SshService`
-------------------

Description
***********

The SshService object represents the OpenSSH server service. When enabled/started the device can be accessed by any SSH and SCP clients. For security reasons this service should only be enabled and used during development. In production a running SSH service is a potential security risk and should be avoided under all circumstances.

:**› Inherits**: :ref:`SystemService <object_SystemService>`

Overview
********

Properties
++++++++++

.. hlist::
  :columns: 1

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
  * :ref:`Object.fromJson() <method_Object_fromJson>`
  * :ref:`Object.toJson() <method_Object_toJson>`

Signals
+++++++

.. hlist::
  :columns: 1

  * :ref:`Object.completed() <signal_Object_completed>`



Properties
**********

Example
*******
See :ref:`SystemService example <example_SystemService>` on how to use SshService.
