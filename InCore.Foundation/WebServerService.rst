
.. _object_WebServerService:


:index:`WebServerService`
-------------------------

Description
***********

The WebServerService object represents the Nginx web server service. When enabled/started the device can be accessed via HTTP. The directory ``/apps/www`` is used as the webserver's root directory.

:**› Inherits**: :ref:`SystemService <object_SystemService>`

Overview
********

Properties
++++++++++

.. hlist::
  :columns: 2

  * :ref:`filesStorage <property_WebServerService_filesStorage>`
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

  * :ref:`SystemService.restart() <method_SystemService_restart>`
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


.. _property_WebServerService_filesStorage:

.. _signal_WebServerService_filesStorageChanged:

.. index::
   single: filesStorage

filesStorage
++++++++++++

This property holds a storage which can be used to store dynamically generated files which are accessible through the ``/incore`` location, e.g. ``http://192.168.123.1/incore/foo.csv``.

This property was introduced in InCore 2.1.

:**› Type**: :ref:`WebServerFilesStorage <object_WebServerFilesStorage>`
:**› Signal**: filesStorageChanged()
:**› Attributes**: Readonly

Example
*******
See :ref:`SystemService example <example_SystemService>` on how to use WebServerService.
