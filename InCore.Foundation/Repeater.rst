
.. _object_Repeater:


:index:`Repeater`
-----------------

Description
***********

The Repeater object is a :ref:`PropertyModifier <object_PropertyModifier>` object which dynamically creates multiple instances of a :ref:`delegate <property_Repeater_delegate>` object based on a provided :ref:`model <property_Repeater_model>`. The created objects are inserted into the target list which the :ref:`Repeater <object_Repeater>` is operating on.

:**› Inherits**: :ref:`PropertyModifier <object_PropertyModifier>`

Overview
********

Properties
++++++++++

.. hlist::
  :columns: 2

  * :ref:`alternativeParent <property_Repeater_alternativeParent>`
  * :ref:`delegate <property_Repeater_delegate>`
  * :ref:`error <property_Repeater_error>`
  * :ref:`errorString <property_Repeater_errorString>`
  * :ref:`model <property_Repeater_model>`
  * :ref:`populated <property_Repeater_populated>`
  * :ref:`updating <property_Repeater_updating>`
  * :ref:`PropertyModifier.targetValue <property_PropertyModifier_targetValue>`
  * :ref:`Object.objectId <property_Object_objectId>`
  * :ref:`Object.parent <property_Object_parent>`

Methods
+++++++

.. hlist::
  :columns: 1

  * :ref:`Object.fromJson() <method_Object_fromJson>`
  * :ref:`Object.toJson() <method_Object_toJson>`

Signals
+++++++

.. hlist::
  :columns: 1

  * :ref:`errorOccurred() <signal_Repeater_errorOccurred>`
  * :ref:`Object.completed() <signal_Object_completed>`

Enumerations
++++++++++++

.. hlist::
  :columns: 1

  * :ref:`Error <enum_Repeater_Error>`



Properties
**********


.. _property_Repeater_alternativeParent:

.. _signal_Repeater_alternativeParentChanged:

.. index::
   single: alternativeParent

alternativeParent
+++++++++++++++++

This property holds an object which to use as parent for the created :ref:`delegate <property_Repeater_delegate>` objects, i.e. the objects become direct children of the specified object. In most cases this property can be left unset which will create the objects as children of the :ref:`Repeater <object_Repeater>`'s parent. The resulting object relationships then look exactly as if the objects were created manually without a :ref:`Repeater <object_Repeater>`.

.. note:: This property may be set once on initialization only. Later changes to it are ignored.

:**› Type**: :ref:`Object <object_Object>`
:**› Signal**: alternativeParentChanged()
:**› Attributes**: Writable, Optional


.. _property_Repeater_delegate:

.. _signal_Repeater_delegateChanged:

.. index::
   single: delegate

delegate
++++++++

This property holds a component (QML/object type) which is instantiated multiple times depending on the :ref:`model <property_Repeater_model>`. Use the local ``index`` or ``modelData`` properties to parametrize the delegate instances.

:**› Type**: <QML component>
:**› Signal**: delegateChanged()
:**› Attributes**: Writable


.. _property_Repeater_error:

.. _signal_Repeater_errorChanged:

.. index::
   single: error

error
+++++

This property holds the most recently occurred error or :ref:`Repeater.NoError <enumitem_Repeater_NoError>` if no error occurred. If the same error occurs multiple times this property does not change. Use the :ref:`errorOccurred() <signal_Repeater_errorOccurred>` signal to detect multiple occurrences of the same error.

:**› Type**: :ref:`Error <enum_Repeater_Error>`
:**› Signal**: errorChanged()
:**› Attributes**: Readonly


.. _property_Repeater_errorString:

.. _signal_Repeater_errorStringChanged:

.. index::
   single: errorString

errorString
+++++++++++

This property holds the current human readable error string corresponding to the current value in the :ref:`error <property_Repeater_error>` property. It may include additional information such as failure reasons or locations.

:**› Type**: String
:**› Signal**: errorStringChanged()
:**› Attributes**: Readonly


.. _property_Repeater_model:

.. _signal_Repeater_modelChanged:

.. index::
   single: model

model
+++++

This property holds the model which describes the data for the individual :ref:`delegate <property_Repeater_delegate>` instances. This can be a single number, a value array or a different :ref:`List <object_List>`. Every change to the model will result in a recreation of the delegate objects.

When specifying a single number, ``N`` delegates are created with a local property ``index`` holding the current delegate index in the range [0..N-1].

For value arrays a delegate for each value is created while the current value is available in a local ``modelData`` property.

When using a :ref:`List <object_List>` object delegates for each list element are created. The corresponding list element is available through a local ``modelData`` property.

:**› Type**: Variant
:**› Signal**: modelChanged()
:**› Attributes**: Writable


.. _property_Repeater_populated:

.. _signal_Repeater_populatedChanged:

.. index::
   single: populated

populated
+++++++++

This property holds whether the target list has been populated completely, i.e. the number of created :ref:`delegate <property_Repeater_delegate>` objects equals the number of items specified by the :ref:`model <property_Repeater_model>` and is greater than zero.

:**› Type**: Boolean
:**› Signal**: populatedChanged()
:**› Attributes**: Readonly


.. _property_Repeater_updating:

.. _signal_Repeater_updatingChanged:

.. index::
   single: updating

updating
++++++++

This property holds whether the repeater is currently performing updates, i.e. is populating objects and updating the target list (if set). This can be used to defer updates in some places until a repeater has finished populating objects.

This property was introduced in InCore 2.0.

:**› Type**: Boolean
:**› Signal**: updatingChanged()
:**› Attributes**: Readonly

Signals
*******


.. _signal_Repeater_errorOccurred:

.. index::
   single: errorOccurred

errorOccurred()
+++++++++++++++

This signal is emitted whenever an error has occurred, regardless of whether the :ref:`error <property_Repeater_error>` property has changed or not. In contrast to the change notification signal of the :ref:`error <property_Repeater_error>` property this signal is also emitted several times if a certain error occurs several times in succession.


Enumerations
************


.. _enum_Repeater_Error:

.. index::
   single: Error

Error
+++++

This enumeration describes all errors which can occur in Repeater objects. The most recently occurred error is stored in the :ref:`error <property_Repeater_error>` property.

.. index::
   single: Repeater.NoError
.. index::
   single: Repeater.InvalidPropertyType
.. index::
   single: Repeater.NotWritableError
.. index::
   single: Repeater.InvalidObjectTypeError
.. index::
   single: Repeater.ObjectInsertionError
.. list-table::
  :widths: auto
  :header-rows: 1

  * - Name
    - Value
    - Description

      .. _enumitem_Repeater_NoError:
  * - ``Repeater.NoError``
    - ``0``
    - No error occurred or was detected.

      .. _enumitem_Repeater_InvalidPropertyType:
  * - ``Repeater.InvalidPropertyType``
    - ``1``
    - Repeater not supported for non-list property "".

      .. _enumitem_Repeater_NotWritableError:
  * - ``Repeater.NotWritableError``
    - ``2``
    - Repeater not supported for readonly property "".

      .. _enumitem_Repeater_InvalidObjectTypeError:
  * - ``Repeater.InvalidObjectTypeError``
    - ``3``
    - Can't add incompatible object to property "".

      .. _enumitem_Repeater_ObjectInsertionError:
  * - ``Repeater.ObjectInsertionError``
    - ``4``
    - Error inserting object to property "".


.. _example_Repeater:


Example
*******

.. code-block:: qml

    import InCore.Foundation 2.0
    import InCore.Modbus 2.0
    
    Application {
    
        DataObjectGroup {
            Repeater on objects {
                model: [ "A", "B", "C" ]
                delegate: DataObject {
                    name: modelData
                }
            }
            onCompleted: {
                for( var i = 0; i < objects.length; ++i )
                {
                    console.log( "Object", i, "has name", objects[i].name )
                }
            }
        }
    
        // create Modbus client
        ModbusTcpClient {
            id: modbusTcpClient
            networkAddress: "192.168.5.2"
    
            //create a slave object
            ModbusSlave {
                id: slave
                address: 1
                // repeat over 3 registers
                Repeater on registers {
                    model: 3
                    ModbusRegister {
                        address: index + 50
                        dataType: ModbusRegister.Float
                        type: ModbusRegister.Input
                        count: 2
                    }
    
                    // handle signal explicitly
                    onPopulatedChanged: {
                        if( populated ) {
                            console.log( "repeater did the job" )
                        } else {
                            console.log( "repeater is working" )
                        }
                    }
                }
            }
            Polling on slaves { interval: 5000 }
        }
    
        // MeasurementGroup to handle data
        MeasurementGroup {
            Repeater on objects {
                // handle signal populated implicitly
                model: slave.registers
                Measurement {
                    objectId: "measurement" + index
                    data: slave.registers[index].data
                }
            }
        }
    }
    