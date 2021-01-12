
.. _object_DockerObject:


:index:`DockerObject`
---------------------

Description
***********

The DockerObject object provides common properties and methods for all kinds of Docker resources such as :ref:`DockerMount <object_DockerMount>`, :ref:`DockerNetwork <object_DockerNetwork>` and :ref:`DockerVolume <object_DockerVolume>`.

:**› Inherits**: :ref:`Object <object_Object>`
:**› Inherited by**: :ref:`DockerNetwork <object_DockerNetwork>`, :ref:`DockerVolume <object_DockerVolume>`

Overview
********

Properties
++++++++++

.. hlist::
  :columns: 1

  * :ref:`driver <property_DockerObject_driver>`
  * :ref:`error <property_DockerObject_error>`
  * :ref:`errorString <property_DockerObject_errorString>`
  * :ref:`name <property_DockerObject_name>`
  * :ref:`options <property_DockerObject_options>`
  * :ref:`Object.objectId <property_Object_objectId>`
  * :ref:`Object.parent <property_Object_parent>`

Methods
+++++++

.. hlist::
  :columns: 1

  * :ref:`create() <method_DockerObject_create>`
  * :ref:`remove() <method_DockerObject_remove>`
  * :ref:`Object.fromJson() <method_Object_fromJson>`
  * :ref:`Object.toJson() <method_Object_toJson>`

Signals
+++++++

.. hlist::
  :columns: 1

  * :ref:`errorOccurred() <signal_DockerObject_errorOccurred>`
  * :ref:`Object.completed() <signal_Object_completed>`

Enumerations
++++++++++++

.. hlist::
  :columns: 1

  * :ref:`Error <enum_DockerObject_Error>`



Properties
**********


.. _property_DockerObject_driver:

.. _signal_DockerObject_driverChanged:

.. index::
   single: driver

driver
++++++

This property holds the name of the driver used to provide this object. This depends on the type of the defined object. See the object-specific documentation for details.

:**› Type**: String
:**› Signal**: driverChanged()
:**› Attributes**: Writable


.. _property_DockerObject_error:

.. _signal_DockerObject_errorChanged:

.. index::
   single: error

error
+++++

This property holds the most recently occurred error or :ref:`DockerObject.NoError <enumitem_DockerObject_NoError>` if no error occurred. If the same error occurs multiple times this property does not change. Use the :ref:`errorOccurred() <signal_DockerObject_errorOccurred>` signal to detect multiple occurrences of the same error.

:**› Type**: :ref:`Error <enum_DockerObject_Error>`
:**› Signal**: errorChanged()
:**› Attributes**: Readonly


.. _property_DockerObject_errorString:

.. _signal_DockerObject_errorStringChanged:

.. index::
   single: errorString

errorString
+++++++++++

This property holds the current human readable error string corresponding to the current value in the :ref:`error <property_DockerObject_error>` property. It may include additional information such as failure reasons or locations.

:**› Type**: String
:**› Signal**: errorStringChanged()
:**› Attributes**: Readonly


.. _property_DockerObject_name:

.. _signal_DockerObject_nameChanged:

.. index::
   single: name

name
++++

This property holds the name of the object to define. This identifier usually may only consist of alphanumeric identifiers.

:**› Type**: String
:**› Signal**: nameChanged()
:**› Attributes**: Writable


.. _property_DockerObject_options:

.. _signal_DockerObject_optionsChanged:

.. index::
   single: options

options
+++++++

This property holds a list of options used by the driver. This depends on the type of the defined object and driver. See the object-specific documentation for details.

:**› Type**: StringList
:**› Signal**: optionsChanged()
:**› Attributes**: Writable

Methods
*******


.. _method_DockerObject_create:

.. index::
   single: create

create()
++++++++

This method creates the described object, e.g. a Docker volume or network. Returns ``true`` on success. Otherwise it returns ``false`` if the object could not be created. In this case the :ref:`error <property_DockerObject_error>` property indicates the failure reason.

:**› Returns**: Boolean



.. _method_DockerObject_remove:

.. index::
   single: remove

remove()
++++++++

This method removes the described object, e.g. a Docker volume or network. Returns ``true`` on success. Otherwise it returns ``false`` if the object could not be removed. In this case the :ref:`error <property_DockerObject_error>` property indicates the failure reason.

:**› Returns**: Boolean


Signals
*******


.. _signal_DockerObject_errorOccurred:

.. index::
   single: errorOccurred

errorOccurred()
+++++++++++++++

This signal is emitted whenever an error has occurred, regardless of whether the :ref:`error <property_DockerObject_error>` property has changed or not. In contrast to the change notification signal of the :ref:`error <property_DockerObject_error>` property this signal is also emitted several times if a certain error occurs several times in succession.


Enumerations
************


.. _enum_DockerObject_Error:

.. index::
   single: Error

Error
+++++

This enumeration describes all errors which can occur in DockerObject objects. The most recently occurred error is stored in the :ref:`error <property_DockerObject_error>` property.

.. index::
   single: DockerObject.NoError
.. index::
   single: DockerObject.ServiceNotFound
.. index::
   single: DockerObject.ServiceNotRunning
.. index::
   single: DockerObject.InvalidName
.. index::
   single: DockerObject.ObjectCreationError
.. list-table::
  :widths: auto
  :header-rows: 1

  * - Name
    - Value
    - Description

      .. _enumitem_DockerObject_NoError:
  * - ``DockerObject.NoError``
    - ``0``
    - No error occurred or was detected.

      .. _enumitem_DockerObject_ServiceNotFound:
  * - ``DockerObject.ServiceNotFound``
    - ``1``
    - Service not found (parent is not a DockerService).

      .. _enumitem_DockerObject_ServiceNotRunning:
  * - ``DockerObject.ServiceNotRunning``
    - ``2``
    - DockerService not enabled or not running.

      .. _enumitem_DockerObject_InvalidName:
  * - ``DockerObject.InvalidName``
    - ``3``
    - The name property is empty or invalid.

      .. _enumitem_DockerObject_ObjectCreationError:
  * - ``DockerObject.ObjectCreationError``
    - ``4``
    - Failed to create the object.
