
.. _object_S7Client:


:index:`S7Client`
-----------------

Description
***********



:**› Inherits**: :ref:`Object <object_Object>`

Overview
********

Properties
++++++++++

.. hlist::
  :columns: 3

  * :ref:`autoConnect <property_S7Client_autoConnect>`
  * :ref:`byteOrder <property_S7Client_byteOrder>`
  * :ref:`connected <property_S7Client_connected>`
  * :ref:`connectionType <property_S7Client_connectionType>`
  * :ref:`error <property_S7Client_error>`
  * :ref:`errorString <property_S7Client_errorString>`
  * :ref:`hostname <property_S7Client_hostname>`
  * :ref:`localTsap <property_S7Client_localTsap>`
  * :ref:`moduleName <property_S7Client_moduleName>`
  * :ref:`moduleTypeName <property_S7Client_moduleTypeName>`
  * :ref:`port <property_S7Client_port>`
  * :ref:`rack <property_S7Client_rack>`
  * :ref:`remoteTsap <property_S7Client_remoteTsap>`
  * :ref:`serialNumber <property_S7Client_serialNumber>`
  * :ref:`slot <property_S7Client_slot>`
  * :ref:`Object.objectId <property_Object_objectId>`
  * :ref:`Object.parent <property_Object_parent>`

Methods
+++++++

.. hlist::
  :columns: 1

  * :ref:`connectToHost() <method_S7Client_connectToHost>`
  * :ref:`disconnectFromHost() <method_S7Client_disconnectFromHost>`
  * :ref:`Object.deserializeProperties() <method_Object_deserializeProperties>`
  * :ref:`Object.fromJson() <method_Object_fromJson>`
  * :ref:`Object.serializeProperties() <method_Object_serializeProperties>`
  * :ref:`Object.toJson() <method_Object_toJson>`

Signals
+++++++

.. hlist::
  :columns: 1

  * :ref:`errorOccurred() <signal_S7Client_errorOccurred>`
  * :ref:`Object.completed() <signal_Object_completed>`

Enumerations
++++++++++++

.. hlist::
  :columns: 1

  * :ref:`ByteOrder <enum_S7Client_ByteOrder>`
  * :ref:`ConnectionType <enum_S7Client_ConnectionType>`
  * :ref:`Error <enum_S7Client_Error>`



Properties
**********


.. _property_S7Client_autoConnect:

.. _signal_S7Client_autoConnectChanged:

.. index::
   single: autoConnect

autoConnect
+++++++++++

This property holds whether the S7 client should connect to the S7 server automatically. Keeping this option enabled will also make the client reconnect on connection errors.

:**› Type**: Boolean
:**› Default**: ``true``
:**› Signal**: autoConnectChanged()
:**› Attributes**: Writable


.. _property_S7Client_byteOrder:

.. _signal_S7Client_byteOrderChanged:

.. index::
   single: byteOrder

byteOrder
+++++++++

This property holds the byte order of the data read from or written to the PLC.

This property was introduced in InCore 2.8.

:**› Type**: :ref:`ByteOrder <enum_S7Client_ByteOrder>`
:**› Default**: :ref:`S7Client.BigEndian <enumitem_S7Client_BigEndian>`
:**› Signal**: byteOrderChanged()
:**› Attributes**: Writable


.. _property_S7Client_connected:

.. _signal_S7Client_connectedChanged:

.. index::
   single: connected

connected
+++++++++

This property holds whether the S7 client is connected to the S7 server.

:**› Type**: Boolean
:**› Default**: ``false``
:**› Signal**: connectedChanged()
:**› Attributes**: Writable


.. _property_S7Client_connectionType:

.. _signal_S7Client_connectionTypeChanged:

.. index::
   single: connectionType

connectionType
++++++++++++++

This property holds the connection type which to use for conneting to the S7 server.

:**› Type**: :ref:`ConnectionType <enum_S7Client_ConnectionType>`
:**› Default**: :ref:`S7Client.PG <enumitem_S7Client_PG>`
:**› Signal**: connectionTypeChanged()
:**› Attributes**: Writable


.. _property_S7Client_error:

.. _signal_S7Client_errorChanged:

.. index::
   single: error

error
+++++

This property holds the most recently occurred error or :ref:`S7Client.NoError <enumitem_S7Client_NoError>` if no error occurred. If the same error occurs multiple times this property does not change. Use the :ref:`errorOccurred() <signal_S7Client_errorOccurred>` signal to detect multiple occurrences of the same error.

:**› Type**: :ref:`Error <enum_S7Client_Error>`
:**› Signal**: errorChanged()
:**› Attributes**: Readonly


.. _property_S7Client_errorString:

.. _signal_S7Client_errorStringChanged:

.. index::
   single: errorString

errorString
+++++++++++

This property holds the current human readable error string corresponding to the current value in the :ref:`error <property_S7Client_error>` property. It may include additional information such as failure reasons or locations.

:**› Type**: String
:**› Signal**: errorStringChanged()
:**› Attributes**: Readonly


.. _property_S7Client_hostname:

.. _signal_S7Client_hostnameChanged:

.. index::
   single: hostname

hostname
++++++++

This property holds the hostname of the S7 server to connect to.

:**› Type**: String
:**› Signal**: hostnameChanged()
:**› Attributes**: Writable


.. _property_S7Client_localTsap:

.. _signal_S7Client_localTsapChanged:

.. index::
   single: localTsap

localTsap
+++++++++



:**› Type**: SignedInteger
:**› Default**: ``256``
:**› Signal**: localTsapChanged()
:**› Attributes**: Writable


.. _property_S7Client_moduleName:

.. _signal_S7Client_moduleNameChanged:

.. index::
   single: moduleName

moduleName
++++++++++



:**› Type**: String
:**› Signal**: moduleNameChanged()
:**› Attributes**: Readonly


.. _property_S7Client_moduleTypeName:

.. _signal_S7Client_moduleTypeNameChanged:

.. index::
   single: moduleTypeName

moduleTypeName
++++++++++++++



:**› Type**: String
:**› Signal**: moduleTypeNameChanged()
:**› Attributes**: Readonly


.. _property_S7Client_port:

.. _signal_S7Client_portChanged:

.. index::
   single: port

port
++++

This property holds the port which the S7 server is listening at.

:**› Type**: SignedInteger
:**› Default**: ``102``
:**› Signal**: portChanged()
:**› Attributes**: Writable


.. _property_S7Client_rack:

.. _signal_S7Client_rackChanged:

.. index::
   single: rack

rack
++++



:**› Type**: SignedInteger
:**› Default**: ``0``
:**› Signal**: rackChanged()
:**› Attributes**: Writable


.. _property_S7Client_remoteTsap:

.. _signal_S7Client_remoteTsapChanged:

.. index::
   single: remoteTsap

remoteTsap
++++++++++



:**› Type**: SignedInteger
:**› Default**: ``0``
:**› Signal**: remoteTsapChanged()
:**› Attributes**: Writable


.. _property_S7Client_serialNumber:

.. _signal_S7Client_serialNumberChanged:

.. index::
   single: serialNumber

serialNumber
++++++++++++



:**› Type**: String
:**› Signal**: serialNumberChanged()
:**› Attributes**: Readonly


.. _property_S7Client_slot:

.. _signal_S7Client_slotChanged:

.. index::
   single: slot

slot
++++



:**› Type**: SignedInteger
:**› Default**: ``0``
:**› Signal**: slotChanged()
:**› Attributes**: Writable

Methods
*******


.. _method_S7Client_connectToHost:

.. index::
   single: connectToHost

connectToHost()
+++++++++++++++





.. _method_S7Client_disconnectFromHost:

.. index::
   single: disconnectFromHost

disconnectFromHost()
++++++++++++++++++++




Signals
*******


.. _signal_S7Client_errorOccurred:

.. index::
   single: errorOccurred

errorOccurred()
+++++++++++++++

This signal is emitted whenever an error has occurred, regardless of whether the :ref:`error <property_S7Client_error>` property has changed or not. In contrast to the change notification signal of the :ref:`error <property_S7Client_error>` property this signal is also emitted several times if a certain error occurs several times in succession.


Enumerations
************


.. _enum_S7Client_ByteOrder:

.. index::
   single: ByteOrder

ByteOrder
+++++++++



.. index::
   single: S7Client.BigEndian
.. index::
   single: S7Client.LittleEndian
.. list-table::
  :widths: auto
  :header-rows: 1

  * - Name
    - Value
    - Description

      .. _enumitem_S7Client_BigEndian:
  * - ``S7Client.BigEndian``
    - ``0``
    - 

      .. _enumitem_S7Client_LittleEndian:
  * - ``S7Client.LittleEndian``
    - ``1``
    - 


.. _enum_S7Client_ConnectionType:

.. index::
   single: ConnectionType

ConnectionType
++++++++++++++



.. index::
   single: S7Client.PG
.. index::
   single: S7Client.OP
.. index::
   single: S7Client.Basic
.. list-table::
  :widths: auto
  :header-rows: 1

  * - Name
    - Value
    - Description

      .. _enumitem_S7Client_PG:
  * - ``S7Client.PG``
    - ``1``
    - 

      .. _enumitem_S7Client_OP:
  * - ``S7Client.OP``
    - ``2``
    - 

      .. _enumitem_S7Client_Basic:
  * - ``S7Client.Basic``
    - ``3``
    - 


.. _enum_S7Client_Error:

.. index::
   single: Error

Error
+++++

This enumeration describes all errors which can occur in S7Client objects. The most recently occurred error is stored in the :ref:`error <property_S7Client_error>` property.

.. index::
   single: S7Client.InvalidObject
.. index::
   single: S7Client.InvalidParam
.. index::
   single: S7Client.NoError
.. index::
   single: S7Client.ConnectError
.. index::
   single: S7Client.DisconnectError
.. index::
   single: S7Client.InvalidPDU
.. index::
   single: S7Client.InvalidDataSize
.. index::
   single: S7Client.NullPointer
.. index::
   single: S7Client.ShortPacket
.. index::
   single: S7Client.TooManyFragments
.. index::
   single: S7Client.PduOverflow
.. index::
   single: S7Client.SendPacket
.. index::
   single: S7Client.RecvPacket
.. index::
   single: S7Client.InvalidTSAP
.. index::
   single: S7Client.NegotiatingPDU
.. index::
   single: S7Client.InvalidParams
.. index::
   single: S7Client.JobPending
.. index::
   single: S7Client.TooManyItems
.. index::
   single: S7Client.InvalidWordLen
.. index::
   single: S7Client.PartialDataWritten
.. index::
   single: S7Client.SizeOverPDU
.. index::
   single: S7Client.InvalidPlcAnswer
.. index::
   single: S7Client.AddressOutOfRange
.. index::
   single: S7Client.InvalidTransportSize
.. index::
   single: S7Client.WriteDataSizeMismatch
.. index::
   single: S7Client.ItemNotAvailable
.. index::
   single: S7Client.InvalidValue
.. index::
   single: S7Client.CannotStartPLC
.. index::
   single: S7Client.AlreadyRun
.. index::
   single: S7Client.CannotStopPLC
.. index::
   single: S7Client.CannotCopyRamToRom
.. index::
   single: S7Client.CannotCompress
.. index::
   single: S7Client.AlreadyStop
.. index::
   single: S7Client.FunNotAvailable
.. index::
   single: S7Client.UploadSequenceFailed
.. index::
   single: S7Client.InvalidDataSizeRecvd
.. index::
   single: S7Client.InvalidBlockType
.. index::
   single: S7Client.InvalidBlockNumber
.. index::
   single: S7Client.InvalidBlockSize
.. index::
   single: S7Client.DownloadSequenceFailed
.. index::
   single: S7Client.InsertRefused
.. index::
   single: S7Client.DeleteRefused
.. index::
   single: S7Client.NeedPassword
.. index::
   single: S7Client.InvalidPassword
.. index::
   single: S7Client.NoPasswordToSetOrClear
.. index::
   single: S7Client.JobTimeout
.. index::
   single: S7Client.PartialDataRead
.. index::
   single: S7Client.BufferTooSmall
.. index::
   single: S7Client.FunctionRefused
.. index::
   single: S7Client.Destroying
.. index::
   single: S7Client.InvalidParamNumber
.. index::
   single: S7Client.CannotChangeParam
.. list-table::
  :widths: auto
  :header-rows: 1

  * - Name
    - Value
    - Description

      .. _enumitem_S7Client_InvalidObject:
  * - ``S7Client.InvalidObject``
    - ``-2``
    - LIB: Invalid object supplied.

      .. _enumitem_S7Client_InvalidParam:
  * - ``S7Client.InvalidParam``
    - ``-1``
    - LIB: Invalid param supplied.

      .. _enumitem_S7Client_NoError:
  * - ``S7Client.NoError``
    - ``0``
    - No error occurred or was detected.

      .. _enumitem_S7Client_ConnectError:
  * - ``S7Client.ConnectError``
    - ``65536``
    - ISO: Connection error.

      .. _enumitem_S7Client_DisconnectError:
  * - ``S7Client.DisconnectError``
    - ``131072``
    - ISO: Disconnect error.

      .. _enumitem_S7Client_InvalidPDU:
  * - ``S7Client.InvalidPDU``
    - ``196608``
    - ISO: Bad PDU format.

      .. _enumitem_S7Client_InvalidDataSize:
  * - ``S7Client.InvalidDataSize``
    - ``262144``
    - ISO: Datasize passed to send/recv buffer is invalid.

      .. _enumitem_S7Client_NullPointer:
  * - ``S7Client.NullPointer``
    - ``327680``
    - ISO: Null passed as pointer.

      .. _enumitem_S7Client_ShortPacket:
  * - ``S7Client.ShortPacket``
    - ``393216``
    - ISO: A short packet received.

      .. _enumitem_S7Client_TooManyFragments:
  * - ``S7Client.TooManyFragments``
    - ``458752``
    - ISO: Too many packets without EoT flag.

      .. _enumitem_S7Client_PduOverflow:
  * - ``S7Client.PduOverflow``
    - ``524288``
    - ISO: The sum of fragments data exceded maximum packet size.

      .. _enumitem_S7Client_SendPacket:
  * - ``S7Client.SendPacket``
    - ``589824``
    - ISO: An error occurred during send.

      .. _enumitem_S7Client_RecvPacket:
  * - ``S7Client.RecvPacket``
    - ``655360``
    - ISO: An error occurred during recv.

      .. _enumitem_S7Client_InvalidTSAP:
  * - ``S7Client.InvalidTSAP``
    - ``720896``
    - ISO: Invalid connection params (wrong TSAPs).

      .. _enumitem_S7Client_NegotiatingPDU:
  * - ``S7Client.NegotiatingPDU``
    - ``1048576``
    - CPU:Error in PDU negotiation.

      .. _enumitem_S7Client_InvalidParams:
  * - ``S7Client.InvalidParams``
    - ``2097152``
    - CLI:invalid param(s) supplied.

      .. _enumitem_S7Client_JobPending:
  * - ``S7Client.JobPending``
    - ``3145728``
    - CLI:Job pending.

      .. _enumitem_S7Client_TooManyItems:
  * - ``S7Client.TooManyItems``
    - ``4194304``
    - CLI:too may items (>20) in multi read/write.

      .. _enumitem_S7Client_InvalidWordLen:
  * - ``S7Client.InvalidWordLen``
    - ``5242880``
    - CLI:invalid WordLength.

      .. _enumitem_S7Client_PartialDataWritten:
  * - ``S7Client.PartialDataWritten``
    - ``6291456``
    - CLI:Partial data written.

      .. _enumitem_S7Client_SizeOverPDU:
  * - ``S7Client.SizeOverPDU``
    - ``7340032``
    - CPU:total data exceeds the PDU size.

      .. _enumitem_S7Client_InvalidPlcAnswer:
  * - ``S7Client.InvalidPlcAnswer``
    - ``8388608``
    - CLI:invalid CPU answer.

      .. _enumitem_S7Client_AddressOutOfRange:
  * - ``S7Client.AddressOutOfRange``
    - ``9437184``
    - CPU:Address out of range.

      .. _enumitem_S7Client_InvalidTransportSize:
  * - ``S7Client.InvalidTransportSize``
    - ``10485760``
    - CPU:Invalid Transport size.

      .. _enumitem_S7Client_WriteDataSizeMismatch:
  * - ``S7Client.WriteDataSizeMismatch``
    - ``11534336``
    - CPU:Data size mismatch.

      .. _enumitem_S7Client_ItemNotAvailable:
  * - ``S7Client.ItemNotAvailable``
    - ``12582912``
    - CPU:Item not available.

      .. _enumitem_S7Client_InvalidValue:
  * - ``S7Client.InvalidValue``
    - ``13631488``
    - CPU:Invalid value supplied.

      .. _enumitem_S7Client_CannotStartPLC:
  * - ``S7Client.CannotStartPLC``
    - ``14680064``
    - CPU:Cannot start PLC.

      .. _enumitem_S7Client_AlreadyRun:
  * - ``S7Client.AlreadyRun``
    - ``15728640``
    - CPU:PLC already RUN.

      .. _enumitem_S7Client_CannotStopPLC:
  * - ``S7Client.CannotStopPLC``
    - ``16777216``
    - CPU:Cannot stop PLC.

      .. _enumitem_S7Client_CannotCopyRamToRom:
  * - ``S7Client.CannotCopyRamToRom``
    - ``17825792``
    - CPU:Cannot copy RAM to ROM.

      .. _enumitem_S7Client_CannotCompress:
  * - ``S7Client.CannotCompress``
    - ``18874368``
    - CPU:Cannot compress.

      .. _enumitem_S7Client_AlreadyStop:
  * - ``S7Client.AlreadyStop``
    - ``19922944``
    - CPU:PLC already STOP.

      .. _enumitem_S7Client_FunNotAvailable:
  * - ``S7Client.FunNotAvailable``
    - ``20971520``
    - CPU:Function not available.

      .. _enumitem_S7Client_UploadSequenceFailed:
  * - ``S7Client.UploadSequenceFailed``
    - ``22020096``
    - CPU:Upload sequence failed.

      .. _enumitem_S7Client_InvalidDataSizeRecvd:
  * - ``S7Client.InvalidDataSizeRecvd``
    - ``23068672``
    - CLI:Invalid data size received.

      .. _enumitem_S7Client_InvalidBlockType:
  * - ``S7Client.InvalidBlockType``
    - ``24117248``
    - CLI:Invalid block type.

      .. _enumitem_S7Client_InvalidBlockNumber:
  * - ``S7Client.InvalidBlockNumber``
    - ``25165824``
    - CLI:Invalid block number.

      .. _enumitem_S7Client_InvalidBlockSize:
  * - ``S7Client.InvalidBlockSize``
    - ``26214400``
    - CLI:Invalid block size.

      .. _enumitem_S7Client_DownloadSequenceFailed:
  * - ``S7Client.DownloadSequenceFailed``
    - ``27262976``
    - CPU:Download sequence failed.

      .. _enumitem_S7Client_InsertRefused:
  * - ``S7Client.InsertRefused``
    - ``28311552``
    - CPU:block insert refused.

      .. _enumitem_S7Client_DeleteRefused:
  * - ``S7Client.DeleteRefused``
    - ``29360128``
    - CPU:block delete refused.

      .. _enumitem_S7Client_NeedPassword:
  * - ``S7Client.NeedPassword``
    - ``30408704``
    - CPU:Function not authorized for current protection level.

      .. _enumitem_S7Client_InvalidPassword:
  * - ``S7Client.InvalidPassword``
    - ``31457280``
    - CPU:Invalid password.

      .. _enumitem_S7Client_NoPasswordToSetOrClear:
  * - ``S7Client.NoPasswordToSetOrClear``
    - ``32505856``
    - CPU:No password to set or clear.

      .. _enumitem_S7Client_JobTimeout:
  * - ``S7Client.JobTimeout``
    - ``33554432``
    - CLI:Job Timeout.

      .. _enumitem_S7Client_PartialDataRead:
  * - ``S7Client.PartialDataRead``
    - ``34603008``
    - CLI:Partial data read.

      .. _enumitem_S7Client_BufferTooSmall:
  * - ``S7Client.BufferTooSmall``
    - ``35651584``
    - CLI:The buffer supplied is too small to accomplish the operation.

      .. _enumitem_S7Client_FunctionRefused:
  * - ``S7Client.FunctionRefused``
    - ``36700160``
    - CLI:function refused by CPU (Unknown error).

      .. _enumitem_S7Client_Destroying:
  * - ``S7Client.Destroying``
    - ``37748736``
    - CLI:Cannot perform (destroying).

      .. _enumitem_S7Client_InvalidParamNumber:
  * - ``S7Client.InvalidParamNumber``
    - ``38797312``
    - CLI:Invalid Param Number.

      .. _enumitem_S7Client_CannotChangeParam:
  * - ``S7Client.CannotChangeParam``
    - ``39845888``
    - CLI:Cannot change this param now.

