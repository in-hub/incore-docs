
.. _object_CanFrame:


:index:`CanFrame`
-----------------

Description
***********

The CanFrame object represents a CAN frame sent or received on a bus.

This object was introduced in InCore 2.0.

:**› Inherits**: :ref:`Object <object_Object>`

Overview
********

Properties
++++++++++

.. hlist::
  :columns: 2

  * :ref:`errors <property_CanFrame_errors>`
  * :ref:`extendedFrameFormat <property_CanFrame_extendedFrameFormat>`
  * :ref:`frameId <property_CanFrame_frameId>`
  * :ref:`payload <property_CanFrame_payload>`
  * :ref:`timestampMicroseconds <property_CanFrame_timestampMicroseconds>`
  * :ref:`timestampSeconds <property_CanFrame_timestampSeconds>`
  * :ref:`type <property_CanFrame_type>`
  * :ref:`valid <property_CanFrame_valid>`
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

  * :ref:`Object.completed() <signal_Object_completed>`

Enumerations
++++++++++++

.. hlist::
  :columns: 1

  * :ref:`Errors <enum_CanFrame_Errors>`
  * :ref:`Type <enum_CanFrame_Type>`



Properties
**********


.. _property_CanFrame_errors:

.. _signal_CanFrame_errorsChanged:

.. index::
   single: errors

errors
++++++

This property holds the error flags of the error frame. If the frame is not an :ref:`CanFrame.ErrorFrame <enumitem_CanFrame_ErrorFrame>`, this property remains :ref:`CanFrame.NoError <enumitem_CanFrame_NoError>`.

:**› Type**: :ref:`Errors <enum_CanFrame_Errors>`
:**› Signal**: errorsChanged()
:**› Attributes**: Writable


.. _property_CanFrame_extendedFrameFormat:

.. _signal_CanFrame_extendedFrameFormatChanged:

.. index::
   single: extendedFrameFormat

extendedFrameFormat
+++++++++++++++++++

This property holds if the CAN frame uses a 29bit identifier. If ``false``, an 11bit identifier is implied.

:**› Type**: Boolean
:**› Signal**: extendedFrameFormatChanged()
:**› Attributes**: Writable


.. _property_CanFrame_frameId:

.. _signal_CanFrame_frameIdChanged:

.. index::
   single: frameId

frameId
+++++++

This property holds the identifier of the CAN frame. The maximum size of a CAN frame identifier is 11 bits, which can be extended up to 29 bits by supporting the CAN extended frame format. The CAN extended frame format setting is automatically set when a frame identifier with more than 11 bits in size is set. When the format is extended and a frame identifier with up to 11 bits or less is set, the CAN extended frame format setting is not changed.

:**› Type**: UnsignedInteger
:**› Signal**: frameIdChanged()
:**› Attributes**: Writable


.. _property_CanFrame_payload:

.. _signal_CanFrame_payloadChanged:

.. index::
   single: payload

payload
+++++++

This property holds the payload for the CAN frame. The maximum size of payload is 8 bytes.

Frames of type :ref:`CanFrame.RemoteRequestFrame <enumitem_CanFrame_RemoteRequestFrame>` (RTR) do not have a payload. However they have to provide an indication of the responses expected payload length. To set the length expection it is necessary to set a fake payload whose length matches the expected payload length of the response.

The payload data in various representations can be accessed through the grouped :ref:`ByteArray <object_ByteArray>` properties, e.g. ``payload.data: [ 0x11, 0x22 ]`` or ``payload.string = "mydata"``.

:**› Type**: :ref:`ByteArray <object_ByteArray>`
:**› Signal**: payloadChanged()
:**› Attributes**: Readonly


.. _property_CanFrame_timestampMicroseconds:

.. _signal_CanFrame_timestampMicrosecondsChanged:

.. index::
   single: timestampMicroseconds

timestampMicroseconds
+++++++++++++++++++++

This property holds the part of the frame timestamp representing seconds.

:**› Type**: SignedBigInteger
:**› Signal**: timestampMicrosecondsChanged()
:**› Attributes**: Readonly


.. _property_CanFrame_timestampSeconds:

.. _signal_CanFrame_timestampSecondsChanged:

.. index::
   single: timestampSeconds

timestampSeconds
++++++++++++++++

This property holds the part of the frame timestamp representing seconds.

:**› Type**: SignedBigInteger
:**› Signal**: timestampSecondsChanged()
:**› Attributes**: Readonly


.. _property_CanFrame_type:

.. _signal_CanFrame_typeChanged:

.. index::
   single: type

type
++++

This property holds the type of the CAN frame. See the :ref:`Type <enum_CanFrame_Type>` enumeration for details.

:**› Type**: :ref:`Type <enum_CanFrame_Type>`
:**› Default**: :ref:`CanFrame.DataFrame <enumitem_CanFrame_DataFrame>`
:**› Signal**: typeChanged()
:**› Attributes**: Writable


.. _property_CanFrame_valid:

.. _signal_CanFrame_validChanged:

.. index::
   single: valid

valid
+++++

This property holds whether the frame is valid. It's ``false`` if :ref:`type <property_CanFrame_type>` is :ref:`CanFrame.InvalidFrame <enumitem_CanFrame_InvalidFrame>`, :ref:`extendedFrameFormat <property_CanFrame_extendedFrameFormat>` is not set although :ref:`frameId <property_CanFrame_frameId>` is longer than 11 bit or the payload is longer than the maximum permitted payload length of 64 byte if *Flexible Data-Rate* mode is enabled or 8 byte if it is disabled. If :ref:`type <property_CanFrame_type>` is :ref:`CanFrame.RemoteRequestFrame <enumitem_CanFrame_RemoteRequestFrame>` and the *Flexible Data-Rate* mode is enabled at the same time it's set to ``false`` as well.

:**› Type**: Boolean
:**› Signal**: validChanged()
:**› Attributes**: Readonly

Enumerations
************


.. _enum_CanFrame_Errors:

.. index::
   single: Errors

Errors
++++++

This enumeration describes a combination of :ref:`Errors <enum_CanFrame_Errors>` flags. The flags represent all possible errors which can be indicated by a CAN error frame.

.. index::
   single: CanFrame.NoError
.. index::
   single: CanFrame.TransmissionTimeoutError
.. index::
   single: CanFrame.LostArbitrationError
.. index::
   single: CanFrame.ControllerError
.. index::
   single: CanFrame.ProtocolViolationError
.. index::
   single: CanFrame.TransceiverError
.. index::
   single: CanFrame.MissingAcknowledgmentError
.. index::
   single: CanFrame.BusOffError
.. index::
   single: CanFrame.BusError
.. index::
   single: CanFrame.ControllerRestartError
.. index::
   single: CanFrame.UnknownError
.. list-table::
  :widths: auto
  :header-rows: 1

  * - Name
    - Value
    - Description

      .. _enumitem_CanFrame_NoError:
  * - ``CanFrame.NoError``
    - ``0``
    - No error has occurred or CAN frame is not an error frame.

      .. _enumitem_CanFrame_TransmissionTimeoutError:
  * - ``CanFrame.TransmissionTimeoutError``
    - ``1``
    - The transmission has timed out.

      .. _enumitem_CanFrame_LostArbitrationError:
  * - ``CanFrame.LostArbitrationError``
    - ``2``
    - The frame could not be sent due to lost arbitration on the bus.

      .. _enumitem_CanFrame_ControllerError:
  * - ``CanFrame.ControllerError``
    - ``4``
    - The CAN controller encountered an error.

      .. _enumitem_CanFrame_ProtocolViolationError:
  * - ``CanFrame.ProtocolViolationError``
    - ``8``
    - A protocol violation has occurred.

      .. _enumitem_CanFrame_TransceiverError:
  * - ``CanFrame.TransceiverError``
    - ``16``
    - A transceiver error occurred.

      .. _enumitem_CanFrame_MissingAcknowledgmentError:
  * - ``CanFrame.MissingAcknowledgmentError``
    - ``32``
    - The transmission received no acknowledgment.

      .. _enumitem_CanFrame_BusOffError:
  * - ``CanFrame.BusOffError``
    - ``64``
    - The CAN bus is offline.

      .. _enumitem_CanFrame_BusError:
  * - ``CanFrame.BusError``
    - ``128``
    - A CAN bus error occurred.

      .. _enumitem_CanFrame_ControllerRestartError:
  * - ``CanFrame.ControllerRestartError``
    - ``256``
    - The controller restarted.

      .. _enumitem_CanFrame_UnknownError:
  * - ``CanFrame.UnknownError``
    - ``512``
    - An unknown error has occurred.


.. _enum_CanFrame_Type:

.. index::
   single: Type

Type
++++

This enumeration describes the type of a CAN frame

.. index::
   single: CanFrame.UnknownFrame
.. index::
   single: CanFrame.DataFrame
.. index::
   single: CanFrame.ErrorFrame
.. index::
   single: CanFrame.RemoteRequestFrame
.. index::
   single: CanFrame.InvalidFrame
.. list-table::
  :widths: auto
  :header-rows: 1

  * - Name
    - Value
    - Description

      .. _enumitem_CanFrame_UnknownFrame:
  * - ``CanFrame.UnknownFrame``
    - ``0``
    - The frame type is unknown.

      .. _enumitem_CanFrame_DataFrame:
  * - ``CanFrame.DataFrame``
    - ``1``
    - This value represents a data frame.

      .. _enumitem_CanFrame_ErrorFrame:
  * - ``CanFrame.ErrorFrame``
    - ``2``
    - This value represents an error frame.

      .. _enumitem_CanFrame_RemoteRequestFrame:
  * - ``CanFrame.RemoteRequestFrame``
    - ``3``
    - This value represents a remote request.

      .. _enumitem_CanFrame_InvalidFrame:
  * - ``CanFrame.InvalidFrame``
    - ``4``
    - This value represents an invalid frame. This type is used for error reporting.

Example
*******
See :ref:`CanBus example <example_CanBus>` on how to use CanFrame.
