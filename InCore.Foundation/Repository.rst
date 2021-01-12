
.. _object_Repository:


:index:`Repository`
-------------------

Description
***********

The Repository object provides access to file resources which can be used e.g. for :ref:`UpdateManager <object_UpdateManager>` instances.

:**› Inherits**: :ref:`Object <object_Object>`
:**› Inherited by**: :ref:`LocalRepository <object_LocalRepository>`

Overview
********

Properties
++++++++++

.. hlist::
  :columns: 1

  * :ref:`error <property_Repository_error>`
  * :ref:`errorString <property_Repository_errorString>`
  * :ref:`Object.objectId <property_Object_objectId>`
  * :ref:`Object.parent <property_Object_parent>`

Methods
+++++++

.. hlist::
  :columns: 1

  * :ref:`Object.fromJson() <method_Object_fromJson>`
  * :ref:`Object.toJson() <method_Object_toJson>`

Signals
+++++++

.. hlist::
  :columns: 1

  * :ref:`errorOccurred() <signal_Repository_errorOccurred>`
  * :ref:`Object.completed() <signal_Object_completed>`

Enumerations
++++++++++++

.. hlist::
  :columns: 1

  * :ref:`Error <enum_Repository_Error>`



Properties
**********


.. _property_Repository_error:

.. _signal_Repository_errorChanged:

.. index::
   single: error

error
+++++

This property holds the most recently occurred error or :ref:`Repository.NoError <enumitem_Repository_NoError>` if no error occurred. If the same error occurs multiple times this property does not change. Use the :ref:`errorOccurred() <signal_Repository_errorOccurred>` signal to detect multiple occurrences of the same error.

:**› Type**: :ref:`Error <enum_Repository_Error>`
:**› Signal**: errorChanged()
:**› Attributes**: Readonly


.. _property_Repository_errorString:

.. _signal_Repository_errorStringChanged:

.. index::
   single: errorString

errorString
+++++++++++

This property holds the current human readable error string corresponding to the current value in the :ref:`error <property_Repository_error>` property. It may include additional information such as failure reasons or locations.

:**› Type**: String
:**› Signal**: errorStringChanged()
:**› Attributes**: Readonly

Signals
*******


.. _signal_Repository_errorOccurred:

.. index::
   single: errorOccurred

errorOccurred()
+++++++++++++++

This signal is emitted whenever an error has occurred, regardless of whether the :ref:`error <property_Repository_error>` property has changed or not. In contrast to the change notification signal of the :ref:`error <property_Repository_error>` property this signal is also emitted several times if a certain error occurs several times in succession.


Enumerations
************


.. _enum_Repository_Error:

.. index::
   single: Error

Error
+++++

This enumeration describes all errors which can occur in Repository objects. The most recently occurred error is stored in the :ref:`error <property_Repository_error>` property.

.. index::
   single: Repository.NoError
.. index::
   single: Repository.ConfigurationError
.. index::
   single: Repository.TransportError
.. index::
   single: Repository.TimeoutError
.. index::
   single: Repository.Unavailable
.. list-table::
  :widths: auto
  :header-rows: 1

  * - Name
    - Value
    - Description

      .. _enumitem_Repository_NoError:
  * - ``Repository.NoError``
    - ``0``
    - No error occurred or was detected.

      .. _enumitem_Repository_ConfigurationError:
  * - ``Repository.ConfigurationError``
    - ``1``
    - Repository has not been configured properly, e.g. missing or invalid settings.

      .. _enumitem_Repository_TransportError:
  * - ``Repository.TransportError``
    - ``2``
    - The underlying transport reported an error, e.g. offline or general communication failure.

      .. _enumitem_Repository_TimeoutError:
  * - ``Repository.TimeoutError``
    - ``3``
    - A timeout occurred while fetching data from the repository.

      .. _enumitem_Repository_Unavailable:
  * - ``Repository.Unavailable``
    - ``4``
    - Repository is unavailable, e.g. offline or storage drive not plugged in.
