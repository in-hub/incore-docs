
.. _object_Ltc2483Adc:


:index:`Ltc2483Adc`
-------------------

Description
***********

The Ltc2483Adc object implements a driver for the I2C-based LTC2483 16 bit ∆Σ ADC. The parent of a :ref:`Ltc2483Adc <object_Ltc2483Adc>` object has to be a corresponding :ref:`I2cBus <object_I2cBus>` object.

:**› Inherits**: :ref:`I2cDevice <object_I2cDevice>`

Overview
********

Properties
++++++++++

.. hlist::
  :columns: 1

  * :ref:`error <property_Ltc2483Adc_error>`
  * :ref:`errorString <property_Ltc2483Adc_errorString>`
  * :ref:`value <property_Ltc2483Adc_value>`
  * :ref:`I2cDevice.address <property_I2cDevice_address>`
  * :ref:`Object.objectId <property_Object_objectId>`
  * :ref:`Object.parent <property_Object_parent>`

Methods
+++++++

.. hlist::
  :columns: 1

  * :ref:`pollValue() <method_Ltc2483Adc_pollValue>`
  * :ref:`I2cDevice.read() <method_I2cDevice_read>`
  * :ref:`I2cDevice.write() <method_I2cDevice_write>`
  * :ref:`Object.deserializeProperties() <method_Object_deserializeProperties>`
  * :ref:`Object.fromJson() <method_Object_fromJson>`
  * :ref:`Object.serializeProperties() <method_Object_serializeProperties>`
  * :ref:`Object.toJson() <method_Object_toJson>`

Signals
+++++++

.. hlist::
  :columns: 1

  * :ref:`errorOccurred() <signal_Ltc2483Adc_errorOccurred>`
  * :ref:`Object.completed() <signal_Object_completed>`

Enumerations
++++++++++++

.. hlist::
  :columns: 1

  * :ref:`Error <enum_Ltc2483Adc_Error>`



Properties
**********


.. _property_Ltc2483Adc_error:

.. _signal_Ltc2483Adc_errorChanged:

.. index::
   single: error

error
+++++

This property holds the most recently occurred error or :ref:`Ltc2483Adc.NoError <enumitem_Ltc2483Adc_NoError>` if no error occurred. If the same error occurs multiple times this property does not change. Use the :ref:`errorOccurred() <signal_Ltc2483Adc_errorOccurred>` signal to detect multiple occurrences of the same error.

:**› Type**: :ref:`Error <enum_Ltc2483Adc_Error>`
:**› Signal**: errorChanged()
:**› Attributes**: Readonly


.. _property_Ltc2483Adc_errorString:

.. _signal_Ltc2483Adc_errorStringChanged:

.. index::
   single: errorString

errorString
+++++++++++

This property holds the current human readable error string corresponding to the current value in the :ref:`error <property_Ltc2483Adc_error>` property. It may include additional information such as failure reasons or locations.

:**› Type**: String
:**› Signal**: errorStringChanged()
:**› Attributes**: Readonly


.. _property_Ltc2483Adc_value:

.. _signal_Ltc2483Adc_valueChanged:

.. index::
   single: value

value
+++++

This property holds the last polled ADC value.

:**› Type**: UnsignedInteger
:**› Signal**: valueChanged()
:**› Attributes**: Readonly, Requires :ref:`Polling <object_Polling>`

Methods
*******


.. _method_Ltc2483Adc_pollValue:

.. index::
   single: pollValue

pollValue()
+++++++++++

This method polls the :ref:`value <property_Ltc2483Adc_value>` property. It is called automatically when using a :ref:`Polling <object_Polling>` property modifier on this property and usually does not have to be called manually.


Signals
*******


.. _signal_Ltc2483Adc_errorOccurred:

.. index::
   single: errorOccurred

errorOccurred()
+++++++++++++++

This signal is emitted whenever an error has occurred, regardless of whether the :ref:`error <property_Ltc2483Adc_error>` property has changed or not. In contrast to the change notification signal of the :ref:`error <property_Ltc2483Adc_error>` property this signal is also emitted several times if a certain error occurs several times in succession.


Enumerations
************


.. _enum_Ltc2483Adc_Error:

.. index::
   single: Error

Error
+++++

This enumeration describes all errors which can occur in Ltc2483Adc objects. The most recently occurred error is stored in the :ref:`error <property_Ltc2483Adc_error>` property.

.. index::
   single: Ltc2483Adc.NoError
.. index::
   single: Ltc2483Adc.BusNotAvailable
.. index::
   single: Ltc2483Adc.ValueReadError
.. list-table::
  :widths: auto
  :header-rows: 1

  * - Name
    - Value
    - Description

      .. _enumitem_Ltc2483Adc_NoError:
  * - ``Ltc2483Adc.NoError``
    - ``0``
    - No error occurred or was detected.

      .. _enumitem_Ltc2483Adc_BusNotAvailable:
  * - ``Ltc2483Adc.BusNotAvailable``
    - ``1``
    - Parent is not an I2cBus object.

      .. _enumitem_Ltc2483Adc_ValueReadError:
  * - ``Ltc2483Adc.ValueReadError``
    - ``2``
    - Could not read value from ADC.


.. _example_Ltc2483Adc:


Example
*******

.. code-block:: qml

    import InCore.Foundation 2.5
    import InCore.IO 2.5
    
    Application {
        FtdiI2cBus {
            Ltc2483Adc {
                address: 0x17
                Polling on value { interval: 250 }
                onValueChanged: console.log(value)
            }
        }
    }
    