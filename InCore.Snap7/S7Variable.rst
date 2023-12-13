
.. _object_S7Variable:


:index:`S7Variable`
-------------------

Description
***********



:**› Inherits**: :ref:`DataObject <object_DataObject>`

Overview
********

Properties
++++++++++

.. hlist::
  :columns: 3

  * :ref:`address <property_S7Variable_address>`
  * :ref:`bit <property_S7Variable_bit>`
  * :ref:`client <property_S7Variable_client>`
  * :ref:`db <property_S7Variable_db>`
  * :ref:`enabled <property_S7Variable_enabled>`
  * :ref:`error <property_S7Variable_error>`
  * :ref:`errorString <property_S7Variable_errorString>`
  * :ref:`type <property_S7Variable_type>`
  * :ref:`DataObject.data <property_DataObject_data>`
  * :ref:`DataObject.dataType <property_DataObject_dataType>`
  * :ref:`DataObject.description <property_DataObject_description>`
  * :ref:`DataObject.name <property_DataObject_name>`
  * :ref:`DataObject.timestamp <property_DataObject_timestamp>`
  * :ref:`DataObject.uuid <property_DataObject_uuid>`
  * :ref:`DataObject.view <property_DataObject_view>`
  * :ref:`Object.objectId <property_Object_objectId>`
  * :ref:`Object.parent <property_Object_parent>`

Methods
+++++++

.. hlist::
  :columns: 1

  * :ref:`pollData() <method_S7Variable_pollData>`
  * :ref:`DataObject.touch() <method_DataObject_touch>`
  * :ref:`Object.deserializeProperties() <method_Object_deserializeProperties>`
  * :ref:`Object.fromJson() <method_Object_fromJson>`
  * :ref:`Object.serializeProperties() <method_Object_serializeProperties>`
  * :ref:`Object.toJson() <method_Object_toJson>`

Signals
+++++++

.. hlist::
  :columns: 1

  * :ref:`errorOccurred() <signal_S7Variable_errorOccurred>`
  * :ref:`Object.completed() <signal_Object_completed>`

Enumerations
++++++++++++

.. hlist::
  :columns: 1

  * :ref:`Error <enum_S7Variable_Error>`
  * :ref:`Type <enum_S7Variable_Type>`
  * :ref:`DataObject.DataType <enum_DataObject_DataType>`



Properties
**********


.. _property_S7Variable_address:

.. _signal_S7Variable_addressChanged:

.. index::
   single: address

address
+++++++

This property holds the address (byte offset).

:**› Type**: SignedInteger
:**› Default**: ``0``
:**› Signal**: addressChanged()
:**› Attributes**: Writable


.. _property_S7Variable_bit:

.. _signal_S7Variable_bitChanged:

.. index::
   single: bit

bit
+++

This property holds the bit number.

:**› Type**: SignedInteger
:**› Default**: ``0``
:**› Signal**: bitChanged()
:**› Attributes**: Writable


.. _property_S7Variable_client:

.. _signal_S7Variable_clientChanged:

.. index::
   single: client

client
++++++



:**› Type**: \enum{S7Client *}
:**› Signal**: clientChanged()
:**› Attributes**: Writable


.. _property_S7Variable_db:

.. _signal_S7Variable_dbChanged:

.. index::
   single: db

db
++

This property holds the data block number.

:**› Type**: SignedInteger
:**› Default**: ``0``
:**› Signal**: dbChanged()
:**› Attributes**: Writable


.. _property_S7Variable_enabled:

.. _signal_S7Variable_enabledChanged:

.. index::
   single: enabled

enabled
+++++++

This property holds whether the variable is enabled. Poll will work only if :ref:`enabled <property_S7Variable_enabled>` is ``true``.

:**› Type**: Boolean
:**› Default**: ``true``
:**› Signal**: enabledChanged()
:**› Attributes**: Writable


.. _property_S7Variable_error:

.. _signal_S7Variable_errorChanged:

.. index::
   single: error

error
+++++

This property holds the most recently occurred error or :ref:`S7Variable.NoError <enumitem_S7Variable_NoError>` if no error occurred. If the same error occurs multiple times this property does not change. Use the :ref:`errorOccurred() <signal_S7Variable_errorOccurred>` signal to detect multiple occurrences of the same error.

:**› Type**: :ref:`Error <enum_S7Variable_Error>`
:**› Signal**: errorChanged()
:**› Attributes**: Readonly


.. _property_S7Variable_errorString:

.. _signal_S7Variable_errorStringChanged:

.. index::
   single: errorString

errorString
+++++++++++

This property holds the current human readable error string corresponding to the current value in the :ref:`error <property_S7Variable_error>` property. It may include additional information such as failure reasons or locations.

:**› Type**: String
:**› Signal**: errorStringChanged()
:**› Attributes**: Readonly


.. _property_S7Variable_type:

.. _signal_S7Variable_typeChanged:

.. index::
   single: type

type
++++

This property holds the type of this variable. It's set automatically if :ref:`DataObject.name <property_DataObject_name>` is set.

:**› Type**: :ref:`Type <enum_S7Variable_Type>`
:**› Default**: :ref:`S7Variable.InvalidType <enumitem_S7Variable_InvalidType>`
:**› Signal**: typeChanged()
:**› Attributes**: Writable

Methods
*******


.. _method_S7Variable_pollData:

.. index::
   single: pollData

pollData()
++++++++++




Signals
*******


.. _signal_S7Variable_errorOccurred:

.. index::
   single: errorOccurred

errorOccurred()
+++++++++++++++

This signal is emitted whenever an error has occurred, regardless of whether the :ref:`error <property_S7Variable_error>` property has changed or not. In contrast to the change notification signal of the :ref:`error <property_S7Variable_error>` property this signal is also emitted several times if a certain error occurs several times in succession.


Enumerations
************


.. _enum_S7Variable_Error:

.. index::
   single: Error

Error
+++++

This enumeration describes all errors which can occur in S7Variable objects. The most recently occurred error is stored in the :ref:`error <property_S7Variable_error>` property.

.. index::
   single: S7Variable.NoError
.. index::
   single: S7Variable.InvalidClientError
.. index::
   single: S7Variable.NameParseError
.. list-table::
  :widths: auto
  :header-rows: 1

  * - Name
    - Value
    - Description

      .. _enumitem_S7Variable_NoError:
  * - ``S7Variable.NoError``
    - ``0``
    - No error occurred or was detected.

      .. _enumitem_S7Variable_InvalidClientError:
  * - ``S7Variable.InvalidClientError``
    - ``1``
    - Can't send requests without a S7Client parent.

      .. _enumitem_S7Variable_NameParseError:
  * - ``S7Variable.NameParseError``
    - ``2``
    - The variable name is malformed and could not be parsed.


.. _enum_S7Variable_Type:

.. index::
   single: Type

Type
++++



.. index::
   single: S7Variable.InvalidType
.. index::
   single: S7Variable.DataBit
.. index::
   single: S7Variable.DataByte
.. index::
   single: S7Variable.DataWord
.. index::
   single: S7Variable.DataDoubleWord
.. index::
   single: S7Variable.DataInt16
.. index::
   single: S7Variable.DataInt32
.. index::
   single: S7Variable.DataReal
.. index::
   single: S7Variable.InputBit
.. index::
   single: S7Variable.InputByte
.. index::
   single: S7Variable.InputWord
.. index::
   single: S7Variable.InputDoubleWord
.. index::
   single: S7Variable.InputInt16
.. index::
   single: S7Variable.InputInt32
.. index::
   single: S7Variable.InputReal
.. index::
   single: S7Variable.OutputBit
.. index::
   single: S7Variable.OutputByte
.. index::
   single: S7Variable.OutputWord
.. index::
   single: S7Variable.OutputDoubleWord
.. index::
   single: S7Variable.OutputInt16
.. index::
   single: S7Variable.OutputInt32
.. index::
   single: S7Variable.OutputReal
.. index::
   single: S7Variable.MemoryBit
.. index::
   single: S7Variable.MemoryByte
.. index::
   single: S7Variable.MemoryWord
.. index::
   single: S7Variable.MemoryDoubleWord
.. index::
   single: S7Variable.MemoryInt16
.. index::
   single: S7Variable.MemoryInt32
.. index::
   single: S7Variable.MemoryReal
.. list-table::
  :widths: auto
  :header-rows: 1

  * - Name
    - Value
    - Description

      .. _enumitem_S7Variable_InvalidType:
  * - ``S7Variable.InvalidType``
    - ``0``
    - 

      .. _enumitem_S7Variable_DataBit:
  * - ``S7Variable.DataBit``
    - ``1``
    - 

      .. _enumitem_S7Variable_DataByte:
  * - ``S7Variable.DataByte``
    - ``2``
    - 

      .. _enumitem_S7Variable_DataWord:
  * - ``S7Variable.DataWord``
    - ``3``
    - 

      .. _enumitem_S7Variable_DataDoubleWord:
  * - ``S7Variable.DataDoubleWord``
    - ``4``
    - 

      .. _enumitem_S7Variable_DataInt16:
  * - ``S7Variable.DataInt16``
    - ``5``
    - 

      .. _enumitem_S7Variable_DataInt32:
  * - ``S7Variable.DataInt32``
    - ``6``
    - 

      .. _enumitem_S7Variable_DataReal:
  * - ``S7Variable.DataReal``
    - ``7``
    - 

      .. _enumitem_S7Variable_InputBit:
  * - ``S7Variable.InputBit``
    - ``8``
    - 

      .. _enumitem_S7Variable_InputByte:
  * - ``S7Variable.InputByte``
    - ``9``
    - 

      .. _enumitem_S7Variable_InputWord:
  * - ``S7Variable.InputWord``
    - ``10``
    - 

      .. _enumitem_S7Variable_InputDoubleWord:
  * - ``S7Variable.InputDoubleWord``
    - ``11``
    - 

      .. _enumitem_S7Variable_InputInt16:
  * - ``S7Variable.InputInt16``
    - ``12``
    - 

      .. _enumitem_S7Variable_InputInt32:
  * - ``S7Variable.InputInt32``
    - ``13``
    - 

      .. _enumitem_S7Variable_InputReal:
  * - ``S7Variable.InputReal``
    - ``14``
    - 

      .. _enumitem_S7Variable_OutputBit:
  * - ``S7Variable.OutputBit``
    - ``15``
    - 

      .. _enumitem_S7Variable_OutputByte:
  * - ``S7Variable.OutputByte``
    - ``16``
    - 

      .. _enumitem_S7Variable_OutputWord:
  * - ``S7Variable.OutputWord``
    - ``17``
    - 

      .. _enumitem_S7Variable_OutputDoubleWord:
  * - ``S7Variable.OutputDoubleWord``
    - ``18``
    - 

      .. _enumitem_S7Variable_OutputInt16:
  * - ``S7Variable.OutputInt16``
    - ``19``
    - 

      .. _enumitem_S7Variable_OutputInt32:
  * - ``S7Variable.OutputInt32``
    - ``20``
    - 

      .. _enumitem_S7Variable_OutputReal:
  * - ``S7Variable.OutputReal``
    - ``21``
    - 

      .. _enumitem_S7Variable_MemoryBit:
  * - ``S7Variable.MemoryBit``
    - ``22``
    - 

      .. _enumitem_S7Variable_MemoryByte:
  * - ``S7Variable.MemoryByte``
    - ``23``
    - 

      .. _enumitem_S7Variable_MemoryWord:
  * - ``S7Variable.MemoryWord``
    - ``24``
    - 

      .. _enumitem_S7Variable_MemoryDoubleWord:
  * - ``S7Variable.MemoryDoubleWord``
    - ``25``
    - 

      .. _enumitem_S7Variable_MemoryInt16:
  * - ``S7Variable.MemoryInt16``
    - ``26``
    - 

      .. _enumitem_S7Variable_MemoryInt32:
  * - ``S7Variable.MemoryInt32``
    - ``27``
    - 

      .. _enumitem_S7Variable_MemoryReal:
  * - ``S7Variable.MemoryReal``
    - ``28``
    - 

