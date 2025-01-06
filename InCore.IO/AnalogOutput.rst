
.. _object_AnalogOutput:


:index:`AnalogOutput`
---------------------

Description
***********

The AnalogOutput object allows outputting a certain voltage at an analog output pin.

This object was introduced in InCore 2.8.

:**› Inherits**: :ref:`Object <object_Object>`

Overview
********

Properties
++++++++++

.. hlist::
  :columns: 1

  * :ref:`current <property_AnalogOutput_current>`
  * :ref:`error <property_AnalogOutput_error>`
  * :ref:`errorString <property_AnalogOutput_errorString>`
  * :ref:`fault <property_AnalogOutput_fault>`
  * :ref:`index <property_AnalogOutput_index>`
  * :ref:`Object.objectId <property_Object_objectId>`
  * :ref:`Object.parent <property_Object_parent>`

Methods
+++++++

.. hlist::
  :columns: 1

  * :ref:`pollFault() <method_AnalogOutput_pollFault>`
  * :ref:`Object.deserializeProperties() <method_Object_deserializeProperties>`
  * :ref:`Object.fromJson() <method_Object_fromJson>`
  * :ref:`Object.serializeProperties() <method_Object_serializeProperties>`
  * :ref:`Object.toJson() <method_Object_toJson>`

Signals
+++++++

.. hlist::
  :columns: 1

  * :ref:`errorOccurred() <signal_AnalogOutput_errorOccurred>`
  * :ref:`Object.completed() <signal_Object_completed>`

Enumerations
++++++++++++

.. hlist::
  :columns: 1

  * :ref:`Error <enum_AnalogOutput_Error>`
  * :ref:`Index <enum_AnalogOutput_Index>`



Properties
**********


.. _property_AnalogOutput_current:

.. _signal_AnalogOutput_currentChanged:

.. index::
   single: current

current
+++++++

This property holds the current to output.

:**› Type**: Float
:**› Default**: ``0``
:**› Signal**: currentChanged()
:**› Attributes**: Writable


.. _property_AnalogOutput_error:

.. _signal_AnalogOutput_errorChanged:

.. index::
   single: error

error
+++++

This property holds the most recently occurred error or :ref:`AnalogOutput.NoError <enumitem_AnalogOutput_NoError>` if no error occurred. If the same error occurs multiple times this property does not change. Use the :ref:`errorOccurred() <signal_AnalogOutput_errorOccurred>` signal to detect multiple occurrences of the same error.

:**› Type**: :ref:`Error <enum_AnalogOutput_Error>`
:**› Signal**: errorChanged()
:**› Attributes**: Readonly


.. _property_AnalogOutput_errorString:

.. _signal_AnalogOutput_errorStringChanged:

.. index::
   single: errorString

errorString
+++++++++++

This property holds the current human readable error string corresponding to the current value in the :ref:`error <property_AnalogOutput_error>` property. It may include additional information such as failure reasons or locations.

:**› Type**: String
:**› Signal**: errorStringChanged()
:**› Attributes**: Readonly


.. _property_AnalogOutput_fault:

.. _signal_AnalogOutput_faultChanged:

.. index::
   single: fault

fault
+++++

This property holds the current state of the analog output's fault pin.

:**› Type**: Boolean
:**› Signal**: faultChanged()
:**› Attributes**: Readonly, Requires :ref:`Polling <object_Polling>`


.. _property_AnalogOutput_index:

.. _signal_AnalogOutput_indexChanged:

.. index::
   single: index

index
+++++

This property holds the index of the input. This property has to be set to work properly.

:**› Type**: :ref:`Index <enum_AnalogOutput_Index>`
:**› Default**: :ref:`AnalogOutput.Invalid <enumitem_AnalogOutput_Invalid>`
:**› Signal**: indexChanged()
:**› Attributes**: Writable

Methods
*******


.. _method_AnalogOutput_pollFault:

.. index::
   single: pollFault

pollFault()
+++++++++++

This method polls the :ref:`fault <property_AnalogOutput_fault>` property. It is called automatically when using a :ref:`Polling <object_Polling>` property modifier on this property and usually does not have to be called manually.


Signals
*******


.. _signal_AnalogOutput_errorOccurred:

.. index::
   single: errorOccurred

errorOccurred()
+++++++++++++++

This signal is emitted whenever an error has occurred, regardless of whether the :ref:`error <property_AnalogOutput_error>` property has changed or not. In contrast to the change notification signal of the :ref:`error <property_AnalogOutput_error>` property this signal is also emitted several times if a certain error occurs several times in succession.


Enumerations
************


.. _enum_AnalogOutput_Error:

.. index::
   single: Error

Error
+++++

This enumeration describes all errors which can occur in AnalogOutput objects. The most recently occurred error is stored in the :ref:`error <property_AnalogOutput_error>` property.

.. index::
   single: AnalogOutput.NoError
.. index::
   single: AnalogOutput.HardwareDriverNotAvailable
.. list-table::
  :widths: auto
  :header-rows: 1

  * - Name
    - Value
    - Description

      .. _enumitem_AnalogOutput_NoError:
  * - ``AnalogOutput.NoError``
    - ``0``
    - No error occurred or was detected.

      .. _enumitem_AnalogOutput_HardwareDriverNotAvailable:
  * - ``AnalogOutput.HardwareDriverNotAvailable``
    - ``1``
    - No hardware driver available for this device.


.. _enum_AnalogOutput_Index:

.. index::
   single: Index

Index
+++++

This enumeration describes the supported analog output indexes.

.. index::
   single: AnalogOutput.Invalid
.. index::
   single: AnalogOutput.AOUT1
.. index::
   single: AnalogOutput.AOUT2
.. list-table::
  :widths: auto
  :header-rows: 1

  * - Name
    - Value
    - Description

      .. _enumitem_AnalogOutput_Invalid:
  * - ``AnalogOutput.Invalid``
    - ``0``
    - No index assigned.

      .. _enumitem_AnalogOutput_AOUT1:
  * - ``AnalogOutput.AOUT1``
    - ``1``
    - The first analog output.

      .. _enumitem_AnalogOutput_AOUT2:
  * - ``AnalogOutput.AOUT2``
    - ``2``
    - The second analog output.

