
.. _object_OpcUaMethodNode:


:index:`OpcUaMethodNode`
------------------------

Description
***********

Please refer to the `Qt OPC UA MethodNode QML type <https://doc.qt.io/QtOPCUA/qml-qtopcua-methodnode.html#->`_ documentation.


Overview
********

Properties
++++++++++

.. hlist::
  :columns: 1

  * `inputArguments <https://doc.qt.io/QtOPCUA/qml-qtopcua-methodnode.html#inputArguments-prop>`_
  * `objectNodeId <https://doc.qt.io/QtOPCUA/qml-qtopcua-methodnode.html#objectNodeId-prop>`_
  * `outputArguments <https://doc.qt.io/QtOPCUA/qml-qtopcua-methodnode.html#outputArguments-prop>`_
  * `resultStatus <https://doc.qt.io/QtOPCUA/qml-qtopcua-methodnode.html#resultStatus-prop>`_

Methods
+++++++

.. hlist::
  :columns: 1

  * `callMethod <https://doc.qt.io/QtOPCUA/qml-qtopcua-methodnode.html#callMethod-method>`_
  * `setObjectNodeId <https://doc.qt.io/QtOPCUA/qml-qtopcua-methodnode.html#setObjectNodeId-method>`_



Properties
**********


.. _property_OpcUaMethodNode_inputArguments:

.. index::
   single: inputArguments

inputArguments
++++++++++++++

Please refer to the `Qt OPC UA MethodNode QML type <https://doc.qt.io/QtOPCUA/qml-qtopcua-methodnode.html#inputArguments-prop>`_ documentation.

:**› Attributes**: Readonly


.. _property_OpcUaMethodNode_objectNodeId:

.. index::
   single: objectNodeId

objectNodeId
++++++++++++

Please refer to the `Qt OPC UA MethodNode QML type <https://doc.qt.io/QtOPCUA/qml-qtopcua-methodnode.html#objectNodeId-prop>`_ documentation.

:**› Attributes**: Writable


.. _property_OpcUaMethodNode_outputArguments:

.. index::
   single: outputArguments

outputArguments
+++++++++++++++

Please refer to the `Qt OPC UA MethodNode QML type <https://doc.qt.io/QtOPCUA/qml-qtopcua-methodnode.html#outputArguments-prop>`_ documentation.

:**› Attributes**: Readonly


.. _property_OpcUaMethodNode_resultStatus:

.. index::
   single: resultStatus

resultStatus
++++++++++++

Please refer to the `Qt OPC UA MethodNode QML type <https://doc.qt.io/QtOPCUA/qml-qtopcua-methodnode.html#resultStatus-prop>`_ documentation.

:**› Attributes**: Readonly

Methods
*******


.. _method_OpcUaMethodNode_callMethod:

.. index::
   single: callMethod

callMethod()
++++++++++++

Please refer to the `Qt OPC UA MethodNode QML type <https://doc.qt.io/QtOPCUA/qml-qtopcua-methodnode.html#callMethod-method>`_ documentation.



.. _example_OpcUaMethodNode:


Example
*******

.. code-block:: qml

    import InCore.Foundation 2.3
    import InCore.OpcUa 2.3
    
    Application {
        OpcUaClient {
            OpcUaConnection {
                // ...
            }
    
            OpcUaMethodNode {
                id: pingMethod
                nodeId: OpcUaNodeId { identifier: "s=Machine.Ping"; ns: "Example Namespace" }
                objectNodeId: OpcUaNodeId { identifier: "s=Machine"; ns: "Example Namespace" }
    
                inputArguments: [
                    OpcUaMethodArgument {
                        value: 123.456
                        type: OpcUaConstants.Double
                    },
                    OpcUaMethodArgument {
                        value: "Hello world"
                        type: OpcUaConstants.String
                    }
                ]
                onOutputArgumentsChanged: console.log("Method returned", JSON.stringify(outputArguments))
            }
        }
    
        Timer {
            onTriggered: pingMethod.callMethod()
        }
    }
    