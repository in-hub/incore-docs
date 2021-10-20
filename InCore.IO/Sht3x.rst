
.. _object_Sht3x:


:index:`Sht3x`
--------------

Description
***********

The Sht3x object implements a driver for the I2C-based SHT3x humidity and temperature sensor. The parent of a :ref:`Sht3x <object_Sht3x>` object has to be a corresponding :ref:`I2cBus <object_I2cBus>` object.

All measurements are polled with high repeatability, leading to best accuracy. The measurement properties are updated approximately 20 *ms* after they got polled, i.e. a measurement has been initiated.

This object was introduced in InCore 2.0.

:**› Inherits**: :ref:`I2cDevice <object_I2cDevice>`

Overview
********

Properties
++++++++++

.. hlist::
  :columns: 1

  * :ref:`humidity <property_Sht3x_humidity>`
  * :ref:`temperature <property_Sht3x_temperature>`
  * :ref:`I2cDevice.address <property_I2cDevice_address>`
  * :ref:`Object.objectId <property_Object_objectId>`
  * :ref:`Object.parent <property_Object_parent>`

Methods
+++++++

.. hlist::
  :columns: 1

  * :ref:`pollHumidity() <method_Sht3x_pollHumidity>`
  * :ref:`pollTemperature() <method_Sht3x_pollTemperature>`
  * :ref:`I2cDevice.read() <method_I2cDevice_read>`
  * :ref:`I2cDevice.write() <method_I2cDevice_write>`
  * :ref:`Object.deserializeProperties() <method_Object_deserializeProperties>`
  * :ref:`Object.fromJson() <method_Object_fromJson>`
  * :ref:`Object.toJson() <method_Object_toJson>`

Signals
+++++++

.. hlist::
  :columns: 1

  * :ref:`Object.completed() <signal_Object_completed>`



Properties
**********


.. _property_Sht3x_humidity:

.. _signal_Sht3x_humidityChanged:

.. index::
   single: humidity

humidity
++++++++

This property holds the last polled humidity value. When polling this property, the :ref:`temperature <property_Sht3x_temperature>` is polled and updated automatically as well.

:**› Type**: Float
:**› Signal**: humidityChanged()
:**› Attributes**: Readonly, Requires :ref:`Polling <object_Polling>`


.. _property_Sht3x_temperature:

.. _signal_Sht3x_temperatureChanged:

.. index::
   single: temperature

temperature
+++++++++++

This property holds the last polled temperature value. When polling this property, the :ref:`humidity <property_Sht3x_humidity>` is polled and updated automatically as well.

:**› Type**: Float
:**› Signal**: temperatureChanged()
:**› Attributes**: Readonly, Requires :ref:`Polling <object_Polling>`

Methods
*******


.. _method_Sht3x_pollHumidity:

.. index::
   single: pollHumidity

pollHumidity()
++++++++++++++

This method polls the :ref:`humidity <property_Sht3x_humidity>` property. It is called automatically when using a :ref:`Polling <object_Polling>` property modifier on this property and usually does not have to be called manually.



.. _method_Sht3x_pollTemperature:

.. index::
   single: pollTemperature

pollTemperature()
+++++++++++++++++

This method polls the :ref:`temperature <property_Sht3x_temperature>` property. It is called automatically when using a :ref:`Polling <object_Polling>` property modifier on this property and usually does not have to be called manually.



.. _example_Sht3x:


Example
*******

.. code-block:: qml

    import InCore.Foundation 2.5
    import InCore.IO 2.5
    
    Application {
        FtdiI2cBus {
            Sht3x {
                id: sht
                address: 0x44
                Polling on temperature { interval: 100 }
                onTemperatureChanged: console.log(Math.floor(temperature*10) / 10, "°C -",
                                                  Math.floor(humidity*10) / 10, "% r.h.")
            }
        }
    }
    