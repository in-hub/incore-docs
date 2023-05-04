
.. _object_VL53L1X:


:index:`VL53L1X`
----------------

Description
***********

The VL53L1X object implements a driver for the ST VL53L1X laser-ranging sensor. The parent of a :ref:`VL53L1X <object_VL53L1X>` object has to be a corresponding :ref:`I2cBus <object_I2cBus>` object.

This object was introduced in InCore 2.7.

:**› Inherits**: :ref:`Object <object_Object>`

Overview
********

Properties
++++++++++

.. hlist::
  :columns: 2

  * :ref:`address <property_VL53L1X_address>`
  * :ref:`bus <property_VL53L1X_bus>`
  * :ref:`distance <property_VL53L1X_distance>`
  * :ref:`distanceMode <property_VL53L1X_distanceMode>`
  * :ref:`error <property_VL53L1X_error>`
  * :ref:`errorString <property_VL53L1X_errorString>`
  * :ref:`interMeasurementPeriod <property_VL53L1X_interMeasurementPeriod>`
  * :ref:`measurementTimingBudget <property_VL53L1X_measurementTimingBudget>`
  * :ref:`offset <property_VL53L1X_offset>`
  * :ref:`Object.objectId <property_Object_objectId>`
  * :ref:`Object.parent <property_Object_parent>`

Methods
+++++++

.. hlist::
  :columns: 1

  * :ref:`calibrate() <method_VL53L1X_calibrate>`
  * :ref:`pollDistance() <method_VL53L1X_pollDistance>`
  * :ref:`Object.deserializeProperties() <method_Object_deserializeProperties>`
  * :ref:`Object.fromJson() <method_Object_fromJson>`
  * :ref:`Object.serializeProperties() <method_Object_serializeProperties>`
  * :ref:`Object.toJson() <method_Object_toJson>`

Signals
+++++++

.. hlist::
  :columns: 1

  * :ref:`errorOccurred() <signal_VL53L1X_errorOccurred>`
  * :ref:`Object.completed() <signal_Object_completed>`

Enumerations
++++++++++++

.. hlist::
  :columns: 1

  * :ref:`DistanceMode <enum_VL53L1X_DistanceMode>`
  * :ref:`Error <enum_VL53L1X_Error>`



Properties
**********


.. _property_VL53L1X_address:

.. _signal_VL53L1X_addressChanged:

.. index::
   single: address

address
+++++++

This property holds the I2C address of the sensor.

:**› Type**: SignedInteger
:**› Default**: ``41``
:**› Signal**: addressChanged()
:**› Attributes**: Writable


.. _property_VL53L1X_bus:

.. _signal_VL53L1X_busChanged:

.. index::
   single: bus

bus
+++

This property holds the index of the I2C bus which the sensor is attached to.

:**› Type**: SignedInteger
:**› Default**: ``0``
:**› Signal**: busChanged()
:**› Attributes**: Writable


.. _property_VL53L1X_distance:

.. _signal_VL53L1X_distanceChanged:

.. index::
   single: distance

distance
++++++++

This property holds the last distance value measured by the sensor.

:**› Type**: UnsignedInteger
:**› Signal**: distanceChanged()
:**› Attributes**: Readonly, Requires :ref:`Polling <object_Polling>`


.. _property_VL53L1X_distanceMode:

.. _signal_VL53L1X_distanceModeChanged:

.. index::
   single: distanceMode

distanceMode
++++++++++++

This property holds the distance mode in which the sensor should operate.

:**› Type**: :ref:`DistanceMode <enum_VL53L1X_DistanceMode>`
:**› Default**: :ref:`VL53L1X.UnknownDistanceMode <enumitem_VL53L1X_UnknownDistanceMode>`
:**› Signal**: distanceModeChanged()
:**› Attributes**: Writable


.. _property_VL53L1X_error:

.. _signal_VL53L1X_errorChanged:

.. index::
   single: error

error
+++++

This property holds the most recently occurred error or :ref:`VL53L1X.NoError <enumitem_VL53L1X_NoError>` if no error occurred. If the same error occurs multiple times this property does not change. Use the :ref:`errorOccurred() <signal_VL53L1X_errorOccurred>` signal to detect multiple occurrences of the same error.

:**› Type**: :ref:`Error <enum_VL53L1X_Error>`
:**› Signal**: errorChanged()
:**› Attributes**: Readonly


.. _property_VL53L1X_errorString:

.. _signal_VL53L1X_errorStringChanged:

.. index::
   single: errorString

errorString
+++++++++++

This property holds the current human readable error string corresponding to the current value in the :ref:`error <property_VL53L1X_error>` property. It may include additional information such as failure reasons or locations.

:**› Type**: String
:**› Signal**: errorStringChanged()
:**› Attributes**: Readonly


.. _property_VL53L1X_interMeasurementPeriod:

.. _signal_VL53L1X_interMeasurementPeriodChanged:

.. index::
   single: interMeasurementPeriod

interMeasurementPeriod
++++++++++++++++++++++

This property holds the time between measurements in ms (has to be >= :ref:`measurementTimingBudget <property_VL53L1X_measurementTimingBudget>`).

:**› Type**: SignedInteger
:**› Default**: ``-1``
:**› Signal**: interMeasurementPeriodChanged()
:**› Attributes**: Writable


.. _property_VL53L1X_measurementTimingBudget:

.. _signal_VL53L1X_measurementTimingBudgetChanged:

.. index::
   single: measurementTimingBudget

measurementTimingBudget
+++++++++++++++++++++++

This property holds the duration of a measurement in ms.

:**› Type**: SignedInteger
:**› Default**: ``-1``
:**› Signal**: measurementTimingBudgetChanged()
:**› Attributes**: Writable


.. _property_VL53L1X_offset:

.. _signal_VL53L1X_offsetChanged:

.. index::
   single: offset

offset
++++++

This property holds an offset added to the distance.

:**› Type**: SignedInteger
:**› Default**: ``0``
:**› Signal**: offsetChanged()
:**› Attributes**: Writable

Methods
*******


.. _method_VL53L1X_calibrate:

.. index::
   single: calibrate

calibrate(SignedInteger distance)
+++++++++++++++++++++++++++++++++



:**› Returns**: SignedInteger



.. _method_VL53L1X_pollDistance:

.. index::
   single: pollDistance

pollDistance()
++++++++++++++

This method polls the :ref:`distance <property_VL53L1X_distance>` property. It is called automatically when using a :ref:`Polling <object_Polling>` property modifier on this property and usually does not have to be called manually.


Signals
*******


.. _signal_VL53L1X_errorOccurred:

.. index::
   single: errorOccurred

errorOccurred()
+++++++++++++++

This signal is emitted whenever an error has occurred, regardless of whether the :ref:`error <property_VL53L1X_error>` property has changed or not. In contrast to the change notification signal of the :ref:`error <property_VL53L1X_error>` property this signal is also emitted several times if a certain error occurs several times in succession.


Enumerations
************


.. _enum_VL53L1X_DistanceMode:

.. index::
   single: DistanceMode

DistanceMode
++++++++++++



.. index::
   single: VL53L1X.UnknownDistanceMode
.. index::
   single: VL53L1X.ShortDistanceMode
.. index::
   single: VL53L1X.LongDistanceMode
.. list-table::
  :widths: auto
  :header-rows: 1

  * - Name
    - Value
    - Description

      .. _enumitem_VL53L1X_UnknownDistanceMode:
  * - ``VL53L1X.UnknownDistanceMode``
    - ``0``
    - 

      .. _enumitem_VL53L1X_ShortDistanceMode:
  * - ``VL53L1X.ShortDistanceMode``
    - ``1``
    - 

      .. _enumitem_VL53L1X_LongDistanceMode:
  * - ``VL53L1X.LongDistanceMode``
    - ``2``
    - 


.. _enum_VL53L1X_Error:

.. index::
   single: Error

Error
+++++

This enumeration describes all errors which can occur in VL53L1X objects. The most recently occurred error is stored in the :ref:`error <property_VL53L1X_error>` property.

.. index::
   single: VL53L1X.NoError
.. index::
   single: VL53L1X.DeviceNotFound
.. index::
   single: VL53L1X.KernelDriverNotAvailable
.. index::
   single: VL53L1X.DeviceBootTimeout
.. index::
   single: VL53L1X.WaitForInterruptFailed
.. index::
   single: VL53L1X.DataReadError
.. list-table::
  :widths: auto
  :header-rows: 1

  * - Name
    - Value
    - Description

      .. _enumitem_VL53L1X_NoError:
  * - ``VL53L1X.NoError``
    - ``0``
    - No error occurred or was detected.

      .. _enumitem_VL53L1X_DeviceNotFound:
  * - ``VL53L1X.DeviceNotFound``
    - ``1``
    - Device not found.

      .. _enumitem_VL53L1X_KernelDriverNotAvailable:
  * - ``VL53L1X.KernelDriverNotAvailable``
    - ``2``
    - Kernel driver not available or accessible.

      .. _enumitem_VL53L1X_DeviceBootTimeout:
  * - ``VL53L1X.DeviceBootTimeout``
    - ``3``
    - Device boot timed out.

      .. _enumitem_VL53L1X_WaitForInterruptFailed:
  * - ``VL53L1X.WaitForInterruptFailed``
    - ``4``
    - Waiting for device interrupt failed.

      .. _enumitem_VL53L1X_DataReadError:
  * - ``VL53L1X.DataReadError``
    - ``5``
    - Could not read data from the sensor.

