
.. _object_ReduceList:


:index:`ReduceList`
-------------------

Description
***********

The ReduceList object is a :ref:`PropertyModifier <object_PropertyModifier>` object which reduces a source list to a single value using an arbitrary :ref:`expression <property_ReduceList_eval>`. The expression is evaluated for each element in the source list and the final result written to the target property. ReduceList manages strong bindings between elements in the source list, the expression and the reduced value, i.e. whenever either an element in the source list or other variable parts of the evaluated expression change the target property is being updated instantly.

:ref:`ReduceList <object_ReduceList>` primarily is designed to use with :ref:`DataObject <object_DataObject>` lists. :ref:`ReduceList <object_ReduceList>` replaces traditional ``for`` loops in a declarative manner which often allows simplifying the code and thus reduce its complexity.

:**› Inherits**: :ref:`PropertyModifier <object_PropertyModifier>`

Overview
********

Properties
++++++++++

.. hlist::
  :columns: 2

  * :ref:`accumulatorInitValue <property_ReduceList_accumulatorInitValue>`
  * :ref:`error <property_ReduceList_error>`
  * :ref:`errorString <property_ReduceList_errorString>`
  * :ref:`eval <property_ReduceList_eval>`
  * :ref:`source <property_ReduceList_source>`
  * :ref:`PropertyModifier.targetValue <property_PropertyModifier_targetValue>`
  * :ref:`Object.objectId <property_Object_objectId>`
  * :ref:`Object.parent <property_Object_parent>`

Methods
+++++++

.. hlist::
  :columns: 1

  * :ref:`Object.deserializeProperties() <method_Object_deserializeProperties>`
  * :ref:`Object.fromJson() <method_Object_fromJson>`
  * :ref:`Object.serializeProperties() <method_Object_serializeProperties>`
  * :ref:`Object.toJson() <method_Object_toJson>`

Signals
+++++++

.. hlist::
  :columns: 1

  * :ref:`errorOccurred() <signal_ReduceList_errorOccurred>`
  * :ref:`Object.completed() <signal_Object_completed>`

Enumerations
++++++++++++

.. hlist::
  :columns: 1

  * :ref:`Error <enum_ReduceList_Error>`



Properties
**********


.. _property_ReduceList_accumulatorInitValue:

.. _signal_ReduceList_accumulatorInitValueChanged:

.. index::
   single: accumulatorInitValue

accumulatorInitValue
++++++++++++++++++++

This property holds the initial value for the accumulator. It should be set even for default values (such as ``false``, ``0`` or ``""``) so that the type for accumulator can be determined properly.

:**› Type**: Variant
:**› Signal**: accumulatorInitValueChanged()
:**› Attributes**: Writable


.. _property_ReduceList_error:

.. _signal_ReduceList_errorChanged:

.. index::
   single: error

error
+++++

This property holds the most recently occurred error or :ref:`ReduceList.NoError <enumitem_ReduceList_NoError>` if no error occurred. If the same error occurs multiple times this property does not change. Use the :ref:`errorOccurred() <signal_ReduceList_errorOccurred>` signal to detect multiple occurrences of the same error.

:**› Type**: :ref:`Error <enum_ReduceList_Error>`
:**› Signal**: errorChanged()
:**› Attributes**: Readonly


.. _property_ReduceList_errorString:

.. _signal_ReduceList_errorStringChanged:

.. index::
   single: errorString

errorString
+++++++++++

This property holds the current human readable error string corresponding to the current value in the :ref:`error <property_ReduceList_error>` property. It may include additional information such as failure reasons or locations.

:**› Type**: String
:**› Signal**: errorStringChanged()
:**› Attributes**: Readonly


.. _property_ReduceList_eval:

.. _signal_ReduceList_evalChanged:

.. index::
   single: eval

eval
++++

This property holds an expression which is evaluated for each element in the source list. The respective source list element is available in a local ``item`` property inside the expression. The result of the expression is written to a local accumulator property which can be read again in the next iteration. After the last element has been processed the accumulator value is written to the target property. The expression is reevaluated whenever the source list element or other parts of the expression change. The target property will therefore always be up-to-date automatically.

:**› Type**: <QML expression>
:**› Signal**: evalChanged()
:**› Attributes**: Writable


.. _property_ReduceList_source:

.. _signal_ReduceList_sourceChanged:

.. index::
   single: source

source
++++++

This property holds a reference to an arbitrary object list or value :ref:`List <object_List>` which to perform the reduce operation on.

:**› Type**: Variant
:**› Signal**: sourceChanged()
:**› Attributes**: Writable

Signals
*******


.. _signal_ReduceList_errorOccurred:

.. index::
   single: errorOccurred

errorOccurred()
+++++++++++++++

This signal is emitted whenever an error has occurred, regardless of whether the :ref:`error <property_ReduceList_error>` property has changed or not. In contrast to the change notification signal of the :ref:`error <property_ReduceList_error>` property this signal is also emitted several times if a certain error occurs several times in succession.


Enumerations
************


.. _enum_ReduceList_Error:

.. index::
   single: Error

Error
+++++

This enumeration describes all errors which can occur in ReduceList objects. The most recently occurred error is stored in the :ref:`error <property_ReduceList_error>` property.

.. index::
   single: ReduceList.NoError
.. index::
   single: ReduceList.InvalidSource
.. index::
   single: ReduceList.EvalExpressionError
.. index::
   single: ReduceList.TargetWriteError
.. list-table::
  :widths: auto
  :header-rows: 1

  * - Name
    - Value
    - Description

      .. _enumitem_ReduceList_NoError:
  * - ``ReduceList.NoError``
    - ``0``
    - No error occurred or was detected.

      .. _enumitem_ReduceList_InvalidSource:
  * - ``ReduceList.InvalidSource``
    - ``1``
    - Operation not supported for empty or non-list source.

      .. _enumitem_ReduceList_EvalExpressionError:
  * - ``ReduceList.EvalExpressionError``
    - ``2``
    - Error while evaluating expression:: <Unknown File>: .

      .. _enumitem_ReduceList_TargetWriteError:
  * - ``ReduceList.TargetWriteError``
    - ``3``
    - The result value could not be written to the target property, likely due to type incompatibilities.


.. _example_ReduceList:


Example
*******

.. code-block:: qml

    import InCore.Foundation 2.5
    
    Application {
    
        List {
            id: simpleValueList
            items: [ 1, 2, 3 ]
        }
    
        property int listSum: 0;
    
        ReduceList on listSum {
            accumulatorInitValue: 0
            source: simpleValueList
            eval: accumulator + item
        }
    
        onListSumChanged: console.log("List value sum:", listSum)
    
        MeasurementGroup {
            id: temperatures
            Measurement { id: temp1; data: 3 }
            Measurement { id: temp2; data: 4 }
            Measurement { id: temp3; data: 5 }
        }
    
        property bool dangerOfFrost: false
    
        ReduceList on dangerOfFrost {
            accumulatorInitValue: false
            source: temperatures.objects
            eval: accumulator || item.data < 3
        }
    
        onDangerOfFrostChanged: console.log("Danger of frost:", dangerOfFrost)
    
        onCompleted: {
            console.log("Updating value list item")
            simpleValueList.setItem( 2, 123 );
    
            console.log("Decreasing temperature")
            temp1.data--;
            console.log("Increasing temperature")
            temp1.data++;
        }
    }
    