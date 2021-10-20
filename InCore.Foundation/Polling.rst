
.. _object_Polling:


:index:`Polling`
----------------

Description
***********

The Polling object is a :ref:`property modifier <object_PropertyModifier>` which polls the target property at a given :ref:`interval <property_Polling_interval>`. It normally is applied on value properties of sensor, input and fieldbus register objects. Some high level objects also support polling collections of subobjects such as a list of registers or whole hardware entities. If a particular property can't be polled the :ref:`error <property_Polling_error>` property will be set to :ref:`Polling.NotSupportedError <enumitem_Polling_NotSupportedError>`.

.. note:: Once a property has been polled it will only be updated by subsequent pollings, i.e. using the :ref:`Polling <object_Polling>` modifier or by calling the corresponding poll method for the property. Reading the property in non-declarative code (e.g. event handlers) will return a cached value in order to prevent duplicate operations.

:**› Inherits**: :ref:`PropertyModifier <object_PropertyModifier>`

Overview
********

Properties
++++++++++

.. hlist::
  :columns: 2

  * :ref:`error <property_Polling_error>`
  * :ref:`errorString <property_Polling_errorString>`
  * :ref:`interval <property_Polling_interval>`
  * :ref:`running <property_Polling_running>`
  * :ref:`timestamp <property_Polling_timestamp>`
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

  * :ref:`errorOccurred() <signal_Polling_errorOccurred>`
  * :ref:`Object.completed() <signal_Object_completed>`

Enumerations
++++++++++++

.. hlist::
  :columns: 1

  * :ref:`Error <enum_Polling_Error>`



Properties
**********


.. _property_Polling_error:

.. _signal_Polling_errorChanged:

.. index::
   single: error

error
+++++

This property holds the most recently occurred error or :ref:`Polling.NoError <enumitem_Polling_NoError>` if no error occurred. If the same error occurs multiple times this property does not change. Use the :ref:`errorOccurred() <signal_Polling_errorOccurred>` signal to detect multiple occurrences of the same error.

:**› Type**: :ref:`Error <enum_Polling_Error>`
:**› Signal**: errorChanged()
:**› Attributes**: Readonly


.. _property_Polling_errorString:

.. _signal_Polling_errorStringChanged:

.. index::
   single: errorString

errorString
+++++++++++

This property holds the current human readable error string corresponding to the current value in the :ref:`error <property_Polling_error>` property. It may include additional information such as failure reasons or locations.

:**› Type**: String
:**› Signal**: errorStringChanged()
:**› Attributes**: Readonly


.. _property_Polling_interval:

.. _signal_Polling_intervalChanged:

.. index::
   single: interval

interval
++++++++

This property holds the interval in milliseconds in which the property is polled. The minimum value is ``1``.

:**› Type**: SignedInteger
:**› Default**: ``1000``
:**› Signal**: intervalChanged()
:**› Attributes**: Writable


.. _property_Polling_running:

.. _signal_Polling_runningChanged:

.. index::
   single: running

running
+++++++

This property holds whether the specified property is polled. This can be used to poll only when the corresponding entity is ready for operation (e.g. connected).

:**› Type**: Boolean
:**› Default**: ``true``
:**› Signal**: runningChanged()
:**› Attributes**: Writable


.. _property_Polling_timestamp:

.. _signal_Polling_timestampChanged:

.. index::
   single: timestamp

timestamp
+++++++++

This property holds a timestamp in milliseconds of the last successful property polling.

This property was introduced in InCore 2.5.

:**› Type**: SignedBigInteger
:**› Signal**: timestampChanged()
:**› Attributes**: Writable

Signals
*******


.. _signal_Polling_errorOccurred:

.. index::
   single: errorOccurred

errorOccurred()
+++++++++++++++

This signal is emitted whenever an error has occurred, regardless of whether the :ref:`error <property_Polling_error>` property has changed or not. In contrast to the change notification signal of the :ref:`error <property_Polling_error>` property this signal is also emitted several times if a certain error occurs several times in succession.


Enumerations
************


.. _enum_Polling_Error:

.. index::
   single: Error

Error
+++++

This enumeration describes all errors which can occur in Polling objects. The most recently occurred error is stored in the :ref:`error <property_Polling_error>` property.

.. index::
   single: Polling.NoError
.. index::
   single: Polling.NotSupportedError
.. list-table::
  :widths: auto
  :header-rows: 1

  * - Name
    - Value
    - Description

      .. _enumitem_Polling_NoError:
  * - ``Polling.NoError``
    - ``0``
    - No error occurred or was detected.

      .. _enumitem_Polling_NotSupportedError:
  * - ``Polling.NotSupportedError``
    - ``1``
    - Polling not supported for property "".


.. _example_Polling:


Example
*******

.. code-block:: qml

    import InCore.Foundation 2.5
    import InCore.IO 2.5
    
    Application {
    
        property var aboveThreshold: false
    
        // this is the output which switches 24V on or off
        DigitalIO {
            id: output
            index: DigitalIO.IO2
            direction: DigitalIO.Output
            value: aboveThreshold ? 1 : 0 // ternary if
        }
    
        // this input enables the threshold testing
        DigitalIO {
            id: enableInput
            index: DigitalIO.IO1
            direction: DigitalIO.Input
            // poll value in high frequency
            Polling on value {
                interval: 50
            }
        }
    
        AnalogInput {
            index: AnalogInput.AIN1
            // poll values if enabled
            Polling on value {
                // default interval = 1000
                running: enableInput.value === 1
            }
            onValueChanged: aboveThreshold = value > 1000 ? 1 : 0
        }
    }
    