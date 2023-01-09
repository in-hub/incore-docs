
.. _object_DockerService:


:index:`DockerService`
----------------------

Description
***********

The DockerService object is a :ref:`SystemService <object_SystemService>` which manages Docker containers. On instantiation it initializes all :ref:`DockerObject <object_DockerObject>` objects attached to its :ref:`containers <property_DockerService_containers>` and starts all enabled :ref:`containers <property_DockerService_containers>` afterards.

:**› Inherits**: :ref:`SystemService <object_SystemService>`

Overview
********

Properties
++++++++++

.. hlist::
  :columns: 2

  * :ref:`containers <property_DockerService_containers>`
  * :ref:`error <property_DockerService_error>`
  * :ref:`errorString <property_DockerService_errorString>`
  * :ref:`password <property_DockerService_password>`
  * :ref:`registry <property_DockerService_registry>`
  * :ref:`username <property_DockerService_username>`
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
  :columns: 2

  * :ref:`login() <method_DockerService_login>`
  * :ref:`logout() <method_DockerService_logout>`
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

  * :ref:`containersDataChanged() <signal_DockerService_containersDataChanged>`
  * :ref:`errorOccurred() <signal_DockerService_errorOccurred>`
  * :ref:`Object.completed() <signal_Object_completed>`

Enumerations
++++++++++++

.. hlist::
  :columns: 1

  * :ref:`Error <enum_DockerService_Error>`



Properties
**********


.. _property_DockerService_containers:

.. _signal_DockerService_containersChanged:

.. index::
   single: containers

containers
++++++++++

This property holds a list of Docker containers to manage and start.

:**› Type**: :ref:`List <object_List>`\<:ref:`DockerContainer <object_DockerContainer>`>
:**› Signal**: containersChanged()
:**› Attributes**: Readonly


.. _property_DockerService_error:

.. _signal_DockerService_errorChanged:

.. index::
   single: error

error
+++++

This property holds the most recently occurred error or :ref:`DockerContainer.NoError <enumitem_DockerContainer_NoError>` if no error occurred. If the same error occurs multiple times this property does not change. Use the :ref:`errorOccurred() <signal_DockerService_errorOccurred>` signal to detect multiple occurrences of the same error.

:**› Type**: :ref:`Error <enum_DockerService_Error>`
:**› Signal**: errorChanged()
:**› Attributes**: Readonly


.. _property_DockerService_errorString:

.. _signal_DockerService_errorStringChanged:

.. index::
   single: errorString

errorString
+++++++++++

This property holds the current human readable error string corresponding to the current value in the :ref:`error <property_DockerService_error>` property. It may include additional information such as failure reasons or locations.

:**› Type**: String
:**› Signal**: errorStringChanged()
:**› Attributes**: Readonly


.. _property_DockerService_password:

.. _signal_DockerService_passwordChanged:

.. index::
   single: password

password
++++++++

This property holds the password used to login to the Docker :ref:`registry <property_DockerService_registry>`.

This property was introduced in InCore 1.1.

:**› Type**: String
:**› Signal**: passwordChanged()
:**› Attributes**: Writable


.. _property_DockerService_registry:

.. _signal_DockerService_registryChanged:

.. index::
   single: registry

registry
++++++++

This property holds the name of a registry, i.e. the server name, to login with :ref:`username <property_DockerService_username>` and :ref:`password <property_DockerService_password>`. See the `official Docker documentation on docker login <https://docs.docker.com/engine/reference/commandline/login/>`_ for details.

This property was introduced in InCore 1.1.

:**› Type**: String
:**› Signal**: registryChanged()
:**› Attributes**: Writable


.. _property_DockerService_username:

.. _signal_DockerService_usernameChanged:

.. index::
   single: username

username
++++++++

This property holds the username used to login to the Docker :ref:`registry <property_DockerService_registry>`.

This property was introduced in InCore 1.1.

:**› Type**: String
:**› Signal**: usernameChanged()
:**› Attributes**: Writable

Methods
*******


.. _method_DockerService_login:

.. index::
   single: login

login()
+++++++

This method logs in to a Docker :ref:`registry <property_DockerService_registry>`. This method is called on instantiation automatically and usually does not have to be called manually. It returns ``true`` if the login was successful. Otherwise ``false`` is returned and :ref:`error <property_DockerService_error>` is set to :ref:`DockerService.LoginError <enumitem_DockerService_LoginError>`.

This method was introduced in InCore 1.1.

:**› Returns**: Boolean



.. _method_DockerService_logout:

.. index::
   single: logout

logout()
++++++++

This method logs out from a Docker :ref:`registry <property_DockerService_registry>`.

This method was introduced in InCore 1.1.


Signals
*******


.. _signal_DockerService_containersDataChanged:

.. index::
   single: containersDataChanged

containersDataChanged(SignedInteger index)
++++++++++++++++++++++++++++++++++++++++++

This signal is emitted whenever the :ref:`List.dataChanged() <signal_List_dataChanged>` signal is emitted, i.e. the item at ``index`` in the :ref:`containers <property_DockerService_containers>` list itself emitted the dataChanged() signal.



.. _signal_DockerService_errorOccurred:

.. index::
   single: errorOccurred

errorOccurred()
+++++++++++++++

This signal is emitted whenever an error has occurred, regardless of whether the :ref:`error <property_DockerService_error>` property has changed or not. In contrast to the change notification signal of the :ref:`error <property_DockerService_error>` property this signal is also emitted several times if a certain error occurs several times in succession.


Enumerations
************


.. _enum_DockerService_Error:

.. index::
   single: Error

Error
+++++

This enumeration describes all errors which can occur in DockerContainer objects. The most recently occurred error is stored in the :ref:`error <property_DockerService_error>` property.

.. index::
   single: DockerService.NoError
.. index::
   single: DockerService.LoginError
.. list-table::
  :widths: auto
  :header-rows: 1

  * - Name
    - Value
    - Description

      .. _enumitem_DockerService_NoError:
  * - ``DockerService.NoError``
    - ``0``
    - No error occurred or was detected.

      .. _enumitem_DockerService_LoginError:
  * - ``DockerService.LoginError``
    - ``1``
    - Docker registry login failed, likely due to invalid credentials.

Example
*******
See :ref:`DockerContainer example <example_DockerContainer>` on how to use DockerService.
