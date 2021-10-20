
.. _object_Select:


:index:`Select`
---------------

Description
***********

The Select object is a :ref:`PropertyModifier <object_PropertyModifier>` object which reduces a source list to a single value using an arbitrary :ref:`expression <property_Select_eval>`. The expression is evaluated for each element in the source list and the final result written to the target property. Select manages strong bindings between elements in the source list, the expression and the reduced value, i.e. whenever either an element in the source list or other variable parts of the evaluated expression change the target property is being updated instantly.

:ref:`Select <object_Select>` primarily is designed to use with :ref:`DataObject <object_DataObject>` lists. :ref:`Select <object_Select>` replaces traditional ``for`` loops in a declarative manner which often allows simplifying the code and thus reduce its complexity.

:**› Inherits**: :ref:`PropertyModifier <object_PropertyModifier>`

Overview
********

Properties
++++++++++

.. hlist::
  :columns: 2

  * :ref:`defaultValue <property_Select_defaultValue>`
  * :ref:`error <property_Select_error>`
  * :ref:`errorString <property_Select_errorString>`
  * :ref:`eval <property_Select_eval>`
  * :ref:`select <property_Select_select>`
  * :ref:`source <property_Select_source>`
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

  * :ref:`errorOccurred() <signal_Select_errorOccurred>`
  * :ref:`Object.completed() <signal_Object_completed>`

Enumerations
++++++++++++

.. hlist::
  :columns: 1

  * :ref:`Error <enum_Select_Error>`



Properties
**********


.. _property_Select_defaultValue:

.. _signal_Select_defaultValueChanged:

.. index::
   single: defaultValue

defaultValue
++++++++++++

This property holds a value to write to the target in case :ref:`select <property_Select_select>` does not evaluate to ``true`` for any source list element.

This property was introduced in InCore 2.0.

:**› Type**: Variant
:**› Signal**: defaultValueChanged()
:**› Attributes**: Writable


.. _property_Select_error:

.. _signal_Select_errorChanged:

.. index::
   single: error

error
+++++

This property holds the most recently occurred error or :ref:`Select.NoError <enumitem_Select_NoError>` if no error occurred. If the same error occurs multiple times this property does not change. Use the :ref:`errorOccurred() <signal_Select_errorOccurred>` signal to detect multiple occurrences of the same error.

:**› Type**: :ref:`Error <enum_Select_Error>`
:**› Signal**: errorChanged()
:**› Attributes**: Readonly


.. _property_Select_errorString:

.. _signal_Select_errorStringChanged:

.. index::
   single: errorString

errorString
+++++++++++

This property holds the current human readable error string corresponding to the current value in the :ref:`error <property_Select_error>` property. It may include additional information such as failure reasons or locations.

:**› Type**: String
:**› Signal**: errorStringChanged()
:**› Attributes**: Readonly


.. _property_Select_eval:

.. _signal_Select_evalChanged:

.. index::
   single: eval

eval
++++

This property holds an expression which is evaluated for the selected element in the source list. The respective source list element is available in a local ``item`` property inside the expression. This allows transforming the selected item or select subproperties. If unset the item itself is written to the target.

:**› Type**: <QML expression>
:**› Signal**: evalChanged()
:**› Attributes**: Writable, Optional


.. _property_Select_select:

.. _signal_Select_selectChanged:

.. index::
   single: select

select
++++++

This property holds an expression which is used to select a list item. The expression is evaluated for each item and needs to evaluate to ``true`` for the particular item to select and write to the target.

:**› Type**: <QML expression>
:**› Signal**: selectChanged()
:**› Attributes**: Writable


.. _property_Select_source:

.. _signal_Select_sourceChanged:

.. index::
   single: source

source
++++++

This property holds a reference to an arbitrary object list or value :ref:`List <object_List>` which to select an item from.

:**› Type**: <QML expression>
:**› Signal**: sourceChanged()
:**› Attributes**: Writable

Signals
*******


.. _signal_Select_errorOccurred:

.. index::
   single: errorOccurred

errorOccurred()
+++++++++++++++

This signal is emitted whenever an error has occurred, regardless of whether the :ref:`error <property_Select_error>` property has changed or not. In contrast to the change notification signal of the :ref:`error <property_Select_error>` property this signal is also emitted several times if a certain error occurs several times in succession.


Enumerations
************


.. _enum_Select_Error:

.. index::
   single: Error

Error
+++++

This enumeration describes all errors which can occur in Select objects. The most recently occurred error is stored in the :ref:`error <property_Select_error>` property.

.. index::
   single: Select.NoError
.. index::
   single: Select.InvalidSource
.. index::
   single: Select.ExpressionError
.. index::
   single: Select.TargetWriteError
.. list-table::
  :widths: auto
  :header-rows: 1

  * - Name
    - Value
    - Description

      .. _enumitem_Select_NoError:
  * - ``Select.NoError``
    - ``0``
    - No error occurred or was detected.

      .. _enumitem_Select_InvalidSource:
  * - ``Select.InvalidSource``
    - ``1``
    - Operation not supported for empty or non-list source.

      .. _enumitem_Select_ExpressionError:
  * - ``Select.ExpressionError``
    - ``2``
    - Error while evaluating select or eval expression: <Unknown File>: .

      .. _enumitem_Select_TargetWriteError:
  * - ``Select.TargetWriteError``
    - ``3``
    - The result value could not be written to the target property, likely due to type incompatibilities.


.. _example_Select:


Example
*******

.. code-block:: qml

    import InCore.Foundation 2.5
    
    Application {
    
        List {
            id: simpleValueList
            items: [ 10, 20, 30 ]
        }
    
        property int simpleValue
        Select on simpleValue {
            source: simpleValueList
            select: item > 20
        }
    
        onSimpleValueChanged: console.log("Selected simple value:", simpleValue)
    
        MeasurementGroup {
            id: measurements
            Measurement { name: "A"; data: 1 }
            Measurement { name: "B"; data: 2 }
            Measurement { name: "C"; data: 3 }
            Measurement { name: "D"; data: 4 }
            Measurement { name: "E"; data: 5 }
        }
    
        property int measurementValue
        Select on measurementValue {
            source: measurements.objects
            select: item.name === "C"
            eval: item.data
        }
    
        onMeasurementValueChanged: console.log("Selected measurement value:", measurementValue)
    
        property var threshold: 3
        property bool anyMeasurementExceedsThreshold: false
    
        Select on anyMeasurementExceedsThreshold {
            defaultValue: false
            source: measurements.objects
            select: item.data > threshold
            eval: true
        }
    
        onAnyMeasurementExceedsThresholdChanged: {
            if(anyMeasurementExceedsThreshold)
                console.log("There's at least one measurement above", threshold)
            else
                console.log("There's no measurement above", threshold)
        }
    
        Timer {
            onTriggered: threshold++
        }
    }
    