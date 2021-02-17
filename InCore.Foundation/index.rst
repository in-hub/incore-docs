
.. _module_Foundation:


:index:`InCore Foundation`
==========================

Description
-----------

The Foundation module is the heart of the InCore framework and provides basic objects, data structures, patterns and mechanisms for building InCore applications. All essential objects can be grouped as follows:

* **Core**: :ref:`Application <object_Application>`, :ref:`Object <object_Object>`, :ref:`ObjectArray <object_ObjectArray>`, :ref:`List <object_List>`, :ref:`ByteArray <object_ByteArray>`, :ref:`FifoBuffer <object_FifoBuffer>`, :ref:`Comparator <object_Comparator>`, :ref:`Counter <object_Counter>`, :ref:`Repeater <object_Repeater>`, :ref:`Gather <object_Gather>`, :ref:`Polling <object_Polling>`, :ref:`DateTime <object_DateTime>`, :ref:`Timer <object_Timer>`
* **Configuration**: :ref:`Configuration <object_Configuration>`, :ref:`ConfigurationArray <object_ConfigurationArray>`, :ref:`ConfigurationObject <object_ConfigurationObject>`, :ref:`ConfigurationItem <object_ConfigurationItem>`, :ref:`ApplicationConfiguration <object_ApplicationConfiguration>`, :ref:`SystemConfiguration <object_SystemConfiguration>`
* **Data**: :ref:`DataObject <object_DataObject>`, :ref:`DataObjectGroup <object_DataObjectGroup>`, :ref:`DataObjectView <object_DataObjectView>`, :ref:`ReduceList <object_ReduceList>`, :ref:`Select <object_Select>`, :ref:`TransformList <object_TransformList>`
* **Docker**: :ref:`DockerContainer <object_DockerContainer>`, :ref:`DockerMount <object_DockerMount>`, :ref:`DockerNetwork <object_DockerNetwork>`, :ref:`DockerVolume <object_DockerVolume>`
* **Events**: :ref:`Event <object_Event>`, :ref:`EventLog <object_EventLog>`, :ref:`EventOutput <object_EventOutput>`, :ref:`EventCategory <object_EventCategory>`, :ref:`EventGroup <object_EventGroup>`, :ref:`EventJournal <object_EventJournal>`, :ref:`EventLogFile <object_EventLogFile>`
* **Firewall**: :ref:`NftFirewall <object_NftFirewall>`, :ref:`NftTable <object_NftTable>`, :ref:`NftChain <object_NftChain>`, :ref:`NftRule <object_NftRule>`, :ref:`NftAddressTranslation <object_NftAddressTranslation>`
* **Input/output**: :ref:`File <object_File>`, :ref:`CsvWriter <object_CsvWriter>`
* **JSON RPC**: :ref:`JsonRpcClient <object_JsonRpcClient>`, :ref:`JsonRpcServer <object_JsonRpcServer>`, :ref:`JsonRpcService <object_JsonRpcService>`
* **Measuring**: :ref:`Measurement <object_Measurement>`, :ref:`MeasurementGroup <object_MeasurementGroup>`, :ref:`MeasurementView <object_MeasurementView>`
* **Networking**: :ref:`TcpSocket <object_TcpSocket>`, :ref:`UdpSocket <object_UdpSocket>`, :ref:`WebSocket <object_WebSocket>`, :ref:`TcpServer <object_TcpServer>`, :ref:`NetworkConfiguration <object_NetworkConfiguration>`, :ref:`NetworkInterface <object_NetworkInterface>`, :ref:`WiredNetworkInterface <object_WiredNetworkInterface>`, :ref:`WirelessNetworkInterface <object_WirelessNetworkInterface>`, :ref:`MobileNetworkInterface <object_MobileNetworkInterface>`, :ref:`Mail <object_Mail>`, :ref:`DhcpServer <object_DhcpServer>`
* **Services**: :ref:`SystemService <object_SystemService>`, :ref:`OpenVpnClientService <object_OpenVpnClientService>`, :ref:`SshService <object_SshService>`, :ref:`WebServerService <object_WebServerService>`, :ref:`DockerService <object_DockerService>`
* **Storage**: :ref:`LocalStorage <object_LocalStorage>`, :ref:`UsbStorage <object_UsbStorage>`, :ref:`InMemoryStorage <object_InMemoryStorage>`
* **System**: :ref:`System <object_System>`, :ref:`Process <object_Process>`, :ref:`UpdateManager <object_UpdateManager>`



Objects
-------

.. toctree::
	:maxdepth: 1

	Application
	ApplicationConfiguration
	ApplicationView
	ByteArray
	Comparator
	Component
	Configuration
	ConfigurationArray
	ConfigurationItem
	ConfigurationObject
	Counter
	CsvWriter
	DataObject
	DataObjectGroup
	DataObjectView
	DataObjectWriter
	DateTime
	DhcpServer
	DockerContainer
	DockerMount
	DockerNetwork
	DockerObject
	DockerService
	DockerVolume
	ErrorCollector
	Event
	EventCategory
	EventGroup
	EventJournal
	EventLog
	EventLogFile
	EventLogItem
	EventOutput
	FifoBuffer
	File
	Gather
	GeneralApplicationSettings
	GeneralSystemSettings
	InMemoryStorage
	IoDevice
	IpSocket
	JsonRpcClient
	JsonRpcServer
	JsonRpcService
	List
	LocalRepository
	LocalStorage
	Mail
	MailAddress
	Measurement
	MeasurementGroup
	MeasurementView
	MobileNetworkInterface
	NetworkConfiguration
	NetworkInterface
	NetworkRoute
	NftAddressTranslation
	NftChain
	NftFirewall
	NftFlow
	NftRule
	NftStatement
	NftTable
	Object
	ObjectArray
	OpenVpnClientService
	Polling
	Process
	PropertyModifier
	ReduceList
	Repeater
	Repository
	Resource
	Select
	Serializer
	Settings
	SmtpConfiguration
	SshService
	Storage
	System
	SystemConfiguration
	SystemService
	TcpServer
	TcpSocket
	Timer
	TransformList
	Translator
	UdpDatagram
	UdpSocket
	UpdateManager
	UpdateTarget
	UsbDriveRepository
	UsbStorage
	WebServerFilesStorage
	WebServerService
	WebSocket
	WiredNetworkInterface
	WirelessNetworkInterface
