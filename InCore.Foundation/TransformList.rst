
.. _object_TransformList:


:index:`TransformList`
----------------------

Description
***********

The TransformList object is a :ref:`PropertyModifier <object_PropertyModifier>` object which transforms a source list into a target list using an arbitrary :ref:`expression <property_TransformList_eval>`. The expression is evaluated for each element in the source list and the result is written to the corresponding element in the target list. ReduceList manages strong bindings between elements in the source list, the expression and the target list, i.e. whenever either an element in the source list or other variable parts of the evaluated expression change the target list is being updated instantly.

:ref:`TransformList <object_TransformList>` primarily is designed to use with :ref:`DataObject <object_DataObject>` lists. :ref:`TransformList <object_TransformList>` replaces traditional ``for`` loops in a declarative manner. This not only reduces the code complexity but also improves performance. When only a few elements in the source list are changed, :ref:`TransformList <object_TransformList>` will only update the corresponding elements of the target list. This saves unnecessary expression evaluations and further processings caused by the updates.

:**› Inherits**: :ref:`PropertyModifier <object_PropertyModifier>`

Overview
********

Properties
++++++++++

.. hlist::
  :columns: 1

  * :ref:`error <property_TransformList_error>`
  * :ref:`errorString <property_TransformList_errorString>`
  * :ref:`eval <property_TransformList_eval>`
  * :ref:`source <property_TransformList_source>`
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

  * :ref:`errorOccurred() <signal_TransformList_errorOccurred>`
  * :ref:`Object.completed() <signal_Object_completed>`

Enumerations
++++++++++++

.. hlist::
  :columns: 1

  * :ref:`Error <enum_TransformList_Error>`



Properties
**********


.. _property_TransformList_error:

.. _signal_TransformList_errorChanged:

.. index::
   single: error

error
+++++

This property holds the most recently occurred error or :ref:`TransformList.NoError <enumitem_TransformList_NoError>` if no error occurred. If the same error occurs multiple times this property does not change. Use the :ref:`errorOccurred() <signal_TransformList_errorOccurred>` signal to detect multiple occurrences of the same error.

:**› Type**: :ref:`Error <enum_TransformList_Error>`
:**› Signal**: errorChanged()
:**› Attributes**: Readonly


.. _property_TransformList_errorString:

.. _signal_TransformList_errorStringChanged:

.. index::
   single: errorString

errorString
+++++++++++

This property holds the current human readable error string corresponding to the current value in the :ref:`error <property_TransformList_error>` property. It may include additional information such as failure reasons or locations.

:**› Type**: String
:**› Signal**: errorStringChanged()
:**› Attributes**: Readonly


.. _property_TransformList_eval:

.. _signal_TransformList_evalChanged:

.. index::
   single: eval

eval
++++

This property holds an expression which is evaluated for each element in the source list. The respective source list element is available in a local ``item`` property inside the expression. The result of the expression is written to the corresponding element in the target list. The expression is reevaluated whenever the source list element or other parts of the expression change. The target list therefore always contains an up-to-date representation of the transformed data.

:**› Type**: <QML expression>
:**› Signal**: evalChanged()
:**› Attributes**: Writable


.. _property_TransformList_source:

.. _signal_TransformList_sourceChanged:

.. index::
   single: source

source
++++++

This property holds a list of elements to transform, i.e. a :ref:`List <object_List>` object or a reference to it.

:**› Type**: Variant
:**› Signal**: sourceChanged()
:**› Attributes**: Writable

Signals
*******


.. _signal_TransformList_errorOccurred:

.. index::
   single: errorOccurred

errorOccurred()
+++++++++++++++

This signal is emitted whenever an error has occurred, regardless of whether the :ref:`error <property_TransformList_error>` property has changed or not. In contrast to the change notification signal of the :ref:`error <property_TransformList_error>` property this signal is also emitted several times if a certain error occurs several times in succession.


Enumerations
************


.. _enum_TransformList_Error:

.. index::
   single: Error

Error
+++++

This enumeration describes all errors which can occur in TransformList objects. The most recently occurred error is stored in the :ref:`error <property_TransformList_error>` property.

.. index::
   single: TransformList.NoError
.. index::
   single: TransformList.InvalidPropertyType
.. index::
   single: TransformList.NotWritableError
.. index::
   single: TransformList.InvalidObjectTypeError
.. index::
   single: TransformList.ObjectInsertionError
.. index::
   single: TransformList.EvalExpressionError
.. list-table::
  :widths: auto
  :header-rows: 1

  * - Name
    - Value
    - Description

      .. _enumitem_TransformList_NoError:
  * - ``TransformList.NoError``
    - ``0``
    - No error occurred or was detected.

      .. _enumitem_TransformList_InvalidPropertyType:
  * - ``TransformList.InvalidPropertyType``
    - ``1``
    - TransformList not supported for non-list property "".

      .. _enumitem_TransformList_NotWritableError:
  * - ``TransformList.NotWritableError``
    - ``2``
    - TransformList not supported for readonly property "".

      .. _enumitem_TransformList_InvalidObjectTypeError:
  * - ``TransformList.InvalidObjectTypeError``
    - ``3``
    - Can't add incompatible object to property "".

      .. _enumitem_TransformList_ObjectInsertionError:
  * - ``TransformList.ObjectInsertionError``
    - ``4``
    - Error inserting object to property "".

      .. _enumitem_TransformList_EvalExpressionError:
  * - ``TransformList.EvalExpressionError``
    - ``5``
    - Error while evaluating expression: <Unknown File>: .


.. _example_TransformList:


Example
*******

.. code-block:: qml

    import InCore.Foundation 2.5
    
    Application {
    
        MeasurementGroup {
            id: randomNegativeMeasurements
            Measurement { data: -Math.random() }
            Measurement { data: -Math.random() }
            Measurement { data: -Math.random() }
            Measurement { data: -Math.random() }
            Measurement { data: -Math.random() }
        }
    
        // create a second MeasurementGroup which contains identical measurements except for data being transformed
        MeasurementGroup {
            id: absoluteMeasurements
            TransformList on objects {
                source: randomNegativeMeasurements.objects
                eval: Math.abs(item.data)
            }
            onObjectsDataChanged: console.log(index, objects[index].data)
        }
    
        // wrap value array into List object
        List {
            id: simpleValueList
            items: [ 1, 2, 3 ]
        }
    
        // create a List which contains transformed items
        List {
            TransformList on items {
                source: simpleValueList
                eval: item*5
            }
            onItemsChanged: console.log(items)
        }
    
        onCompleted: {
            // update a value and observe an automatic update of the list above
            simpleValueList.setItem( 1, 123 )
        }
    
    }
    