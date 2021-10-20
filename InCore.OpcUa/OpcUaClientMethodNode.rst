
.. _object_OpcUaClientMethodNode:


:index:`OpcUaClientMethodNode`
------------------------------

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


.. _property_OpcUaClientMethodNode_inputArguments:

.. index::
   single: inputArguments

inputArguments
++++++++++++++

Please refer to the `Qt OPC UA MethodNode QML type <https://doc.qt.io/QtOPCUA/qml-qtopcua-methodnode.html#inputArguments-prop>`_ documentation.

:**› Attributes**: Readonly


.. _property_OpcUaClientMethodNode_objectNodeId:

.. index::
   single: objectNodeId

objectNodeId
++++++++++++

Please refer to the `Qt OPC UA MethodNode QML type <https://doc.qt.io/QtOPCUA/qml-qtopcua-methodnode.html#objectNodeId-prop>`_ documentation.

:**› Attributes**: Writable


.. _property_OpcUaClientMethodNode_outputArguments:

.. index::
   single: outputArguments

outputArguments
+++++++++++++++

Please refer to the `Qt OPC UA MethodNode QML type <https://doc.qt.io/QtOPCUA/qml-qtopcua-methodnode.html#outputArguments-prop>`_ documentation.

:**› Attributes**: Readonly


.. _property_OpcUaClientMethodNode_resultStatus:

.. index::
   single: resultStatus

resultStatus
++++++++++++

Please refer to the `Qt OPC UA MethodNode QML type <https://doc.qt.io/QtOPCUA/qml-qtopcua-methodnode.html#resultStatus-prop>`_ documentation.

:**› Attributes**: Readonly

Methods
*******


.. _method_OpcUaClientMethodNode_callMethod:

.. index::
   single: callMethod

callMethod()
++++++++++++

Please refer to the `Qt OPC UA MethodNode QML type <https://doc.qt.io/QtOPCUA/qml-qtopcua-methodnode.html#callMethod-method>`_ documentation.



.. _example_OpcUaClientMethodNode:


Example
*******

.. code-block:: qml

    import InCore.Foundation 2.5
    import InCore.OpcUa 2.5
    
    Application {
        OpcUaClient {
            OpcUaClientConnection {
                // ...
            }
    
            OpcUaClientMethodNode {
                id: pingMethod
                nodeId: OpcUaClientNodeId { identifier: "s=Machine.Ping"; ns: "Example Namespace" }
                objectNodeId: OpcUaClientNodeId { identifier: "s=Machine"; ns: "Example Namespace" }
    
                inputArguments: [
                    OpcUaClientMethodArgument {
                        value: 123.456
                        type: OpcUaType.Double
                    },
                    OpcUaClientMethodArgument {
                        value: "Hello world"
                        type: OpcUaType.String
                    }
                ]
                onOutputArgumentsChanged: console.log("Method returned", JSON.stringify(outputArguments))
            }
        }
    
        Timer {
            onTriggered: pingMethod.callMethod()
        }
    }
    