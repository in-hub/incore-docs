
.. _object_BackplaneBus:


:index:`BackplaneBus`
---------------------

Description
***********

The BackplaneBus object represents the backplane bus and is used for device discovery.

:**› Inherits**: :ref:`Object <object_Object>`

Overview
********

Properties
++++++++++

.. hlist::
  :columns: 2

  * :ref:`communicationTimeout <property_BackplaneBus_communicationTimeout>`
  * :ref:`connectionTimeout <property_BackplaneBus_connectionTimeout>`
  * :ref:`devices <property_BackplaneBus_devices>`
  * :ref:`error <property_BackplaneBus_error>`
  * :ref:`errorString <property_BackplaneBus_errorString>`
  * :ref:`setupTimeout <property_BackplaneBus_setupTimeout>`
  * :ref:`state <property_BackplaneBus_state>`
  * :ref:`Object.objectId <property_Object_objectId>`
  * :ref:`Object.parent <property_Object_parent>`

Methods
+++++++

.. hlist::
  :columns: 1

  * :ref:`reset() <method_BackplaneBus_reset>`
  * :ref:`Object.fromJson() <method_Object_fromJson>`
  * :ref:`Object.toJson() <method_Object_toJson>`

Signals
+++++++

.. hlist::
  :columns: 1

  * :ref:`busReady() <signal_BackplaneBus_busReady>`
  * :ref:`devicesDataChanged() <signal_BackplaneBus_devicesDataChanged>`
  * :ref:`errorOccurred() <signal_BackplaneBus_errorOccurred>`
  * :ref:`Object.completed() <signal_Object_completed>`

Enumerations
++++++++++++

.. hlist::
  :columns: 1

  * :ref:`Error <enum_BackplaneBus_Error>`
  * :ref:`State <enum_BackplaneBus_State>`



Properties
**********


.. _property_BackplaneBus_communicationTimeout:

.. _signal_BackplaneBus_communicationTimeoutChanged:

.. index::
   single: communicationTimeout

communicationTimeout
++++++++++++++++++++

This property holds the timeout for communicating with the backplane bus server. If the backplane bus server does not respond to a message within the specified time, the bus is reset.

This property was introduced in InCore 1.1.

:**› Type**: SignedInteger
:**› Default**: ``5000``
:**› Signal**: communicationTimeoutChanged()
:**› Attributes**: Writable


.. _property_BackplaneBus_connectionTimeout:

.. _signal_BackplaneBus_connectionTimeoutChanged:

.. index::
   single: connectionTimeout

connectionTimeout
+++++++++++++++++

This property holds the timeout for connecting to the backplane bus server. If the backplane bus server does not respond within the specified time, the connection is retried.

:**› Type**: SignedInteger
:**› Default**: ``1000``
:**› Signal**: connectionTimeoutChanged()
:**› Attributes**: Writable


.. _property_BackplaneBus_devices:

.. _signal_BackplaneBus_devicesChanged:

.. index::
   single: devices

devices
+++++++

This property holds the list of devices on the bus to communicate with.

:**› Type**: :ref:`List <object_List>`\<:ref:`BackplaneBusDevice <object_BackplaneBusDevice>`>
:**› Signal**: devicesChanged()
:**› Attributes**: Readonly


.. _property_BackplaneBus_error:

.. _signal_BackplaneBus_errorChanged:

.. index::
   single: error

error
+++++

This property holds the most recently occurred error or :ref:`BackplaneBus.NoError <enumitem_BackplaneBus_NoError>` if no error occurred. If the same error occurs multiple times this property does not change. Use the :ref:`errorOccurred() <signal_BackplaneBus_errorOccurred>` signal to detect multiple occurrences of the same error.

:**› Type**: :ref:`Error <enum_BackplaneBus_Error>`
:**› Signal**: errorChanged()
:**› Attributes**: Readonly


.. _property_BackplaneBus_errorString:

.. _signal_BackplaneBus_errorStringChanged:

.. index::
   single: errorString

errorString
+++++++++++

This property holds the current human readable error string corresponding to the current value in the :ref:`error <property_BackplaneBus_error>` property. It may include additional information such as failure reasons or locations.

:**› Type**: String
:**› Signal**: errorStringChanged()
:**› Attributes**: Readonly


.. _property_BackplaneBus_setupTimeout:

.. _signal_BackplaneBus_setupTimeoutChanged:

.. index::
   single: setupTimeout

setupTimeout
++++++++++++

This property holds the timeout for the bus setup operation in milliseconds. If the connected devices can't be detected within this time out, the backplane bus is reset and device discovery is started again.

:**› Type**: SignedInteger
:**› Default**: ``15000``
:**› Signal**: setupTimeoutChanged()
:**› Attributes**: Writable


.. _property_BackplaneBus_state:

.. _signal_BackplaneBus_stateChanged:

.. index::
   single: state

state
+++++

This property holds the current state of the backplane bus. See the :ref:`State <enum_BackplaneBus_State>` enumeration for details.

:**› Type**: :ref:`State <enum_BackplaneBus_State>`
:**› Default**: :ref:`BackplaneBus.Unconnected <enumitem_BackplaneBus_Unconnected>`
:**› Signal**: stateChanged()
:**› Attributes**: Readonly

Methods
*******


.. _method_BackplaneBus_reset:

.. index::
   single: reset

reset()
+++++++

This method Restarts the backplane bus server, resets the connection to it and restarts the device discovery process.


Signals
*******


.. _signal_BackplaneBus_busReady:

.. index::
   single: busReady

busReady()
++++++++++

This signal is emitted when the bus enters the :ref:`BackplaneBus.Ready <enumitem_BackplaneBus_Ready>` state, i.e. all devices have been discovered and assigned to according :ref:`BackplaneBusDevice <object_BackplaneBusDevice>` objects.



.. _signal_BackplaneBus_devicesDataChanged:

.. index::
   single: devicesDataChanged

devicesDataChanged(SignedInteger index)
+++++++++++++++++++++++++++++++++++++++

This signal is emitted whenever the :ref:`List.dataChanged() <signal_List_dataChanged>` signal is emitted, i.e. the item at ``index`` in the :ref:`devices <property_BackplaneBus_devices>` list itself emitted the dataChanged() signal.



.. _signal_BackplaneBus_errorOccurred:

.. index::
   single: errorOccurred

errorOccurred()
+++++++++++++++

This signal is emitted whenever an error has occurred, regardless of whether the :ref:`error <property_BackplaneBus_error>` property has changed or not. In contrast to the change notification signal of the :ref:`error <property_BackplaneBus_error>` property this signal is also emitted several times if a certain error occurs several times in succession.


Enumerations
************


.. _enum_BackplaneBus_Error:

.. index::
   single: Error

Error
+++++

This enumeration describes all errors which can occur in BackplaneBus objects. The most recently occurred error is stored in the :ref:`error <property_BackplaneBus_error>` property.

.. index::
   single: BackplaneBus.NoError
.. index::
   single: BackplaneBus.ServerError
.. index::
   single: BackplaneBus.SocketError
.. list-table::
  :widths: auto
  :header-rows: 1

  * - Name
    - Value
    - Description

      .. _enumitem_BackplaneBus_NoError:
  * - ``BackplaneBus.NoError``
    - ``0``
    - No error occurred or was detected.

      .. _enumitem_BackplaneBus_ServerError:
  * - ``BackplaneBus.ServerError``
    - ``1``
    - Backplane bus server not running.

      .. _enumitem_BackplaneBus_SocketError:
  * - ``BackplaneBus.SocketError``
    - ``2``
    - Socket error: Unknown error.


.. _enum_BackplaneBus_State:

.. index::
   single: State

State
+++++

This enumeration describes the current state of the backplane bus.

.. index::
   single: BackplaneBus.Unconnected
.. index::
   single: BackplaneBus.Connecting
.. index::
   single: BackplaneBus.Discovering
.. index::
   single: BackplaneBus.Ready
.. list-table::
  :widths: auto
  :header-rows: 1

  * - Name
    - Value
    - Description

      .. _enumitem_BackplaneBus_Unconnected:
  * - ``BackplaneBus.Unconnected``
    - ``0``
    - No connection to the backplane bus server has been established.

      .. _enumitem_BackplaneBus_Connecting:
  * - ``BackplaneBus.Connecting``
    - ``1``
    - A connection to the backplane bus server is being established.

      .. _enumitem_BackplaneBus_Discovering:
  * - ``BackplaneBus.Discovering``
    - ``2``
    - Devices are being discovered on the backplane bus.

      .. _enumitem_BackplaneBus_Ready:
  * - ``BackplaneBus.Ready``
    - ``3``
    - All devices on the backplane bus have been discovered and assigned.

Example
*******
See :ref:`EnergyAddonEN100 example <example_EnergyAddonEN100>` on how to use BackplaneBus.
