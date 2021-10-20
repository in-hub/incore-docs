
.. _object_AlphasenseOpcN3:


:index:`AlphasenseOpcN3`
------------------------

Description
***********

The AlphasenseOpcN3 object implements a driver for the USB-ISS-based Alphasense OPC-N3 sensor.

:**› Inherits**: :ref:`SerialPortBusNode <object_SerialPortBusNode>`

Overview
********

Properties
++++++++++

.. hlist::
  :columns: 3

  * :ref:`binCounts <property_AlphasenseOpcN3_binCounts>`
  * :ref:`deviceInformation <property_AlphasenseOpcN3_deviceInformation>`
  * :ref:`error <property_AlphasenseOpcN3_error>`
  * :ref:`errorString <property_AlphasenseOpcN3_errorString>`
  * :ref:`fan <property_AlphasenseOpcN3_fan>`
  * :ref:`initialized <property_AlphasenseOpcN3_initialized>`
  * :ref:`laser <property_AlphasenseOpcN3_laser>`
  * :ref:`massPM10 <property_AlphasenseOpcN3_massPM10>`
  * :ref:`massPM1_0 <property_AlphasenseOpcN3_massPM1_0>`
  * :ref:`massPM2_5 <property_AlphasenseOpcN3_massPM2_5>`
  * :ref:`mtof <property_AlphasenseOpcN3_mtof>`
  * :ref:`pollMassConcentrationsOnly <property_AlphasenseOpcN3_pollMassConcentrationsOnly>`
  * :ref:`relativeHumidity <property_AlphasenseOpcN3_relativeHumidity>`
  * :ref:`samplingFlowRate <property_AlphasenseOpcN3_samplingFlowRate>`
  * :ref:`samplingPeriod <property_AlphasenseOpcN3_samplingPeriod>`
  * :ref:`serialNumber <property_AlphasenseOpcN3_serialNumber>`
  * :ref:`temperature <property_AlphasenseOpcN3_temperature>`
  * :ref:`values <property_AlphasenseOpcN3_values>`
  * :ref:`SerialPortBusNode.bus <property_SerialPortBusNode_bus>`
  * :ref:`SerialPortBusNode.portName <property_SerialPortBusNode_portName>`
  * :ref:`SerialPortBusNode.responseTimeout <property_SerialPortBusNode_responseTimeout>`
  * :ref:`SerialPortBusNode.serialPort <property_SerialPortBusNode_serialPort>`
  * :ref:`Object.objectId <property_Object_objectId>`
  * :ref:`Object.parent <property_Object_parent>`

Methods
+++++++

.. hlist::
  :columns: 1

  * :ref:`pollDeviceInformation() <method_AlphasenseOpcN3_pollDeviceInformation>`
  * :ref:`pollSerialNumber() <method_AlphasenseOpcN3_pollSerialNumber>`
  * :ref:`pollValues() <method_AlphasenseOpcN3_pollValues>`
  * :ref:`reset() <method_AlphasenseOpcN3_reset>`
  * :ref:`Object.deserializeProperties() <method_Object_deserializeProperties>`
  * :ref:`Object.fromJson() <method_Object_fromJson>`
  * :ref:`Object.toJson() <method_Object_toJson>`

Signals
+++++++

.. hlist::
  :columns: 1

  * :ref:`errorOccurred() <signal_AlphasenseOpcN3_errorOccurred>`
  * :ref:`Object.completed() <signal_Object_completed>`

Enumerations
++++++++++++

.. hlist::
  :columns: 1

  * :ref:`Error <enum_AlphasenseOpcN3_Error>`



Properties
**********


.. _property_AlphasenseOpcN3_binCounts:

.. _signal_AlphasenseOpcN3_binCountsChanged:

.. index::
   single: binCounts

binCounts
+++++++++

This property holds the number of particles in the individual bins.

:**› Type**: List
:**› Signal**: binCountsChanged()
:**› Attributes**: Readonly


.. _property_AlphasenseOpcN3_deviceInformation:

.. _signal_AlphasenseOpcN3_deviceInformationChanged:

.. index::
   single: deviceInformation

deviceInformation
+++++++++++++++++

This property holds a device information string containing hardware and software information.

:**› Type**: String
:**› Signal**: deviceInformationChanged()
:**› Attributes**: Readonly, Requires :ref:`Polling <object_Polling>`


.. _property_AlphasenseOpcN3_error:

.. _signal_AlphasenseOpcN3_errorChanged:

.. index::
   single: error

error
+++++

This property holds the most recently occurred error or :ref:`AlphasenseOpcN3.NoError <enumitem_AlphasenseOpcN3_NoError>` if no error occurred. If the same error occurs multiple times this property does not change. Use the :ref:`errorOccurred() <signal_AlphasenseOpcN3_errorOccurred>` signal to detect multiple occurrences of the same error.

:**› Type**: :ref:`Error <enum_AlphasenseOpcN3_Error>`
:**› Signal**: errorChanged()
:**› Attributes**: Readonly


.. _property_AlphasenseOpcN3_errorString:

.. _signal_AlphasenseOpcN3_errorStringChanged:

.. index::
   single: errorString

errorString
+++++++++++

This property holds the current human readable error string corresponding to the current value in the :ref:`error <property_AlphasenseOpcN3_error>` property. It may include additional information such as failure reasons or locations.

:**› Type**: String
:**› Signal**: errorStringChanged()
:**› Attributes**: Readonly


.. _property_AlphasenseOpcN3_fan:

.. _signal_AlphasenseOpcN3_fanChanged:

.. index::
   single: fan

fan
+++

This property holds the status of the fan inside the OPC-N3 sensor.

:**› Type**: Boolean
:**› Default**: ``false``
:**› Signal**: fanChanged()
:**› Attributes**: Writable


.. _property_AlphasenseOpcN3_initialized:

.. _signal_AlphasenseOpcN3_initializedChanged:

.. index::
   single: initialized

initialized
+++++++++++

This property holds whether the communication with the OPC-N3 sensor has been initialized successfully.

:**› Type**: Boolean
:**› Signal**: initializedChanged()
:**› Attributes**: Readonly


.. _property_AlphasenseOpcN3_laser:

.. _signal_AlphasenseOpcN3_laserChanged:

.. index::
   single: laser

laser
+++++

This property holds the status of the laser inside the OPC-N3 sensor.

:**› Type**: Boolean
:**› Default**: ``false``
:**› Signal**: laserChanged()
:**› Attributes**: Writable


.. _property_AlphasenseOpcN3_massPM10:

.. _signal_AlphasenseOpcN3_massPM10Changed:

.. index::
   single: massPM10

massPM10
++++++++

This property holds the mass concentration *PM10* in *μg/m³*.

:**› Type**: Float
:**› Signal**: massPM10Changed()
:**› Attributes**: Readonly


.. _property_AlphasenseOpcN3_massPM1_0:

.. _signal_AlphasenseOpcN3_massPM1_0Changed:

.. index::
   single: massPM1_0

massPM1_0
+++++++++

This property holds the mass concentration *PM1.0* in *μg/m³*.

:**› Type**: Float
:**› Signal**: massPM1_0Changed()
:**› Attributes**: Readonly


.. _property_AlphasenseOpcN3_massPM2_5:

.. _signal_AlphasenseOpcN3_massPM2_5Changed:

.. index::
   single: massPM2_5

massPM2_5
+++++++++

This property holds the mass concentration *PM2.5* in *μg/m³*.

:**› Type**: Float
:**› Signal**: massPM2_5Changed()
:**› Attributes**: Readonly


.. _property_AlphasenseOpcN3_mtof:

.. _signal_AlphasenseOpcN3_mtofChanged:

.. index::
   single: mtof

mtof
++++

This property holds represents the average amount of time that particles sized in the stated bin took to cross the OPS's laser beam. Each value is in 1/3 *µs*. i.e. a value of ``10`` would represent 3.33 µs.

:**› Type**: List
:**› Signal**: mtofChanged()
:**› Attributes**: Readonly


.. _property_AlphasenseOpcN3_pollMassConcentrationsOnly:

.. _signal_AlphasenseOpcN3_pollMassConcentrationsOnlyChanged:

.. index::
   single: pollMassConcentrationsOnly

pollMassConcentrationsOnly
++++++++++++++++++++++++++

This property holds whether to poll the mass concentrations :ref:`massPM1_0 <property_AlphasenseOpcN3_massPM1_0>`, :ref:`massPM2_5 <property_AlphasenseOpcN3_massPM2_5>` and :ref:`massPM10 <property_AlphasenseOpcN3_massPM10>` only when polling the :ref:`values <property_AlphasenseOpcN3_values>` property. This reduces both communication traffic with the sensor and the CPU load of the device. Set to ``false`` if any other measurements such as :ref:`binCounts <property_AlphasenseOpcN3_binCounts>` or :ref:`temperature <property_AlphasenseOpcN3_temperature>` are required.

:**› Type**: Boolean
:**› Signal**: pollMassConcentrationsOnlyChanged()
:**› Attributes**: Readonly


.. _property_AlphasenseOpcN3_relativeHumidity:

.. _signal_AlphasenseOpcN3_relativeHumidityChanged:

.. index::
   single: relativeHumidity

relativeHumidity
++++++++++++++++

This property holds the measured relative humidity.

:**› Type**: Float
:**› Signal**: relativeHumidityChanged()
:**› Attributes**: Readonly


.. _property_AlphasenseOpcN3_samplingFlowRate:

.. _signal_AlphasenseOpcN3_samplingFlowRateChanged:

.. index::
   single: samplingFlowRate

samplingFlowRate
++++++++++++++++

This property holds represents the sample flow rate in *ml/s* x100

:**› Type**: SignedInteger
:**› Signal**: samplingFlowRateChanged()
:**› Attributes**: Readonly


.. _property_AlphasenseOpcN3_samplingPeriod:

.. _signal_AlphasenseOpcN3_samplingPeriodChanged:

.. index::
   single: samplingPeriod

samplingPeriod
++++++++++++++

This property holds the measure of the histogram's actual sampling period in *seconds* x100

:**› Type**: SignedInteger
:**› Signal**: samplingPeriodChanged()
:**› Attributes**: Readonly


.. _property_AlphasenseOpcN3_serialNumber:

.. _signal_AlphasenseOpcN3_serialNumberChanged:

.. index::
   single: serialNumber

serialNumber
++++++++++++

This property holds the serial number of the sensor.

:**› Type**: String
:**› Signal**: serialNumberChanged()
:**› Attributes**: Readonly, Requires :ref:`Polling <object_Polling>`


.. _property_AlphasenseOpcN3_temperature:

.. _signal_AlphasenseOpcN3_temperatureChanged:

.. index::
   single: temperature

temperature
+++++++++++

This property holds the measured temperature.

:**› Type**: Float
:**› Signal**: temperatureChanged()
:**› Attributes**: Readonly


.. _property_AlphasenseOpcN3_values:

.. _signal_AlphasenseOpcN3_valuesChanged:

.. index::
   single: values

values
++++++

This property holds all available values provided for convenience in the following order:

* *PM1.0*: :ref:`massPM1_0 <property_AlphasenseOpcN3_massPM1_0>`
* *PM2.5*: :ref:`massPM2_5 <property_AlphasenseOpcN3_massPM2_5>`
* *PM10*: :ref:`massPM10 <property_AlphasenseOpcN3_massPM10>`

If :ref:`pollMassConcentrationsOnly <property_AlphasenseOpcN3_pollMassConcentrationsOnly>` is set to ``false`` the following properties are appended additionally:

* Bin counts: :ref:`binCounts <property_AlphasenseOpcN3_binCounts>`
* Sampling period: :ref:`samplingPeriod <property_AlphasenseOpcN3_samplingPeriod>`
* Sampling flow rate: :ref:`samplingFlowRate <property_AlphasenseOpcN3_samplingFlowRate>`
* Temperature: :ref:`temperature <property_AlphasenseOpcN3_temperature>`
* Relative humidity: :ref:`relativeHumidity <property_AlphasenseOpcN3_relativeHumidity>`
* MTOF: :ref:`mtof <property_AlphasenseOpcN3_mtof>`


:**› Type**: List
:**› Signal**: valuesChanged()
:**› Attributes**: Readonly, Requires :ref:`Polling <object_Polling>`

Methods
*******


.. _method_AlphasenseOpcN3_pollDeviceInformation:

.. index::
   single: pollDeviceInformation

pollDeviceInformation()
+++++++++++++++++++++++

This method polls the :ref:`deviceInformation <property_AlphasenseOpcN3_deviceInformation>` property. It is called automatically when using a :ref:`Polling <object_Polling>` property modifier on this property and usually does not have to be called manually.



.. _method_AlphasenseOpcN3_pollSerialNumber:

.. index::
   single: pollSerialNumber

pollSerialNumber()
++++++++++++++++++

This method polls the :ref:`serialNumber <property_AlphasenseOpcN3_serialNumber>` property. It is called automatically when using a :ref:`Polling <object_Polling>` property modifier on this property and usually does not have to be called manually.



.. _method_AlphasenseOpcN3_pollValues:

.. index::
   single: pollValues

pollValues()
++++++++++++

This method polls the :ref:`values <property_AlphasenseOpcN3_values>` property. It is called automatically when using a :ref:`Polling <object_Polling>` property modifier on this property and usually does not have to be called manually.



.. _method_AlphasenseOpcN3_reset:

.. index::
   single: reset

reset()
+++++++

This method resets the communication with the OPC-N3 sensor and reloads all parameters and properties. This method should be called on communication errors.


Signals
*******


.. _signal_AlphasenseOpcN3_errorOccurred:

.. index::
   single: errorOccurred

errorOccurred()
+++++++++++++++

This signal is emitted whenever an error has occurred, regardless of whether the :ref:`error <property_AlphasenseOpcN3_error>` property has changed or not. In contrast to the change notification signal of the :ref:`error <property_AlphasenseOpcN3_error>` property this signal is also emitted several times if a certain error occurs several times in succession.


Enumerations
************


.. _enum_AlphasenseOpcN3_Error:

.. index::
   single: Error

Error
+++++

This enumeration describes all errors which can occur in AlphasenseOpcN3 objects. The most recently occurred error is stored in the :ref:`error <property_AlphasenseOpcN3_error>` property.

.. index::
   single: AlphasenseOpcN3.NoError
.. index::
   single: AlphasenseOpcN3.InvalidSerialPort
.. index::
   single: AlphasenseOpcN3.SerialPortOpenError
.. index::
   single: AlphasenseOpcN3.CommunicationError
.. index::
   single: AlphasenseOpcN3.ResponseTimeoutError
.. list-table::
  :widths: auto
  :header-rows: 1

  * - Name
    - Value
    - Description

      .. _enumitem_AlphasenseOpcN3_NoError:
  * - ``AlphasenseOpcN3.NoError``
    - ``0``
    - No error occurred or was detected.

      .. _enumitem_AlphasenseOpcN3_InvalidSerialPort:
  * - ``AlphasenseOpcN3.InvalidSerialPort``
    - ``1``
    - No serial port has been specified.

      .. _enumitem_AlphasenseOpcN3_SerialPortOpenError:
  * - ``AlphasenseOpcN3.SerialPortOpenError``
    - ``2``
    - Could not open or configure specified serial port.

      .. _enumitem_AlphasenseOpcN3_CommunicationError:
  * - ``AlphasenseOpcN3.CommunicationError``
    - ``3``
    - Error while communicating with the Alphasense OPC-N3 sensor.

      .. _enumitem_AlphasenseOpcN3_ResponseTimeoutError:
  * - ``AlphasenseOpcN3.ResponseTimeoutError``
    - ``4``
    - Did not receive response to request within 5000 ms.


.. _example_AlphasenseOpcN3:


Example
*******

.. code-block:: qml

    import InCore.Foundation 2.5
    import InCore.IO 2.5
    
    Application {
    
        AlphasenseOpcN3 {
            id: primarySensor
            serialPort: SerialPort { portName: "ttyACM0" }
            onSerialNumberChanged: console.log(serialNumber)
            onDeviceInformationChanged: console.log(deviceInformation)
            Polling on values { interval: 1000 }
            onValuesChanged: console.log(values)
            pollMassConcentrationsOnly: false
        }
    
        // mockup for multi-device configuration by serial number
    
        property list<SerialPort> availableDevices
        property list<AlphasenseOpcN3> devices
    
        Gather on availableDevices {
            source: SerialPortManager { }
            expressionFilter: item.vendorIdentifier === 0x04d8 && item.productIdentifier === 0xffee
        }
    
        Repeater on devices {
            model: config.objects
            AlphasenseOpcN3 {
                Select on serialPort {
                    source: availableDevices
                    select: item.serialNumber === modelData.serialNumber.data
                }
            }
        }
    
        property var config: Configuration {
            name: "Alphasense OPC-N3 devices"
            objectId: "opcN3Devices"
            id: config
    
            Repeater on objects {
                model: 3
    
                ConfigurationObject {
                    id: configObject
                    objectId: ("opcN3Device%1").arg(("0"+(index+1)).slice(-2))
                    property int orderIndex: index
    
                    property var enabled: ConfigurationItem {
                        id: enabled;
                        name: "Enabled"
                        data: false
                        dataType: ConfigurationItem.Boolean;
                        view: DataObjectView { widget: DataObjectView.Switch; orderIndex: 1 }
                    }
    
                    property var name: ConfigurationItem {
                        id: name;
                        name: "Name"
                        data: ("OPC-N3 %1").arg(index+1)
                        dataType: ConfigurationItem.String;
                        view: DataObjectView { widget: DataObjectView.TextInput; orderIndex: 2 }
                    }
    
                    property var serialNumber: ConfigurationItem {
                        id: serialNumber;
                        name: "Modbus device ID"
                        dataType: ConfigurationItem.UnsignedInteger;
                        data: 0
                        view: DataObjectView {
                            widget: DataObjectView.Combobox;
                            orderIndex: 3;
                            widgetData: {
                                var map = {};
                                for( var i = 0; i < availableDevices.length; ++i )
                                {
                                    map[availableDevices.serialNumber] = "OPC-N3 " + availableDevices.serialNumber;
                                }
                                return map;
                            }
                        }
                    }
                }
            }
        }
    }
    