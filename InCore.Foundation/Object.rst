
.. _object_Object:


:index:`Object`
---------------

Description
***********

The Object object provides basic common functionality for all objects such as the :ref:`completed() <signal_Object_completed>` signal and the :ref:`objectId <property_Object_objectId>` and :ref:`parent <property_Object_parent>` properties.

:**› Inherited by**: :ref:`ApplicationView <object_ApplicationView>`, :ref:`ByteArray <object_ByteArray>`, :ref:`Comparator <object_Comparator>`, :ref:`Component <object_Component>`, :ref:`Configuration <object_Configuration>`, :ref:`ConfigurationArray <object_ConfigurationArray>`, :ref:`ConfigurationObject <object_ConfigurationObject>`, :ref:`Counter <object_Counter>`, :ref:`CsvWriter <object_CsvWriter>`, :ref:`DataObject <object_DataObject>`, :ref:`DataObjectGroup <object_DataObjectGroup>`, :ref:`DataObjectView <object_DataObjectView>`, :ref:`DataObjectWriter <object_DataObjectWriter>`, :ref:`DhcpServer <object_DhcpServer>`, :ref:`DockerContainer <object_DockerContainer>`, :ref:`DockerMount <object_DockerMount>`, :ref:`DockerNetwork <object_DockerNetwork>`, :ref:`DockerObject <object_DockerObject>`, :ref:`ErrorCollector <object_ErrorCollector>`, :ref:`EventJournal <object_EventJournal>`, :ref:`EventLog <object_EventLog>`, :ref:`EventLogItem <object_EventLogItem>`, :ref:`EventOutput <object_EventOutput>`, :ref:`File <object_File>`, :ref:`InMemoryStorage <object_InMemoryStorage>`, :ref:`IoDevice <object_IoDevice>`, :ref:`JsonRpcClient <object_JsonRpcClient>`, :ref:`JsonRpcServer <object_JsonRpcServer>`, :ref:`List <object_List>`, :ref:`LocalRepository <object_LocalRepository>`, :ref:`Mail <object_Mail>`, :ref:`MailAddress <object_MailAddress>`, :ref:`NetworkRoute <object_NetworkRoute>`, :ref:`NftChain <object_NftChain>`, :ref:`NftFirewall <object_NftFirewall>`, :ref:`NftRule <object_NftRule>`, :ref:`NftStatement <object_NftStatement>`, :ref:`NftTable <object_NftTable>`, :ref:`ObjectArray <object_ObjectArray>`, :ref:`Process <object_Process>`, :ref:`PropertyModifier <object_PropertyModifier>`, :ref:`Repository <object_Repository>`, :ref:`Serializer <object_Serializer>`, :ref:`Settings <object_Settings>`, :ref:`SmtpConfiguration <object_SmtpConfiguration>`, :ref:`Storage <object_Storage>`, :ref:`System <object_System>`, :ref:`SystemService <object_SystemService>`, :ref:`TcpServer <object_TcpServer>`, :ref:`Timer <object_Timer>`, :ref:`Translator <object_Translator>`, :ref:`UpdateManager <object_UpdateManager>`, :ref:`UpdateTarget <object_UpdateTarget>`

Overview
********

Properties
++++++++++

.. hlist::
  :columns: 1

  * :ref:`objectId <property_Object_objectId>`
  * :ref:`parent <property_Object_parent>`

Methods
+++++++

.. hlist::
  :columns: 1

  * :ref:`deserializeProperties() <method_Object_deserializeProperties>`
  * :ref:`fromJson() <method_Object_fromJson>`
  * :ref:`toJson() <method_Object_toJson>`

Signals
+++++++

.. hlist::
  :columns: 1

  * :ref:`completed() <signal_Object_completed>`



Properties
**********


.. _property_Object_objectId:

.. _signal_Object_objectIdChanged:

.. index::
   single: objectId

objectId
++++++++

This property holds an optional ID for the object in case the object does not have an QML ID assigned. Like the QML ID the object ID should be a simple string with alphanumeric characters only.

:**› Type**: String
:**› Signal**: objectIdChanged()
:**› Attributes**: Writable


.. _property_Object_parent:

.. _signal_Object_parentChanged:

.. index::
   single: parent

parent
++++++

This property holds a reference to the current parent of the object.

:**› Type**: :ref:`Object <object_Object>`
:**› Signal**: parentChanged()
:**› Attributes**: Writable

Methods
*******


.. _method_Object_deserializeProperties:

.. index::
   single: deserializeProperties

deserializeProperties(Map variantMap)
+++++++++++++++++++++++++++++++++++++

This method deserializes (loads) the corresponding properties of this object instance and children objects. It works similarly to :ref:`fromJson() <method_Object_fromJson>` but takes a map/dictionary instead of a JSON string.

This method was introduced in InCore 2.4.



.. _method_Object_fromJson:

.. index::
   single: fromJson

fromJson(String data)
+++++++++++++++++++++

This method parses the specified JSON string and deserializes (loads) the corresponding properties of this object instance and children objects.



.. _method_Object_toJson:

.. index::
   single: toJson

toJson(JSValue jsValue)
+++++++++++++++++++++++

This method returns a JSON representation of all properties of this instance and all children objects if no argument is passed. If the argument is a property or a JavaScript value (object, array etc.) it is converted to a human-readable JSON string. This allows dumping complex data structures easily while debugging. When requiring additional control over how and which properties are to be serialized, :ref:`Serializer <object_Serializer>` should be used instead.

:**› Returns**: String


Signals
*******


.. _signal_Object_completed:

.. index::
   single: completed

completed()
+++++++++++

This signal is emitted when the object and all its children objects have been loaded and initialized completely. A handler for this signal can be used to start certain operations such as opening a resource, initiating a connection or logging the successful initialization.

.. note:: Most operational objects provide properties for automatically starting their operation and should be used instead of calling the corresponding methods manually in a handler of this signal.



.. _example_Object:


Example
*******

.. code-block:: qml

    import InCore.Foundation 2.5
    
    Application {
    
        Object {
            objectId: "testObject"
            property string foo: "bar"
            onCompleted: {
                console.log("Hello world, I'm", objectId, "and my vendor is", parent.vendor)
                console.log("My JSON representation is", toJson())
            }
        }
    }
    