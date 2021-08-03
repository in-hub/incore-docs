
.. _object_EdgeDetector:


:index:`EdgeDetector`
---------------------

Description
***********

The EdgeDetector object provides an efficient mechanism for detecting digital signal changes on on a pin represented by the target property. The interrupt-based mechanism is only supported for properties associated with GPIO lines such as :ref:`DigitalIO.inputValue <property_DigitalIO_inputValue>` or :ref:`AnalogInput.analogFault <property_AnalogInput_analogFault>` and should be used in favor of :ref:`Polling <object_Polling>` wherever applicable.

This object was introduced in InCore 2.2.

:**› Inherits**: :ref:`PropertyModifier <object_PropertyModifier>`

Overview
********

Properties
++++++++++

.. hlist::
  :columns: 1

  * :ref:`error <property_EdgeDetector_error>`
  * :ref:`errorString <property_EdgeDetector_errorString>`
  * :ref:`PropertyModifier.targetValue <property_PropertyModifier_targetValue>`
  * :ref:`Object.objectId <property_Object_objectId>`
  * :ref:`Object.parent <property_Object_parent>`

Methods
+++++++

.. hlist::
  :columns: 1

  * :ref:`Object.deserializeProperties() <method_Object_deserializeProperties>`
  * :ref:`Object.fromJson() <method_Object_fromJson>`
  * :ref:`Object.toJson() <method_Object_toJson>`

Signals
+++++++

.. hlist::
  :columns: 1

  * :ref:`errorOccurred() <signal_EdgeDetector_errorOccurred>`
  * :ref:`fallingEdge() <signal_EdgeDetector_fallingEdge>`
  * :ref:`risingEdge() <signal_EdgeDetector_risingEdge>`
  * :ref:`Object.completed() <signal_Object_completed>`

Enumerations
++++++++++++

.. hlist::
  :columns: 1

  * :ref:`Error <enum_EdgeDetector_Error>`



Properties
**********


.. _property_EdgeDetector_error:

.. _signal_EdgeDetector_errorChanged:

.. index::
   single: error

error
+++++

This property holds the most recently occurred error or :ref:`EdgeDetector.NoError <enumitem_EdgeDetector_NoError>` if no error occurred. If the same error occurs multiple times this property does not change. Use the :ref:`errorOccurred() <signal_EdgeDetector_errorOccurred>` signal to detect multiple occurrences of the same error.

:**› Type**: :ref:`Error <enum_EdgeDetector_Error>`
:**› Signal**: errorChanged()
:**› Attributes**: Readonly


.. _property_EdgeDetector_errorString:

.. _signal_EdgeDetector_errorStringChanged:

.. index::
   single: errorString

errorString
+++++++++++

This property holds the current human readable error string corresponding to the current value in the :ref:`error <property_EdgeDetector_error>` property. It may include additional information such as failure reasons or locations.

:**› Type**: String
:**› Signal**: errorStringChanged()
:**› Attributes**: Readonly

Signals
*******


.. _signal_EdgeDetector_errorOccurred:

.. index::
   single: errorOccurred

errorOccurred()
+++++++++++++++

This signal is emitted whenever an error has occurred, regardless of whether the :ref:`error <property_EdgeDetector_error>` property has changed or not. In contrast to the change notification signal of the :ref:`error <property_EdgeDetector_error>` property this signal is also emitted several times if a certain error occurs several times in succession.



.. _signal_EdgeDetector_fallingEdge:

.. index::
   single: fallingEdge

fallingEdge()
+++++++++++++

This signal is emitted whenever a falling edge has been detected at the source pin.



.. _signal_EdgeDetector_risingEdge:

.. index::
   single: risingEdge

risingEdge()
++++++++++++

This signal is emitted whenever a rising edge has been detected at the source pin.


Enumerations
************


.. _enum_EdgeDetector_Error:

.. index::
   single: Error

Error
+++++

This enumeration describes all errors which can occur in EdgeDetector objects. The most recently occurred error is stored in the :ref:`error <property_EdgeDetector_error>` property.

.. index::
   single: EdgeDetector.NoError
.. index::
   single: EdgeDetector.NotSupportedError
.. list-table::
  :widths: auto
  :header-rows: 1

  * - Name
    - Value
    - Description

      .. _enumitem_EdgeDetector_NoError:
  * - ``EdgeDetector.NoError``
    - ``0``
    - No error occurred or was detected.

      .. _enumitem_EdgeDetector_NotSupportedError:
  * - ``EdgeDetector.NotSupportedError``
    - ``1``
    - EdgeDetector not supported for target property.

Example
*******
See :ref:`DigitalIO example <example_DigitalIO>` on how to use EdgeDetector.
