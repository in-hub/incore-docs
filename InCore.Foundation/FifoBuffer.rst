
.. _object_FifoBuffer:


:index:`FifoBuffer`
-------------------

Description
***********

The FifoBuffer object implements a buffer based on the FIFO (First-In-First-Out) principle. It can be either used as a queue which grows whenever a producer writes to it and shrinks whenever a consumer reads from it. Alternatively a ring-buffer-like behaviour can be achieved by limiting the size of the FIFO buffer through the :ref:`maximumSize <property_FifoBuffer_maximumSize>` property.

:**› Inherits**: :ref:`List <object_List>`

Overview
********

Properties
++++++++++

.. hlist::
  :columns: 2

  * :ref:`input <property_FifoBuffer_input>`
  * :ref:`maximumSize <property_FifoBuffer_maximumSize>`
  * :ref:`output <property_FifoBuffer_output>`
  * :ref:`size <property_FifoBuffer_size>`
  * :ref:`List.count <property_List_count>`
  * :ref:`List.items <property_List_items>`
  * :ref:`List.reference <property_List_reference>`
  * :ref:`Object.objectId <property_Object_objectId>`
  * :ref:`Object.parent <property_Object_parent>`

Methods
+++++++

.. hlist::
  :columns: 1

  * :ref:`read() <method_FifoBuffer_read>`
  * :ref:`write() <method_FifoBuffer_write>`
  * :ref:`List.setItem() <method_List_setItem>`
  * :ref:`Object.fromJson() <method_Object_fromJson>`
  * :ref:`Object.toJson() <method_Object_toJson>`

Signals
+++++++

.. hlist::
  :columns: 1

  * :ref:`List.changed() <signal_List_changed>`
  * :ref:`List.dataChanged() <signal_List_dataChanged>`
  * :ref:`List.itemAppended() <signal_List_itemAppended>`
  * :ref:`List.itemsCleared() <signal_List_itemsCleared>`
  * :ref:`List.objectAppended() <signal_List_objectAppended>`
  * :ref:`Object.completed() <signal_Object_completed>`



Properties
**********


.. _property_FifoBuffer_input:

.. _signal_FifoBuffer_inputChanged:

.. index::
   single: input

input
+++++

This property holds the input of the FIFO buffer. Whenever the input is written it is added to the FIFO, i.e. to the front of :ref:`List.items <property_List_items>`. If the new FIFO size exceeds :ref:`maximumSize <property_FifoBuffer_maximumSize>` the least-recently added item is removed.

:**› Type**: Variant
:**› Signal**: inputChanged()
:**› Attributes**: Writable


.. _property_FifoBuffer_maximumSize:

.. _signal_FifoBuffer_maximumSizeChanged:

.. index::
   single: maximumSize

maximumSize
+++++++++++

This property holds the desired maximum size of the FIFO buffer. The FIFO buffer will never contain more items than specified by this property. Leave at ``0`` to implement a queue which is always to be drained manually through the :ref:`read() <method_FifoBuffer_read>` method.

:**› Type**: SignedInteger
:**› Default**: ``0``
:**› Signal**: maximumSizeChanged()
:**› Attributes**: Writable


.. _property_FifoBuffer_output:

.. _signal_FifoBuffer_outputChanged:

.. index::
   single: output

output
++++++

This property holds the output of the FIFO buffer, i.e. the last item of :ref:`List.items <property_List_items>`. This property is updated automatically.

:**› Type**: Variant
:**› Signal**: outputChanged()
:**› Attributes**: Readonly


.. _property_FifoBuffer_size:

.. _signal_FifoBuffer_sizeChanged:

.. index::
   single: size

size
++++

This property holds the current size of the FIFO buffer, i.e. the number of items in the :ref:`List.items <property_List_items>` property. This property is provided for convenience only and equals to ``items.length``.

:**› Type**: SignedInteger
:**› Signal**: sizeChanged()
:**› Attributes**: Readonly

Methods
*******


.. _method_FifoBuffer_read:

.. index::
   single: read

read()
++++++

This method reads the output of the FIFO buffer. This is the same as reading from the :ref:`output <property_FifoBuffer_output>` property except for the additional removal of the read data from the FIFO buffer. If the FIFO buffer is empty, an invalid value (``undefined``) is returned.

:**› Returns**: Variant



.. _method_FifoBuffer_write:

.. index::
   single: write

write(Variant data)
+++++++++++++++++++

This method writes the given data into the FIFO buffer. This is the same as writing/updating the :ref:`input <property_FifoBuffer_input>` property.



.. _example_FifoBuffer:


Example
*******

.. code-block:: qml

    import InCore.Foundation 2.0
    import InCore.Modbus 2.0
    
    Application {
    
        // calculate the 5 second average of the (fake) measurements taken every 50 ms
        property var measurementInterval: 50
        property var averagingInterval: 5000
    
        Measurement {
            ReduceList on data {
                source: FifoBuffer {
                    id: fifoBuffer
                    maximumSize: averagingInterval / measurementInterval
                    property var timer : Timer {
                        interval: measurementInterval
                        onTriggered: fifoBuffer.write( Math.random() )
                    }
                }
                accumulatorInitValue: 0
                eval: accumulator + item / source.items.length;
            }
            onDataChanged: console.log("Average of", fifoBuffer.items.length, "measurements:", data)
        }
    
        // calculate electric charge (ampere hours) from a charge rate retrieved through a fictional Modbus register
    
        ModbusRegister {
            id: chargeRateInAmpere
            dataType: ModbusRegister.Float
            address: 123
            count: 2
            Polling on data {
                interval: 1000
            }
        }
    
        Measurement {
            ReduceList on data {
                source: FifoBuffer {
                    maximumSize: 3600
                    input: chargeRateInAmpere.data
                }
                accumulatorInitValue: 0
                eval: accumulator + item
            }
            onDataChanged: console.log("Total charge:", data, "Ah")
        }
    }
    