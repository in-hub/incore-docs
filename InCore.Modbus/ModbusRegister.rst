
.. _object_ModbusRegister:


:index:`ModbusRegister`
-----------------------

Description
***********

The ModbusRegister object encapsulates a modbus register or a array of it. This can be used for example to read a character string with 20 characters in 10 consecutive registers. The :ref:`DataObject.dataType <property_DataObject_dataType>` has to be set to work properly. Unlike the default value in the :ref:`DataObject <object_DataObject>` base class the the data type defaults to :ref:`DataObject.UnsignedSmallInteger <enumitem_DataObject_UnsignedSmallInteger>` for all :ref:`ModbusRegister <object_ModbusRegister>` objects. Always check :ref:`byteOrder <property_ModbusRegister_byteOrder>` and :ref:`registerOrder <property_ModbusRegister_registerOrder>` if you encounter any problems.

:**› Inherits**: :ref:`DataObject <object_DataObject>`

Overview
********

Properties
++++++++++

.. hlist::
  :columns: 3

  * :ref:`address <property_ModbusRegister_address>`
  * :ref:`byteOrder <property_ModbusRegister_byteOrder>`
  * :ref:`count <property_ModbusRegister_count>`
  * :ref:`enabled <property_ModbusRegister_enabled>`
  * :ref:`error <property_ModbusRegister_error>`
  * :ref:`errorString <property_ModbusRegister_errorString>`
  * :ref:`registerOrder <property_ModbusRegister_registerOrder>`
  * :ref:`type <property_ModbusRegister_type>`
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

  * :ref:`pollData() <method_ModbusRegister_pollData>`
  * :ref:`DataObject.touch() <method_DataObject_touch>`
  * :ref:`Object.deserializeProperties() <method_Object_deserializeProperties>`
  * :ref:`Object.fromJson() <method_Object_fromJson>`
  * :ref:`Object.serializeProperties() <method_Object_serializeProperties>`
  * :ref:`Object.toJson() <method_Object_toJson>`

Signals
+++++++

.. hlist::
  :columns: 1

  * :ref:`errorOccurred() <signal_ModbusRegister_errorOccurred>`
  * :ref:`Object.completed() <signal_Object_completed>`

Enumerations
++++++++++++

.. hlist::
  :columns: 1

  * :ref:`ByteOrder <enum_ModbusRegister_ByteOrder>`
  * :ref:`Error <enum_ModbusRegister_Error>`
  * :ref:`RegisterOrder <enum_ModbusRegister_RegisterOrder>`
  * :ref:`Type <enum_ModbusRegister_Type>`
  * :ref:`DataObject.DataType <enum_DataObject_DataType>`



Properties
**********


.. _property_ModbusRegister_address:

.. _signal_ModbusRegister_addressChanged:

.. index::
   single: address

address
+++++++

This property holds the address of the register to poll.

:**› Type**: SignedInteger
:**› Default**: ``-1``
:**› Signal**: addressChanged()
:**› Attributes**: Writable


.. _property_ModbusRegister_byteOrder:

.. _signal_ModbusRegister_byteOrderChanged:

.. index::
   single: byteOrder

byteOrder
+++++++++

This property holds the byte order which is used to combine two bytes to one 16-bit register. Transmitted data ``0xDE 0xAD`` would be interpreted as unsigned integer as ``57005`` (`BigEndian`) or ``44510`` (`LittleEndian`).

:**› Type**: :ref:`ByteOrder <enum_ModbusRegister_ByteOrder>`
:**› Default**: :ref:`ModbusRegister.LittleEndian <enumitem_ModbusRegister_LittleEndian>`
:**› Signal**: byteOrderChanged()
:**› Attributes**: Writable


.. _property_ModbusRegister_count:

.. _signal_ModbusRegister_countChanged:

.. index::
   single: count

count
+++++

This property holds the number of contiguous entries to poll at once. This number has to be a multiple of the size needed by :ref:`DataObject.dataType <property_DataObject_dataType>` to work properly. For example :ref:`count <property_ModbusRegister_count>` has to be ``2`` to poll one single float, for a string containing 5 characters it has to be ``3`` (2 character per register + 1 padding). Be carefull with :ref:`byteOrder <property_ModbusRegister_byteOrder>` and :ref:`registerOrder <property_ModbusRegister_registerOrder>`.

:**› Type**: SignedInteger
:**› Default**: ``1``
:**› Signal**: countChanged()
:**› Attributes**: Writable


.. _property_ModbusRegister_enabled:

.. _signal_ModbusRegister_enabledChanged:

.. index::
   single: enabled

enabled
+++++++

This property holds whether the register is enabled. Poll will work only if :ref:`enabled <property_ModbusRegister_enabled>` is ``true``.

:**› Type**: Boolean
:**› Default**: ``true``
:**› Signal**: enabledChanged()
:**› Attributes**: Writable


.. _property_ModbusRegister_error:

.. _signal_ModbusRegister_errorChanged:

.. index::
   single: error

error
+++++

This property holds the most recently occurred error or :ref:`ModbusRegister.NoError <enumitem_ModbusRegister_NoError>` if no error occurred. If the same error occurs multiple times this property does not change. Use the :ref:`errorOccurred() <signal_ModbusRegister_errorOccurred>` signal to detect multiple occurrences of the same error.

:**› Type**: :ref:`Error <enum_ModbusRegister_Error>`
:**› Signal**: errorChanged()
:**› Attributes**: Readonly


.. _property_ModbusRegister_errorString:

.. _signal_ModbusRegister_errorStringChanged:

.. index::
   single: errorString

errorString
+++++++++++

This property holds the current human readable error string corresponding to the current value in the :ref:`error <property_ModbusRegister_error>` property. It may include additional information such as failure reasons or locations.

:**› Type**: String
:**› Signal**: errorStringChanged()
:**› Attributes**: Readonly


.. _property_ModbusRegister_registerOrder:

.. _signal_ModbusRegister_registerOrderChanged:

.. index::
   single: registerOrder

registerOrder
+++++++++++++

This property holds the register order which is used when :ref:`count <property_ModbusRegister_count>` is greater than ``1``. This property is similar to :ref:`byteOrder <property_ModbusRegister_byteOrder>` but considers the order between the registers.

:**› Type**: :ref:`RegisterOrder <enum_ModbusRegister_RegisterOrder>`
:**› Default**: :ref:`ModbusRegister.MostSignificantRegisterFirst <enumitem_ModbusRegister_MostSignificantRegisterFirst>`
:**› Signal**: registerOrderChanged()
:**› Attributes**: Writable


.. _property_ModbusRegister_type:

.. _signal_ModbusRegister_typeChanged:

.. index::
   single: type

type
++++

This property holds the type of the register. Writing on input registers is not allowed.

:**› Type**: :ref:`Type <enum_ModbusRegister_Type>`
:**› Default**: :ref:`ModbusRegister.InvalidType <enumitem_ModbusRegister_InvalidType>`
:**› Signal**: typeChanged()
:**› Attributes**: Writable

Methods
*******


.. _method_ModbusRegister_pollData:

.. index::
   single: pollData

pollData()
++++++++++

This method polls the :ref:`DataObject.data <property_DataObject_data>` property. It is called automatically when using a :ref:`Polling <object_Polling>` property modifier on this property and usually does not have to be called manually.


Signals
*******


.. _signal_ModbusRegister_errorOccurred:

.. index::
   single: errorOccurred

errorOccurred()
+++++++++++++++

This signal is emitted whenever an error has occurred, regardless of whether the :ref:`error <property_ModbusRegister_error>` property has changed or not. In contrast to the change notification signal of the :ref:`error <property_ModbusRegister_error>` property this signal is also emitted several times if a certain error occurs several times in succession.


Enumerations
************


.. _enum_ModbusRegister_ByteOrder:

.. index::
   single: ByteOrder

ByteOrder
+++++++++

This enumeration describes the supported byte orders.

.. index::
   single: ModbusRegister.BigEndian
.. index::
   single: ModbusRegister.LittleEndian
.. list-table::
  :widths: auto
  :header-rows: 1

  * - Name
    - Value
    - Description

      .. _enumitem_ModbusRegister_BigEndian:
  * - ``ModbusRegister.BigEndian``
    - ``0``
    - The Most Significant Byte is stored first (in lowest address).

      .. _enumitem_ModbusRegister_LittleEndian:
  * - ``ModbusRegister.LittleEndian``
    - ``1``
    - The Least Significant Byte is stored first.


.. _enum_ModbusRegister_Error:

.. index::
   single: Error

Error
+++++

This enumeration describes all errors which can occur in ModbusRegister objects. The most recently occurred error is stored in the :ref:`error <property_ModbusRegister_error>` property.

.. index::
   single: ModbusRegister.NoError
.. index::
   single: ModbusRegister.InvalidSlaveError
.. index::
   single: ModbusRegister.SlaveDisabledError
.. index::
   single: ModbusRegister.UnsupportedDataTypeError
.. list-table::
  :widths: auto
  :header-rows: 1

  * - Name
    - Value
    - Description

      .. _enumitem_ModbusRegister_NoError:
  * - ``ModbusRegister.NoError``
    - ``0``
    - No error occurred or was detected.

      .. _enumitem_ModbusRegister_InvalidSlaveError:
  * - ``ModbusRegister.InvalidSlaveError``
    - ``1``
    - Can't send requests without a ModbusSlave parent.

      .. _enumitem_ModbusRegister_SlaveDisabledError:
  * - ``ModbusRegister.SlaveDisabledError``
    - ``2``
    - Can't send requests when ModbusSlave is not enabled.

      .. _enumitem_ModbusRegister_UnsupportedDataTypeError:
  * - ``ModbusRegister.UnsupportedDataTypeError``
    - ``3``
    - Selected data type is not supported for Modbus registers.


.. _enum_ModbusRegister_RegisterOrder:

.. index::
   single: RegisterOrder

RegisterOrder
+++++++++++++

This enumeration describes the supported register orders.

.. index::
   single: ModbusRegister.MostSignificantRegisterFirst
.. index::
   single: ModbusRegister.LeastSignificantRegisterFirst
.. list-table::
  :widths: auto
  :header-rows: 1

  * - Name
    - Value
    - Description

      .. _enumitem_ModbusRegister_MostSignificantRegisterFirst:
  * - ``ModbusRegister.MostSignificantRegisterFirst``
    - ``0``
    - The most significant register is stored first (in lowest address).

      .. _enumitem_ModbusRegister_LeastSignificantRegisterFirst:
  * - ``ModbusRegister.LeastSignificantRegisterFirst``
    - ``1``
    - The least significant register is stored first.


.. _enum_ModbusRegister_Type:

.. index::
   single: Type

Type
++++

This enumeration describes all supported register types

.. index::
   single: ModbusRegister.InvalidType
.. index::
   single: ModbusRegister.DiscreteInput
.. index::
   single: ModbusRegister.Coil
.. index::
   single: ModbusRegister.Input
.. index::
   single: ModbusRegister.Holding
.. list-table::
  :widths: auto
  :header-rows: 1

  * - Name
    - Value
    - Description

      .. _enumitem_ModbusRegister_InvalidType:
  * - ``ModbusRegister.InvalidType``
    - ``0``
    - This type is an invalid type.

      .. _enumitem_ModbusRegister_DiscreteInput:
  * - ``ModbusRegister.DiscreteInput``
    - ``1``
    - 1-bit single input.

      .. _enumitem_ModbusRegister_Coil:
  * - ``ModbusRegister.Coil``
    - ``2``
    - 1-bit input/output.

      .. _enumitem_ModbusRegister_Input:
  * - ``ModbusRegister.Input``
    - ``3``
    - 16-bit input only.

      .. _enumitem_ModbusRegister_Holding:
  * - ``ModbusRegister.Holding``
    - ``4``
    - 16-bit input/output.


.. _example_ModbusRegister:


Example
*******

.. code-block:: qml

    import InCore.Foundation 2.5
    import InCore.Modbus 2.5
    
    Application {
    
        name: "Modbus register example"
    
        ModbusRtuMaster {
    
            ModbusSlave {
                // talk to slave with ID 5
                address: 5
    
                // read pressure from input register 7
                ModbusRegister {
                    id: pressure
                    type: ModbusRegister.Input
                    // dataType: ModbusRegister.UnsignedSmallInteger - not needed; it is default
                    address: 7
                    onDataChanged: console.log("Pressure", data)
                }
    
                // define Modbus register for a coil with an imaginary LED
                ModbusRegister {
                    id: led
                    type: ModbusRegister.Coil
                    address: 3
                }
    
                // read serial number of slave
                ModbusRegister {
                    id: serialNumber
                    type: ModbusRegister.Holding
                    dataType: ModbusRegister.String
                    byteOrder: ModbusRegister.BigEndian
                    registerOrder: ModbusRegister.LeastSignificantRegisterFirst
                    address: 200
                    // read 20 chars packed in 10 x 16-bit
                    count: 10
                    onDataChanged: console.log("serial number", data)
                }
    
                Polling on registers { interval: 100 }
            }
    
            onConnected: {
                pressure.pollData()
                led.data = true
            }
        }
    }
    