
.. _object_Gather:


:index:`Gather`
---------------

Description
***********

The Gather object is a :ref:`PropertyModifier <object_PropertyModifier>` object which gathers references to objects and stores them in a target list. The behaviour of the gather operation is very flexible and can be customized through :ref:`recursive <property_Gather_recursive>` and combinations of filters such as :ref:`typeFilter <property_Gather_typeFilter>`, :ref:`expressionFilter <property_Gather_expressionFilter>` and :ref:`nameFilter <property_Gather_nameFilter>`.

Like other objects, :ref:`Gather <object_Gather>` monitors the :ref:`source <property_Gather_source>` object and all of its subobjects for property changes and updates the target automatically.

The most typical use case is to flatten a hierarchical object structure into a list, optionally based on certain criteria.

:**› Inherits**: :ref:`PropertyModifier <object_PropertyModifier>`

Overview
********

Properties
++++++++++

.. hlist::
  :columns: 2

  * :ref:`deferUpdatesWhileDeserializing <property_Gather_deferUpdatesWhileDeserializing>`
  * :ref:`deferUpdatesWhileRepeatersUpdating <property_Gather_deferUpdatesWhileRepeatersUpdating>`
  * :ref:`error <property_Gather_error>`
  * :ref:`errorString <property_Gather_errorString>`
  * :ref:`expressionFilter <property_Gather_expressionFilter>`
  * :ref:`maximumRecursionDepth <property_Gather_maximumRecursionDepth>`
  * :ref:`nameFilter <property_Gather_nameFilter>`
  * :ref:`orderBy <property_Gather_orderBy>`
  * :ref:`recursive <property_Gather_recursive>`
  * :ref:`source <property_Gather_source>`
  * :ref:`typeFilter <property_Gather_typeFilter>`
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

  * :ref:`errorOccurred() <signal_Gather_errorOccurred>`
  * :ref:`Object.completed() <signal_Object_completed>`

Enumerations
++++++++++++

.. hlist::
  :columns: 1

  * :ref:`Error <enum_Gather_Error>`



Properties
**********


.. _property_Gather_deferUpdatesWhileDeserializing:

.. _signal_Gather_deferUpdatesWhileDeserializingChanged:

.. index::
   single: deferUpdatesWhileDeserializing

deferUpdatesWhileDeserializing
++++++++++++++++++++++++++++++

This property holds whether to defer and combine updates when many related properties are changed in a row, e.g. when deserializing properties of the source object or one of its child objects. This can improve performance significantly however the list of gathered objects is not up to date until the property updates have been finished.

This property was introduced in InCore 2.0.

:**› Type**: Boolean
:**› Default**: ``true``
:**› Signal**: deferUpdatesWhileDeserializingChanged()
:**› Attributes**: Writable


.. _property_Gather_deferUpdatesWhileRepeatersUpdating:

.. _signal_Gather_deferUpdatesWhileRepeatersUpdatingChanged:

.. index::
   single: deferUpdatesWhileRepeatersUpdating

deferUpdatesWhileRepeatersUpdating
++++++++++++++++++++++++++++++++++

This property holds whether to defer and combine updates while one or multiple children of type :ref:`Repeater <object_Repeater>` are :ref:`populating <property_Repeater_updating>` objects.

This property was introduced in InCore 2.0.

:**› Type**: Boolean
:**› Default**: ``true``
:**› Signal**: deferUpdatesWhileRepeatersUpdatingChanged()
:**› Attributes**: Writable


.. _property_Gather_error:

.. _signal_Gather_errorChanged:

.. index::
   single: error

error
+++++

This property holds the most recently occurred error or :ref:`Gather.NoError <enumitem_Gather_NoError>` if no error occurred. If the same error occurs multiple times this property does not change. Use the :ref:`errorOccurred() <signal_Gather_errorOccurred>` signal to detect multiple occurrences of the same error.

:**› Type**: :ref:`Error <enum_Gather_Error>`
:**› Signal**: errorChanged()
:**› Attributes**: Readonly


.. _property_Gather_errorString:

.. _signal_Gather_errorStringChanged:

.. index::
   single: errorString

errorString
+++++++++++

This property holds the current human readable error string corresponding to the current value in the :ref:`error <property_Gather_error>` property. It may include additional information such as failure reasons or locations.

:**› Type**: String
:**› Signal**: errorStringChanged()
:**› Attributes**: Readonly


.. _property_Gather_expressionFilter:

.. _signal_Gather_expressionFilterChanged:

.. index::
   single: expressionFilter

expressionFilter
++++++++++++++++

This property holds an expression which is used to filter objects. The expression is evaluated for each object and needs to evaluate to ``true`` in order to include an object in the target list. The respective object is provided in the ``item`` variable. This allows gathering only objects whose properties match certain criteria, e.g. a value above a threshold. See the :ref:`Gather example <example_Gather>` for further details.

:**› Type**: <QML expression>
:**› Signal**: expressionFilterChanged()
:**› Attributes**: Writable


.. _property_Gather_maximumRecursionDepth:

.. _signal_Gather_maximumRecursionDepthChanged:

.. index::
   single: maximumRecursionDepth

maximumRecursionDepth
+++++++++++++++++++++

This property holds the maximum recursion depth when gathering children objects of the :ref:`source <property_Gather_source>` and :ref:`recursive <property_Gather_recursive>` is set to ``true``. If set to ``-1``, the recursion is not limited.

This property was introduced in InCore 2.7.

:**› Type**: SignedInteger
:**› Default**: ``-1``
:**› Signal**: maximumRecursionDepthChanged()
:**› Attributes**: Writable


.. _property_Gather_nameFilter:

.. _signal_Gather_nameFilterChanged:

.. index::
   single: nameFilter

nameFilter
++++++++++

This property holds a string or `regular expression <https://en.wikipedia.org/wiki/Regular_expression>`_ used to filter objects by name or :ref:`Object.objectId <property_Object_objectId>`. The name of each object has to contain the string or match the regular expression to be added to the target list.

:**› Type**: String
:**› Signal**: nameFilterChanged()
:**› Attributes**: Writable


.. _property_Gather_orderBy:

.. _signal_Gather_orderByChanged:

.. index::
   single: orderBy

orderBy
+++++++

This property holds an expression evaluating to a value by which to order the objects before inserting them into the target list. When left blank, the order of the objects is random and non-deterministic. The respective object is provided in the ``item`` variable. This also allows specifying the property of a subobject, e.g. ``item.view.orderIndex`` to sort :ref:`DataObject <object_DataObject>` objects by :ref:`DataObjectView.orderIndex <property_DataObjectView_orderIndex>`.

:**› Type**: <QML expression>
:**› Signal**: orderByChanged()
:**› Attributes**: Writable, Optional


.. _property_Gather_recursive:

.. _signal_Gather_recursiveChanged:

.. index::
   single: recursive

recursive
+++++++++

This property holds whether to search for objects recursively. When set to ``false`` only direct child objects of the :ref:`source <property_Gather_source>` object and objects in list properties of the :ref:`source <property_Gather_source>` object are gathered.

.. note:: When using :ref:`Repeaters <object_Repeater>` on list properties of the :ref:`source <property_Gather_source>` object and :ref:`Repeater.alternativeParent <property_Repeater_alternativeParent>` is set the populated objects do not become children of the source object. They therefore are only gathered (as children of the list property) when :ref:`recursive <property_Gather_recursive>` is set to ``true``.

:**› Type**: Boolean
:**› Default**: ``true``
:**› Signal**: recursiveChanged()
:**› Attributes**: Writable


.. _property_Gather_source:

.. _signal_Gather_sourceChanged:

.. index::
   single: source

source
++++++

This property holds the source object which to gather objects from.

:**› Type**: :ref:`Object <object_Object>`
:**› Signal**: sourceChanged()
:**› Attributes**: Writable


.. _property_Gather_typeFilter:

.. _signal_Gather_typeFilterChanged:

.. index::
   single: typeFilter

typeFilter
++++++++++

This property holds a component (QML/object type) which to filter objects. When set the target list contains only objects which either are exactly of the specified object type or inherit from it. This allows gathering e.g. only :ref:`Measurement <object_Measurement>` objects from a list or tree of :ref:`DataObject <object_DataObject>` objects.

:**› Type**: <QML component>
:**› Signal**: typeFilterChanged()
:**› Attributes**: Writable

Signals
*******


.. _signal_Gather_errorOccurred:

.. index::
   single: errorOccurred

errorOccurred()
+++++++++++++++

This signal is emitted whenever an error has occurred, regardless of whether the :ref:`error <property_Gather_error>` property has changed or not. In contrast to the change notification signal of the :ref:`error <property_Gather_error>` property this signal is also emitted several times if a certain error occurs several times in succession.


Enumerations
************


.. _enum_Gather_Error:

.. index::
   single: Error

Error
+++++

This enumeration describes all errors which can occur in Gather objects. The most recently occurred error is stored in the :ref:`error <property_Gather_error>` property.

.. index::
   single: Gather.NoError
.. index::
   single: Gather.InvalidPropertyType
.. index::
   single: Gather.NotWritableError
.. index::
   single: Gather.InvalidObjectTypeError
.. index::
   single: Gather.ObjectInsertionError
.. index::
   single: Gather.FilterExpressionError
.. list-table::
  :widths: auto
  :header-rows: 1

  * - Name
    - Value
    - Description

      .. _enumitem_Gather_NoError:
  * - ``Gather.NoError``
    - ``0``
    - No error occurred or was detected.

      .. _enumitem_Gather_InvalidPropertyType:
  * - ``Gather.InvalidPropertyType``
    - ``1``
    - Gather not supported for non-list property "".

      .. _enumitem_Gather_NotWritableError:
  * - ``Gather.NotWritableError``
    - ``2``
    - Gather not supported for readonly property "".

      .. _enumitem_Gather_InvalidObjectTypeError:
  * - ``Gather.InvalidObjectTypeError``
    - ``3``
    - Can't add incompatible object to property "".

      .. _enumitem_Gather_ObjectInsertionError:
  * - ``Gather.ObjectInsertionError``
    - ``4``
    - Error inserting object to property "".

      .. _enumitem_Gather_FilterExpressionError:
  * - ``Gather.FilterExpressionError``
    - ``5``
    - Error while evaluating filter expression: <Unknown File>: .


.. _example_Gather:


Example
*******

.. code-block:: qml

    import InCore.Foundation 2.0
    
    Application {
    
        property var dynMeas1;
        property var dynMeas2;
    
        ObjectArray {
            id: dataObjects
    
            // group with statically populated objects
            DataObjectGroup {
                DataObject { id: meas1; data: -10 }
                DateTime { id: dateTime }
                Measurement { id: meas2; data: 2 }
                property var meas3: Measurement { id: meas3; data: 3 }
            }
    
            // group with dynamically populated objects
            MeasurementGroup {
                onCompleted: {
                    Qt.createQmlObject('import InCore.Foundation 2.5; DataObject { id: dynDO1; data: 10 }', this);
                    Qt.createQmlObject('import InCore.Foundation 2.5; DataObject { id: dynDO2; data: 5.2 }', this);
                    dynMeas1 = Qt.createQmlObject('import InCore.Foundation 2.5; Measurement { id: dynMeas1; data: 10 }', this);
                    dynMeas2 = Qt.createQmlObject('import InCore.Foundation 2.5; Measurement { id: dynMeas2; data: 20 }', dynMeas1);
                    // destroy object again so we should observe a decrease in number of gathered objects
                    dynMeas2.destroy();
                }
            }
        }
    
        // gather all objects recursively
        List {
            Gather on items {
                source: dataObjects
            }
            onItemsChanged: console.log("Total object count:", items.length)
    
        }
    
        // gather all Temperature objects
        List {
            Gather on items {
                source: dataObjects
                typeFilter: Measurement { }
            }
            onItemsChanged: console.log("Measurement object count:", items.length)
            // log any changes of the gathered temperatures
            onDataChanged: console.log("Measurement", index, "changed to", items[index].data)
        }
    
        // gather all dynamically created objects
        List {
            Gather on items {
                source: dataObjects
                nameFilter: "dyn.*"
            }
            onItemsChanged: console.log("Number of dynamic objects:", items.length)
        }
    
        // gather all measurements with value above 10
        List {
            Gather on items {
                source: dataObjects
                typeFilter: Measurement { }
                expressionFilter: item.data > 10
            }
            onItemsChanged: console.log("Number of measurements with value above 10:", items.length)
        }
    
        // sort measurements by value
        List {
            Gather on items {
                source: dataObjects
                typeFilter: Measurement { }
                orderBy: item.data
            }
            onItemsChanged: {
                var values = []
                for( var key in items )
                {
                    values.push(items[key].data);
                }
                console.log("Sorted measurement values:", values)
            }
        }
    
        // increase measurement value dynamically to observe changes in the list above
        Timer {
            running: true
            interval: 1000
            onTriggered: {
                dynMeas1.data++;
            }
        }
    }
    