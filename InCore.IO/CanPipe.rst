
.. _object_CanPipe:


:index:`CanPipe`
----------------

Description
***********

The CanPipe object provides a logical data pipe between two CAN nodes. The pipe can be used to exchange arbitrarily sized messages. All messages are split into chunks to fit into the payload of a CAN frame and are transmitted as multiple :ref:`CAN frames <object_CanFrame>` if necessary.

The CAN pipe consists of two endpoints using the same :ref:`address <property_CanPipe_address>` but different :ref:`endpointType <property_CanPipe_endpointType>`.

This object was introduced in InCore 2.0.

:**› Inherits**: :ref:`IoDevice <object_IoDevice>`

Overview
********

Properties
++++++++++

.. hlist::
  :columns: 3

  * :ref:`address <property_CanPipe_address>`
  * :ref:`endpointType <property_CanPipe_endpointType>`
  * :ref:`error <property_CanPipe_error>`
  * :ref:`errorString <property_CanPipe_errorString>`
  * :ref:`receivedData <property_CanPipe_receivedData>`
  * :ref:`IoDevice.append <property_IoDevice_append>`
  * :ref:`IoDevice.atEnd <property_IoDevice_atEnd>`
  * :ref:`IoDevice.autoOpen <property_IoDevice_autoOpen>`
  * :ref:`IoDevice.bytesAvailable <property_IoDevice_bytesAvailable>`
  * :ref:`IoDevice.canReadLine <property_IoDevice_canReadLine>`
  * :ref:`IoDevice.deviceErrorString <property_IoDevice_deviceErrorString>`
  * :ref:`IoDevice.isOpen <property_IoDevice_isOpen>`
  * :ref:`IoDevice.isWritable <property_IoDevice_isWritable>`
  * :ref:`IoDevice.nameArgument <property_IoDevice_nameArgument>`
  * :ref:`IoDevice.pos <property_IoDevice_pos>`
  * :ref:`IoDevice.readOnly <property_IoDevice_readOnly>`
  * :ref:`IoDevice.size <property_IoDevice_size>`
  * :ref:`IoDevice.truncate <property_IoDevice_truncate>`
  * :ref:`IoDevice.unbuffered <property_IoDevice_unbuffered>`
  * :ref:`Object.objectId <property_Object_objectId>`
  * :ref:`Object.parent <property_Object_parent>`

Methods
+++++++

.. hlist::
  :columns: 2

  * :ref:`IoDevice.close() <method_IoDevice_close>`
  * :ref:`IoDevice.flush() <method_IoDevice_flush>`
  * :ref:`IoDevice.open() <method_IoDevice_open>`
  * :ref:`IoDevice.peekAll() <method_IoDevice_peekAll>`
  * :ref:`IoDevice.read() <method_IoDevice_read>`
  * :ref:`IoDevice.readAll() <method_IoDevice_readAll>`
  * :ref:`IoDevice.readLine() <method_IoDevice_readLine>`
  * :ref:`IoDevice.sync() <method_IoDevice_sync>`
  * :ref:`IoDevice.write() <method_IoDevice_write>`
  * :ref:`Object.fromJson() <method_Object_fromJson>`
  * :ref:`Object.toJson() <method_Object_toJson>`

Signals
+++++++

.. hlist::
  :columns: 1

  * :ref:`errorOccurred() <signal_CanPipe_errorOccurred>`
  * :ref:`IoDevice.lineAvailableForRead() <signal_IoDevice_lineAvailableForRead>`
  * :ref:`IoDevice.readyRead() <signal_IoDevice_readyRead>`
  * :ref:`Object.completed() <signal_Object_completed>`

Enumerations
++++++++++++

.. hlist::
  :columns: 1

  * :ref:`EndpointType <enum_CanPipe_EndpointType>`
  * :ref:`Error <enum_CanPipe_Error>`



Properties
**********


.. _property_CanPipe_address:

.. _signal_CanPipe_addressChanged:

.. index::
   single: address

address
+++++++

This property holds the address of the logical CAN pipe. It has to be identical on both endpoints.

:**› Type**: UnsignedInteger
:**› Signal**: addressChanged()
:**› Attributes**: Writable


.. _property_CanPipe_endpointType:

.. _signal_CanPipe_endpointTypeChanged:

.. index::
   single: endpointType

endpointType
++++++++++++

This property holds the type of the local CAN pipe endpoint. A logical CAN pipe consists of a dominant and a recessive endpoint talking to each other.

:**› Type**: :ref:`EndpointType <enum_CanPipe_EndpointType>`
:**› Default**: :ref:`CanPipe.InvalidEndpoint <enumitem_CanPipe_InvalidEndpoint>`
:**› Signal**: endpointTypeChanged()
:**› Attributes**: Writable


.. _property_CanPipe_error:

.. _signal_CanPipe_errorChanged:

.. index::
   single: error

error
+++++

This property holds the most recently occurred error or :ref:`CanPipe.NoError <enumitem_CanPipe_NoError>` if no error occurred. If the same error occurs multiple times this property does not change. Use the :ref:`errorOccurred() <signal_CanPipe_errorOccurred>` signal to detect multiple occurrences of the same error.

:**› Type**: :ref:`Error <enum_CanPipe_Error>`
:**› Signal**: errorChanged()
:**› Attributes**: Readonly


.. _property_CanPipe_errorString:

.. _signal_CanPipe_errorStringChanged:

.. index::
   single: errorString

errorString
+++++++++++

This property holds the current human readable error string corresponding to the current value in the :ref:`error <property_CanPipe_error>` property. It may include additional information such as failure reasons or locations.

:**› Type**: String
:**› Signal**: errorStringChanged()
:**› Attributes**: Readonly


.. _property_CanPipe_receivedData:

.. _signal_CanPipe_receivedDataChanged:

.. index::
   single: receivedData

receivedData
++++++++++++

This property holds the data received through this CAN pipe. This property can be used to access the received data directly instead of calling :ref:`IoDevice.read() <method_IoDevice_read>`. After processing the data make sure to remove it from the byte array, e.g. by calling :ref:`ByteArray.remove() <method_ByteArray_remove>`.

:**› Type**: :ref:`ByteArray <object_ByteArray>`
:**› Signal**: receivedDataChanged()
:**› Attributes**: Readonly

Signals
*******


.. _signal_CanPipe_errorOccurred:

.. index::
   single: errorOccurred

errorOccurred()
+++++++++++++++

This signal is emitted whenever an error has occurred, regardless of whether the :ref:`error <property_CanPipe_error>` property has changed or not. In contrast to the change notification signal of the :ref:`error <property_CanPipe_error>` property this signal is also emitted several times if a certain error occurs several times in succession.


Enumerations
************


.. _enum_CanPipe_EndpointType:

.. index::
   single: EndpointType

EndpointType
++++++++++++

This enumeration describes the type of the pipe endpoint.

.. index::
   single: CanPipe.InvalidEndpoint
.. index::
   single: CanPipe.DominantEndpoint
.. index::
   single: CanPipe.RecessiveEndpoint
.. list-table::
  :widths: auto
  :header-rows: 1

  * - Name
    - Value
    - Description

      .. _enumitem_CanPipe_InvalidEndpoint:
  * - ``CanPipe.InvalidEndpoint``
    - ``0``
    - No pipe endpoint type configured.

      .. _enumitem_CanPipe_DominantEndpoint:
  * - ``CanPipe.DominantEndpoint``
    - ``1``
    - The pipe endpoint is dominant, i.e. it has a higher priority on the CAN bus.

      .. _enumitem_CanPipe_RecessiveEndpoint:
  * - ``CanPipe.RecessiveEndpoint``
    - ``2``
    - The pipe endpoint is recessive, i.e. it has a lower priority on the CAN bus.


.. _enum_CanPipe_Error:

.. index::
   single: Error

Error
+++++

This enumeration describes all errors which can occur in CanPipe objects. The most recently occurred error is stored in the :ref:`error <property_CanPipe_error>` property.

.. index::
   single: CanPipe.NoError
.. index::
   single: CanPipe.InvalidBusError
.. list-table::
  :widths: auto
  :header-rows: 1

  * - Name
    - Value
    - Description

      .. _enumitem_CanPipe_NoError:
  * - ``CanPipe.NoError``
    - ``0``
    - No error occurred or was detected.

      .. _enumitem_CanPipe_InvalidBusError:
  * - ``CanPipe.InvalidBusError``
    - ``1``
    - Parent is not a CanBus object.

