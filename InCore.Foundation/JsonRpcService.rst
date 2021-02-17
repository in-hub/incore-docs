
.. _object_JsonRpcService:


:index:`JsonRpcService`
-----------------------

Description
***********

The JsonRpcService object provides mechanisms for exposing user-defined functions via JSON-RPC. Additionally arbitrary user-defined properties inside this object can be read and written via :ref:`getProperty() <method_JsonRpcService_getProperty>` and :ref:`setProperty() <method_JsonRpcService_setProperty>`.


Overview
********

Methods
+++++++

.. hlist::
  :columns: 1

  * :ref:`getProperty() <method_JsonRpcService_getProperty>`
  * :ref:`setProperty() <method_JsonRpcService_setProperty>`



Properties
**********

Methods
*******


.. _method_JsonRpcService_getProperty:

.. index::
   single: getProperty

getProperty(Variant name)
+++++++++++++++++++++++++

This method can be called remotely and returns the property specified by name if it exists.

:**› Returns**: Variant



.. _method_JsonRpcService_setProperty:

.. index::
   single: setProperty

setProperty(Variant name, Variant value)
++++++++++++++++++++++++++++++++++++++++

This method can be called remotely and sets the property specified by name to the given value.

:**› Returns**: Variant



.. _example_JsonRpcService:


Example
*******

.. code-block:: qml

    import InCore.Foundation 2.2
    
    Application {
    
        JsonRpcClient {
            id: rpcClient
            onErrorCodeReceived: console.log("Call to", name, "returned with error code", errorCode)
            onErrorMessageReceived: console.log("Call to", name, "returned with error message", errorMessage)
        }
    
        onCompleted:  {
            rpcClient.getProperty("systemClock", (value) => { console.log("System clock:", value) })
            rpcClient.call("callMe", ["My message"], (retval) => { console.log("callMe() returned:", retval)})
            rpcClient.call("nonExistingFunction", [])
        }
    
        MeasurementGroup {
            id: myMeasurements
            Measurement { id: meas1; data: Math.random() }
            Measurement { id: meas2; data: Math.random() }
            Measurement { id: meas3; data: Math.random() }
        }
    
        System {
            id: system
        }
    
        JsonRpcServer {
            JsonRpcService {
                // calling getProperty("myMeasurements") via JSON-RPC will return JSON-serialized representation
                // of the MeasurementGroup
                readonly property alias measurements: myMeasurements
    
                // allow to read and write the system clock via JSON-RPC e.g. by calling
                // setProperty("systemClock", 1569241016)
                property alias systemClock: system.clock
    
                function callMe(message)
                {
                    console.log("I have a message for you:", message)
                    return [ "Hello", "world" ]
                }
            }
        }
    }
    