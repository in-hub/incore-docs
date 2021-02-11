
.. _module_Modbus:


:index:`InCore Modbus`
======================

Description
-----------

The Modbus module contains objects which can be used to communicate with a modbus network. Modbus enables communication among many devices connected to the same network, for example, a system that measures temperature and humidity and communicates the results to a consumer. The :ref:`ModbusRtuMaster <object_ModbusRtuMaster>` have be used to communicate over a RS485 interface. ModbusTcpClient is used for communications over TCP/IP networks. For detailed information see `Modbus on Wikipedia <https://en.wikipedia.org/wiki/Modbus>`_.


Objects
-------

.. toctree::
	:maxdepth: 1

	ModbusBackplaneMaster
	ModbusClient
	ModbusDevice
	ModbusRegister
	ModbusRtuMaster
	ModbusRtuSlave
	ModbusServer
	ModbusSlave
	ModbusTcpClient
	ModbusTcpServer
