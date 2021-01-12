
.. _object_CanFilter:


:index:`CanFilter`
------------------

Description
***********

The CanFilter object represents a filter for CAN frames. CAN frame filtering happens at the driver and hardware level and is thus very efficient. This can be used on CAN nodes which need to receive CAN frames for their own frame id only.

This object was introduced in InCore 2.0.

:**› Inherits**: :ref:`Object <object_Object>`

Overview
********

Properties
++++++++++

.. hlist::
  :columns: 1

  * :ref:`format <property_CanFilter_format>`
  * :ref:`frameId <property_CanFilter_frameId>`
  * :ref:`frameIdMask <property_CanFilter_frameIdMask>`
  * :ref:`type <property_CanFilter_type>`
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

  * :ref:`Format <enum_CanFilter_Format>`



Properties
**********


.. _property_CanFilter_format:

.. _signal_CanFilter_formatChanged:

.. index::
   single: format

format
++++++

This property holds the frame format of the matching CAN bus frame.

:**› Type**: :ref:`Format <enum_CanFilter_Format>`
:**› Default**: :ref:`CanFilter.MatchBaseAndExtendedFormat <enumitem_CanFilter_MatchBaseAndExtendedFormat>`
:**› Signal**: formatChanged()
:**› Attributes**: Writable


.. _property_CanFilter_frameId:

.. _signal_CanFilter_frameIdChanged:

.. index::
   single: frameId

frameId
+++++++

This property holds the frame id used to filter the incoming frames.

The :ref:`frameId <property_CanFilter_frameId>` is used in conjunction with :ref:`frameIdMask <property_CanFilter_frameIdMask>`. The matching is successful if the following evaluates to ``true``:

``(receivedFrameId & frameIdMask) == (frameId & frameIdMask)``

:**› Type**: UnsignedInteger
:**› Default**: ``0``
:**› Signal**: frameIdChanged()
:**› Attributes**: Writable


.. _property_CanFilter_frameIdMask:

.. _signal_CanFilter_frameIdMaskChanged:

.. index::
   single: frameIdMask

frameIdMask
+++++++++++

This property holds the bit mask that is applied to the frame id of the filter and the received frame.

The two frame ids are matching if the following evaluates to ``true``:

``(receivedFrameId & frameIdMask) == (frameId & frameIdMask)``

:**› Type**: UnsignedInteger
:**› Default**: ``0``
:**› Signal**: frameIdMaskChanged()
:**› Attributes**: Writable


.. _property_CanFilter_type:

.. _signal_CanFilter_typeChanged:

.. index::
   single: type

type
++++

This property holds the type of the frame to be filtered. Any CAN bus frame type can be matched by setting this property to :ref:`CanFrame.InvalidFrame <enumitem_CanFrame_InvalidFrame>`. The filter object is invalid if type is equal to :ref:`CanFrame.UnknownFrame <enumitem_CanFrame_UnknownFrame>`.

:**› Type**: :ref:`CanFrame.Type <enum_CanFrame_Type>`
:**› Default**: :ref:`CanFrame.InvalidFrame <enumitem_CanFrame_InvalidFrame>`
:**› Signal**: typeChanged()
:**› Attributes**: Writable

Enumerations
************


.. _enum_CanFilter_Format:

.. index::
   single: Format

Format
++++++

This enumeration describes the format pattern, which is used to filter incoming :ref:`CanFrame <object_CanFrame>`.

.. index::
   single: CanFilter.MatchBaseFormat
.. index::
   single: CanFilter.MatchExtendedFormat
.. index::
   single: CanFilter.MatchBaseAndExtendedFormat
.. list-table::
  :widths: auto
  :header-rows: 1

  * - Name
    - Value
    - Description

      .. _enumitem_CanFilter_MatchBaseFormat:
  * - ``CanFilter.MatchBaseFormat``
    - ``1``
    - The CAN bus frame must use the base frame format (11 bit identifier).

      .. _enumitem_CanFilter_MatchExtendedFormat:
  * - ``CanFilter.MatchExtendedFormat``
    - ``2``
    - The CAN bus frame must use the extended frame format (29 bit identifier).

      .. _enumitem_CanFilter_MatchBaseAndExtendedFormat:
  * - ``CanFilter.MatchBaseAndExtendedFormat``
    - ``3``
    - The CAN bus frame can have a base or an extended frame format.


.. _example_CanFilter:


Example
*******

.. code-block:: qml

    import InCore.Foundation 2.0
    import InCore.IO 2.0
    
    Application {
    
        CanBus {
            // assume nodes encode their address in bits 8..10 and message type in bits 0..7 of the CAN frame id
            // then this configuration will make the bus receive only frames (any message type) from slave 4 and
            // error frames from any slave
            rawFilters: [
                CanFilter {
                    type: CanFrame.DataFrame
                    frameId: 4 << 8
                    frameIdMask: 0xff00
                },
                CanFilter {
                    type: CanFrame.ErrorFrame
                }
            ]
    
            onFrameReceived: {
                console.log("Received CAN frame with ID", currentFrame.frameId, "and payload", currentFrame.payload.hex)
            }
        }
    }
    